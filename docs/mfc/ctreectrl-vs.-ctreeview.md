---
title: "CTreeCtrl vs. CTreeView"
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
  - "CTreeCtrl"
  - "CTreeView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tree view controls"
  - "CTreeCtrl class, vs. CTreeView class"
  - "CTreeView class, vs. CTreeCtrl class"
  - "tree controls, and tree view"
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
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
# CTreeCtrl vs. CTreeView
MFC provides two classes that encapsulate tree controls: [CTreeCtrl](../mfcref/ctreectrl-class.md) and [CTreeView](../mfcref/ctreeview-class.md). Each class is useful in different situations.  
  
 Use `CTreeCtrl` when you need a plain child window control; for instance, in a dialog box. You'd especially want to use `CTreeCtrl` if there will be other child controls in the window, as in a typical dialog box.  
  
 Use `CTreeView` when you want the tree control to act like a view window in document/view architecture as well as a tree control. A `CTreeView` will occupy the entire client area of a frame window or splitter window. It will be automatically resized when its parent window is resized, and it can process command messages from menus, accelerator keys, and toolbars. Since a tree control contains the data necessary to display the tree, the corresponding document object does not have to be complicated — you could even use [CDocument](../mfcref/cdocument-class.md) as the document type in your document template.  
  
## See Also  
 [Using CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Controls](../mfc/controls--mfc-.md)