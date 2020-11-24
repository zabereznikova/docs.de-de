---
title: ICorProfilerCallback::JITCachedFunctionSearchFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: fe07270989df897c3dbf689305784f9f0af65742
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684043"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="432c8-102">ICorProfilerCallback::JITCachedFunctionSearchFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="432c8-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>

<span data-ttu-id="432c8-103">Benachrichtigt den Profiler, dass eine Suche für eine Funktion abgeschlossen wurde, die zuvor mit dem Native Image Generator (NGen.exe) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="432c8-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="432c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="432c8-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="432c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="432c8-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="432c8-106">\[in] die ID der Funktion, für die die Suche durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="432c8-106">\[in] The ID of the function for which the search was performed.</span></span>

- `result`

  <span data-ttu-id="432c8-107">\[in] ein Wert der [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) -Enumeration, die das Ergebnis der Suche angibt.</span><span class="sxs-lookup"><span data-stu-id="432c8-107">\[in] A value of the [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>

## <a name="remarks"></a><span data-ttu-id="432c8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="432c8-108">Remarks</span></span>  

 <span data-ttu-id="432c8-109">In der .NET Framework Version 2,0 werden die [ICorProfilerCallback:: JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) -und `JITCachedFunctionSearchFinished` Rückrufe nicht für alle Funktionen in regulären NGen-Images erstellt.</span><span class="sxs-lookup"><span data-stu-id="432c8-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="432c8-110">Nur NGen-Images, die für einen Profiler optimiert sind, generieren Rückrufe für alle Funktionen im Image.</span><span class="sxs-lookup"><span data-stu-id="432c8-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="432c8-111">Aufgrund des zusätzlichen Aufwands sollte ein Profiler jedoch nur Profiler-optimierte NGen-Images anfordern, wenn er diese Rückrufe verwenden soll, um zu erzwingen, dass eine Funktion Just-in-time (JIT) kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="432c8-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="432c8-112">Andernfalls sollte der Profiler eine verzögerte Strategie zum Sammeln von Funktions Informationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="432c8-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="432c8-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="432c8-113">Requirements</span></span>  

 <span data-ttu-id="432c8-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="432c8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="432c8-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="432c8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="432c8-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="432c8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="432c8-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="432c8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="432c8-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="432c8-118">See also</span></span>

- [<span data-ttu-id="432c8-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="432c8-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
