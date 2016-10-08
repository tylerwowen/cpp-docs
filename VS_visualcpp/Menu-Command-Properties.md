---
title: "Menu Command Properties"
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
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
caps.latest.revision: 11
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
# Menu Command Properties
The information below is organized according to the Menu properties that appear in the [Properties Window](../Topic/Properties%20Window.md) when you select a menu command. These are listed alphabetically although the Properties window also enables you to view these properties by category.  
  
|Property|Description|  
|--------------|-----------------|  
|**Break**|Can be one of these values:<br /><br /> -   **None** (Default): No break.<br />-   **Column**: For static menus, this value places the menu command on a new line. For pop-up menus, this value places the menu command in a new column with no dividing line between the columns. Setting this property affects the appearance of the menu only at run time, not in the menu editor.<br />-   **Bar**: Same as Column except, for pop-up menus, this value separates the new column from the old column with a vertical line. Setting this property affects the appearance of the menu only at run time, not in the Menu editor.|  
|**Caption**|The text that labels the menu command (the menu name). To make one of the letters in the caption of a menu command the mnemonic key, precede it with an ampersand (&).|  
|**Checked**|If True, the menu command is initially checked. Type: Bool. Default: False.|  
|**Enabled**|If **False**, the menu item is disabled.|  
|**Grayed**|If True, the menu command is initially grayed and inactive. Type: Bool. Default: False.|  
|**Help**|Aligns menu item to the right. For example, the **Help** menu command is always on the right in all Windows applications. If you set this property on a menu item, that item will appear at the very far right and at the very end of the menu. Applies to top-level items. Default: **False**.|  
|**ID**|A symbol defined in the header file. Type: Symbol, Integer, or Quoted String. You may use any symbol that is commonly available in any of the editors, even though the [Properties Window](../Topic/Properties%20Window.md) does not provide a drop-down list for you to select from.|  
|**Popup**|If True, the menu command is a pop-up menu. Type: Bool. Default: True for top-level menus on a menu bar; otherwise False.|  
|**Prompt**|Contains text to appear in the status bar when this menu command is highlighted. The text is placed in the string table with the same identifier as the menu command. This property is available for any type of project, but the run-time functionality is MFC specific.|  
|**Right to Left Justify**|Right-justifies the menu command on the menu bar at run time. Type: Bool. Default: False.|  
|**Right to Left Order**|Allows menu commands to display right to left when the interface is localized to any language that reads right-to-left, such as Hebrew or Arabic.|  
|**Separator**|If True, the menu command is a separator. Type: Bool. Default: False.|  
  
 For information on adding resources to managed projects, please see [Resources in Applications](../Topic/Resources%20in%20Desktop%20Apps.md) in the *.NET Framework Developer's Guide.* For information on manually adding resource files to managed projects, accessing resources, displaying static resources, and assigning resources strings to properties, see [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Requirements  
 Win32  
  
## See Also  
 [Menu Editor](../VS_visualcpp/Menu-Editor.md)