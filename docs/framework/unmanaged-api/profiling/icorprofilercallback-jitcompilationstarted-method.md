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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b75eebd8d9bf439a0317521a61c06ece3745be0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787919"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="5e8c8-102">ICorProfilerCallback::JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="5e8c8-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="5e8c8-103">Benachrichtigt den Profiler, dass der just-in-Time-Compiler (JIT) gestartet wurde, mit der Kompilierung einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e8c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e8c8-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e8c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e8c8-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="5e8c8-106">[in] Die ID der Funktion für die die Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="5e8c8-107">[in] Ein Wert, der angibt, an den Profiler an, ob blockierende wirkt sich auf den Vorgang der Runtime.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="5e8c8-108">Der Wert ist `true` Wenn Blockierungen der Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten führen kann, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="5e8c8-109">Obwohl ein Wert von `true` wird die Runtime nicht beschädigen, können sie die Ergebnisse der profilerstellung verzerren.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e8c8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e8c8-110">Remarks</span></span>  
 <span data-ttu-id="5e8c8-111">Es ist möglich, erhalten mehr als ein Spaltenpaar `JITCompilationStarted` und [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) Ruft für jede Funktion aufgrund der Art und Weise die Laufzeit behandelt-Klasse, Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="5e8c8-112">Z. B. die Laufzeit startet JIT-Kompilieren-Methode ein, aber der Klassenkonstruktor für Klasse B ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="5e8c8-113">Aus diesem Grund die Laufzeit-JIT-kompiliert wird der Konstruktor für die Klasse B und wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="5e8c8-114">Während der Konstruktor ausgeführt wird, ist es einen Aufruf der Methode A, die Methode ein JIT-kompilierten erneut werden kann.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="5e8c8-115">In diesem Szenario wird die erste JIT-Kompilierung der Methode ein angehalten.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="5e8c8-116">Allerdings werden beide versucht, ein JIT-Kompilieren-Methode mit JIT-Kompilierung Ereignisse gemeldet.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="5e8c8-117">Wenn der Profiler Microsoft intermediate Language (MSIL)-Code für die Methode A durch den Aufruf zu ersetzen ist die [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) -Methode, sie müssen dies für beide `JITCompilationStarted` Ereignisse, aber sie können den gleichen MSIL-Block für beides an.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="5e8c8-118">Profiler müssen die Abfolge der JIT-Rückrufe in Fällen unterstützen, in denen zwei Threads gleichzeitig Rückrufe durchführen.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="5e8c8-119">Thread A ruft z. B. `JITCompilationStarted`.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="5e8c8-120">Jedoch vor dem Thread A ruft `JITCompilationFinished`, Thread B ruft [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) mit der Funktions-ID von Thread A `JITCompilationStarted` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="5e8c8-121">Sie scheinen, dass die Funktions-ID noch nicht gültig ist da einen Aufruf von `JITCompilationFinished` hatte noch nicht empfangen durch den Profiler.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="5e8c8-122">In einem Fall wie diesem ist jedoch die Funktions-ID gültig.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e8c8-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e8c8-123">Requirements</span></span>  
 <span data-ttu-id="5e8c8-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e8c8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e8c8-125">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e8c8-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e8c8-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e8c8-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e8c8-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e8c8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e8c8-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e8c8-128">See also</span></span>

- [<span data-ttu-id="5e8c8-129">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e8c8-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5e8c8-130">JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="5e8c8-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
