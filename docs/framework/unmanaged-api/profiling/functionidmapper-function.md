---
title: FunctionIDMapper-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 24e48ecb551a5faacc7da94b857b2e260f5aeca0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="functionidmapper-function"></a><span data-ttu-id="9b3f1-102">FunctionIDMapper-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b3f1-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="9b3f1-103">Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zu verwendende zugeordnet werden kann die [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), und [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) Rückrufe für diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="9b3f1-104">Mit `FunctionIDMapper`kann der Profiler auch angeben, ob er Rückrufe für diese Funktion empfangen will.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b3f1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b3f1-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b3f1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b3f1-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="9b3f1-107">[in] Der Funktionsbezeichner, der neu zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-107">[in] The function identifier to be remapped.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="9b3f1-108">[out] Ein Zeiger auf einen Wert, der Profiler festlegt, `true` , wenn er empfangen will `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Rückrufe; andernfalls wird dieser Wert auf `false`.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-108">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b3f1-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9b3f1-109">Return Value</span></span>  
 <span data-ttu-id="9b3f1-110">Der Profiler gibt einen Wert zurück, den das Ausführungsmodul als alternativen Funktionsbezeichner verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="9b3f1-111">Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="9b3f1-112">Andernfalls liefert ein Rückgabewert von null zu unvorhersehbaren Ergebnissen, einschließlich des möglichen Anhaltens des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b3f1-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b3f1-113">Remarks</span></span>  
 <span data-ttu-id="9b3f1-114">Die `FunctionIDMapper` -Funktion ist ein Rückruf.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="9b3f1-115">Die Implementierung erfolgt durch den Profiler an eine Partitionsfunktions-ID auf einen anderen Bezeichner neu zuordnen, die besser eignet, um den Profiler.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="9b3f1-116">Die `FunctionIDMapper` gibt die alternative-ID für jede gegebene Funktion verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="9b3f1-117">Das Ausführungsmodul berücksichtigt dann die Anforderung des Profilers übergeben diese alternative ID zusätzlich zu den herkömmlichen Funktions-ID an dem Profiler in den `clientData` Parameter von der `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Hooks, um zu identifizieren die Funktion für die die Hookfunktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="9b3f1-118">Können Sie die [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) an die Implementierung der Methode der `FunctionIDMapper` Funktion.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="9b3f1-119">Sie erreichen die `ICorProfilerInfo::SetFunctionIDMapper` -Methode nur einmal, und wir empfehlen zudem, dass Sie daher in der [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="9b3f1-120">Standardmäßig wird davon ausgegangen, dass ein Profiler, die das COR_PRF_MONITOR_ENTERLEAVE-Flag mithilfe festlegt [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), und Hooks über [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) oder [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), erhalten die `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Rückrufe für jede Funktion.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="9b3f1-121">Allerdings Profiler implementieren können `FunctionIDMapper` , selektiv zu vermeiden, dass diese Rückrufe für bestimmte Funktionen durch Festlegen von `pbHookFunction` auf `false`.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="9b3f1-122">Profiler sollten fehlertolerante der Fälle werden, in denen mehrere Threads einer Anwendung mit Profil dieselbe Methode/Funktion gleichzeitig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="9b3f1-123">In solchen Fällen erhält der Profiler kann mehrere `FunctionIDMapper` Rückrufe für dieselbe `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="9b3f1-124">Der Profiler sollte sichergestellt sein, um die Werte von diesem Rückruf zurückgeben, wenn sie mehrere Male, mit dem gleichen aufgerufen wird `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="9b3f1-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b3f1-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b3f1-125">Requirements</span></span>  
 <span data-ttu-id="9b3f1-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b3f1-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b3f1-127">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="9b3f1-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="9b3f1-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b3f1-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b3f1-129">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b3f1-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b3f1-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b3f1-130">See Also</span></span>  
 [<span data-ttu-id="9b3f1-131">SetFunctionIDMapper-Methode</span><span class="sxs-lookup"><span data-stu-id="9b3f1-131">SetFunctionIDMapper Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="9b3f1-132">FunctionIDMapper2-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b3f1-132">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 [<span data-ttu-id="9b3f1-133">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b3f1-133">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="9b3f1-134">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b3f1-134">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="9b3f1-135">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b3f1-135">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="9b3f1-136">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="9b3f1-136">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
