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
ms.openlocfilehash: 81d11c87c9bc970dd5b5c9010023610cea7c0e72
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865193"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="e0ace-102">ICorProfilerCallback4::ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="e0ace-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="e0ace-103">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="e0ace-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ace-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0ace-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0ace-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="e0ace-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e0ace-106">in Die ID der Funktion, für die der JIT-Compiler mit der erneuten Kompilierung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="e0ace-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="e0ace-107">in Die neukompilierungs-ID der neuen Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="e0ace-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="e0ace-108">[in] `true`, um anzugeben, dass eine Blockierung bewirken kann, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet. `false`, um anzugeben, dass die Blockierung sich nicht auf den Lauf Zeit Vorgang auswirkt.</span><span class="sxs-lookup"><span data-stu-id="e0ace-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="e0ace-109">Der Wert `true` schadet nicht der Laufzeit, kann jedoch die Profil Erstellungs Ergebnisse beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="e0ace-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0ace-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0ace-110">Remarks</span></span>  
 <span data-ttu-id="e0ace-111">Es ist möglich, mehr als ein paar von `ReJITCompilationStarted` und [rejitcompilationbeendete](icorprofilercallback4-rejitcompilationfinished-method.md) -Methodenaufrufe für jede Funktion zu erhalten, da die Laufzeit Klassenkonstruktoren verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e0ace-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="e0ace-112">Die Laufzeit startet z. B. die Neukompilierung der Methode A, der Klassenkonstruktor für Klasse B muss jedoch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e0ace-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="e0ace-113">Daher kompiliert die Runtime den Konstruktor für Klasse B neu und führt Sie aus.</span><span class="sxs-lookup"><span data-stu-id="e0ace-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="e0ace-114">Während der Konstruktor ausgeführt wird, ruft er die Methode a auf, die bewirkt, dass die Methode a erneut neu kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="e0ace-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="e0ace-115">In diesem Szenario wird die erste Neukompilierung der Methode A angehalten.</span><span class="sxs-lookup"><span data-stu-id="e0ace-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="e0ace-116">Beide Versuche, Methode A erneut zu kompilieren, werden jedoch mit JIT-neukompilierungs Ereignissen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e0ace-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="e0ace-117">Profiler müssen die Abfolge der JIT-neukompilierungs Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe erstellen.</span><span class="sxs-lookup"><span data-stu-id="e0ace-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="e0ace-118">Thread A ruft z. b. `ReJITCompilationStarted`; bevor Thread a [rejitcompilationbeendete](icorprofilercallback4-rejitcompilationfinished-method.md)aufruft, ruft Thread B jedoch [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID aus dem `ReJITCompilationStarted`-Rückruf für Thread A auf. Es kann vorkommen, dass die Funktions-ID noch nicht gültig ist, weil ein Aufruf von [rejitcompilationbeendeten](icorprofilercallback4-rejitcompilationfinished-method.md) noch nicht vom Profiler empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="e0ace-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="e0ace-119">In diesem Fall ist die Funktions-ID jedoch gültig.</span><span class="sxs-lookup"><span data-stu-id="e0ace-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0ace-120">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0ace-120">Requirements</span></span>  
 <span data-ttu-id="e0ace-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0ace-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0ace-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0ace-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0ace-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0ace-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0ace-124">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0ace-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ace-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0ace-125">See also</span></span>

- [<span data-ttu-id="e0ace-126">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0ace-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e0ace-127">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0ace-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="e0ace-128">JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="e0ace-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="e0ace-129">ReJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="e0ace-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
