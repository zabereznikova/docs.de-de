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
ms.openlocfilehash: 07e2ebe8afe6002dee6c45f56fa1f11a4083d6bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145599"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="312b1-102">ICorProfilerCallback::RuntimeSuspendFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="312b1-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="312b1-103">Benachrichtigt den Profiler an, die die Laufzeit Anhalten aller Threads der Common Language Runtime abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="312b1-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="312b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="312b1-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="312b1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="312b1-105">Remarks</span></span>  
 <span data-ttu-id="312b1-106">Alle Common Language Runtime-Threads, die in nicht verwaltetem Code können weiterhin ausgeführt, bis sie versuchen, auf die Runtime erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="312b1-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="312b1-107">Sie werden an dieser Stelle auch angehalten, bis die Laufzeit fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="312b1-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="312b1-108">Dies gilt auch für neue Threads, die die Laufzeit eingeben.</span><span class="sxs-lookup"><span data-stu-id="312b1-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="312b1-109">Alle Threads in der Laufzeit sind, dass entweder sofort angehalten, wenn sie bereits im unterbrechbaren Code, oder sie, zum Anhalten aufgefordert werden, wenn sie unterbrechbaren Code erreichen.</span><span class="sxs-lookup"><span data-stu-id="312b1-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="312b1-110">Die `RuntimeSuspendFinished` Rückruf wird garantiert auf im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="312b1-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="312b1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="312b1-111">Requirements</span></span>  
 <span data-ttu-id="312b1-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="312b1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="312b1-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="312b1-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="312b1-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="312b1-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="312b1-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="312b1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="312b1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="312b1-116">See also</span></span>

- [<span data-ttu-id="312b1-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="312b1-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="312b1-118">RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="312b1-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
