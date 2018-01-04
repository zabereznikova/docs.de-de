---
title: ICorProfilerCallback4::ReJITCompilationStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 903db06089f7c68843b503c94483087ff9fce636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="92b18-102">ICorProfilerCallback4::ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="92b18-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="92b18-103">Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler eine Funktion neu kompiliert gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="92b18-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92b18-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92b18-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92b18-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="92b18-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="92b18-106">[in] Die ID der Funktion, die der JIT-Compiler gestartet wurde, neu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="92b18-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="92b18-107">[in] Die ID der Neukompilierung der neuen Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="92b18-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="92b18-108">[in] `true` um anzugeben, dass die Blockierung der Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten verursachen `false` um anzugeben, dass blockiert die Ausführung von der Laufzeit nicht beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="92b18-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="92b18-109">Ein Wert von `true` ist nicht auf die Common Language Runtime Schaden anrichten, jedoch können die Profilerstellungsergebnisse auswirken.</span><span class="sxs-lookup"><span data-stu-id="92b18-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92b18-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92b18-110">Remarks</span></span>  
 <span data-ttu-id="92b18-111">Es ist möglich, mehr als ein Spaltenpaar empfangen `ReJITCompilationStarted` und [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) Methodenaufrufe für jede Funktion aufgrund der Art und Weise der Common Language Runtime Klassenkonstruktoren Handles.</span><span class="sxs-lookup"><span data-stu-id="92b18-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="92b18-112">Z. B. die Common Language Runtime beginnt Methode A Methode neu kompiliert, aber der Klassenkonstruktor für Klasse B ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="92b18-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="92b18-113">Aus diesem Grund die Common Language Runtime den Konstruktor für die Klasse B kompiliert und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="92b18-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="92b18-114">Während der Konstruktor ausgeführt wird, macht es einen Aufruf der Methode ein, die bewirkt, dass die Methode A erneut kompiliert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="92b18-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="92b18-115">In diesem Szenario wird die erste Neukompilierung Methode A angehalten.</span><span class="sxs-lookup"><span data-stu-id="92b18-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="92b18-116">Beide jedoch so kompilieren Sie die Methode einer mit JIT-Neukompilierung-Ereignisse gemeldet, dass versucht.</span><span class="sxs-lookup"><span data-stu-id="92b18-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="92b18-117">Profiler müssen die Sequenz der JIT-Neukompilierung Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe durchführen.</span><span class="sxs-lookup"><span data-stu-id="92b18-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="92b18-118">Beispielsweise ruft Thread A `ReJITCompilationStarted`; jedoch vor dem Thread A ruft [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), Thread B ruft [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) mit dem Funktions-ID aus der `ReJITCompilationStarted` Rückruf für Thread A. Es scheint, dass die Funktions-ID noch nicht gültig ist da einen Aufruf von [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) wurde noch nicht empfangen vom Profiler.</span><span class="sxs-lookup"><span data-stu-id="92b18-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="92b18-119">Allerdings ist in diesem Fall die Funktions-ID gültig.</span><span class="sxs-lookup"><span data-stu-id="92b18-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92b18-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92b18-120">Requirements</span></span>  
 <span data-ttu-id="92b18-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92b18-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92b18-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92b18-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92b18-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92b18-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92b18-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92b18-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b18-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92b18-125">See Also</span></span>  
 [<span data-ttu-id="92b18-126">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92b18-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="92b18-127">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92b18-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="92b18-128">JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="92b18-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [<span data-ttu-id="92b18-129">ReJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="92b18-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
