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
ms.openlocfilehash: 8168f6f1079ec34b9fb53a485da0f32175446719
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865427"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="7fd05-102">ICorProfilerCallback3::ProfilerAttachComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="7fd05-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="7fd05-103">Wird von der Common Language Runtime (CLR) aufgerufen, um anzugeben, dass der Profiler jetzt die Catch-up-Methoden [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) und [ICorProfilerInfo3:: EnumModules](icorprofilerinfo3-enummodules-method.md) aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="7fd05-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fd05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fd05-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7fd05-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7fd05-105">Remarks</span></span>  
 <span data-ttu-id="7fd05-106">Der `ProfilerAttachComplete`-Rückruf wird ausgegeben, nachdem die [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) -Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="7fd05-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="7fd05-107">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7fd05-107">It indicates the following:</span></span>  
  
- <span data-ttu-id="7fd05-108">Die vom Profiler in `InitializeForAttach` angeforderten Rückrufe wurden aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7fd05-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
- <span data-ttu-id="7fd05-109">Der Profiler kann jetzt einen Ausgleich für die zugeordneten IDs auch ohne Benachrichtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="7fd05-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="7fd05-110">Die CLR ignoriert den Rückgabewert von diesem Rückruf.</span><span class="sxs-lookup"><span data-stu-id="7fd05-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fd05-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7fd05-111">Requirements</span></span>  
 <span data-ttu-id="7fd05-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fd05-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fd05-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7fd05-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7fd05-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fd05-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fd05-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fd05-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd05-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fd05-116">See also</span></span>

- [<span data-ttu-id="7fd05-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fd05-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7fd05-118">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fd05-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="7fd05-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7fd05-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="7fd05-120">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="7fd05-120">Profiling</span></span>](index.md)
