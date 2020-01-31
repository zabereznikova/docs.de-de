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
ms.openlocfilehash: 01989812b85cf98aedfd8855bee7b2dfbfd375f4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790064"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="10fe9-102">ICorProfilerCallback::JITCachedFunctionSearchStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="10fe9-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="10fe9-103">Benachrichtigt den Profiler, dass eine Suche für eine Funktion gestartet wurde, die zuvor mit dem Native Image Generator (Ngen. exe) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="10fe9-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10fe9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10fe9-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10fe9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="10fe9-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="10fe9-106">\[in] die ID der Funktion, für die die Suche ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="10fe9-106">\[in] The ID of the function for which the search is being performed.</span></span>

- `pbUseCachedFunction`

  <span data-ttu-id="10fe9-107">\[out] `true`, wenn die Ausführungs-Engine die zwischengespeicherte Version einer Funktion (falls verfügbar) verwenden soll. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="10fe9-107">\[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="10fe9-108">Wenn der Wert `false`ist, kompiliert die Ausführungs-Engine die Funktion, anstatt eine Version zu verwenden, die nicht JIT-kompiliert ist.</span><span class="sxs-lookup"><span data-stu-id="10fe9-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="10fe9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10fe9-109">Remarks</span></span>  
 <span data-ttu-id="10fe9-110">In der .NET Framework Version 2,0 werden die Methoden Rückrufe `JITCachedFunctionSearchStarted` und [ICorProfilerCallback:: jitcachedfunctionsearchfertige](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) nicht für alle Funktionen in regulären NGen-Images erstellt.</span><span class="sxs-lookup"><span data-stu-id="10fe9-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="10fe9-111">Nur NGen-Images, die für ein Profil optimiert werden, generieren Rückrufe für alle Funktionen im Image.</span><span class="sxs-lookup"><span data-stu-id="10fe9-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="10fe9-112">Aufgrund des zusätzlichen Aufwands sollte ein Profiler jedoch nur Profiler-optimierte NGen-Images anfordern, wenn er diese Rückrufe verwenden soll, um zu erzwingen, dass eine Funktion Just-in-time (JIT) kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="10fe9-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="10fe9-113">Andernfalls sollte der Profiler eine verzögerte Strategie zum Sammeln von Funktions Informationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="10fe9-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="10fe9-114">Profiler müssen Fälle unterstützen, in denen mehrere Threads einer profilierten Anwendung dieselbe Methode gleichzeitig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="10fe9-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="10fe9-115">Thread A ruft z. b. `JITCachedFunctionSearchStarted` auf, und der Profiler antwortet durch Festlegen von *pbUseCachedFunction*auf false, um die JIT-Kompilierung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="10fe9-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="10fe9-116">Thread A ruft dann [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) und [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)auf.</span><span class="sxs-lookup"><span data-stu-id="10fe9-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="10fe9-117">Nun ruft Thread B `JITCachedFunctionSearchStarted` für dieselbe Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="10fe9-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="10fe9-118">Obwohl der Profiler seine Absicht zur JIT-Kompilierung der Funktion angegeben hat, empfängt der Profiler den zweiten Rückruf, da Thread B den Rückruf sendet, bevor der Profiler auf den `JITCachedFunctionSearchStarted`von Thread A geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="10fe9-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="10fe9-119">Die Reihenfolge, in der die Threads Aufrufe ausführen, hängt davon ab, wie die Threads geplant werden.</span><span class="sxs-lookup"><span data-stu-id="10fe9-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="10fe9-120">Wenn der Profiler doppelte Rückrufe empfängt, muss der Wert, auf den durch `pbUseCachedFunction` verwiesen wird, auf denselben Wert für alle doppelten Rückrufe festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="10fe9-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="10fe9-121">Das heißt, wenn `JITCachedFunctionSearchStarted` mehrmals mit dem gleichen `functionId` Wert aufgerufen wird, muss der Profiler jedes Mal gleich reagieren.</span><span class="sxs-lookup"><span data-stu-id="10fe9-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10fe9-122">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10fe9-122">Requirements</span></span>  
 <span data-ttu-id="10fe9-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10fe9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10fe9-124">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="10fe9-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="10fe9-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10fe9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10fe9-126">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10fe9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10fe9-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10fe9-127">See also</span></span>

- [<span data-ttu-id="10fe9-128">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10fe9-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
