---
title: ICorProfilerCallback::JITCompilationFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9bd1a163fa5e941c68c5dd8d7d3221e8a5aa3df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="8b970-102">ICorProfilerCallback::JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="8b970-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="8b970-103">Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler Kompilieren eine Funktion abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="8b970-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b970-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b970-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b970-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b970-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8b970-106">[in] Die ID der Funktion, die kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="8b970-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="8b970-107">[in] Ein Wert, der angibt, ob die Kompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8b970-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="8b970-108">[in] Ein Wert, der angibt, an den Profiler an, ob blockierende wird die Funktion der Laufzeit beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="8b970-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="8b970-109">Der Wert ist `true` Wenn blockiert die Common Language Runtime von diesem Rückruf; Zurückgeben der aufrufende Thread warten führen kann, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="8b970-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="8b970-110">Obwohl ein Wert von `true` wird nicht auf die Common Language Runtime Schaden anrichten, sie können die Profilerstellungsergebnisse verzerren.</span><span class="sxs-lookup"><span data-stu-id="8b970-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b970-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b970-111">Requirements</span></span>  
 <span data-ttu-id="8b970-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b970-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b970-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b970-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b970-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b970-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b970-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b970-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b970-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b970-116">See Also</span></span>  
 [<span data-ttu-id="8b970-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b970-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="8b970-118">JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="8b970-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
