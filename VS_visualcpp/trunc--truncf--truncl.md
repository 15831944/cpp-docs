---
title: "trunc, truncf, truncl"
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
  - trunc
  - truncf
  - truncl
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
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
caps.latest.revision: 13
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
# trunc, truncf, truncl
Determines the nearest integer that is less than or equal to the specified floating-point value.  
  
## Syntax  
  
```  
double trunc(  
   double x  
);  
  
float trunc(  
   float x  
); //C++ only  
  
long double trunc(  
   long double x  
); //C++ only  
  
float trunc(  
   float x  
); //C++ only  
  
long double truncl(  
   long double x  
);  
  
```  
  
#### Parameters  
 [in] `x`  
 The value to truncate.  
  
## Return Value  
 If successful, returns an integer value of `x`, rounded towards zero.  
  
 Otherwise, may return one of the following:  
  
|Issue|Return|  
|-----------|------------|  
|`x` = ±INFINITY|x|  
|`x` =  ±0|x|  
|`x` = NaN|NaN|  
  
 Errors are reported as specified in [_matherr](../VS_visualcpp/_matherr.md).  
  
## Remarks  
 Because C++ allows overloading, you can call overloads of `trunc` that take and return float and long double types. In a C program, `trunc` always takes and returns a double.  
  
 Because the largest floating-point values are exact integers, this function will not overflow on its own. However, you may cause the function to overflow by returning a value into an integer type.  
  
 You can also round down by implicitly converting from floating-point to integral; however, doing so is limited to the values that can be stored in the target type.  
  
## Requirements  
  
|Function|C header|C++ header|  
|--------------|--------------|------------------|  
|`trunc`,                `truncf`,  `truncl`|<math.h>|<cmath\>|  
  
 For additional compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md).  
  
## See Also  
 [Alphabetical Function Reference](../VS_visualcpp/CRT-Alphabetical-Function-Reference.md)   
 [floor, floorf, floorl](../VS_visualcpp/floor--floorf--floorl.md)   
 [ceil, ceilf, ceill](../VS_visualcpp/ceil--ceilf--ceill.md)   
 [round, roundf, roundl](../VS_visualcpp/round--roundf--roundl.md)