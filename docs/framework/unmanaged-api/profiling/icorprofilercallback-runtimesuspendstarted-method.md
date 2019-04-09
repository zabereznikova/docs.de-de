---
title: ICorProfilerCallback::RuntimeSuspendStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5606a556dd7aeafe6d7a6408d236f2bee8dc773
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168973"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="02146-102">ICorProfilerCallback::RuntimeSuspendStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="02146-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="02146-103">Benachrichtigt, dass die Laufzeit zum Anhalten von Threads für alle Common Language Runtime den Profiler.</span><span class="sxs-lookup"><span data-stu-id="02146-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02146-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02146-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02146-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="02146-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="02146-106">[in] Der Wert der [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) -Enumeration, die den Grund für die Unterbrechung angibt.</span><span class="sxs-lookup"><span data-stu-id="02146-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02146-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02146-107">Remarks</span></span>  
 <span data-ttu-id="02146-108">Alle Common Language Runtime-Threads, die in nicht verwaltetem Code können weiterhin ausgeführt, bis sie versuchen, auf die Runtime erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="02146-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="02146-109">Sie werden an dieser Stelle auch angehalten, bis die Laufzeit fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="02146-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="02146-110">Dies gilt auch für neue Threads, die die Laufzeit eingeben.</span><span class="sxs-lookup"><span data-stu-id="02146-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="02146-111">Alle Threads in der Laufzeit sind, dass entweder sofort angehalten, wenn sie bereits im unterbrechbaren Code, oder sie, zum Anhalten aufgefordert werden, wenn sie unterbrechbaren Code erreichen.</span><span class="sxs-lookup"><span data-stu-id="02146-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02146-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02146-112">Requirements</span></span>  
 <span data-ttu-id="02146-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02146-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02146-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02146-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02146-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02146-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="02146-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="02146-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="02146-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02146-117">See also</span></span>

- [<span data-ttu-id="02146-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02146-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="02146-119">RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="02146-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="02146-120">RuntimeSuspendFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="02146-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
