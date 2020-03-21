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
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177082"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="c4199-102">ICorProfilerCallback4::ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="c4199-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="c4199-103">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) mit der Neukompilierung einer Funktion begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="c4199-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4199-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4199-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4199-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4199-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c4199-106">[in] Die ID der Funktion, mit deren Neukompilierung der JIT-Compiler begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="c4199-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="c4199-107">[in] Die Neukompilierungs-ID der neuen Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="c4199-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="c4199-108">[in] `true` , um anzugeben, dass das Blockieren dazu führen kann, dass die Laufzeit darauf wartet, dass der aufrufende Thread von diesem Rückruf zurückkehrt. `false` , um anzugeben, dass die Blockierung den Betrieb der Laufzeit nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="c4199-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="c4199-109">Ein Wert `true` von schadet der Laufzeit nicht, kann sich aber auf die Profilerstellungsergebnisse auswirken.</span><span class="sxs-lookup"><span data-stu-id="c4199-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4199-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c4199-110">Remarks</span></span>  
 <span data-ttu-id="c4199-111">Es ist möglich, mehr als `ReJITCompilationStarted` ein Paar von und [ReJITCompilationFinished-Methodenaufrufe](icorprofilercallback4-rejitcompilationfinished-method.md) für jede Funktion zu empfangen, da die Laufzeit Klassenkonstruktoren verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c4199-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="c4199-112">Beispielsweise beginnt die Laufzeit mit der Neukompilierung von Methode A, aber der Klassenkonstruktor für Klasse B muss ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c4199-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="c4199-113">Daher kompiliert die Laufzeit den Konstruktor für Klasse B neu und führt ihn aus.</span><span class="sxs-lookup"><span data-stu-id="c4199-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="c4199-114">Während der Konstruktor ausgeführt wird, wird die Methode A aufaufruft, wodurch Methode A erneut kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="c4199-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="c4199-115">In diesem Szenario wird die erste Neukompilierung von Methode A angehalten.</span><span class="sxs-lookup"><span data-stu-id="c4199-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="c4199-116">Beide Versuche, Methode A neu zu kompilieren, werden jedoch mit JIT-Neukompilierungsereignissen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="c4199-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="c4199-117">Profiler müssen die Reihenfolge der JIT-Neukompilierungsrückrufe unterstützen, wenn zwei Threads gleichzeitig Rückrufe ausführen.</span><span class="sxs-lookup"><span data-stu-id="c4199-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="c4199-118">Thread A ruft `ReJITCompilationStarted`z. B. auf; Vor dem Aufruf von [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)ruft Thread B jedoch [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID aus dem `ReJITCompilationStarted` Rückruf für Thread A auf. Es könnte den Anschein haben, dass die Funktions-ID noch nicht gültig sein sollte, da ein Aufruf von [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) noch nicht vom Profiler empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="c4199-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="c4199-119">In diesem Fall ist jedoch die Funktions-ID gültig.</span><span class="sxs-lookup"><span data-stu-id="c4199-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4199-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4199-120">Requirements</span></span>  
 <span data-ttu-id="c4199-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4199-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4199-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4199-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4199-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4199-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4199-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4199-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4199-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4199-125">See also</span></span>

- [<span data-ttu-id="c4199-126">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4199-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c4199-127">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4199-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="c4199-128">JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="c4199-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="c4199-129">ReJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="c4199-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
