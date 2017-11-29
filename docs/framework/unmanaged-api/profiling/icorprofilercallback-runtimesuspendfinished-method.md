---
title: ICorProfilerCallback::RuntimeSuspendFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c922ee4f986df22f213820b8aed60ea28a76377c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="6db22-102">ICorProfilerCallback::RuntimeSuspendFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="6db22-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="6db22-103">Benachrichtigt den Profiler, dass die Common Language Runtime Anhalten des Threads für alle Common Language Runtime abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="6db22-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6db22-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6db22-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6db22-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6db22-105">Remarks</span></span>  
 <span data-ttu-id="6db22-106">Alle Common Language Runtime-Threads, die in nicht verwaltetem Code sind dürfen weiter ausgeführt wird, bis sie versuchen, auf die Common Language Runtime erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="6db22-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="6db22-107">An diesem Punkt werden sie auch angehalten, bis die Laufzeit fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6db22-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="6db22-108">Dies gilt auch für neue Threads, die die Common Language Runtime eingeben.</span><span class="sxs-lookup"><span data-stu-id="6db22-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="6db22-109">Alle Threads in der Laufzeit sind entweder sofort angehalten, wenn sie bereits im Code parallelisiert sind oder sie aufgefordert werden, angehalten, wenn sie unterbrechbaren Code erreichen.</span><span class="sxs-lookup"><span data-stu-id="6db22-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="6db22-110">Die `RuntimeSuspendFinished` ist gewährleistet, dass Rückruf auftreten, auf dem gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="6db22-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6db22-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6db22-111">Requirements</span></span>  
 <span data-ttu-id="6db22-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6db22-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6db22-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6db22-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6db22-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6db22-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6db22-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6db22-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db22-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6db22-116">See Also</span></span>  
 [<span data-ttu-id="6db22-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6db22-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="6db22-118">RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="6db22-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
