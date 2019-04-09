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
ms.openlocfilehash: 1abc4dd209581c9f7c8e950ea1addc74c611d248
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226057"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="19f89-102">ICorProfilerCallback::JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="19f89-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="19f89-103">Benachrichtigt den Profiler, dass der just-in-Time (JIT)-Compiler die Kompilierung einer Funktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="19f89-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19f89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19f89-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19f89-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="19f89-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="19f89-106">[in] Die ID der Funktion, die kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="19f89-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="19f89-107">[in] Ein Wert, der angibt, ob die Kompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="19f89-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="19f89-108">[in] Ein Wert, der angibt, an den Profiler an, ob blockierende wirkt sich auf den Vorgang der Runtime.</span><span class="sxs-lookup"><span data-stu-id="19f89-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="19f89-109">Der Wert ist `true` Wenn Blockierungen der Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten führen kann, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="19f89-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="19f89-110">Obwohl ein Wert von `true` wird die Runtime nicht beschädigen, können sie die Ergebnisse der profilerstellung verzerren.</span><span class="sxs-lookup"><span data-stu-id="19f89-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19f89-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19f89-111">Requirements</span></span>  
 <span data-ttu-id="19f89-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19f89-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19f89-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="19f89-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="19f89-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19f89-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="19f89-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="19f89-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="19f89-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19f89-116">See also</span></span>

- [<span data-ttu-id="19f89-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19f89-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="19f89-118">JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="19f89-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
