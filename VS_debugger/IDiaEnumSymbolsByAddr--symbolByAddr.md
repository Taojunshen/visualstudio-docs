---
title: "IDiaEnumSymbolsByAddr::symbolByAddr"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-debug
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0b6f5a68-8402-4f29-8219-20576fda8166
caps.latest.revision: 8
manager: ghogen
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
# IDiaEnumSymbolsByAddr::symbolByAddr
Positions the enumerator by performing a lookup by image section number and offset.  
  
## Syntax  
  
```cpp#  
HRESULT symbolByAddr (   
   DWORD**      isect,  
   DWORD**      offsect,  
   IDiaSymbol** ppsymbol  
);  
```  
  
#### Parameters  
 isect  
 [in] Image section number.  
  
 offsect  
 [in] Offset in section.  
  
 ppsymbol  
 [out] Returns an [IDiaSymbol](../VS_debugger/IDiaSymbol.md) object representing the symbol found.  
  
## Return Value  
 If successful, returns `S_OK`. Returns `S_FALSE` if the symbol could not be found. Otherwise, returns an error code.  
  
## See Also  
 [IDiaEnumSymbolsByAddr](../VS_debugger/IDiaEnumSymbolsByAddr.md)   
 [IDiaSymbol](../VS_debugger/IDiaSymbol.md)