---
title: "CRowset::IsSameRow"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CRowset::IsSameRow"
  - "CRowset.IsSameRow"
  - "IsSameRow"
  - "ATL::CRowset::IsSameRow"
  - "ATL.CRowset.IsSameRow"
  - "CRowset<TAccessor>::IsSameRow"
  - "ATL.CRowset<TAccessor>.IsSameRow"
  - "CRowset<TAccessor>.IsSameRow"
  - "ATL::CRowset<TAccessor>::IsSameRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsSameRow method"
ms.assetid: 53cba847-52f5-4dd9-973f-bbe7454c425c
caps.latest.revision: 10
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
# CRowset::IsSameRow
Compares the specified row with the current row.  
  
## Syntax  
  
```  
  
      HRESULT IsSameRow(   
   HROW hRow    
) const throw( );  
```  
  
#### Parameters  
 `hRow`  
 [in] A handle to the row to compare to the current row.  
  
## Return Value  
 A standard `HRESULT`. `S_OK` indicates the rows are the same. For other values, see [IRowsetIndentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) in the *OLE DB Programmer's Reference* in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Requirements  
 **Header:** atldbcli.h  
  
## See Also  
 [CRowset Class](../data/crowset-class.md)