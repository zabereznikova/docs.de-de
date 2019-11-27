---
title: FunctionIDMapper2-Funktion
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
ms.openlocfilehash: 7f83469920956d73a275f510b0d3c3e94a4caa8d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440674"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="e2d0f-102">FunctionIDMapper2-Funktion</span><span class="sxs-lookup"><span data-stu-id="e2d0f-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="e2d0f-103">Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)-, [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)-und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)-und[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)-, [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)-und [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) -Rückrufe für diese Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e2d0f-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="e2d0f-104">`FunctionIDMapper2` ermöglicht es dem Profiler außerdem anzugeben, ob er Rückrufe für diese Funktion empfangen möchte.</span><span class="sxs-lookup"><span data-stu-id="e2d0f-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d0f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2d0f-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2d0f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2d0f-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="e2d0f-107">[in] Der Funktionsbezeichner, der neu zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2d0f-107">[in] The function identifier to be remapped.</span></span>  
  
 `clientData`  
 <span data-ttu-id="e2d0f-108">[in] Ein Zeiger auf Daten, mit denen Mehrdeutigkeiten zwischen Laufzeiten aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e2d0f-108">[in] A pointer to data that is used to disambiguate among runtimes.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="e2d0f-109">[out] Ein Zeiger auf einen Wert, den der Profiler auf `true` festlegt, wenn er die Rückrufe `FunctionEnter3`, `FunctionLeave3` und `FunctionTailcall3` oder `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo` und `FunctionTailcall3WithInfo` empfangen möchte. Andernfalls wird der Wert auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e2d0f-109">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2d0f-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e2d0f-110">Return Value</span></span>  
 <span data-ttu-id="e2d0f-111">Der Profiler gibt einen Wert zurück, den die Ausführungs-Engine als alternativen Funktionsbezeichner verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2d0f-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="e2d0f-112">Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e2d0f-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="e2d0f-113">Andernfalls führt ein Rückgabewert von NULL zu unvorhersehbaren Ergebnissen, einschließlich des möglichen Anhaltens des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="e2d0f-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2d0f-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2d0f-114">Remarks</span></span>  
 <span data-ttu-id="e2d0f-115">Diese Methode erweitert die [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) -Funktion mit einem zusätzlichen Parameter, der verwendet wird, um Client Daten zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="e2d0f-115">This method extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="e2d0f-116">Die Clientdaten werden verwendet, um Mehrdeutigkeiten zwischen Laufzeiten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="e2d0f-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2d0f-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e2d0f-117">Requirements</span></span>  
 <span data-ttu-id="e2d0f-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2d0f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2d0f-119">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="e2d0f-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e2d0f-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2d0f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2d0f-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2d0f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d0f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2d0f-122">See also</span></span>

- [<span data-ttu-id="e2d0f-123">ICorProfilerInfo:: SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="e2d0f-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="e2d0f-124">ICorProfilerInfo3:: SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="e2d0f-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="e2d0f-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="e2d0f-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="e2d0f-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="e2d0f-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="e2d0f-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="e2d0f-127">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="e2d0f-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2d0f-128">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="e2d0f-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2d0f-129">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="e2d0f-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2d0f-130">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="e2d0f-131">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="e2d0f-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
