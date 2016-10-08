---
title: "Changing a Symbol&#39;s Numeric Value"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
caps.latest.revision: 7
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
# Changing a Symbol&#39;s Numeric Value
For symbols associated with a single resource, you can use the [Properties Window](../Topic/Properties%20Window.md) to change the symbol value. You can use the [Resource Symbols dialog box](../VS_visualcpp/Resource-Symbols-Dialog-Box.md) to change the value of symbols not currently assigned to a resource. For more information, see [Changing Unassigned Symbols](../VS_visualcpp/Changing-Unassigned-Symbols.md).  
  
### To change a symbol value assigned to a single resource or object  
  
1.  In [Resource View](../VS_visualcpp/Resource-View-Window.md), select the resource.  
  
    > [!NOTE]
    >  If your project doesn't already contain an .rc file, please see [Creating a New Resource Script File](../VS_visualcpp/How-to--Create-a-Resource-Script-File.md).  
  
2.  In the **Properties** window, type the symbol name followed by an equal sign and an integer in the **ID** box, for example:  
  
    ```  
    IDC_EDITNAME=5100  
    ```  
  
 The new value is stored in the symbol header file the next time you save the project. Only the symbol name remains visible in the ID box; the equal sign and value are not displayed after they are validated.  
  
 For information on adding resources to managed projects, please see [Resources in Applications](../Topic/Resources%20in%20Desktop%20Apps.md) in the *.NET Framework Developer's Guide.* For information on manually adding resource files to managed projects, accessing resources, displaying static resources, and assigning resources strings to properties, and [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Requirements  
  
 Win32  
  
## See Also  
 [Symbol Value Restrictions](../VS_visualcpp/Symbol-Value-Restrictions.md)   
 [Predefined Symbol IDs](../VS_visualcpp/Predefined-Symbol-IDs.md)