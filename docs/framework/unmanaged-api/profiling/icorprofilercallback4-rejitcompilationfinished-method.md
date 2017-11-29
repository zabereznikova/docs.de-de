---
title: ICorProfilerCallback4::ReJITCompilationFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 768c77a91c072cadc2975d9dde704c134e719220
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="89ffe-102">ICorProfilerCallback4::ReJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="89ffe-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="89ffe-103">Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler Kompilieren eine Funktion abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="89ffe-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89ffe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89ffe-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89ffe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="89ffe-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="89ffe-106">[in] Die ID der Funktion, die neu kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="89ffe-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="89ffe-107">[in] Die Identität der erneut JIT-kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="89ffe-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="89ffe-108">[in] Ein Wert, der angibt, ob der JIT-Neukompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="89ffe-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="89ffe-109">[in] `true` um anzugeben, dass die Blockierung der Laufzeit von diesem Rückruf; Zurückgeben der aufrufende Thread warten verursachen `false` um anzugeben, dass blockiert die Ausführung von der Laufzeit nicht beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="89ffe-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="89ffe-110">Ein Wert von `true` ist nicht auf die Common Language Runtime Schaden anrichten, jedoch können die Profilerstellungsergebnisse auswirken.</span><span class="sxs-lookup"><span data-stu-id="89ffe-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89ffe-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89ffe-111">Requirements</span></span>  
 <span data-ttu-id="89ffe-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89ffe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89ffe-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89ffe-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89ffe-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89ffe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89ffe-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89ffe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89ffe-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89ffe-116">See Also</span></span>  
 [<span data-ttu-id="89ffe-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89ffe-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="89ffe-118">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89ffe-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="89ffe-119">JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="89ffe-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [<span data-ttu-id="89ffe-120">ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="89ffe-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
