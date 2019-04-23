---
title: ICorProfilerCallback::RuntimeThreadSuspended-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a0748802599926f4ec218362e6f7d086aab2d8f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080227"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="ccb29-102">ICorProfilerCallback::RuntimeThreadSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="ccb29-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="ccb29-103">Benachrichtigt den Profiler an, der angegebene Thread wurde angehalten oder unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="ccb29-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb29-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccb29-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccb29-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ccb29-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="ccb29-106">[in] Die ID des Threads, der angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="ccb29-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccb29-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ccb29-107">Remarks</span></span>  
 <span data-ttu-id="ccb29-108">Die `RuntimeThreadSuspended` Notifications können jederzeit zwischen der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) und den zugehörigen [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) Rückrufe.</span><span class="sxs-lookup"><span data-stu-id="ccb29-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="ccb29-109">Benachrichtigungen, die zwischen den [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) und `RuntimeResumeStarted` sind für Threads, die ausgeführt wurden, in nicht Code verwaltetem und beim Einstieg in die Laufzeit angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="ccb29-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="ccb29-110">Im Allgemeinen tritt dieser Rückruf unmittelbar nach ein Thread angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="ccb29-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="ccb29-111">Allerdings ist der aktuell ausgeführte Thread (der Thread, der dieser Rückruf aufgerufen wird) die, die gesperrt wird, wird dieser Rückruf auftreten, kurz bevor der Thread angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="ccb29-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccb29-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ccb29-112">Requirements</span></span>  
 <span data-ttu-id="ccb29-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccb29-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccb29-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ccb29-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ccb29-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccb29-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccb29-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccb29-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb29-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccb29-117">See also</span></span>

- [<span data-ttu-id="ccb29-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccb29-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ccb29-119">RuntimeThreadResumed-Methode</span><span class="sxs-lookup"><span data-stu-id="ccb29-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
