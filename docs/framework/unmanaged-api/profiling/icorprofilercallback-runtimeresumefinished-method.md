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
ms.openlocfilehash: 8bc97bb0d36a046353587a95aa2b79eff12866e0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499882"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="03e6e-102">ICorProfilerCallback::RuntimeResumeFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="03e6e-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="03e6e-103">Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads fortgesetzt hat und an den normalen Vorgang zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="03e6e-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03e6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03e6e-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="03e6e-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="03e6e-105">Remarks</span></span>  
 <span data-ttu-id="03e6e-106">`RuntimeResumeFinished`Es ist nicht garantiert, dass der Rückruf im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) -Rückruf erfolgt.</span><span class="sxs-lookup"><span data-stu-id="03e6e-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="03e6e-107">Es ist jedoch garantiert, dass Sie im gleichen Thread wie der [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) -Rückruf auftritt.</span><span class="sxs-lookup"><span data-stu-id="03e6e-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03e6e-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="03e6e-108">Requirements</span></span>  
 <span data-ttu-id="03e6e-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03e6e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03e6e-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="03e6e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="03e6e-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03e6e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03e6e-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03e6e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03e6e-113">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="03e6e-113">See also</span></span>

- [<span data-ttu-id="03e6e-114">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="03e6e-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
