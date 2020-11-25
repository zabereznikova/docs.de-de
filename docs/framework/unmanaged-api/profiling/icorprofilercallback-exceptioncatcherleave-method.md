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
ms.openlocfilehash: c0a24a8f9b7c40d87f9b9b6fe77eba7d6c0ea89f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700027"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="ee6f5-102">ICorProfilerCallback::ExceptionCatcherLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="ee6f5-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>

<span data-ttu-id="ee6f5-103">Benachrichtigt den Profiler, dass das Steuerelement aus dem entsprechenden-Block herausgegeben wird `catch` .</span><span class="sxs-lookup"><span data-stu-id="ee6f5-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee6f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee6f5-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ee6f5-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee6f5-105">Remarks</span></span>  

 <span data-ttu-id="ee6f5-106">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="ee6f5-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="ee6f5-107">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ee6f5-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="ee6f5-108">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="ee6f5-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee6f5-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ee6f5-109">Requirements</span></span>  

 <span data-ttu-id="ee6f5-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee6f5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee6f5-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ee6f5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ee6f5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee6f5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee6f5-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee6f5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee6f5-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee6f5-114">See also</span></span>

- [<span data-ttu-id="ee6f5-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee6f5-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ee6f5-116">ExceptionCatcherEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="ee6f5-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
