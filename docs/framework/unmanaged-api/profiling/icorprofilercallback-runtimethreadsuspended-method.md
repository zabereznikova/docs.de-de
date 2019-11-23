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
ms.openlocfilehash: 509d6cd2e65c2eb8c92f6d79deae9e01e75298f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433449"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="b5309-102">ICorProfilerCallback::RuntimeThreadSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="b5309-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="b5309-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span><span class="sxs-lookup"><span data-stu-id="b5309-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5309-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5309-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5309-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5309-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b5309-106">[in] The ID of the thread that has been suspended.</span><span class="sxs-lookup"><span data-stu-id="b5309-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5309-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5309-107">Remarks</span></span>  
 <span data-ttu-id="b5309-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span><span class="sxs-lookup"><span data-stu-id="b5309-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="b5309-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span><span class="sxs-lookup"><span data-stu-id="b5309-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="b5309-110">Generally, this callback occurs just after a thread is suspended.</span><span class="sxs-lookup"><span data-stu-id="b5309-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="b5309-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span><span class="sxs-lookup"><span data-stu-id="b5309-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5309-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5309-112">Requirements</span></span>  
 <span data-ttu-id="b5309-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5309-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5309-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b5309-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b5309-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5309-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5309-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5309-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5309-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5309-117">See also</span></span>

- [<span data-ttu-id="b5309-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b5309-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b5309-119">RuntimeThreadResumed-Methode</span><span class="sxs-lookup"><span data-stu-id="b5309-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
