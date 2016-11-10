---
title: "Debugging and Error Reporting Global Functions"
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
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 12
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
# Debugging and Error Reporting Global Functions
These functions provide useful debugging and trace facilities.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](../Topic/AtlHresultFromLastError.md)|Returns a                             `GetLastError` error code in the form of an HRESULT.|  
|[AtlHresultFromWin32](../Topic/AtlHresultFromWin32.md)|Converts a Win32 error code into an HRESULT.|  
|[AtlReportError](../Topic/AtlReportError.md)|Sets up                             **IErrorInfo** to provide error details to a client.|  
|[AtlThrow](../Topic/AtlThrow.md)|Throws a                             `CAtlException`.|  
|[AtlThrowLastWin32](../Topic/AtlThrowLastWin32.md)|Call this function to signal an error based on the result of the Windows function                             `GetLastError`.|  
|[AtlTraceLoadSettings](../Topic/AtlTraceLoadSettings.md)|Call this function to load trace settings from a file.|  
|[AtlTraceSaveSettings](../Topic/AtlTraceSaveSettings.md)|Call this function to save the current trace settings to a file.|  
  
##  <a name="atlhresultfromlasterror"></a>  AtlHresultFromLastError  
 Returns the calling thread's last-error code value in the form of an HRESULT.  
  
```  
HRESULT AtlHresultFromLastError();  
```  
  
### Remarks  
 `AtlHresultFromLastError` calls                         `GetLastError` to obtain the last error and returns the error after converting it to an HRESULT using the                         **HRESULT_FROM_WIN32** macro.  
  
##  <a name="atlhresultfromwin32"></a>  AtlHresultFromWin32  
 Converts a Win32 error code into an HRESULT.  
  
```  
AtlHresultFromWin32{  
        DWORD error  
        };  
```  
  
### Parameters  
 *error*  
 The error value to convert.  
  
### Remarks  
 Converts a Win32 error code into an HRESULT, using the macro                         **HRESULT_FROM_WIN32**.  
  
> [!NOTE]
>  Instead of using                             **HRESULT_FROM_WIN32(GetLastError())**, use the function                             [AtlHresultFromLastError](../Topic/AtlHresultFromLastError.md).  
  
##  <a name="atlreporterror"></a>  AtlReportError  
 Sets up the                 `IErrorInfo` interface to provide error information to clients of the object.  
  
```  
HRESULT     WINAPI  
        AtlReportError(  
           const           CLSID& clsid,  
    LPCOLESTR lpszDesc,  
    const           IID& iid = GUID_NULL,  
           HRESULT hRes = 0   
        );  
  
        HRESULT     WINAPI  
        AtlReportError(  
           const           CLSID& clsid,  
    LPCOLESTR lpszDesc,  
    DWORD dwHelpID,  
    LPCOLESTR lpszHelpFile,  
    const           IID& iid = GUID_NULL,  
           HRESULT hRes = 0   
        );  
  
        HRESULT     WINAPI  
        AtlReportError(  
           const           CLSID& clsid,  
    LPCSTR lpszDesc,  
    const           IID& iid = GUID_NULL,  
           HRESULT hRes = 0   
        );  
  
        HRESULT     WINAPI  
        AtlReportError(  
           const           CLSID& clsid,  
    LPCSTR lpszDesc,  
    DWORD dwHelpID,  
    LPCSTR lpszHelpFile,  
    const           IID& iid = GUID_NULL,  
           HRESULT hRes = 0   
        );  
  
        HRESULT     WINAPI  
        AtlReportError(  
           const           CLSID& clsid,  
    UINT nID,  
    const           IID& iid = GUID_NULL,  
           HRESULT hRes = 0,  
           HINSTANCE hInst = _AtlBaseModule.GetResourceInstance()  
        );  
  
        HRESULT     WINAPI  
        AtlReportError(  
           const           CLSID& clsid,  
    UINT nID,  
    DWORD dwHelpID,  
    LPCOLESTR lpszHelpFile,  
    const           IID& iid = GUID_NULL,  
           HRESULT hRes = 0,  
           HINSTANCE hInst = _AtlBaseModule.GetResourceInstance()  
        );  
```  
  
