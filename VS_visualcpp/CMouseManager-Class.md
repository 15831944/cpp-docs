---
title: "CMouseManager Class"
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
ms.topic: reference
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: 23
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
# CMouseManager Class
Allows a user to associate different commands with a particular [CView](../VS_visualcpp/CView-Class.md) object when the user double-clicks inside that view.  
  
## Syntax  
  
```  
class CMouseManager : public CObject  
```  
  
## Members  
  
### Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMouseManager::AddView](#cmousemanager__addview)|Adds a `CView` object to the **Customization** dialog box. The **Customization** dialog box enables the user to associate a double-click with a command for each of the listed views.|  
|[CMouseManager::GetViewDblClickCommand](#cmousemanager__getviewdblclickcommand)|Returns the command that is executed when the user double-clicks inside the provided view.|  
|[CMouseManager::GetViewIconId](#cmousemanager__getviewiconid)|Returns the icon associated with the provided view ID.|  
|[CMouseManager::GetViewIdByName](#cmousemanager__getviewidbyname)|Returns the view ID associated with the provided view name.|  
|[CMouseManager::GetViewNames](#cmousemanager__getviewnames)|Retrieves a list of all added view names.|  
|[CMouseManager::LoadState](#cmousemanager__loadstate)|Loads the `CMouseManager` state from the Windows registry.|  
|[CMouseManager::SaveState](#cmousemanager__savestate)|Writes the `CMouseManager` state to the Windows registry.|  
|[CMouseManager::SetCommandForDblClk](#cmousemanager__setcommandfordblclk)|Associates the provided command and the provided view.|  
  
## Remarks  
 The `CMouseManager` class maintains a collection of `CView` objects. Each view is identified by a name and by an ID. These views are shown in the **Customization** dialog box. The user can change the command that is associated with any view through the **Customization** dialog box. The associated command is executed when the user double-clicks in that view. To support this from a coding perspective, you must process the `WM_LBUTTONDBLCLK` message and call the [CWinAppEx::OnViewDoubleClick](../VS_visualcpp/CWinAppEx-Class.md#cwinappex__onviewdoubleclick) function in the code for that `CView` object..  
  
 You should not create a `CMouseManager` object manually. It will be created by the framework of your application. It will also be destroyed automatically when the user exits the application. To get a pointer to the mouse manager for your application, call [CWinAppEx::GetMouseManager](../VS_visualcpp/CWinAppEx-Class.md#cwinappex__getmousemanager).  
  
## Inheritance Hierarchy  
 [CObject](../VS_visualcpp/CObject-Class.md)  
  
 [CMouseManager](../VS_visualcpp/CMouseManager-Class.md)  
  
## Requirements  
 **Header:** afxmousemanager.h  
  
##  <a name="cmousemanager__addview"></a>  CMouseManager::AddView  
 Registers a [CView](../VS_visualcpp/CView-Class.md) object with the [CMouseManager Class](../VS_visualcpp/CMouseManager-Class.md) to support custom mouse behavior.  
  
```  
BOOL AddView(  
    int iViewId,  
    UINT uiViewNameResId,  
    UINT uiIconId = 0);  
  
BOOL AddView(  
    int iId,  
    LPCTSTR lpszViewName,  
    UINT uiIconId = 0);  
```  
  
### Parameters  
 [in] `iViewId`  
 A view ID.  
  
 [in] `uiViewNameResId`  
 A resource string ID that references the view name.  
  
 [in] `uiIconId`  
 A view icon ID.  
  
 [in] `iId`  
 A view ID.  
  
 [in] `lpszViewName`  
 A view name.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 In order to support custom mouse behavior, a view must be registered with the `CMouseManager` object. Any object derived from the `CView` class can be registered with the mouse manager. The string and icon associated with a view are displayed in the **Mouse** tab of the **Customize** dialog box.  
  
 It is the responsibility of the programmer to create and maintain view IDs such as `iViewId` and `iId`.  
  
 For more information about how to provide custom mouse behavior, see [Keyboard and Mouse Customization](../VS_visualcpp/Keyboard-and-Mouse-Customization.md).  
  
### Example  
 The following example demonstrates how to retrieve a pointer to a `CMouseManager` object by using the `CWinAppEx::GetMouseManager` method and the `AddView` method in the `CMouseManager` class. This code snippet is part of the [State Collection sample](../VS_visualcpp/Visual-C---Samples.md).  
  
 [!CODE [NVC_MFC_StateCollection#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StateCollection#4)]  
  
##  <a name="cmousemanager__getviewdblclickcommand"></a>  CMouseManager::GetViewDblClickCommand  
 Returns the command that is executed when the user double-clicks inside the provided view.  
  
```  
UINT GetViewDblClickCommand( int iId ) const;  
```  
  
### Parameters  
 [in] `iId`  
 The view ID.  
  
### Return Value  
 The command identifier if the view is associated with a command; otherwise 0.  
  
##  <a name="cmousemanager__getviewiconid"></a>  CMouseManager::GetViewIconId  
 Retrieves the icon associated with a view ID.  
  
```  
UINT GetViewIconId( int iViewId ) const;  
```  
  
### Parameters  
 [in] `iViewId`  
 The view ID.  
  
### Return Value  
 An icon resource identifier if successful; otherwise 0.  
  
### Remarks  
 This method will fail if the view is not first registered by using [CMouseManager::AddView](#cmousemanager__addview).  
  
##  <a name="cmousemanager__getviewidbyname"></a>  CMouseManager::GetViewIdByName  
 Retrieves the view ID associated with a view name.  
  
```  
int GetViewIdByName( LPCTSTR lpszName ) const;  
```  
  
### Parameters  
 [in] `lpszName`  
 The view name.  
  
### Return Value  
 A view ID if successful; otherwise 0.  
  
### Remarks  
 This method searches through views registered by using [CMouseManager::AddView](#cmousemanager__addview).  
  
##  <a name="cmousemanager__getviewnames"></a>  CMouseManager::GetViewNames  
 Retrieves a list of all the registered view names.  
  
```  
void GetViewNames( CStringList& listOfNames ) const;  
```  
  
### Parameters  
 [out] `listOfNames`  
 A reference to `CStringList` object.  
  
### Remarks  
 This method fills the parameter `listOfNames` with the names of all the views registered by using [CMouseManager::AddView](#cmousemanager__addview).  
  
##  <a name="cmousemanager__loadstate"></a>  CMouseManager::LoadState  
 Loads the state of the [CMouseManager Class](../VS_visualcpp/CMouseManager-Class.md) from the registry.  
  
```  
BOOL LoadState(  
    LPCTSTR lpszProfileName = NULL);  
```  
  
### Parameters  
 [in] `lpszProfileName`  
 A path of a registry key.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 The state information loaded from the registry includes the registered views, view identifiers, and the associated commands. If the parameter `lpszProfileName` is `NULL`, this function loads the `CMouseManager` data from the default registry location controlled by the [CWinAppEx Class](../VS_visualcpp/CWinAppEx-Class.md).  
  
 In most cases, you do not have to call this function directly. It is called as a part of the workspace initialization process. For more information about the workspace initialization process, see [CWinAppEx::LoadState](../VS_visualcpp/CWinAppEx-Class.md#cwinappex__loadstate).  
  
##  <a name="cmousemanager__savestate"></a>  CMouseManager::SaveState  
 Writes the state of the [CMouseManager Class](../VS_visualcpp/CMouseManager-Class.md) to the registry.  
  
```  
BOOL SaveState(  
    LPCTSTR lpszProfileName = NULL);  
```  
  
### Parameters  
 [in] `lpszProfileName`  
 A path of a registry key.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 The state information written to the registry includes all registered views, view identifiers, and the associated commands. If the parameter `lpszProfileName` is `NULL`, this function writes the `CMouseManager` data to the default registry location controlled by the [CWinAppEx Class](../VS_visualcpp/CWinAppEx-Class.md).  
  
 In most cases, you do not have to call this function directly. It is called as a part of the workspace serialization process. For more information about the workspace serialization process, see [CWinAppEx::SaveState](../VS_visualcpp/CWinAppEx-Class.md#cwinappex__savestate).  
  
##  <a name="cmousemanager__setcommandfordblclk"></a>  CMouseManager::SetCommandForDblClk  
 Associates a custom command with a view that is first registered with the mouse manager.  
  
```  
void SetCommandForDblClk(  
    int iViewId,  
    UINT uiCmd );  
```  
  
### Parameters  
 [in] `iViewId`  
 The view identifier.  
  
 [in] `uiCmd`  
 The command identifier.  
  
### Remarks  
 In order to associate a custom command with a view, you must first register the view by using [CMouseManager::AddView](#cmousemanager__addview). The `AddView` method requires a view identifier as an input parameter. Once you register a view, you can call `CMouseManager::SetCommandForDblClk` with the same view identifier input parameter that you supplied to `AddView`. Thereafter, when the user double-clicks the mouse in the registered view, the application will execute the command indicated by `uiCmd.` To support the custom mouse behavior, you will also need to customize the view registered with the mouse manager. For more information about custom mouse behavior, see [Keyboard and Mouse Customization](../VS_visualcpp/Keyboard-and-Mouse-Customization.md).  
  
 If `uiCmd` is set to 0, the specified view is no longer associated with a command.  
  
## See Also  
 [Hierarchy Chart](../VS_visualcpp/Hierarchy-Chart.md)   
 [Classes](../VS_visualcpp/MFC-Classes.md)   
 [CWinAppEx Class](../VS_visualcpp/CWinAppEx-Class.md)   
 [Keyboard and Mouse Customization](../VS_visualcpp/Keyboard-and-Mouse-Customization.md)