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
ms.openlocfilehash: d5bf6626e2c6ba15fa9a5da08bcf2d9052866750
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866943"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="dba6d-102">FunctionIDMapper-Funktion</span><span class="sxs-lookup"><span data-stu-id="dba6d-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="dba6d-103">Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter2](functionenter2-function.md)-, [FunctionLeave2](functionleave2-function.md)-und [FunctionTailcall2](functiontailcall2-function.md) -Rückrufe für diese Funktion verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dba6d-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="dba6d-104">Mit `FunctionIDMapper`kann der Profiler auch angeben, ob er Rückrufe für diese Funktion empfangen will.</span><span class="sxs-lookup"><span data-stu-id="dba6d-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba6d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="dba6d-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dba6d-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="dba6d-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="dba6d-107">\[in] der Funktions Bezeichner, der neu zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dba6d-107">\[in] The function identifier to be remapped.</span></span>

- `pbHookFunction`

  <span data-ttu-id="dba6d-108">\[out] ein Zeiger auf einen Wert, den der Profiler auf `true` festlegt, wenn er `FunctionEnter2`, `FunctionLeave2`und `FunctionTailcall2` Rückrufe empfangen möchte. Andernfalls wird dieser Wert auf `false`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dba6d-108">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="dba6d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dba6d-109">Return Value</span></span>  
 <span data-ttu-id="dba6d-110">Der Profiler gibt einen Wert zurück, den die Ausführungs-Engine als alternativen Funktionsbezeichner verwendet.</span><span class="sxs-lookup"><span data-stu-id="dba6d-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="dba6d-111">Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dba6d-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="dba6d-112">Andernfalls führt ein NULL-Rückgabewert zu unvorhersehbaren Ergebnissen, einschließlich der möglichen Beendigung des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="dba6d-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dba6d-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dba6d-113">Remarks</span></span>  
 <span data-ttu-id="dba6d-114">Die `FunctionIDMapper`-Funktion ist ein Rückruf.</span><span class="sxs-lookup"><span data-stu-id="dba6d-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="dba6d-115">Sie wird vom Profiler implementiert, um eine Funktions-ID einem anderen Bezeichner zuzuordnen, der für den Profiler nützlicher ist.</span><span class="sxs-lookup"><span data-stu-id="dba6d-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="dba6d-116">Der `FunctionIDMapper` gibt die Alternative ID zurück, die für eine bestimmte Funktion verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dba6d-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="dba6d-117">Die Ausführungs-Engine berücksichtigt dann die Anforderung des Profilers durch Übergeben dieser alternativen ID zusätzlich zur herkömmlichen Funktions-ID an den Profiler im `clientData`-Parameter der `FunctionEnter2`, `FunctionLeave2`und `FunctionTailcall2` Hooks, um die Funktion zu identifizieren, für die der Hook aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dba6d-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="dba6d-118">Sie können die [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) -Methode verwenden, um die Implementierung der `FunctionIDMapper`-Funktion anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dba6d-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="dba6d-119">Die `ICorProfilerInfo::SetFunctionIDMapper`-Methode kann nur einmal aufgerufen werden, und es wird empfohlen, dass Sie dies im [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf durchführen.</span><span class="sxs-lookup"><span data-stu-id="dba6d-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="dba6d-120">Standardmäßig wird davon ausgegangen, dass ein Profiler, der das COR_PRF_MONITOR_ENTERLEAVE-Flag mithilfe von [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)festlegt und Hooks über [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) oder [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)festlegt, die `FunctionEnter2`-, `FunctionLeave2`-und `FunctionTailcall2` Rückrufe für jede Funktion empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="dba6d-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="dba6d-121">Allerdings können Profiler `FunctionIDMapper` implementieren, um den Empfang dieser Rückrufe für bestimmte Funktionen selektiv zu vermeiden, indem Sie `pbHookFunction` auf `false`festlegen.</span><span class="sxs-lookup"><span data-stu-id="dba6d-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="dba6d-122">Profiler sollten für Fälle tolerant sein, in denen mehrere Threads einer profilierten Anwendung dieselbe Methode bzw. Funktion gleichzeitig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="dba6d-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="dba6d-123">In solchen Fällen empfängt der Profiler möglicherweise mehrere `FunctionIDMapper` Rückrufe für denselben `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="dba6d-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="dba6d-124">Der Profiler sollte sicher sein, dass er dieselben Werte von diesem Rückruf zurückgibt, wenn er mehrmals mit demselben `FunctionID`aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dba6d-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dba6d-125">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dba6d-125">Requirements</span></span>  
 <span data-ttu-id="dba6d-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dba6d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dba6d-127">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="dba6d-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="dba6d-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dba6d-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dba6d-129">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dba6d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba6d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dba6d-130">See also</span></span>

- [<span data-ttu-id="dba6d-131">SetFunctionIDMapper-Methode</span><span class="sxs-lookup"><span data-stu-id="dba6d-131">SetFunctionIDMapper Method</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="dba6d-132">FunctionIDMapper2-Funktion</span><span class="sxs-lookup"><span data-stu-id="dba6d-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)
- [<span data-ttu-id="dba6d-133">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="dba6d-133">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="dba6d-134">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="dba6d-134">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="dba6d-135">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="dba6d-135">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="dba6d-136">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="dba6d-136">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