### Parameters  
 `clsid`  
 [in] The CLSID of the object reporting the error.  
  
 `lpszDesc`  
 [in] The string describing the error. The Unicode versions specify that                                 `lpszDesc` is of type                                 **LPCOLESTR**; the ANSI version specifies a type of                                 `LPCSTR`.  
  
 `iid`  
 [in] The IID of the interface defining the error or                                 `GUID_NULL` if the error is defined by the operating system.  
  
 `hRes`  
 [in] The                                 `HRESULT` you want returned to the caller.  
  
 `nID`  
 [in] The resource identifier where the error description string is stored. This value should lie between 0x0200 and 0xFFFF, inclusively. In debug builds, an                                 **ASSERT** will result if                                 `nID` does not index a valid string. In release builds, the error description string will be set to "Unknown Error."  
  
 `dwHelpID`  
 [in] The help context identifier for the error.  
  
 `lpszHelpFile`  
 [in] The path and name of the help file describing the error.  
  
 `hInst`  
 [in] The handle to the resource. By default, this parameter is                                 **__AtlBaseModuleModule::GetResourceInstance**, where                                 **__AtlBaseModuleModule** is the global instance of                                 [CAtlBaseModule](../VS_visualcpp/CAtlBaseModule-Class.md) or a class derived from it.  
  
### Return Value  
 If the                         `hRes` parameter is nonzero, returns the value of                         `hRes`. If                         `hRes` is zero, then the first four versions of                         `AtlReportError` return                         `DISP_E_EXCEPTION`. The last two versions return the result of the macro                         **MAKE_HRESULT( 1, FACILITY_ITF,** `nID` **)**.  
  
### Remarks  
 The string                         *lpszDesc* is used as the text description of the error. When the client receives the                         `hRes` you return from                         `AtlReportError`, the client can access the                         **IErrorInfo** structure for details about the error.  
  
### Example  
 [!CODE [NVC_ATL_COM#52](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#52)]  
  
> [!CAUTION]
>  Do not use                                     `AtlReportError` in C++ catch handlers. Some overrides of these functions use the ATL string conversion macros internally, which in turn use the                                     `_alloca` function internally. Using                                     `AtlReportError` in a C++ catch handler can cause exceptions in C++ catch handlers.  
  
##  <a name="atlthrow"></a>  AtlThrow  
 Call this function to signal an error based on a                 `HRESULT` status code.  
  
```  
__declspec(noreturn) inline void AtlThrow(           HRESULT hr );  
```  
  
### Parameters  
 `hr`  
 Standard HRESULT value.  
  
### Remarks  
 This function is used by ATL and MFC code in the event of an error condition. It can also be called from your own code. The default implementation of this function depends on the definition of the symbol                         **_ATL_NO_EXCEPTIONS** and on the type of project, MFC or ATL.  
  
 In all cases, this function traces the HRESULT to the debugger.  
  
 In Visual Studio 2015 Update 3 and later, this function is attributed __declspec(noreturn) to avoid spurious SAL warnings.  
  
 If                         **_ATL_NO_EXCEPTIONS** is not defined in an MFC project, this function throws a                         [CMemoryException](../VS_visualcpp/CMemoryException-Class.md) or a                         [COleException](../VS_visualcpp/COleException-Class.md) based on the value of the HRESULT.  
  
 If                         **_ATL_NO_EXCEPTIONS** is not defined in an ATL project, the function throws a                         [CAtlException](../VS_visualcpp/CAtlException-Class.md).  
  
 If                         **_ATL_NO_EXCEPTIONS** is defined, the function causes an assertion failure instead of throwing an exception.  
  
 For ATL projects, it is possible to provide your own implementation of this function to be used by ATL in the event of a failure. To do this, define your own function with the same signature as                         `AtlThrow` and #define                         `AtlThrow` to be the name of your function. This must be done before including atlexcept.h (which means that it must be done prior to including any ATL headers since atlbase.h includes atlexcept.h). Attribute your function                         `__declspec(noreturn)` to avoid spurious SAL warnings.  
  
### Example  
 [!CODE [NVC_ATL_Windowing#95](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#95)]  
  
##  <a name="atlthrowlastwin32"></a>  AtlThrowLastWin32  
 Call this function to signal an error based on the result of the Windows function                 `GetLastError`.  
  
```  
inline void AtlThrowLastWin32();  
```  
  
### Remarks  
 This function traces the result of                         `GetLastError` to the debugger.  
  
 If                         **_ATL_NO_EXCEPTIONS** is not defined in an MFC project, this function throws a                         [CMemoryException](../VS_visualcpp/CMemoryException-Class.md) or a                         [COleException](../VS_visualcpp/COleException-Class.md) based on the value returned by                         `GetLastError`.  
  
 If                         **_ATL_NO_EXCEPTIONS** is not defined in an ATL project, the function throws a                         [CAtlException](../VS_visualcpp/CAtlException-Class.md).  
  
 If                         **_ATL_NO_EXCEPTIONS** is defined, the function causes an assertion failure instead of throwing an exception.  
  
## See Also  
 [Functions](../VS_visualcpp/ATL-Functions.md)   
 [Debugging and Error Reporting Macros](../VS_visualcpp/Debugging-and-Error-Reporting-Macros.md)