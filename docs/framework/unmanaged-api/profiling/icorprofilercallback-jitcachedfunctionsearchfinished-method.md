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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 882d3b3c359724688c0fb8fe5e2b567f1d575e76
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782869"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="a7657-102">ICorProfilerCallback::JITCachedFunctionSearchFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="a7657-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="a7657-103">Benachrichtigt den Profiler, dass eine Suche für eine Funktion abgeschlossen ist, die vorher mit dem Native Image Generator (NGen.exe) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="a7657-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7657-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7657-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7657-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7657-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a7657-106">[in] Die ID der Funktion für die Suche ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a7657-106">[in] The ID of the function for which the search was performed.</span></span>  
  
 `result`  
 <span data-ttu-id="a7657-107">[in] Der Wert der [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) -Enumeration, der das Ergebnis der Suche angibt.</span><span class="sxs-lookup"><span data-stu-id="a7657-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7657-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7657-108">Remarks</span></span>  
 <span data-ttu-id="a7657-109">In .NET Framework, Version 2.0 der [ICorProfilerCallback:: JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) und `JITCachedFunctionSearchFinished` Rückrufe kommt nicht zustande, für alle Funktionen in reguläre NGen-Images.</span><span class="sxs-lookup"><span data-stu-id="a7657-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="a7657-110">Nur NGen-Images, die für ein Profiler optimiert generiert Rückrufe für alle Funktionen in der Abbildung.</span><span class="sxs-lookup"><span data-stu-id="a7657-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="a7657-111">Aufgrund der zusätzlichen Aufwand, sollte ein Profiler jedoch optimierten Profiler der NGen-Images anfordern, nur dann, wenn diese Rückrufe verwendet, eine Funktion, die kompilierten just-in-Time (JIT) werden erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a7657-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="a7657-112">Andernfalls sollte der Profiler eine Strategie für die verzögerte verwenden, zum Erfassen von Funktionsinformationen.</span><span class="sxs-lookup"><span data-stu-id="a7657-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7657-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7657-113">Requirements</span></span>  
 <span data-ttu-id="a7657-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7657-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7657-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7657-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7657-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7657-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7657-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7657-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7657-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7657-118">See also</span></span>

- [<span data-ttu-id="a7657-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7657-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
