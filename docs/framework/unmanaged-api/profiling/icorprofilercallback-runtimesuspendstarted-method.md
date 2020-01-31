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
ms.openlocfilehash: e88f6356c2e29a1d8a9e49527c5921e8155c3ce4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865882"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="2ff15-102">ICorProfilerCallback::RuntimeSuspendStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="2ff15-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="2ff15-103">Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads aussetzen soll.</span><span class="sxs-lookup"><span data-stu-id="2ff15-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ff15-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ff15-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ff15-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2ff15-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="2ff15-106">in Ein Wert der [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) -Enumeration, die den Grund für die Unterbrechung angibt.</span><span class="sxs-lookup"><span data-stu-id="2ff15-106">[in] A value of the [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ff15-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ff15-107">Remarks</span></span>  
 <span data-ttu-id="2ff15-108">Alle Laufzeitthreads in nicht verwaltetem Code können weiter ausgeführt werden, bis Sie versuchen, die Laufzeit erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="2ff15-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="2ff15-109">An diesem Punkt werden Sie auch angehalten, bis die Laufzeit fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="2ff15-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="2ff15-110">Dies gilt auch für neue Threads, die zur Laufzeit gelangen.</span><span class="sxs-lookup"><span data-stu-id="2ff15-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="2ff15-111">Alle Threads in der Laufzeit werden entweder sofort angehalten, wenn Sie sich bereits in interruptebarem Code befinden, oder Sie werden angehalten, wenn Sie unter brechbaren Code erreichen.</span><span class="sxs-lookup"><span data-stu-id="2ff15-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ff15-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ff15-112">Requirements</span></span>  
 <span data-ttu-id="2ff15-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ff15-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ff15-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2ff15-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2ff15-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ff15-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ff15-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ff15-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ff15-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ff15-117">See also</span></span>

- [<span data-ttu-id="2ff15-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ff15-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2ff15-119">RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="2ff15-119">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="2ff15-120">RuntimeSuspendFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="2ff15-120">RuntimeSuspendFinished Method</span></span>](icorprofilercallback-runtimesuspendfinished-method.md)
