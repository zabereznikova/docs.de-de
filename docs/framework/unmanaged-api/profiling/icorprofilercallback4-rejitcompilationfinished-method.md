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
ms.openlocfilehash: e010a49dabd3b44602136e70b4c5524a68bdd9e2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865206"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="9fbf8-102">ICorProfilerCallback4::ReJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="9fbf8-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="9fbf8-103">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die erneute Kompilierung einer Funktion abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="9fbf8-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fbf8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fbf8-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fbf8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9fbf8-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="9fbf8-106">in Die ID der Funktion, die neu kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="9fbf8-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="9fbf8-107">[in] Die Identität der erneut JIT-kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="9fbf8-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="9fbf8-108">in Ein Wert, der angibt, ob die JIT-Neukompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="9fbf8-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="9fbf8-109">[in] `true`, um anzugeben, dass eine Blockierung bewirken kann, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet. `false`, um anzugeben, dass die Blockierung sich nicht auf den Lauf Zeit Vorgang auswirkt.</span><span class="sxs-lookup"><span data-stu-id="9fbf8-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="9fbf8-110">Der Wert `true` schadet nicht der Laufzeit, kann jedoch die Profil Erstellungs Ergebnisse beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="9fbf8-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fbf8-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9fbf8-111">Requirements</span></span>  
 <span data-ttu-id="9fbf8-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fbf8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fbf8-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9fbf8-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9fbf8-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fbf8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fbf8-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fbf8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fbf8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fbf8-116">See also</span></span>

- [<span data-ttu-id="9fbf8-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fbf8-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9fbf8-118">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fbf8-118">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="9fbf8-119">JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="9fbf8-119">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="9fbf8-120">ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="9fbf8-120">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
