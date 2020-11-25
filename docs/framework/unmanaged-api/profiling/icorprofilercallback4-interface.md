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
ms.openlocfilehash: 942ee8234b79c6579acc009960f4571801fc3185
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730291"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="04206-102">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04206-102">ICorProfilerCallback4 Interface</span></span>

<span data-ttu-id="04206-103">Stellt Rückruf Methoden bereit, die vom Common Language Runtime (CLR) zum Übermitteln von Informationen an den Profiler verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04206-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04206-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="04206-104">Methods</span></span>  
  
|<span data-ttu-id="04206-105">Methode</span><span class="sxs-lookup"><span data-stu-id="04206-105">Method</span></span>|<span data-ttu-id="04206-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04206-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04206-107">GetReJITParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="04206-107">GetReJITParameters Method</span></span>](icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="04206-108">Ermöglicht dem Codeprofiler das Festlegen von Flags für die Alternative Codegenerierung für einen neuen neu kompilierten Methoden Text.</span><span class="sxs-lookup"><span data-stu-id="04206-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="04206-109">MovedReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="04206-109">MovedReferences2 Method</span></span>](icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="04206-110">Meldet das neue Layout von Objekten im Heap als Ergebnis einer komprimierenden Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="04206-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="04206-111">ReJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="04206-111">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="04206-112">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="04206-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="04206-113">ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="04206-113">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="04206-114">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="04206-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="04206-115">ReJITError-Methode</span><span class="sxs-lookup"><span data-stu-id="04206-115">ReJITError Method</span></span>](icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="04206-116">Meldet einen Fehler, der beim Verarbeiten einer Anforderung zum erneuten Kompilieren aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="04206-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="04206-117">SurvivingReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="04206-117">SurvivingReferences2 Method</span></span>](icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="04206-118">Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="04206-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04206-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="04206-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04206-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="04206-120">Requirements</span></span>  

 <span data-ttu-id="04206-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04206-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04206-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04206-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04206-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04206-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04206-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04206-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04206-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04206-125">See also</span></span>

- [<span data-ttu-id="04206-126">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04206-126">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="04206-127">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="04206-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="04206-128">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04206-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
