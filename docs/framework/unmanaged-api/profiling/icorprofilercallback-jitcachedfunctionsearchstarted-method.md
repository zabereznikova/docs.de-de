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
ms.openlocfilehash: 938da4e3b7cc45c24dcac872ab504755116197a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684030"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="7a31a-102">ICorProfilerCallback::JITCachedFunctionSearchStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="7a31a-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>

<span data-ttu-id="7a31a-103">Benachrichtigt den Profiler, dass eine Suche für eine Funktion gestartet wurde, die zuvor mit dem Native Image Generator (NGen.exe) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="7a31a-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a31a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a31a-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a31a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a31a-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="7a31a-106">\[in] die ID der Funktion, für die die Suche ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7a31a-106">\[in] The ID of the function for which the search is being performed.</span></span>

- `pbUseCachedFunction`

  <span data-ttu-id="7a31a-107">\[out] `true` , wenn die Ausführungs-Engine die zwischengespeicherte Version einer Funktion (falls verfügbar) verwenden soll, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="7a31a-107">\[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="7a31a-108">Wenn der Wert ist `false` , kompiliert die Ausführungs-Engine die Funktion, anstatt eine Version zu verwenden, die nicht JIT-kompiliert ist.</span><span class="sxs-lookup"><span data-stu-id="7a31a-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="7a31a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a31a-109">Remarks</span></span>  

 <span data-ttu-id="7a31a-110">In der .NET Framework Version 2,0 werden die `JITCachedFunctionSearchStarted` Methoden Rückrufe und [ICorProfilerCallback:: jitcachedfunctionsearchbeendeten](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) nicht für alle Funktionen in regulären NGen-Images erstellt.</span><span class="sxs-lookup"><span data-stu-id="7a31a-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="7a31a-111">Nur NGen-Images, die für ein Profil optimiert werden, generieren Rückrufe für alle Funktionen im Image.</span><span class="sxs-lookup"><span data-stu-id="7a31a-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="7a31a-112">Aufgrund des zusätzlichen Aufwands sollte ein Profiler jedoch nur Profiler-optimierte NGen-Images anfordern, wenn er diese Rückrufe verwenden soll, um zu erzwingen, dass eine Funktion Just-in-time (JIT) kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="7a31a-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="7a31a-113">Andernfalls sollte der Profiler eine verzögerte Strategie zum Sammeln von Funktions Informationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a31a-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="7a31a-114">Profiler müssen Fälle unterstützen, in denen mehrere Threads einer profilierten Anwendung dieselbe Methode gleichzeitig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7a31a-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="7a31a-115">Beispielsweise ruft Thread A auf, `JITCachedFunctionSearchStarted` und der Profiler antwortet, indem *pbUseCachedFunction* auf false festgelegt wird, um die JIT-Kompilierung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="7a31a-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction* to FALSE to force JIT compilation.</span></span> <span data-ttu-id="7a31a-116">Thread A ruft dann [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) und [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationfinished-method.md)auf.</span><span class="sxs-lookup"><span data-stu-id="7a31a-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="7a31a-117">Nun ruft Thread B `JITCachedFunctionSearchStarted` für dieselbe Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="7a31a-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="7a31a-118">Obwohl der Profiler seine Absicht zur JIT-Kompilierung der Funktion angegeben hat, empfängt der Profiler den zweiten Rückruf, da Thread B den Rückruf sendet, bevor der Profiler auf den Aufrufe von Thread A geantwortet hat `JITCachedFunctionSearchStarted` .</span><span class="sxs-lookup"><span data-stu-id="7a31a-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="7a31a-119">Die Reihenfolge, in der die Threads Aufrufe ausführen, hängt davon ab, wie die Threads geplant werden.</span><span class="sxs-lookup"><span data-stu-id="7a31a-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="7a31a-120">Wenn der Profiler doppelte Rückrufe empfängt, muss der Wert, auf den von verwiesen wird, `pbUseCachedFunction` auf denselben Wert für alle doppelten Rückrufe festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7a31a-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="7a31a-121">Das heißt, wenn `JITCachedFunctionSearchStarted` mehrmals mit demselben Wert aufgerufen wird `functionId` , muss der Profiler jedes Mal gleich reagieren.</span><span class="sxs-lookup"><span data-stu-id="7a31a-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a31a-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7a31a-122">Requirements</span></span>  

 <span data-ttu-id="7a31a-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a31a-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a31a-124">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a31a-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a31a-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a31a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a31a-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a31a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a31a-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a31a-127">See also</span></span>

- [<span data-ttu-id="7a31a-128">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a31a-128">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
