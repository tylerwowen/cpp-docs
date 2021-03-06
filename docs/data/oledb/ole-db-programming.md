---
title: "OLE DB Programming | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB [C++]"
  - "data access [C++], OLE DB programming"
  - "OLE DB [C++], about OLE DB"
ms.assetid: 52a80d66-17a9-43a1-9b90-392ae43cea2b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# OLE DB Programming
Microsoft OLE DB is a legacy technology; for new applications it is the required data access API for linked SQL Servers. All other new applications should use ODBC. The current OLE DB provider for SQL Server is SQLNCLI11.DLL. The provider is still shipping in SQL Server 2016. This documentation is intended for developers who are maintaining existing applications that already use OLE DB.
  
 The OLE DB templates are C++ templates that make the high-performance OLE DB database technology easier to use by providing classes that implement many commonly used OLE DB interfaces. This template library is divided into consumer templates and provider templates.  
  
 Visual C++ also has wizard support for creating OLE DB starter applications.  
  
 In addition, you can use attributes to implement the OLE DB consumer templates.  
  
|To learn more about|See|  
|-------------------------|---------|  
|Using the OLE DB consumer templates (conceptual topics)|[OLE DB Consumer Templates](../../data/oledb/ole-db-consumer-templates-cpp.md)|  
|Using the OLE DB provider templates (conceptual topics)|[OLE DB Provider Templates](../../data/oledb/ole-db-provider-templates-cpp.md)|  
|OLE DB templates classes and macros|[OLE DB Templates Reference](../../data/oledb/ole-db-templates.md) (Visual C++)|  
|OLE DB consumer attributes|[OLE DB Consumer Attributes](../../windows/ole-db-consumer-attributes.md)|  
|OLE DB interfaces|[OLE DB programmer's reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx) (in the [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)])|  
|OLE DB templates samples|[OLE DB Templates Samples](http://msdn.microsoft.com/en-us/08958863-0b5f-41ad-ae99-fca7440c553c)| 
|Data access programming overview (Visual C++)|[Data Access Programming](../../data/data-access-programming-mfc-atl.md)|  
|ODBC conceptual topics|[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)|  

  
## See Also  
 [Data Access](../data-access-in-cpp.md)