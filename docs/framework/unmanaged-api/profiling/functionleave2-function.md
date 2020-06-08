---
title: FunctionLeave2-Funktion
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
ms.openlocfilehash: a2a3d58e0631fceab96c32f9d86fef25973fed84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500662"
---
# <a name="functionleave2-function"></a><span data-ttu-id="a4d57-102">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="a4d57-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="a4d57-103">Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren, und stellt Informationen zum Stapel Rahmen und Funktionsrückgabewert bereit.</span><span class="sxs-lookup"><span data-stu-id="a4d57-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4d57-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4d57-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a4d57-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="a4d57-106">\[in] der Bezeichner der Funktion, die zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a4d57-106">\[in] The identifier of the function that is returning.</span></span>

- `clientData`

  <span data-ttu-id="a4d57-107">\[in] der neu zugeordnete Funktions Bezeichner, den der Profiler zuvor über die [FunctionIDMapper](functionidmapper-function.md) -Funktion angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="a4d57-107">\[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>

- `func`

  <span data-ttu-id="a4d57-108">\[in] ein- `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapel Rahmen zeigt.</span><span class="sxs-lookup"><span data-stu-id="a4d57-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="a4d57-109">Der Profiler sollte dies als ein undurchsichtiges Handle behandeln, das an die Ausführungs-Engine in der [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) -Methode zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="a4d57-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `retvalRange`

  <span data-ttu-id="a4d57-110">\[in] ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) -Struktur, die die Speicherposition des Rückgabewerts der Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="a4d57-110">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>

  <span data-ttu-id="a4d57-111">Um auf Rückgabewert Informationen zugreifen zu können, `COR_PRF_ENABLE_FUNCTION_RETVAL` muss das-Flag festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a4d57-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="a4d57-112">Der Profiler kann die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um die Ereignisflags festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a4d57-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4d57-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a4d57-113">Remarks</span></span>  
 <span data-ttu-id="a4d57-114">Die Werte des `func` -Parameters und des- `retvalRange` Parameters sind nach der Rückgabe der Funktion ungültig, `FunctionLeave2` da sich die Werte möglicherweise ändern oder zerstört werden.</span><span class="sxs-lookup"><span data-stu-id="a4d57-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="a4d57-115">Die `FunctionLeave2` Funktion ist ein Rückruf. Sie müssen Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="a4d57-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="a4d57-116">Die-Implementierung muss das `__declspec` `naked` Speicher Klassen Attribut () verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4d57-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="a4d57-117">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="a4d57-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="a4d57-118">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="a4d57-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="a4d57-119">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="a4d57-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="a4d57-120">Die Implementierung von `FunctionLeave2` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="a4d57-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="a4d57-121">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="a4d57-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="a4d57-122">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionLeave2` .</span><span class="sxs-lookup"><span data-stu-id="a4d57-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="a4d57-123">Außerdem darf die `FunctionLeave2` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="a4d57-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4d57-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a4d57-124">Requirements</span></span>  
 <span data-ttu-id="a4d57-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4d57-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4d57-126">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="a4d57-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a4d57-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4d57-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4d57-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4d57-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d57-129">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a4d57-129">See also</span></span>

- [<span data-ttu-id="a4d57-130">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="a4d57-130">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="a4d57-131">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="a4d57-131">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="a4d57-132">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="a4d57-132">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="a4d57-133">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="a4d57-133">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
