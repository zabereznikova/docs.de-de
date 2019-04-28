---
title: ICorProfilerCallback4::ReJITCompilationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0ec2981cbee4675f9cd2a4fd13d507f50ad2a3ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597140"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="a9b9f-102">ICorProfilerCallback4::ReJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="a9b9f-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="a9b9f-103">Benachrichtigt den Profiler, dass der just-in-Time-Compiler (JIT) die erneute Kompilierung einer Funktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a9b9f-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9b9f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9b9f-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9b9f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9b9f-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a9b9f-106">[in] Die ID der Funktion, die neu kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="a9b9f-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="a9b9f-107">[in] Die Identität der erneut JIT-kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="a9b9f-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a9b9f-108">[in] Ein Wert, der angibt, ob der JIT-Neukompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a9b9f-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="a9b9f-109">[in] `true` um anzugeben, dass blockiert die Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten verursachen `false` um anzugeben, dass die Blockierung der Vorgang der Laufzeit nicht beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="a9b9f-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="a9b9f-110">Der Wert `true` kompatibilitätsgesichtspunkten sich nicht auf die Laufzeit nimmt allerdings die Ergebnisse der profilerstellung.</span><span class="sxs-lookup"><span data-stu-id="a9b9f-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9b9f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a9b9f-111">Requirements</span></span>  
 <span data-ttu-id="a9b9f-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9b9f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9b9f-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a9b9f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a9b9f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9b9f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9b9f-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9b9f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b9f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9b9f-116">See also</span></span>

- [<span data-ttu-id="a9b9f-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9b9f-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a9b9f-118">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9b9f-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="a9b9f-119">JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="a9b9f-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="a9b9f-120">ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="a9b9f-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
