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
ms.openlocfilehash: a3fb5c398b8ccd7caba0b005bcf03e64ecef4ba5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503249"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="c00f5-102">ICorProfilerCallback::RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="c00f5-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="c00f5-103">Benachrichtigt den Profiler, dass die Laufzeit das Eintreten der Lauf Zeit Unterbrechung abgebrochen hat.</span><span class="sxs-lookup"><span data-stu-id="c00f5-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c00f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c00f5-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c00f5-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c00f5-105">Remarks</span></span>  
 <span data-ttu-id="c00f5-106">Die Lauf Zeit Unterbrechung kann abgebrochen werden, wenn zwei Threads gleichzeitig versuchen, die Laufzeit anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="c00f5-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="c00f5-107">Entweder der Rückruf " [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendfinished-method.md) " oder der `RuntimeSuspendAborted` Rückruf erfolgt in einem einzelnen Thread nach einem [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) -Rückruf.</span><span class="sxs-lookup"><span data-stu-id="c00f5-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="c00f5-108">Der `RuntimeSuspendAborted` Rückruf ist garantiert im gleichen Thread wie der `RuntimeSuspendStarted` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="c00f5-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c00f5-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c00f5-109">Requirements</span></span>  
 <span data-ttu-id="c00f5-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c00f5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c00f5-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c00f5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c00f5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c00f5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c00f5-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c00f5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00f5-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c00f5-114">See also</span></span>

- [<span data-ttu-id="c00f5-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c00f5-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
