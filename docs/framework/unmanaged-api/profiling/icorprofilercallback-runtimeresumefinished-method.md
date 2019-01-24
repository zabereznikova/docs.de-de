---
title: ICorProfilerCallback::RuntimeResumeFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2cf80c7e02d706b0b00ea87aa62986107cdd6a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689743"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="2747f-102">ICorProfilerCallback::RuntimeResumeFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="2747f-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="2747f-103">Benachrichtigt den Profiler, dass die Laufzeit verfügt über alle Common Language Runtime-Threads fortgesetzt und in den normalen Betrieb zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="2747f-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2747f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2747f-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2747f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2747f-105">Remarks</span></span>  
 <span data-ttu-id="2747f-106">Die `RuntimeResumeFinished` Rückruf ist nicht garantiert auf im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="2747f-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="2747f-107">Allerdings es ist garantiert auf im gleichen Thread wie der [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="2747f-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2747f-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2747f-108">Requirements</span></span>  
 <span data-ttu-id="2747f-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2747f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2747f-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2747f-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2747f-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2747f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2747f-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2747f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2747f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2747f-113">See also</span></span>
- [<span data-ttu-id="2747f-114">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2747f-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
