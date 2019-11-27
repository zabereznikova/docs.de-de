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
ms.openlocfilehash: 7d61a6db8f42398a0d6e0d818605592f4fe71cf7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445009"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="a697f-102">ICorProfilerCallback::ExceptionCatcherLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="a697f-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="a697f-103">Benachrichtigt den Profiler, dass das Steuerelement aus dem entsprechenden `catch`-Block herausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a697f-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a697f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a697f-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a697f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a697f-105">Remarks</span></span>  
 <span data-ttu-id="a697f-106">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a697f-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="a697f-107">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a697f-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="a697f-108">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="a697f-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a697f-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a697f-109">Requirements</span></span>  
 <span data-ttu-id="a697f-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a697f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a697f-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a697f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a697f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a697f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a697f-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a697f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a697f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a697f-114">See also</span></span>

- [<span data-ttu-id="a697f-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a697f-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a697f-116">ExceptionCatcherEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="a697f-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
