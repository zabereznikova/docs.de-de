---
title: ICorProfilerCallback::JITCompilationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c5556fecb6251a2dd6a131332dbff1b5ca2f5d95
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493335"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="a838e-102">ICorProfilerCallback::JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="a838e-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="a838e-103">Benachrichtigt den Profiler, dass der just-in-Time (JIT)-Compiler die Kompilierung einer Funktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a838e-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a838e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a838e-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a838e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a838e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a838e-106">[in] Die ID der Funktion, die kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="a838e-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a838e-107">[in] Ein Wert, der angibt, ob die Kompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a838e-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="a838e-108">[in] Ein Wert, der angibt, an den Profiler an, ob blockierende wirkt sich auf den Vorgang der Runtime.</span><span class="sxs-lookup"><span data-stu-id="a838e-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="a838e-109">Der Wert ist `true` Wenn Blockierungen der Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten führen kann, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="a838e-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="a838e-110">Obwohl ein Wert von `true` wird die Runtime nicht beschädigen, können sie die Ergebnisse der profilerstellung verzerren.</span><span class="sxs-lookup"><span data-stu-id="a838e-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a838e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a838e-111">Requirements</span></span>  
 <span data-ttu-id="a838e-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a838e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a838e-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a838e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a838e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a838e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a838e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a838e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a838e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a838e-116">See also</span></span>
- [<span data-ttu-id="a838e-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a838e-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a838e-118">JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="a838e-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
