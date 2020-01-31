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
ms.openlocfilehash: 6b7aa7c60b5e861787d7a115d90a00d67cc48db0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866532"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="8f6ab-102">ICorProfilerCallback::ExceptionCatcherLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="8f6ab-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="8f6ab-103">Benachrichtigt den Profiler, dass das Steuerelement aus dem entsprechenden `catch`-Block herausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8f6ab-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f6ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f6ab-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8f6ab-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f6ab-105">Remarks</span></span>  
 <span data-ttu-id="8f6ab-106">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8f6ab-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="8f6ab-107">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8f6ab-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="8f6ab-108">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="8f6ab-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f6ab-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f6ab-109">Requirements</span></span>  
 <span data-ttu-id="8f6ab-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f6ab-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f6ab-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f6ab-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f6ab-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f6ab-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f6ab-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f6ab-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f6ab-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f6ab-114">See also</span></span>

- [<span data-ttu-id="8f6ab-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f6ab-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="8f6ab-116">ExceptionCatcherEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="8f6ab-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
