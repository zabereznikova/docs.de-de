---
title: ICorProfilerCallback::RuntimeSuspendFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f69c39938384c7feca28ae40aba3e80a0ba28ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706653"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="6ae7c-102">ICorProfilerCallback::RuntimeSuspendFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="6ae7c-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="6ae7c-103">Benachrichtigt den Profiler an, die die Laufzeit Anhalten aller Threads der Common Language Runtime abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="6ae7c-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ae7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ae7c-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6ae7c-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ae7c-105">Remarks</span></span>  
 <span data-ttu-id="6ae7c-106">Alle Common Language Runtime-Threads, die in nicht verwaltetem Code können weiterhin ausgeführt, bis sie versuchen, auf die Runtime erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="6ae7c-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="6ae7c-107">Sie werden an dieser Stelle auch angehalten, bis die Laufzeit fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6ae7c-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="6ae7c-108">Dies gilt auch für neue Threads, die die Laufzeit eingeben.</span><span class="sxs-lookup"><span data-stu-id="6ae7c-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="6ae7c-109">Alle Threads in der Laufzeit sind, dass entweder sofort angehalten, wenn sie bereits im unterbrechbaren Code, oder sie, zum Anhalten aufgefordert werden, wenn sie unterbrechbaren Code erreichen.</span><span class="sxs-lookup"><span data-stu-id="6ae7c-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="6ae7c-110">Die `RuntimeSuspendFinished` Rückruf wird garantiert auf im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="6ae7c-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ae7c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ae7c-111">Requirements</span></span>  
 <span data-ttu-id="6ae7c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ae7c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ae7c-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ae7c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ae7c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ae7c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ae7c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ae7c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae7c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ae7c-116">See also</span></span>
- [<span data-ttu-id="6ae7c-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ae7c-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="6ae7c-118">RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="6ae7c-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
