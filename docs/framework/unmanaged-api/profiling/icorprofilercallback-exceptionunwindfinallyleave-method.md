---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
ms.openlocfilehash: e02716350aa2bf32bdd7c4b2e01841405de6dc14
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720398"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="7d878-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="7d878-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>

<span data-ttu-id="7d878-103">Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung eine-Klausel hinterlassen hat `finally` .</span><span class="sxs-lookup"><span data-stu-id="7d878-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d878-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d878-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7d878-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d878-105">Remarks</span></span>  

 <span data-ttu-id="7d878-106">Der Profiler sollte während dieses Aufrufes nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="7d878-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="7d878-107">Wenn der Profiler hier blockiert wird und ein Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7d878-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="7d878-108">Außerdem darf der Profiler während dieses Aufrufes nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="7d878-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d878-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7d878-109">Requirements</span></span>  

 <span data-ttu-id="7d878-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d878-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d878-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7d878-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7d878-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d878-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d878-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d878-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d878-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d878-114">See also</span></span>

- [<span data-ttu-id="7d878-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d878-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7d878-116">ExceptionUnwindFinallyEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="7d878-116">ExceptionUnwindFinallyEnter Method</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)
