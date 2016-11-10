---
title: "InterfaceTraits::CanCastTo Method"
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
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
caps.latest.revision: 5
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
# InterfaceTraits::CanCastTo Method
Supports the WRL infrastructure and is not intended to be used directly from your code.  
  
## Syntax  
  
```  
  
template<typename T>  
static __forceinline bool CanCastTo(  
   _In_ T* ptr,  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
  
```  
  
#### Parameters  
 `ptr`  
 The name of a pointer to a type.  
  
 `riid`  
 The interface ID of `Base`.  
  
 `ppv`  
 If this operation is successful, `ppv` points to the interface specified by `Base`. Otherwise, `ppv` is set to `nullptr`.  
  
## Return Value  
 `true` if this operation is successful and `ptr` is cast to a pointer to `Base`; otherwise, `false` .  
  
## Remarks  
 Indicates whether the specified pointer can be cast to a pointer to `Base`.  
  
 For more information about `Base`, see the Public Typedefs section in [InterfaceTraits Structure](../VS_visualcpp/InterfaceTraits-Structure.md).  
  
## Requirements  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## See Also  
 [InterfaceTraits Structure](../VS_visualcpp/InterfaceTraits-Structure.md)   
 [Microsoft::WRL::Details Namespace](../VS_visualcpp/Microsoft--WRL--Details-Namespace.md)