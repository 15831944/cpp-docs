---
title: "User Button Handlers"
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
  - "ON_BN_HILITE"
  - "ON_BN_DOUBLECLICKED"
  - "ON_BN_CLICKED"
  - "ON_BN_PAINT"
  - "ON_BN_DISABLE"
  - "ON_BN_UNHILITE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_BN_PAINT"
  - "user buttons"
  - "ON_BN_DOUBLECLICKED"
  - "ON_BN_DISABLE"
  - "ON_BN_UNHILITE"
  - "ON_BN_HILITE"
  - "ON_BN_CLICKED"
ms.assetid: 410ea968-478f-4806-b7b8-5d7c8dc2bf42
caps.latest.revision: 8
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
# User Button Handlers
The following map entries correspond to the function prototypes.  
  
|Map entry|Function prototype|  
|---------------|------------------------|  
|ON_BN_CLICKED( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_BN_DISABLE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_BN_DOUBLECLICKED( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_BN_HILITE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_BN_PAINT( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_BN_UNHILITE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
  
## See Also  
 [Message Maps](../mfcref/message-maps--mfc-.md)