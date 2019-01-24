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
ms.openlocfilehash: de225a0d4855cbd3f8a46787c2472ca727558fc9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669652"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="eac21-102">ICorProfilerCallback::JITCachedFunctionSearchFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="eac21-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="eac21-103">Benachrichtigt den Profiler, dass eine Suche für eine Funktion abgeschlossen ist, die vorher mit dem Native Image Generator (NGen.exe) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="eac21-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eac21-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eac21-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eac21-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eac21-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="eac21-106">[in] Die ID der Funktion für die Suche ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="eac21-106">[in] The ID of the function for which the search was performed.</span></span>  
  
 `result`  
 <span data-ttu-id="eac21-107">[in] Der Wert der [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) -Enumeration, der das Ergebnis der Suche angibt.</span><span class="sxs-lookup"><span data-stu-id="eac21-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eac21-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eac21-108">Remarks</span></span>  
 <span data-ttu-id="eac21-109">In .NET Framework, Version 2.0 der [ICorProfilerCallback:: JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) und `JITCachedFunctionSearchFinished` Rückrufe kommt nicht zustande, für alle Funktionen in reguläre NGen-Images.</span><span class="sxs-lookup"><span data-stu-id="eac21-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="eac21-110">Nur NGen-Images, die für ein Profiler optimiert generiert Rückrufe für alle Funktionen in der Abbildung.</span><span class="sxs-lookup"><span data-stu-id="eac21-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="eac21-111">Aufgrund der zusätzlichen Aufwand, sollte ein Profiler jedoch optimierten Profiler der NGen-Images anfordern, nur dann, wenn diese Rückrufe verwendet, eine Funktion, die kompilierten just-in-Time (JIT) werden erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="eac21-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="eac21-112">Andernfalls sollte der Profiler eine Strategie für die verzögerte verwenden, zum Erfassen von Funktionsinformationen.</span><span class="sxs-lookup"><span data-stu-id="eac21-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eac21-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eac21-113">Requirements</span></span>  
 <span data-ttu-id="eac21-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eac21-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eac21-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eac21-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eac21-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eac21-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eac21-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eac21-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac21-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eac21-118">See also</span></span>
- [<span data-ttu-id="eac21-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eac21-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
