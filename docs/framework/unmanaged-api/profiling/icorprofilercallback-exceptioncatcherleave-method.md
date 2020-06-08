---
title: ICorProfilerCallback::ExceptionCatcherLeave-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
ms.openlocfilehash: cff2dd9fdb05ea4dd160dfa57df6f047beb57f69
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500298"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="bb867-102">ICorProfilerCallback::ExceptionCatcherLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="bb867-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="bb867-103">Benachrichtigt den Profiler, dass das Steuerelement aus dem entsprechenden-Block herausgegeben wird `catch` .</span><span class="sxs-lookup"><span data-stu-id="bb867-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb867-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb867-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="bb867-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bb867-105">Remarks</span></span>  
 <span data-ttu-id="bb867-106">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="bb867-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="bb867-107">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bb867-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="bb867-108">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="bb867-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb867-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bb867-109">Requirements</span></span>  
 <span data-ttu-id="bb867-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb867-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb867-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb867-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bb867-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb867-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb867-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb867-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb867-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="bb867-114">See also</span></span>

- [<span data-ttu-id="bb867-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb867-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="bb867-116">ExceptionCatcherEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="bb867-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
