---
title: FunctionIDMapper-Funktion
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0320c831648c15dfec42c1b693be2f13e6888ae9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475163"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="7be1c-102">FunctionIDMapper-Funktion</span><span class="sxs-lookup"><span data-stu-id="7be1c-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="7be1c-103">Benachrichtigt Sie den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zu verwendende zugeordnet werden kann die [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), und [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) Rückrufe für diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="7be1c-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="7be1c-104">Mit `FunctionIDMapper`kann der Profiler auch angeben, ob er Rückrufe für diese Funktion empfangen will.</span><span class="sxs-lookup"><span data-stu-id="7be1c-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be1c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7be1c-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7be1c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7be1c-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="7be1c-107">[in] Der Funktionsbezeichner, der neu zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7be1c-107">[in] The function identifier to be remapped.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="7be1c-108">[out] Ein Zeiger auf ein Wert, der der Profiler wird auf `true` , wenn sie empfangen möchte `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Rückrufe; andernfalls wird dieser Wert auf `false`.</span><span class="sxs-lookup"><span data-stu-id="7be1c-108">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7be1c-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7be1c-109">Return Value</span></span>  
 <span data-ttu-id="7be1c-110">Der Profiler gibt einen Wert zurück, den die Ausführungs-Engine als alternativen Funktionsbezeichner verwendet.</span><span class="sxs-lookup"><span data-stu-id="7be1c-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="7be1c-111">Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7be1c-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="7be1c-112">Andernfalls erzeugt ein Rückgabewert von null zu unvorhersehbaren Ergebnissen, einschließlich des möglichen Anhaltens des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="7be1c-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7be1c-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7be1c-113">Remarks</span></span>  
 <span data-ttu-id="7be1c-114">Die `FunctionIDMapper` Funktion ist ein Rückruf.</span><span class="sxs-lookup"><span data-stu-id="7be1c-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="7be1c-115">Die Implementierung erfolgt durch den Profiler an einen anderen Bezeichner eine Funktions-ID neu zuordnen, die für den Profiler nützlicher ist.</span><span class="sxs-lookup"><span data-stu-id="7be1c-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="7be1c-116">Die `FunctionIDMapper` gibt zurück, die alternative ID für eine bestimmte Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7be1c-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="7be1c-117">Berücksichtigt die ausführungs-Engine dann die Anfrage des Profilers übergeben Sie diese alternative ID zusätzlich zu der herkömmlichen Funktions-ID, zurück an dem Profiler in den `clientData` Parameter der `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Hooks, um zu identifizieren die Funktion für die der Hook aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7be1c-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="7be1c-118">Können Sie die [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) Methode an die Implementierung der `FunctionIDMapper` Funktion.</span><span class="sxs-lookup"><span data-stu-id="7be1c-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="7be1c-119">Rufen Sie die `ICorProfilerInfo::SetFunctionIDMapper` Methode nur einmal, und es wird empfohlen, haben also in der [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="7be1c-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="7be1c-120">Es wird standardmäßig davon ausgegangen, dass ein Profiler, die das COR_PRF_MONITOR_ENTERLEAVE-Flag mithilfe von festlegt [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), und die Hooks über [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) oder [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), erhalten die `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Rückrufe für jede Funktion.</span><span class="sxs-lookup"><span data-stu-id="7be1c-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="7be1c-121">Allerdings Profiler implementiert möglicherweise `FunctionIDMapper` selektiv vermeiden diese Rückrufe für bestimmte Funktionen durch Festlegen von `pbHookFunction` zu `false`.</span><span class="sxs-lookup"><span data-stu-id="7be1c-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="7be1c-122">Profiler sollte der Fälle fehlertoleranten sein, in denen mehrere Threads einer Anwendung ein Profil erstellt wurde gleichzeitig die gleiche Methode/Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7be1c-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="7be1c-123">In solchen Fällen erhält der Profiler kann mehrere `FunctionIDMapper` Rückrufe für den gleichen `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="7be1c-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="7be1c-124">Der Profiler sollte sichergestellt sein, um die Werte von diesem Rückruf zurückgeben, wenn sie mehrere Male, mit dem gleichen aufgerufen wird `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="7be1c-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be1c-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7be1c-125">Requirements</span></span>  
 <span data-ttu-id="7be1c-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7be1c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be1c-127">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7be1c-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7be1c-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7be1c-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7be1c-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be1c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be1c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7be1c-130">See also</span></span>
- [<span data-ttu-id="7be1c-131">SetFunctionIDMapper-Methode</span><span class="sxs-lookup"><span data-stu-id="7be1c-131">SetFunctionIDMapper Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="7be1c-132">FunctionIDMapper2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7be1c-132">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [<span data-ttu-id="7be1c-133">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7be1c-133">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="7be1c-134">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7be1c-134">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="7be1c-135">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7be1c-135">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="7be1c-136">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="7be1c-136">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
