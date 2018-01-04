---
title: ICorProfilerCallback::RuntimeThreadSuspended-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeThreadSuspended
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f22e9a6ed8c62256bb3e614dbc1278dea24d4e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="62bed-102">ICorProfilerCallback::RuntimeThreadSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="62bed-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="62bed-103">Benachrichtigt den Profiler, der angegebene Thread angehalten wurde oder unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="62bed-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62bed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62bed-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62bed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="62bed-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="62bed-106">[in] Die ID des Threads, die angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="62bed-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62bed-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62bed-107">Remarks</span></span>  
 <span data-ttu-id="62bed-108">Die `RuntimeThreadSuspended` Notifications können einem beliebigen Zeitpunkt zwischen dem [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) und den zugehörigen [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) Rückrufe.</span><span class="sxs-lookup"><span data-stu-id="62bed-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="62bed-109">Benachrichtigungen, die zwischen auftreten [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) und `RuntimeResumeStarted` sind für Threads, die ausgeführt wurden, in nicht Code verwaltetem und beim Einstieg in die Laufzeit angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="62bed-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="62bed-110">Im Allgemeinen tritt dieser Rückruf unmittelbar nach ein Thread angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="62bed-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="62bed-111">Allerdings ist der aktuell ausgeführte Thread (der Thread, die dieser Rückruf aufgerufen wird) die, die wird angehalten, wird dieser Rückruf auftreten, kurz bevor der Thread angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="62bed-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62bed-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62bed-112">Requirements</span></span>  
 <span data-ttu-id="62bed-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62bed-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62bed-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62bed-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="62bed-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62bed-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62bed-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62bed-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62bed-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62bed-117">See Also</span></span>  
 [<span data-ttu-id="62bed-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62bed-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="62bed-119">RuntimeThreadResumed-Methode</span><span class="sxs-lookup"><span data-stu-id="62bed-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
