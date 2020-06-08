---
title: ICorProfilerCallback3::ProfilerAttachComplete-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
ms.openlocfilehash: bcc938ff9322fca4f45366fdc695e0c3901484b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499661"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="94d20-102">ICorProfilerCallback3::ProfilerAttachComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="94d20-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="94d20-103">Wird von der Common Language Runtime (CLR) aufgerufen, um anzugeben, dass der Profiler jetzt die Catch-up-Methoden [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) und [ICorProfilerInfo3:: EnumModules](icorprofilerinfo3-enummodules-method.md) aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="94d20-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94d20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94d20-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="94d20-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="94d20-105">Remarks</span></span>  
 <span data-ttu-id="94d20-106">Der `ProfilerAttachComplete` Rückruf wird ausgegeben, nachdem die [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) -Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="94d20-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="94d20-107">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="94d20-107">It indicates the following:</span></span>  
  
- <span data-ttu-id="94d20-108">Die vom Profiler in `InitializeForAttach` angeforderten Rückrufe wurden aktiviert.</span><span class="sxs-lookup"><span data-stu-id="94d20-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
- <span data-ttu-id="94d20-109">Der Profiler kann jetzt einen Ausgleich für die zugeordneten IDs auch ohne Benachrichtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="94d20-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="94d20-110">Die CLR ignoriert den Rückgabewert von diesem Rückruf. </span><span class="sxs-lookup"><span data-stu-id="94d20-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94d20-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="94d20-111">Requirements</span></span>  
 <span data-ttu-id="94d20-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94d20-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94d20-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="94d20-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="94d20-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94d20-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94d20-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94d20-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94d20-116">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="94d20-116">See also</span></span>

- [<span data-ttu-id="94d20-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94d20-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="94d20-118">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94d20-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="94d20-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="94d20-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="94d20-120">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="94d20-120">Profiling</span></span>](index.md)
