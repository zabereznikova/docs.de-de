---
title: ICorProfilerCallback::JITCompilationStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a12ae3e33d5553ed99a5a26b8fc872f0d07de81e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="e2448-102">ICorProfilerCallback::JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="e2448-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="e2448-103">Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler zum Kompilieren einer funktionsrückgabewerts gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e2448-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2448-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2448-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2448-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2448-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e2448-106">[in] Die ID der Funktion für die die Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e2448-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="e2448-107">[in] Ein Wert, der angibt, an den Profiler an, ob blockierende wird die Funktion der Laufzeit beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="e2448-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="e2448-108">Der Wert ist `true` Wenn blockiert die Common Language Runtime von diesem Rückruf; Zurückgeben der aufrufende Thread warten führen kann, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="e2448-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="e2448-109">Obwohl ein Wert von `true` wird nicht auf die Common Language Runtime Schaden anrichten, sie können die Profilerstellungsergebnisse verzerren.</span><span class="sxs-lookup"><span data-stu-id="e2448-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2448-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2448-110">Remarks</span></span>  
 <span data-ttu-id="e2448-111">Es ist möglich, mehr als ein Spaltenpaar empfangen `JITCompilationStarted` und [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) Ruft für jede Funktion aufgrund der Art und Weise die Laufzeit Klassenkonstruktoren Handles.</span><span class="sxs-lookup"><span data-stu-id="e2448-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="e2448-112">Z. B. die Common Language Runtime beginnt JIT-kompiliert Methode A, aber den Konstruktor der Klasse für die Klasse B ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="e2448-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="e2448-113">Aus diesem Grund die Laufzeit-JIT-kompiliert der Konstruktor für die Klasse B und wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e2448-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="e2448-114">Während der Konstruktor ausgeführt wird, wird einen Aufruf der Methode ein, wodurch ein JIT-kompilierte erneut werden-Methode wird vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="e2448-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="e2448-115">In diesem Szenario wird die erste JIT-Kompilierung der Methode A angehalten.</span><span class="sxs-lookup"><span data-stu-id="e2448-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="e2448-116">Allerdings werden beide Versuche einer JIT-Kompilierung Methode A mit JIT-Kompilierung Ereignisse gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e2448-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="e2448-117">Wenn der Profiler mit der Microsoft intermediate Language (MSIL)-Code für die Methode A Ersetzen Sie durch Aufrufen der [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) -Methode, sie müssen dazu für beide `JITCompilationStarted` Ereignisse, aber sie können die gleichen MSIL-Block für beide.</span><span class="sxs-lookup"><span data-stu-id="e2448-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="e2448-118">Profiler müssen die Sequenz von JIT-Rückrufen in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe durchführen.</span><span class="sxs-lookup"><span data-stu-id="e2448-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="e2448-119">Beispielsweise ruft Thread A `JITCompilationStarted`.</span><span class="sxs-lookup"><span data-stu-id="e2448-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="e2448-120">Jedoch vor dem Thread A ruft `JITCompilationFinished`, Thread B ruft [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) mit dem Funktions-ID von Thread A `JITCompilationStarted` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="e2448-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="e2448-121">Es scheint, dass die Funktions-ID noch nicht gültig ist da einen Aufruf von `JITCompilationFinished` wurde noch nicht empfangen vom Profiler.</span><span class="sxs-lookup"><span data-stu-id="e2448-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="e2448-122">In einem Fall wie diesem ist jedoch die Funktions-ID gültig.</span><span class="sxs-lookup"><span data-stu-id="e2448-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2448-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2448-123">Requirements</span></span>  
 <span data-ttu-id="e2448-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2448-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2448-125">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e2448-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e2448-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2448-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2448-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2448-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2448-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2448-128">See Also</span></span>  
 [<span data-ttu-id="e2448-129">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2448-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="e2448-130">JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="e2448-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
