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
ms.openlocfilehash: 17dd0cc8d26c328bf6128795f02d751b7ae9e471
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717236"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="6a846-102">ICorProfilerCallback::RuntimeSuspendFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="6a846-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>

<span data-ttu-id="6a846-103">Benachrichtigt den Profiler, dass die Laufzeit alle Laufzeitthreads angehalten hat.</span><span class="sxs-lookup"><span data-stu-id="6a846-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a846-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a846-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6a846-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a846-105">Remarks</span></span>  

 <span data-ttu-id="6a846-106">Alle Laufzeitthreads in nicht verwaltetem Code können weiter ausgeführt werden, bis Sie versuchen, die Laufzeit erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="6a846-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="6a846-107">An diesem Punkt werden Sie auch angehalten, bis die Laufzeit fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6a846-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="6a846-108">Dies gilt auch für neue Threads, die zur Laufzeit gelangen.</span><span class="sxs-lookup"><span data-stu-id="6a846-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="6a846-109">Alle Threads in der Laufzeit werden entweder sofort angehalten, wenn Sie sich bereits in interruptebarem Code befinden, oder Sie werden angehalten, wenn Sie unter brechbaren Code erreichen.</span><span class="sxs-lookup"><span data-stu-id="6a846-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="6a846-110">Der `RuntimeSuspendFinished` Rückruf ist garantiert im gleichen Thread wie der [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) -Rückruf.</span><span class="sxs-lookup"><span data-stu-id="6a846-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a846-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6a846-111">Requirements</span></span>  

 <span data-ttu-id="6a846-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a846-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a846-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a846-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a846-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a846-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a846-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a846-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a846-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a846-116">See also</span></span>

- [<span data-ttu-id="6a846-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a846-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6a846-118">RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="6a846-118">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
