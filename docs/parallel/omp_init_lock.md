---
title: "omp_init_lock"
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
  - "omp_init_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_init_lock OpenMP function"
ms.assetid: 7a65e3e2-2e31-4645-964c-c1e82e2a4d0e
caps.latest.revision: 13
ms.author: "mithom"
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
# omp_init_lock
Initializes a simple lock.  
  
## Syntax  
  
```  
void omp_init_lock(  
   omp_lock_t *lock  
);  
```  
  
#### Parameters  
 `lock`  
 A variable of type [omp_lock_t](../parallel/omp_lock_t.md).  
  
## Remarks  
 For more information, see [3.2.1 omp_init_lock and omp_init_nest_lock Functions](../parallel/3.2.1-omp_init_lock-and-omp_init_nest_lock-functions.md).  
  
## Example  
  
```  
// omp_init_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t my_lock;  
  
int main() {  
   omp_init_lock(&my_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num( );  
      int i, j;  
  
      for (i = 0; i < 5; ++i) {  
         omp_set_lock(&my_lock);  
         printf_s("Thread %d - starting locked region\n", tid);  
         printf_s("Thread %d - ending locked region\n", tid);  
         omp_unset_lock(&my_lock);  
      }  
   }  
  
   omp_destroy_lock(&my_lock);  
}  
```  
  
 **Thread 0 - starting locked region**  
**Thread 0 - ending locked region**  
**Thread 0 - starting locked region**  
**Thread 0 - ending locked region**  
**Thread 0 - starting locked region**  
**Thread 0 - ending locked region**  
**Thread 0 - starting locked region**  
**Thread 0 - ending locked region**  
**Thread 0 - starting locked region**  
**Thread 0 - ending locked region**  
**Thread 1 - starting locked region**  
**Thread 1 - ending locked region**  
**Thread 1 - starting locked region**  
**Thread 1 - ending locked region**  
**Thread 1 - starting locked region**  
**Thread 1 - ending locked region**  
**Thread 1 - starting locked region**  
**Thread 1 - ending locked region**  
**Thread 1 - starting locked region**  
**Thread 1 - ending locked region**  
**Thread 2 - starting locked region**  
**Thread 2 - ending locked region**  
**Thread 2 - starting locked region**  
**Thread 2 - ending locked region**  
**Thread 2 - starting locked region**  
**Thread 2 - ending locked region**  
**Thread 2 - starting locked region**  
**Thread 2 - ending locked region**  
**Thread 2 - starting locked region**  
**Thread 2 - ending locked region**  
**Thread 3 - starting locked region**  
**Thread 3 - ending locked region**  
**Thread 3 - starting locked region**  
**Thread 3 - ending locked region**  
**Thread 3 - starting locked region**  
**Thread 3 - ending locked region**  
**Thread 3 - starting locked region**  
**Thread 3 - ending locked region**  
**Thread 3 - starting locked region**  
**Thread 3 - ending locked region**   
## See Also  
 [Functions](../parallel/openmp-functions.md)