---
title: "SDI Server Applications"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - FSharp
  - VB
  - CSharp
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-debug
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 09713718-1376-4753-b119-26f36639693e
caps.latest.revision: 15
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
# SDI Server Applications
If you are debugging an SDI server application, you must specify `/Embedding` or `/Automation` in the **Command line arguments** property in the *Project* Property Pages dialog box for C/C++, C#, or Visual Basic projects.  
  
 With these command line arguments, the debugger can launch the server application as though it were launched from a container. Starting the container from Program Manager or File Manager will then cause the container to use the instance of the server started in the debugger.  
  
## Finding the Command Line Arguments Property  
 To access the *Project* Property Pages dialog box, right-click your project in Solution Explorer, and then choose Properties from the shortcut menu. To find the Command line arguments property, expand the Configuration Properties category and click the Debugging page.  
  
## See Also  
 [COM and ActiveX Debugging](../VS_debugger/COM-and-ActiveX-Debugging.md)   
 [How to: Debug COM Servers](../VS_debugger/How-to--Debug-COM-Servers.md)