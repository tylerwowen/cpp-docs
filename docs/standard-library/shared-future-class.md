---
title: "shared_future Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: ['future/std::shared_future', 'future/std::shared_future::shared_future', 'future/std::shared_future::get', 'future/std::shared_future::valid', 'future/std::shared_future::wait', 'future/std::shared_future::wait_for', 'future/std::shared_future::wait_until']  
dev_langs: 
  - "C++"
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
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
# shared_future Class
Describes an *asynchronous return object*. In contrast with a [future](../standard-library/future-class.md) object, an *asynchronous provider* can be associated with any number of `shared_future` objects.  
  
## Syntax  
  
```
template <class Ty>
class shared_future;
```  
  
## Remarks  
 Do not call any methods other than `valid`, `operator=`, and the destructor on a `shared_future` object that's *empty*.  
  
 `shared_future` objects are not synchronized. Calling methods on the same object from multiple threads introduces a data race that has unpredictable results.  
  
## Members  
  
### Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[shared_future](#shared_future__shared_future)|Constructs a `shared_future` object.|  
  
### Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[get](#shared_future__get)|Retrieves the result that's stored in the *associated asynchronous state*.|  
|[valid](#shared_future__valid)|Specifies whether the object is not empty.|  
|[wait](#shared_future__wait)|Blocks the current thread until the associated asynchronous state is ready.|  
|[wait_for](#shared_future__wait_for)|Blocks until the associated asynchronous state is ready or until the specified time has elapsed.|  
|[wait_until](#shared_future__wait_until)|Blocks until the associated asynchronous state is ready or until a specified point in time.|  
  
### Public Operators  
  
|Name|Description|  
|----------|-----------------|  
|[shared_future::operator=](#shared_future__operator_eq)|Assigns a new associated asynchronous state.|  
  
## Requirements  
 **Header:** \<future>  
  
 **Namespace:** std  
  
##  <a name="shared_future__get"></a>  shared_future::get
 Retrieves the result that's stored in the *associated asynchronous state*.  
  
```
const Ty& get() const;

Ty& get() const;

void get() const;
```  
  
### Remarks  
 If the result is an exception, the method rethrows it. Otherwise, the result is returned.  
  
 Before it retrieves the result, this method blocks the current thread until the associated asynchronous state is ready.  
  
 For the partial specialization `shared_future<Ty&>`, the stored value is effectively a reference to the object that was passed to the *asynchronous provider* as the return value.  
  
 Because no stored value exists for the specialization `shared_future<void>`, the method returns `void`.  
  
##  <a name="shared_future__operator_eq"></a>  shared_future::operator=  
 Transfers an *associated asynchronous state* from a specified object.  
  
```
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```  
  
### Parameters  
 `Right`  
 A `shared_future` object.  
  
### Return Value  
 `*this`  
  
### Remarks  
 For the first operator, `Right` no longer has an associated asynchronous state after the operation.  
  
 For the second method, `Right` maintains its associated asynchronous state.  
  
##  <a name="shared_future__shared_future"></a>  shared_future::shared_future Constructor  
 Constructs a `shared_future` object.  
  
```
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```  
  
### Parameters  
 `Right`  
 A [future](../standard-library/future-class.md) or `shared_future` object.  
  
### Remarks  
 The first constructor constructs a `shared_future` object that has no *associated asynchronous state*.  
  
 The second and third constructors construct a `shared_future` object and transfer the associated asynchronous state from `Right`. `Right` no longer has an associated asynchronous state.  
  
 The fourth constructor constructs a `shared_future` object that has the same associated asynchronous state as `Right`.  
  
##  <a name="shared_future__valid"></a>  shared_future::valid
 Specifies whether the object has an *associated asynchronous state*.  
  
```
bool valid() noexcept;
```  
  
### Return Value  
 `true` if the object has an associated asynchronous state; otherwise, `false`.  
  
##  <a name="shared_future__wait"></a>  shared_future::wait
 Blocks the current thread until the *associated asynchronous state* is *ready*.  
  
```
void wait() const;
```  
  
### Remarks  
 An associated asynchronous state is ready only if its asynchronous provider has stored a return value or stored an exception.  
  
##  <a name="shared_future__wait_for"></a>  shared_future::wait_for
 Blocks the current thread until the associated asynchronous state is *ready* or until a specified time has elapsed.  
  
```
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```  
  
### Parameters  
 `Rel_time`  
 A [chrono::duration](../standard-library/duration-class.md) object that specifies a maximum time interval that the thread blocks.  
  
### Return Value  
 A [future_status](../standard-library/future-enums.md#future_status) that indicates the reason for returning.  
  
### Remarks  
 An associated asynchronous state is *ready* only if its asynchronous provider has stored a return value or stored an exception.  
  
##  <a name="shared_future__wait_until"></a>  shared_future::wait_until
 Blocks the current thread until the associated asynchronous state is *ready* or until after a specified time point.  
  
```
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```  
  
### Parameters  
 `Abs_time`  
 A [chrono::time_point](../standard-library/time-point-class.md) object that specifies a time after which the thread can unblock.  
  
### Return Value  
 A [future_status](../standard-library/future-enums.md#future_status) that indicates the reason for returning.  
  
### Remarks  
 An associated asynchronous state is ready only if its asynchronous provider has stored a return value or stored an exception.  
  
## See Also  
 [Header Files Reference](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)



