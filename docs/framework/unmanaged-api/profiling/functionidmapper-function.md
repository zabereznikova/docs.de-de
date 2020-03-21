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
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175173"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="8a48e-102">FunctionIDMapper-Funktion</span><span class="sxs-lookup"><span data-stu-id="8a48e-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="8a48e-103">Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den Callbacks [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)und [FunctionTailcall2](functiontailcall2-function.md) für diese Funktion verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8a48e-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="8a48e-104">Mit `FunctionIDMapper`kann der Profiler auch angeben, ob er Rückrufe für diese Funktion empfangen will.</span><span class="sxs-lookup"><span data-stu-id="8a48e-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a48e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a48e-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a48e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a48e-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="8a48e-107">\[in] Der Funktionsbezeichner, der neu zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8a48e-107">\[in] The function identifier to be remapped.</span></span>

- `pbHookFunction`

  <span data-ttu-id="8a48e-108">\[out] Ein Zeiger auf einen Wert, `true` auf den der `FunctionEnter2` `FunctionLeave2`Profiler `FunctionTailcall2` setzt, wenn er , und Rückrufe empfangen möchte; Andernfalls wird dieser Wert `false`auf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8a48e-108">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="8a48e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8a48e-109">Return Value</span></span>  
 <span data-ttu-id="8a48e-110">Der Profiler gibt einen Wert zurück, den die Ausführungs-Engine als alternativen Funktionsbezeichner verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a48e-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="8a48e-111">Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8a48e-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="8a48e-112">Andernfalls führt ein NULL-Rückgabewert zu unvorhersehbaren Ergebnissen, einschließlich des möglicherweise anhaltenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="8a48e-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a48e-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8a48e-113">Remarks</span></span>  
 <span data-ttu-id="8a48e-114">Die `FunctionIDMapper` Funktion ist ein Rückruf.</span><span class="sxs-lookup"><span data-stu-id="8a48e-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="8a48e-115">Sie wird vom Profiler implementiert, um eine Funktions-ID einem anderen Bezeichner neu zuzuordnen, der für den Profiler nützlicher ist.</span><span class="sxs-lookup"><span data-stu-id="8a48e-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="8a48e-116">Der `FunctionIDMapper` gibt die alternative ID zurück, die für eine bestimmte Funktion verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8a48e-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="8a48e-117">Das Ausführungsmodul berücksichtigt dann die Anforderung des Profilers, indem es diese alternative ID zusätzlich `clientData` zur traditionellen `FunctionEnter2` `FunctionLeave2`Funktions-ID an den Profiler im Parameter von , und `FunctionTailcall2` Hooks zurückgibt, um die Funktion zu identifizieren, für die der Hook aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8a48e-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="8a48e-118">Sie können die [ICorProfilerInfo::SetFunctionIDMapper-Methode](icorprofilerinfo-setfunctionidmapper-method.md) verwenden, `FunctionIDMapper` um die Implementierung der Funktion anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8a48e-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="8a48e-119">Sie können `ICorProfilerInfo::SetFunctionIDMapper` die Methode nur einmal aufrufen, und wir empfehlen, dies im [ICorProfilerCallback::Initialize-Rückruf](icorprofilercallback-initialize-method.md) zu tun.</span><span class="sxs-lookup"><span data-stu-id="8a48e-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="8a48e-120">Standardmäßig wird davon ausgegangen, dass ein Profiler, der das COR_PRF_MONITOR_ENTERLEAVE-Flag mithilfe von [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md)festlegt und Hooks über [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) oder [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), für jede Funktion empfängt. `FunctionEnter2` `FunctionLeave2` `FunctionTailcall2`</span><span class="sxs-lookup"><span data-stu-id="8a48e-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="8a48e-121">Profiler können jedoch `FunctionIDMapper` implementieren, um selektiv den Empfang dieser `pbHookFunction` Rückrufe für bestimmte Funktionen zu vermeiden, indem sie auf `false`festlegen.</span><span class="sxs-lookup"><span data-stu-id="8a48e-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="8a48e-122">Profiler sollten tolerant gegenüber Fällen sein, in denen mehrere Threads einer profilierten Anwendung dieselbe Methode/Funktion gleichzeitig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8a48e-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="8a48e-123">In solchen Fällen kann der `FunctionIDMapper` Profiler mehrere Rückrufe für dieselbe `FunctionID`erhalten.</span><span class="sxs-lookup"><span data-stu-id="8a48e-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="8a48e-124">Der Profiler sollte sicher sein, dass er dieselben Werte aus diesem `FunctionID`Rückruf zurückgibt, wenn er mehrmals mit derselben aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8a48e-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a48e-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8a48e-125">Requirements</span></span>  
 <span data-ttu-id="8a48e-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a48e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a48e-127">**Kopfzeile:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="8a48e-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8a48e-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a48e-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a48e-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a48e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a48e-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a48e-130">See also</span></span>

- [<span data-ttu-id="8a48e-131">SetFunctionIDMapper-Methode</span><span class="sxs-lookup"><span data-stu-id="8a48e-131">SetFunctionIDMapper Method</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="8a48e-132">FunctionIDMapper2-Funktion</span><span class="sxs-lookup"><span data-stu-id="8a48e-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)
- [<span data-ttu-id="8a48e-133">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="8a48e-133">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="8a48e-134">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="8a48e-134">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="8a48e-135">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="8a48e-135">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="8a48e-136">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a48e-136">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
