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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6bd3326aa5807bd7f2dd882991d211cbbf873067
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150409"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="2dee8-102">ICorProfilerCallback3::ProfilerAttachComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="2dee8-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="2dee8-103">Wird aufgerufen, von der common Language Runtime (CLR), um anzugeben, dass der Profiler jetzt aufrufen kann die [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) und [ICorProfilerInfo3:: EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) -Ausgleichsmethode.</span><span class="sxs-lookup"><span data-stu-id="2dee8-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dee8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2dee8-104">Syntax</span></span>  
  
```  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2dee8-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2dee8-105">Remarks</span></span>  
 <span data-ttu-id="2dee8-106">Die `ProfilerAttachComplete` -Rückruf wird ausgegeben, nachdem die [ICorProfilerCallback3:: InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2dee8-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="2dee8-107">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2dee8-107">It indicates the following:</span></span>  
  
-   <span data-ttu-id="2dee8-108">Die vom Profiler in `InitializeForAttach` angeforderten Rückrufe wurden aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2dee8-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
-   <span data-ttu-id="2dee8-109">Der Profiler kann jetzt einen Ausgleich für die zugeordneten IDs auch ohne Benachrichtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="2dee8-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="2dee8-110">Die CLR ignoriert den Rückgabewert von diesem Rückruf. </span><span class="sxs-lookup"><span data-stu-id="2dee8-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dee8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2dee8-111">Requirements</span></span>  
 <span data-ttu-id="2dee8-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2dee8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dee8-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2dee8-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2dee8-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dee8-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2dee8-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2dee8-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2dee8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dee8-116">See also</span></span>

- [<span data-ttu-id="2dee8-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2dee8-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2dee8-118">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2dee8-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="2dee8-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2dee8-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="2dee8-120">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="2dee8-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
