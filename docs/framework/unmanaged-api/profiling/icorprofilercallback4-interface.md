---
title: ICorProfilerCallback4-Schnittstelle
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3eb1f46900199db65be5d14c56bfc0b6f55bf269
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598183"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="79251-102">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79251-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="79251-103">Stellt Rückrufmethoden bereit, die common Language Runtime (CLR) verwendet, um Informationen an den Profiler zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="79251-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="79251-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="79251-104">Methods</span></span>  
  
|<span data-ttu-id="79251-105">Methode</span><span class="sxs-lookup"><span data-stu-id="79251-105">Method</span></span>|<span data-ttu-id="79251-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79251-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="79251-107">GetReJITParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="79251-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="79251-108">Ermöglicht den Codeprofiler alternativen codeerstellungskennzeichen für einen neuen Methodentext für die neu kompilierte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79251-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="79251-109">MovedReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="79251-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="79251-110">Gibt das neue Layout der Objekte im Heap als Folge einer komprimierenden Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="79251-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="79251-111">ReJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="79251-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="79251-112">Benachrichtigt den Profiler, dass der just-in-Time-Compiler (JIT) die erneute Kompilierung einer Funktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="79251-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="79251-113">ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="79251-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="79251-114">Benachrichtigt den Profiler, dass der just-in-Time-Compiler (JIT) gestartet wurde, eine Funktion neu kompiliert.</span><span class="sxs-lookup"><span data-stu-id="79251-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="79251-115">ReJITError-Methode</span><span class="sxs-lookup"><span data-stu-id="79251-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="79251-116">Meldet Fehler beim Verarbeiten einer Anforderung für die Neukompilierung an.</span><span class="sxs-lookup"><span data-stu-id="79251-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="79251-117">SurvivingReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="79251-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="79251-118">Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="79251-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79251-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79251-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79251-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="79251-120">Requirements</span></span>  
 <span data-ttu-id="79251-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79251-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79251-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79251-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79251-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79251-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79251-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79251-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79251-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79251-125">See also</span></span>

- [<span data-ttu-id="79251-126">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79251-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="79251-127">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="79251-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="79251-128">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79251-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
