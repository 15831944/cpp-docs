---
title: "ccosh, ccoshf, ccoshl"
ms.custom: na
ms.date: 10/06/2016
ms.devlang: 
  - C
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - cpp
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
apiname: 
  - ccosh
  - ccoshf
  - ccoshl
apilocation: 
  - msvcrt.dll
  - msvcr80.dll
  - msvcr90.dll
  - msvcr100.dll
  - msvcr100_clr0400.dll
  - msvcr110.dll
  - msvcr110_clr0400.dll
  - msvcr120.dll
  - msvcr120_clr0400.dll
  - ucrtbase.dll
  - api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
ms.assetid: 79667449-4edf-4948-bf6b-720adf2b3f3b
caps.latest.revision: 8
manager: ghogen
translation.priority.mt: 
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
# ccosh, ccoshf, ccoshl
Retrieves the hyperbolic cosine of a complex number.  
  
## Syntax  
  
```  
_Dcomplex ccosh(   
   _Dcomplex z   
);  
_Fcomplex ccosh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex ccosh(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex ccoshf(   
   _Fcomplex z   
);  
_Lcomplex ccoshl(   
   _Lcomplex z   
);  
```  
  
#### Parameters  
 `z`  
 A complex number that represents the angle, in radians.  
  
## Return Value  
 The hyperbolic cosine of `z`, in radians.  
  
## Remarks  
 Because C++ allows overloading, you can call overloads of `ccosh` that take and return `_Fcomplex` and `_Lcomplex` values. In a C program, `ccosh` always takes and returns a `_Dcomplex` value.  
  
## Requirements  
  
|Routine|C header|C++ header|  
|-------------|--------------|------------------|  
|`ccosh`,               `ccoshf`, `ccoshl`|<complex.h>|<ccomplex\>|  
  
 For more compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md) in the Introduction.  
  
## See Also  
 [Alphabetical Function Reference](../VS_visualcpp/CRT-Alphabetical-Function-Reference.md)   
 [catanh, catanhf, catanhl](../VS_visualcpp/catanh--catanhf--catanhl.md)   
 [ctanh, ctanhf, ctanhl](../VS_visualcpp/ctanh--ctanhf--ctanhl.md)   
 [catan, catanf, catanl](../VS_visualcpp/catan--catanf--catanl.md)   
 [csinh, csinhf, csinhl](../VS_visualcpp/csinh--csinhf--csinhl.md)   
 [casinh, casinhf, casinhl](../VS_visualcpp/casinh--casinhf--casinhl.md)   
 [cacosh, cacoshf, cacoshl](../VS_visualcpp/cacosh--cacoshf--cacoshl.md)   
 [cacos, cacosf, cacosl](../VS_visualcpp/cacos--cacosf--cacosl.md)   
 [ctan, ctanf, ctanl](../VS_visualcpp/ctan--ctanf--ctanl.md)   
 [csin, csinf, csinl](../VS_visualcpp/csin--csinf--csinl.md)   
 [casin, casinf, casinl](../VS_visualcpp/casin--casinf--casinl.md)   
 [ccos, ccosf, ccosl](../VS_visualcpp/ccos--ccosf--ccosl.md)   
 [csqrt, csqrtf, csqrtl](../VS_visualcpp/csqrt--csqrtf--csqrtl.md)