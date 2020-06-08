---
title: ICorProfilerCallback::ExceptionUnwindFinallyEnter-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
ms.openlocfilehash: f5e4939c814239c297fc0aa88644dc0472b0c419
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500155"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="cb365-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="cb365-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="cb365-103">Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung in eine `finally` in der angegebenen Funktion enthaltene Klausel eintritt.</span><span class="sxs-lookup"><span data-stu-id="cb365-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb365-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb365-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb365-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cb365-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="cb365-106">\[in] die ID der Funktion, die die- `finally` Klausel enthält.</span><span class="sxs-lookup"><span data-stu-id="cb365-106">\[in] The ID of the function that contains the `finally` clause.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb365-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cb365-107">Remarks</span></span>  
 <span data-ttu-id="cb365-108">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="cb365-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="cb365-109">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cb365-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="cb365-110">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="cb365-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb365-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cb365-111">Requirements</span></span>  
 <span data-ttu-id="cb365-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb365-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb365-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb365-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb365-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb365-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb365-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb365-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb365-116">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="cb365-116">See also</span></span>

- [<span data-ttu-id="cb365-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb365-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="cb365-118">GetNotifiedExceptionClauseInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="cb365-118">GetNotifiedExceptionClauseInfo Method</span></span>](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="cb365-119">ExceptionUnwindFinallyLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="cb365-119">ExceptionUnwindFinallyLeave Method</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)
