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
ms.openlocfilehash: 1c7b3c3ea5e976645c265b34327caa38ef6a28fd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226988"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="0104a-102">ICorProfilerCallback::RuntimeResumeFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="0104a-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="0104a-103">Benachrichtigt den Profiler, dass die Laufzeit verfügt über alle Common Language Runtime-Threads fortgesetzt und in den normalen Betrieb zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="0104a-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0104a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0104a-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0104a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0104a-105">Remarks</span></span>  
 <span data-ttu-id="0104a-106">Die `RuntimeResumeFinished` Rückruf ist nicht garantiert auf im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="0104a-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="0104a-107">Allerdings es ist garantiert auf im gleichen Thread wie der [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="0104a-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0104a-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0104a-108">Requirements</span></span>  
 <span data-ttu-id="0104a-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0104a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0104a-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0104a-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0104a-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0104a-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0104a-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="0104a-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0104a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0104a-113">See also</span></span>

- [<span data-ttu-id="0104a-114">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0104a-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
