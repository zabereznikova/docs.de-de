---
title: FunctionEnter2-Funktion
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: 8c88e97f8187ac347f4ff39890c8d87ee80c8f9e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500714"
---
# <a name="functionenter2-function"></a><span data-ttu-id="66168-102">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="66168-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="66168-103">Benachrichtigt den Profiler, dass die Steuerung an eine Funktion übermittelt wird, und stellt Informationen über den Stapel Rahmen und die Funktionsargumente bereit.</span><span class="sxs-lookup"><span data-stu-id="66168-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="66168-104">Diese Funktion löst die [FunctionEnter](functionenter-function.md) -Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="66168-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66168-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="66168-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66168-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="66168-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="66168-107">\[in] der Bezeichner der Funktion, an die das Steuerelement übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="66168-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="66168-108">\[in] der neu zugeordnete Funktions Bezeichner, den der Profiler zuvor mithilfe der [FunctionIDMapper](functionidmapper-function.md) -Funktion angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="66168-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="66168-109">\[in] ein- `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapel Rahmen zeigt.</span><span class="sxs-lookup"><span data-stu-id="66168-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="66168-110">Der Profiler sollte dies als ein undurchsichtiges Handle behandeln, das an die Ausführungs-Engine in der [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) -Methode zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="66168-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="66168-111">\[in] ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) -Struktur, die die Speicherorte im Speicher der Argumente der Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="66168-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="66168-112">Um auf Argument Informationen zuzugreifen, muss das- `COR_PRF_ENABLE_FUNCTION_ARGS` Flag festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="66168-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="66168-113">Der Profiler kann die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um die Ereignisflags festzulegen.</span><span class="sxs-lookup"><span data-stu-id="66168-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="66168-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="66168-114">Remarks</span></span>  
 <span data-ttu-id="66168-115">Die Werte des `func` -Parameters und des- `argumentInfo` Parameters sind nach der Rückgabe der Funktion ungültig, `FunctionEnter2` da sich die Werte möglicherweise ändern oder zerstört werden.</span><span class="sxs-lookup"><span data-stu-id="66168-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="66168-116">Die `FunctionEnter2` Funktion ist ein Rückruf. Sie müssen Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="66168-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="66168-117">Die-Implementierung muss das `__declspec` `naked` Speicher Klassen Attribut () verwenden.</span><span class="sxs-lookup"><span data-stu-id="66168-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="66168-118">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="66168-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="66168-119">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="66168-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="66168-120">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="66168-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="66168-121">Die Implementierung von `FunctionEnter2` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="66168-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="66168-122">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="66168-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="66168-123">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionEnter2` .</span><span class="sxs-lookup"><span data-stu-id="66168-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="66168-124">Außerdem darf die `FunctionEnter2` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="66168-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66168-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="66168-125">Requirements</span></span>  
 <span data-ttu-id="66168-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66168-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66168-127">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="66168-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="66168-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66168-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66168-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66168-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66168-130">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="66168-130">See also</span></span>

- [<span data-ttu-id="66168-131">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="66168-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="66168-132">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="66168-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="66168-133">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="66168-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="66168-134">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="66168-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
