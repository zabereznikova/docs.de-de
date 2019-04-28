---
title: ICorProfilerCallback4::ReJITCompilationStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8f2ada73686dfbe5629e21cfc6468becbd4ccc5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597361"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="30d69-102">ICorProfilerCallback4::ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="30d69-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="30d69-103">Benachrichtigt den Profiler, dass der just-in-Time-Compiler (JIT) gestartet wurde, eine Funktion neu kompiliert.</span><span class="sxs-lookup"><span data-stu-id="30d69-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30d69-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30d69-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30d69-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="30d69-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="30d69-106">[in] Die ID der Funktion, die der JIT-Compiler gestartet wurde, neu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="30d69-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="30d69-107">[in] Die Neukompilierung-ID der neuen Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="30d69-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="30d69-108">[in] `true` um anzugeben, dass blockiert die Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten verursachen `false` um anzugeben, dass die Blockierung der Vorgang der Laufzeit nicht beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="30d69-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="30d69-109">Der Wert `true` kompatibilitätsgesichtspunkten sich nicht auf die Laufzeit nimmt allerdings die Ergebnisse der profilerstellung.</span><span class="sxs-lookup"><span data-stu-id="30d69-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30d69-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30d69-110">Remarks</span></span>  
 <span data-ttu-id="30d69-111">Es ist möglich, erhalten mehr als ein Spaltenpaar `ReJITCompilationStarted` und [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) Methodenaufrufe für jede Funktion aufgrund der Art und Weise der Common Language Runtime behandelt-Klasse, Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="30d69-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="30d69-112">Beispielsweise Starten der Laufzeit Methode A Methode neu kompiliert, aber der Klassenkonstruktor für Klasse B ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="30d69-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="30d69-113">Aus diesem Grund die Laufzeit den Konstruktor für die Klasse B kompiliert und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="30d69-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="30d69-114">Während der Konstruktor ausgeführt wird, ist es einen Aufruf der Methode ein, die bewirkt, dass die Methode A erneut kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="30d69-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="30d69-115">In diesem Szenario wird die erste Neukompilierung der Methode ein angehalten.</span><span class="sxs-lookup"><span data-stu-id="30d69-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="30d69-116">Allerdings beide versucht, Kompilieren die Methode, die einer mit JIT-Neukompilierung-Ereignisse gemeldet.</span><span class="sxs-lookup"><span data-stu-id="30d69-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="30d69-117">Profiler müssen die Abfolge der JIT-Neukompilierung Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe durchführen.</span><span class="sxs-lookup"><span data-stu-id="30d69-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="30d69-118">Thread A ruft z. B. `ReJITCompilationStarted`; allerdings vor dem Thread A ruft [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), Thread B ruft [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID von der `ReJITCompilationStarted` Rückruf für den Thread A. Sie scheinen, dass die Funktions-ID noch nicht gültig ist da einen Aufruf von [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) hatte noch nicht empfangen durch den Profiler.</span><span class="sxs-lookup"><span data-stu-id="30d69-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="30d69-119">In diesem Fall jedoch ist die Funktions-ID gültig.</span><span class="sxs-lookup"><span data-stu-id="30d69-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30d69-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30d69-120">Requirements</span></span>  
 <span data-ttu-id="30d69-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30d69-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30d69-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30d69-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30d69-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30d69-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30d69-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30d69-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d69-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30d69-125">See also</span></span>

- [<span data-ttu-id="30d69-126">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30d69-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="30d69-127">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30d69-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="30d69-128">JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="30d69-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="30d69-129">ReJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="30d69-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
