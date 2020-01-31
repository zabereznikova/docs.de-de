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
ms.openlocfilehash: c8645bf828d0ad99bd25c1909cbee3314a11abf9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865869"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="40731-102">ICorProfilerCallback::RuntimeThreadSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="40731-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="40731-103">Benachrichtigt den Profiler, dass der angegebene Thread angehalten wurde oder im Begriff ist, angehalten zu werden.</span><span class="sxs-lookup"><span data-stu-id="40731-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40731-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40731-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40731-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="40731-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="40731-106">in Die ID des Threads, der angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="40731-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40731-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40731-107">Remarks</span></span>  
 <span data-ttu-id="40731-108">Die `RuntimeThreadSuspended` Benachrichtigung kann jederzeit zwischen der [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) -und der zugeordneten [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) -Rückrufe auftreten.</span><span class="sxs-lookup"><span data-stu-id="40731-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="40731-109">Benachrichtigungen zwischen [ICorProfilerCallback:: runtimesuspendend](icorprofilercallback-runtimesuspendfinished-method.md) und `RuntimeResumeStarted` gelten für Threads, die in nicht verwaltetem Code ausgeführt wurden und bei einem Eintrag zur Laufzeit angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="40731-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="40731-110">Dieser Rückruf tritt im Allgemeinen auf, wenn ein Thread angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="40731-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="40731-111">Wenn jedoch der derzeit ausgeführte Thread (der Thread, der diesen Rückruf aufgerufen hat) der Vorgang ist, der angehalten wird, wird dieser Rückruf unmittelbar vor dem Aussetzen des Threads ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="40731-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40731-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40731-112">Requirements</span></span>  
 <span data-ttu-id="40731-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40731-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40731-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40731-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40731-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40731-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40731-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40731-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40731-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40731-117">See also</span></span>

- [<span data-ttu-id="40731-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40731-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="40731-119">RuntimeThreadResumed-Methode</span><span class="sxs-lookup"><span data-stu-id="40731-119">RuntimeThreadResumed Method</span></span>](icorprofilercallback-runtimethreadresumed-method.md)
