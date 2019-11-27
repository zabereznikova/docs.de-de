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
ms.openlocfilehash: 81c26214762fba1cac43e42adc1ee9909759972f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430314"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="882ae-102">ICorProfilerCallback::RuntimeResumeFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="882ae-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="882ae-103">Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads fortgesetzt hat und an den normalen Vorgang zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="882ae-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="882ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="882ae-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="882ae-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="882ae-105">Remarks</span></span>  
 <span data-ttu-id="882ae-106">Es ist nicht garantiert, dass der `RuntimeResumeFinished` Rückruf im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) -Rückruf erfolgt.</span><span class="sxs-lookup"><span data-stu-id="882ae-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="882ae-107">Es ist jedoch garantiert, dass Sie im gleichen Thread wie der [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) -Rückruf auftritt.</span><span class="sxs-lookup"><span data-stu-id="882ae-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="882ae-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="882ae-108">Requirements</span></span>  
 <span data-ttu-id="882ae-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="882ae-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="882ae-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="882ae-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="882ae-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="882ae-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="882ae-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="882ae-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="882ae-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="882ae-113">See also</span></span>

- [<span data-ttu-id="882ae-114">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="882ae-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
