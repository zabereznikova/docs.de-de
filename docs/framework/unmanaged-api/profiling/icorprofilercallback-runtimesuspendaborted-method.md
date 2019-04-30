---
title: ICorProfilerCallback::RuntimeSuspendAborted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9aaf7325b8e7e65aa98904513cc7efe94e35087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041807"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="6a301-102">ICorProfilerCallback::RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="6a301-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="6a301-103">Benachrichtigt den Profiler, dass die Runtime die Runtime-Unterbrechung abgebrochen wurde, die aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6a301-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a301-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a301-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6a301-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a301-105">Remarks</span></span>  
 <span data-ttu-id="6a301-106">Die Runtime-Unterbrechung kann abgebrochen werden, wenn zwei Threads gleichzeitig versuchen, die Laufzeit angehalten.</span><span class="sxs-lookup"><span data-stu-id="6a301-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="6a301-107">Entweder die [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) Rückruf oder `RuntimeSuspendAborted` Rückruf erfolgt in einer einzelnen Thread nach einem [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="6a301-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="6a301-108">Die `RuntimeSuspendAborted` Rückruf wird garantiert auf im gleichen Thread wie der `RuntimeSuspendStarted` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="6a301-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a301-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a301-109">Requirements</span></span>  
 <span data-ttu-id="6a301-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a301-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a301-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a301-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a301-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a301-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a301-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a301-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a301-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a301-114">See also</span></span>

- [<span data-ttu-id="6a301-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a301-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
