---
title: ICorProfilerCallback::RuntimeSuspendStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 358536aa51dfef2d079813b34eddbd1b01294bcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="055b1-102">ICorProfilerCallback::RuntimeSuspendStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="055b1-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="055b1-103">Benachrichtigt den Profiler, dass die Laufzeit alle Runtime Threads anhalten.</span><span class="sxs-lookup"><span data-stu-id="055b1-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="055b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="055b1-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="055b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="055b1-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="055b1-106">[in] Der Wert der [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) -Enumeration, der den Grund für die Unterbrechung angibt.</span><span class="sxs-lookup"><span data-stu-id="055b1-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="055b1-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="055b1-107">Remarks</span></span>  
 <span data-ttu-id="055b1-108">Alle Common Language Runtime-Threads, die in nicht verwaltetem Code sind dürfen weiter ausgeführt wird, bis sie versuchen, auf die Common Language Runtime erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="055b1-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="055b1-109">An diesem Punkt werden sie auch angehalten, bis die Laufzeit fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="055b1-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="055b1-110">Dies gilt auch für neue Threads, die die Common Language Runtime eingeben.</span><span class="sxs-lookup"><span data-stu-id="055b1-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="055b1-111">Alle Threads in der Laufzeit sind entweder sofort angehalten, wenn sie bereits im Code parallelisiert sind oder sie aufgefordert werden, angehalten, wenn sie unterbrechbaren Code erreichen.</span><span class="sxs-lookup"><span data-stu-id="055b1-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="055b1-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="055b1-112">Requirements</span></span>  
 <span data-ttu-id="055b1-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="055b1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="055b1-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="055b1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="055b1-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="055b1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="055b1-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="055b1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="055b1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="055b1-117">See Also</span></span>  
 [<span data-ttu-id="055b1-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="055b1-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="055b1-119">RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="055b1-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)  
 [<span data-ttu-id="055b1-120">RuntimeSuspendFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="055b1-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
