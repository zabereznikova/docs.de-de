---
title: ICorProfilerCallback4-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: efcbc9adce9b5cfc39c5eb3e1649a35d458e99c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="50c20-102">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50c20-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="50c20-103">Stellt Rückrufmethoden, die die common Language Runtime (CLR) verwendet wird, um die Übermittlung von Informationen an den Profiler.</span><span class="sxs-lookup"><span data-stu-id="50c20-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50c20-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="50c20-104">Methods</span></span>  
  
|<span data-ttu-id="50c20-105">Methode</span><span class="sxs-lookup"><span data-stu-id="50c20-105">Method</span></span>|<span data-ttu-id="50c20-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50c20-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50c20-107">GetReJITParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="50c20-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="50c20-108">Ermöglicht die Codeprofiler, alternative codeerstellungskennzeichen für einen neuen Methodentext für die neu kompilierte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="50c20-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="50c20-109">MovedReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="50c20-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="50c20-110">Meldet das neue Layout von Objekten im Heap als Folge einer komprimierenden Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="50c20-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="50c20-111">ReJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="50c20-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="50c20-112">Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler die Neukompilierung einer Funktion abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="50c20-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="50c20-113">ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="50c20-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="50c20-114">Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler eine Funktion neu kompiliert gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="50c20-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="50c20-115">ReJITError-Methode</span><span class="sxs-lookup"><span data-stu-id="50c20-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="50c20-116">Meldet einen Fehler beim Verarbeiten einer Anforderung Recompile gefunden.</span><span class="sxs-lookup"><span data-stu-id="50c20-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="50c20-117">SurvivingReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="50c20-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="50c20-118">Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="50c20-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50c20-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50c20-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50c20-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50c20-120">Requirements</span></span>  
 <span data-ttu-id="50c20-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50c20-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50c20-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50c20-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50c20-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50c20-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50c20-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50c20-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c20-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50c20-125">See Also</span></span>  
 [<span data-ttu-id="50c20-126">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50c20-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="50c20-127">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="50c20-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="50c20-128">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50c20-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
