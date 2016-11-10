---
title: "Date and Time: SYSTEMTIME Support"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "SYSTEMTIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system time"
  - "FILETIME structure, with CTime class"
  - "time [C++], formatting"
  - "SYSTEMTIME structure"
  - "dates [C++], MFC"
  - "formatting [C++], time"
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
caps.latest.revision: 9
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
# Date and Time: SYSTEMTIME Support
The [CTime](../atl/ctime-class.md) class has constructors that accept system and file times from Win32. If you use `CTime` objects for these purposes, you must modify their initialization accordingly, as described in this article.  
  
 For information about the SYSTEMTIME structure, see [SYSTEMTIME](../mfcref/systemtime-structure1.md). For information about the FILETIME structure, see FILETIME.  
  
 MFC still provides `CTime` constructors that take time arguments in the MS-DOS style, but, starting in MFC version 3.0, the `CTime` class also supports a constructor that takes a Win32 `SYSTEMTIME` structure and another that takes a Win32 `FILETIME` structure.  
  
 The new `CTime` constructors are:  
  
-   CTime(const SYSTEMTIME& `sysTime`);  
  
-   CTime(const FILETIME& `fileTime`);  
  
 The `fileTime` parameter is a reference to a Win32 `FILETIME` structure, which represents time as a 64-bit value, a more convenient format for internal storage than a `SYSTEMTIME` structure and the format used by Win32 to represent the time of file creation.  
  
 If your code contains a `CTime` object initialized with the system time, you should use the `SYSTEMTIME` constructor in Win32.  
  
 You most likely will not use `CTime` `FILETIME` initialization directly. If you use a `CFile` object to manipulate a file, [CFile::GetStatus](../Topic/CFile::GetStatus.md) retrieves the file timestamp for you via a `CTime` object initialized with a `FILETIME` structure.  
  
## What do you want to know more about?  
  
-   [General date and time programming in MFC](../atl/date-and-time.md)  
  
-   [Automation support of date and time programming](../atl/date-and-time--automation-support.md)  
  
-   [General-purpose classes for date and time programming](../atl/date-and-time--general-purpose-classes.md)  
  
## See Also  
 [Date and Time](../atl/date-and-time.md)