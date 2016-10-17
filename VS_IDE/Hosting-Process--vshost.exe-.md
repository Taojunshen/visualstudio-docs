---
title: "Hosting Process (vshost.exe)"
ms.custom: na
ms.date: 10/03/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-general
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c6b9e2be-f18d-4d75-ac52-56d55784734b
caps.latest.revision: 10
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# Hosting Process (vshost.exe)
The hosting process is a feature in Visual Studio that improves debugging performance, enables partial trust debugging, and enables design time expression evaluation. The hosting process files contain vshost in the file name and are placed in the output folder of your project. For more information, see [Debugging and the Hosting Process](../VS_debugger/Debugging-and-the-Hosting-Process.md).  
  
> [!NOTE]
>  Hosting process files (.vshost.exe) are for use by Visual Studio and should not be run directly or deployed with your application.  
  
## Improved Debugging Performance  
 The hosting process creates an application domain and associates the debugger with the application. Performing these tasks can introduce a noticeable delay between the time debugging is started and the time the application begins running. The hosting process helps increase performance by creating the application domain and associating the debugger in the background, and saving the application domain and debugger state between runs of the application. For more information on application domains, see [Application Domains](../Topic/Application%20Domains.md).  
  
## Partial Trust Debugging  
 An application can be specified as a partial trust application in the [Security page](../VS_IDE/Security-Page--Project-Designer.md) of the **Project Designer**. Debugging a partial trust application requires special initialization of the application domain. This initialization is handled by the hosting process.  
  
## Design-Time Expression Evaluation  
 Design-time expression evaluation enables you to test code from the **Immediate** window without having to run the application. The hosting process executes this code during design time expression evaluation. For more information, see [Immediate Window](../VS_IDE/Immediate-Window.md).  
  
## See Also  
 [Debugging and the Hosting Process](../VS_debugger/Debugging-and-the-Hosting-Process.md)   
 [How to: Disable the Hosting Process](../VS_IDE/How-to--Disable-the-Hosting-Process.md)   
 [Immediate Window](../VS_IDE/Immediate-Window.md)   
 [Application Domains](../Topic/Application%20Domains.md)