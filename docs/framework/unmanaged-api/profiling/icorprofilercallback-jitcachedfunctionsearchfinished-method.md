---
title: ICorProfilerCallback::JITCachedFunctionSearchFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ffbe331399334d179cf8325e7d9e6773b5bf7012
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="3b7ca-102">ICorProfilerCallback::JITCachedFunctionSearchFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="3b7ca-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="3b7ca-103">Benachrichtigt den Profiler, dass eine Suche für eine Funktion abgeschlossen ist, die zuvor mit der Native Image Generator (NGen.exe) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="3b7ca-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b7ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b7ca-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b7ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3b7ca-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="3b7ca-106">[in] Die ID der Funktion für die Suche durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="3b7ca-106">[in] The ID of the function for which the search was performed.</span></span>  
  
 `result`  
 <span data-ttu-id="3b7ca-107">[in] Der Wert der [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) -Enumeration, der das Ergebnis der Suche angibt.</span><span class="sxs-lookup"><span data-stu-id="3b7ca-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b7ca-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b7ca-108">Remarks</span></span>  
 <span data-ttu-id="3b7ca-109">In .NET Framework, Version 2.0 die [ICorProfilerCallback:: JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) und `JITCachedFunctionSearchFinished` Rückrufe werden nicht für alle Funktionen in regulären NGen-Images gestellt.</span><span class="sxs-lookup"><span data-stu-id="3b7ca-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="3b7ca-110">Nur NGen-Images, die für ein Profiler optimiert generiert Rückrufe für alle Funktionen in der Abbildung.</span><span class="sxs-lookup"><span data-stu-id="3b7ca-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="3b7ca-111">Aufgrund der zusätzlichen Verwaltungsaufwand, sollte ein Profiler jedoch Profiler optimiert NGen-Images anfordern, nur, wenn sie beabsichtigt, diese Rückrufe verwenden, um eine Funktion zu kompilierten just-in-Time (JIT) zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="3b7ca-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="3b7ca-112">Andernfalls sollte der Profiler eine Strategie für die verzögerte verwenden, für das Sammeln von Informationen.</span><span class="sxs-lookup"><span data-stu-id="3b7ca-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b7ca-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3b7ca-113">Requirements</span></span>  
 <span data-ttu-id="3b7ca-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b7ca-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b7ca-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b7ca-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b7ca-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b7ca-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b7ca-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b7ca-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b7ca-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b7ca-118">See Also</span></span>  
 [<span data-ttu-id="3b7ca-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b7ca-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
