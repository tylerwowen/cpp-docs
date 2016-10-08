---
title: "free"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
  - C
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
apiname: 
  - free
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
  - api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 14
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
# free
Deallocates or frees a memory block.  
  
## Syntax  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### Parameters  
 `memblock`  
 Previously allocated memory block to be freed.  
  
## Remarks  
 The `free` function deallocates a memory block (`memblock`) that was previously allocated by a call to `calloc`, `malloc`, or `realloc`. The number of freed bytes is equivalent to the number of bytes requested when the block was allocated (or reallocated, in the case of `realloc`). If `memblock` is `NULL`, the pointer is ignored and `free` immediately returns. Attempting to free an invalid pointer (a pointer to a memory block that was not allocated by `calloc`, `malloc`, or `realloc`) may affect subsequent allocation requests and cause errors.  
  
 If an error occurs in freeing the memory, `errno` is set with information from the operating system on the nature of the failure. For more information, see [errno, _doserrno, _sys_errlist, and _sys_nerr](../VS_visualcpp/errno--_doserrno--_sys_errlist--and-_sys_nerr.md).  
  
 After a memory block has been freed, [_heapmin](../VS_visualcpp/_heapmin.md) minimizes the amount of free memory on the heap by coalescing the unused regions and releasing them back to the operating system. Freed memory that is not released to the operating system is restored to the free pool and is available for allocation again.  
  
 When the application is linked with a debug version of the C run-time libraries, `free` resolves to [_free_dbg](../VS_visualcpp/_free_dbg.md). For more information about how the heap is managed during the debugging process, see [The CRT Debug Heap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `free` is marked `__declspec(noalias)`, meaning that the function is guaranteed not to modify global variables. For more information, see [noalias](../VS_visualcpp/noalias.md).  
  
 To free memory allocated with [_malloca](../VS_visualcpp/_malloca.md), use [_freea](../VS_visualcpp/_freea.md).  
  
## Requirements  
  
|Function|Required header|  
|--------------|---------------------|  
|`free`|<stdlib.h> and <malloc.h>|  
  
 For additional compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md) in the Introduction.  
  
## Example  
 See the example for [malloc](../VS_visualcpp/malloc.md).  
  
## .NET Framework Equivalent  
 Not applicable. To call the standard C function, use `PInvoke`. For more information, see [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## See Also  
 [Memory Allocation](../VS_visualcpp/Memory-Allocation.md)   
 [_alloca](../VS_visualcpp/_alloca.md)   
 [calloc](../VS_visualcpp/calloc.md)   
 [malloc](../VS_visualcpp/malloc.md)   
 [realloc](../VS_visualcpp/realloc.md)   
 [_free_dbg](../VS_visualcpp/_free_dbg.md)   
 [_heapmin](../VS_visualcpp/_heapmin.md)   
 [_freea](../VS_visualcpp/_freea.md)