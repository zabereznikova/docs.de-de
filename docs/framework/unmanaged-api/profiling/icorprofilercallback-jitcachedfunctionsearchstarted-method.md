---
title: ICorProfilerCallback::JITCachedFunctionSearchStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d97b40412b6999000a601b72904a03edf2acd08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454033"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="8563e-102">ICorProfilerCallback::JITCachedFunctionSearchStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="8563e-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="8563e-103">Benachrichtigt den Profiler, dass eine Suche für eine Funktion, die zuvor mit der Native Image Generator (NGen.exe) kompiliert wurde, gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="8563e-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8563e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8563e-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8563e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8563e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8563e-106">[in] Die ID der Funktion für die Suche durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8563e-106">[in] The ID of the function for which the search is being performed.</span></span>  
  
 `pbUseCachedFunction`  
 <span data-ttu-id="8563e-107">[out] `true` , wenn das Ausführungsmodul die zwischengespeicherte Version einer Funktion (falls vorhanden) verwenden soll; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="8563e-107">[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="8563e-108">Wenn der Wert `false`, das Ausführungsmodul JIT-kompiliert der Funktion statt mit einer Version, die keine JIT-kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="8563e-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8563e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8563e-109">Remarks</span></span>  
 <span data-ttu-id="8563e-110">In .NET Framework, Version 2.0 die `JITCachedFunctionSearchStarted` und [ICorProfilerCallback:: JITCachedFunctionSearchFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) Rückrufe werden nicht für alle Funktionen in regulären NGen-Images gestellt.</span><span class="sxs-lookup"><span data-stu-id="8563e-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="8563e-111">Nur NGen-Images, die für ein Profil optimiert generiert Rückrufe für alle Funktionen in der Abbildung.</span><span class="sxs-lookup"><span data-stu-id="8563e-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="8563e-112">Aufgrund der zusätzlichen Verwaltungsaufwand, sollte ein Profiler jedoch Profiler optimiert NGen-Images anfordern, nur, wenn sie beabsichtigt, diese Rückrufe verwenden, um eine Funktion zu kompilierten just-in-Time (JIT) zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8563e-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="8563e-113">Andernfalls sollte der Profiler eine Strategie für die verzögerte verwenden, für das Sammeln von Informationen.</span><span class="sxs-lookup"><span data-stu-id="8563e-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="8563e-114">Profiler müssen Fälle unterstützen, in denen mehrere Threads einer Anwendung mit Profil dieselbe Methode gleichzeitig aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8563e-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="8563e-115">Beispielsweise ruft Thread A `JITCachedFunctionSearchStarted` und der Profiler reagiert durch Festlegen von *PbUseCachedFunction*auf "false", um JIT-Kompilierung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8563e-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="8563e-116">Anschließend ruft Thread A [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) und [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="8563e-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="8563e-117">Jetzt ruft thread B `JITCachedFunctionSearchStarted` für die gleiche Funktion.</span><span class="sxs-lookup"><span data-stu-id="8563e-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="8563e-118">Auch wenn der Profiler die Absicht JIT-kompiliert die Funktion angegeben wurde, empfängt der Profiler die zweite Rückruf, weil Thread B den Rückruf sendet, bevor Sie der Profiler an Thread A Aufruf reagiert wurde `JITCachedFunctionSearchStarted`.</span><span class="sxs-lookup"><span data-stu-id="8563e-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="8563e-119">Die Reihenfolge, in der die Threads Aufrufe ausführen, hängt davon ab, wie die Threads geplant werden.</span><span class="sxs-lookup"><span data-stu-id="8563e-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="8563e-120">Wenn der Profiler doppelte Rückrufe empfängt, muss er legen Sie den Wert verweist `pbUseCachedFunction` auf den gleichen Wert für alle doppelten Rückrufe.</span><span class="sxs-lookup"><span data-stu-id="8563e-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="8563e-121">Das heißt, wenn `JITCachedFunctionSearchStarted` mehrere Male aufgerufen wird, mit dem gleichen `functionId` Wert, der Profiler muss die gleiche jedes Mal reagieren.</span><span class="sxs-lookup"><span data-stu-id="8563e-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8563e-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8563e-122">Requirements</span></span>  
 <span data-ttu-id="8563e-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8563e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8563e-124">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8563e-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8563e-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8563e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8563e-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8563e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8563e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8563e-127">See Also</span></span>  
 [<span data-ttu-id="8563e-128">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8563e-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
