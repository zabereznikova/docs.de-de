---
title: ICorProfilerCallback::JITCompilationStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
ms.openlocfilehash: e05cb944ea4f3a9ca718dc22c6cd726b6a516ea9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866233"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="d0beb-102">ICorProfilerCallback::JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="d0beb-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="d0beb-103">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die Kompilierung einer Funktion gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="d0beb-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0beb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0beb-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0beb-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d0beb-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d0beb-106">in Die ID der Funktion, für die die Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="d0beb-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="d0beb-107">in Ein Wert, der angibt, ob die Blockierung den Lauf Zeitvorgang beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="d0beb-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="d0beb-108">Der Wert ist `true`, wenn eine Blockierung bewirkt, dass die Laufzeit darauf wartet, dass der aufrufenden Thread von diesem Rückruf zurückgegeben wird. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d0beb-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d0beb-109">Obwohl der Wert `true` die Laufzeit nicht beeinträchtigt, kann er die Profil Erstellungs Ergebnisse verzerren.</span><span class="sxs-lookup"><span data-stu-id="d0beb-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0beb-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d0beb-110">Remarks</span></span>  
 <span data-ttu-id="d0beb-111">Es ist möglich, mehr als ein paar von `JITCompilationStarted` und [ICorProfilerCallback:: jitcompilationabgeschlossene](icorprofilercallback-jitcompilationfinished-method.md) Aufrufe für jede Funktion zu erhalten, da die Laufzeit Klassenkonstruktoren verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d0beb-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="d0beb-112">Beispielsweise beginnt die Laufzeit mit der JIT-Kompilierungs Methode A, aber der Klassenkonstruktor für Klasse B muss ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d0beb-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="d0beb-113">Daher kompiliert die Runtime JIT den Konstruktor für Klasse B und führt Sie aus.</span><span class="sxs-lookup"><span data-stu-id="d0beb-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="d0beb-114">Während der Konstruktor ausgeführt wird, ruft er die Methode a auf, die bewirkt, dass die Methode a erneut JIT-kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="d0beb-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="d0beb-115">In diesem Szenario wird die erste JIT-Kompilierung der Methode A angehalten.</span><span class="sxs-lookup"><span data-stu-id="d0beb-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="d0beb-116">Beide Versuche der JIT-Kompilierungs Methode A werden jedoch mit JIT-Kompilierungs Ereignissen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="d0beb-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="d0beb-117">Wenn der Profiler Microsoft Intermediate Language (MSIL)-Code durch Aufrufen der [ICorProfilerInfo:: SetILFunctionBody-Methode durch Aufrufen der ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) -Methode ersetzen soll, `JITCompilationStarted` muss er den gleichen MSIL-Block für beide Ereignisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0beb-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="d0beb-118">Profiler müssen die Sequenz der JIT-Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe erstellen.</span><span class="sxs-lookup"><span data-stu-id="d0beb-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="d0beb-119">Thread A ruft z. b. `JITCompilationStarted`auf.</span><span class="sxs-lookup"><span data-stu-id="d0beb-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="d0beb-120">Bevor Thread a jedoch `JITCompilationFinished`aufruft, ruft Thread B [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID aus dem `JITCompilationStarted` Rückruf von Thread a auf.</span><span class="sxs-lookup"><span data-stu-id="d0beb-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="d0beb-121">Es kann vorkommen, dass die Funktions-ID noch nicht gültig ist, weil ein `JITCompilationFinished` noch nicht vom Profiler empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0beb-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="d0beb-122">In einem solchen Fall ist die Funktions-ID jedoch gültig.</span><span class="sxs-lookup"><span data-stu-id="d0beb-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0beb-123">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0beb-123">Requirements</span></span>  
 <span data-ttu-id="d0beb-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0beb-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0beb-125">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0beb-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0beb-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0beb-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0beb-127">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0beb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0beb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0beb-128">See also</span></span>

- [<span data-ttu-id="d0beb-129">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0beb-129">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d0beb-130">JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="d0beb-130">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
