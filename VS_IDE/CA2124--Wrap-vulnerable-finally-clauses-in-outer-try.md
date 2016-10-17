---
title: "CA2124: Wrap vulnerable finally clauses in outer try"
ms.custom: na
ms.date: 10/04/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-devops-test
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
caps.latest.revision: 20
manager: douge
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# CA2124: Wrap vulnerable finally clauses in outer try
|||  
|-|-|  
|TypeName|WrapVulnerableFinallyClausesInOuterTry|  
|CheckId|CA2124|  
|Category|Microsoft.Security|  
|Breaking Change|Non Breaking|  
  
## Cause  
 In versions 1.0 and 1.1 of the .NET Framework, a public or protected method contains a `try`/`catch`/`finally` block. The `finally` block appears to reset security state and is not enclosed in a `finally` block.  
  
## Rule Description  
 This rule locates `try`/`finally` blocks in code that targets versions 1.0 and 1.1 of the .NET Framework that might be vulnerable to malicious exception filters present in the call stack. If sensitive operations such as impersonation occur in the try block, and an exception is thrown, the filter can execute before the `finally` block. For the impersonation example, this means that the filter would execute as the impersonated user. Filters are currently implementable only in Visual Basic.  
  
> [!WARNING]
>  **Note** In versions 2.0 and later of the .NET Framework, the runtime automatically protects a `try`/`catch`/ `finally` block from malicious exception filters, if the reset occurs directly within the method that contains the exception block.  
  
## How to Fix Violations  
 Place the unwrapped `try`/`finally` in an outer try block. See the second example that follows. This forces the `finally` to execute before filter code.  
  
## When to Suppress Warnings  
 Do not suppress a warning from this rule.  
  
## Pseudo-code Example  
  
### Description  
 The following pseudo-code illustrates the pattern detected by this rule.  
  
### Code  
  
```  
try {  
   // Do some work.  
   Impersonator imp = new Impersonator("John Doe");  
   imp.AddToCreditCardBalance(100);  
}  
finally {  
   // Reset security state.  
   imp.Revert();  
}  
```  
  
## Example  
 The following pseudo-code shows the pattern that you can use to protect your code and satisfy this rule.  
  
```  
try {  
     try {  
        // Do some work.  
     }  
     finally {  
        // Reset security state.  
     }  
}  
catch()  
{  
    throw;  
}  
```