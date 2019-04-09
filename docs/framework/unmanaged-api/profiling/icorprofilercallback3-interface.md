---
title: ICorProfilerCallback3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66e6a67ce022365fa8c9e1005dfecbe4b23abd10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158380"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="ff86e-102">ICorProfilerCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff86e-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="ff86e-103">Stellt Rückrufmethoden bereit, die common Language Runtime (CLR) verwendet wird, für die Kommunikation, Anfügen und Trennen von Zustandsinformationen an den Profiler an.</span><span class="sxs-lookup"><span data-stu-id="ff86e-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff86e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ff86e-104">Methods</span></span>  
  
|<span data-ttu-id="ff86e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ff86e-105">Method</span></span>|<span data-ttu-id="ff86e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff86e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff86e-107">InitializeForAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="ff86e-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="ff86e-108">Wird aufgerufen, von der CLR, die der Profiler das Initialisieren seines Zustands nach einem Anfügevorgang zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ff86e-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="ff86e-109">ProfilerAttachComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="ff86e-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="ff86e-110">Wird aufgerufen, von der CLR, um anzugeben, dass der Profiler jetzt die-Ausgleichsmethode aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="ff86e-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="ff86e-111">ProfilerDetachSucceeded-Methode</span><span class="sxs-lookup"><span data-stu-id="ff86e-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="ff86e-112">Benachrichtigt den Profiler, dass die CLR (Common Language Runtime) die Profiler-DLL entladen wird.</span><span class="sxs-lookup"><span data-stu-id="ff86e-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff86e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff86e-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff86e-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff86e-114">Requirements</span></span>  
 <span data-ttu-id="ff86e-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff86e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff86e-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff86e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff86e-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff86e-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ff86e-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ff86e-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ff86e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff86e-119">See also</span></span>

- [<span data-ttu-id="ff86e-120">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ff86e-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ff86e-121">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff86e-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="ff86e-122">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff86e-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="ff86e-123">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff86e-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
