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
ms.openlocfilehash: e40687f7f843dc563801bb01b503d2ae94a094fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446015"
---
# <a name="functionleave2-function"></a><span data-ttu-id="a45e5-102">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="a45e5-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="a45e5-103">Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren, und stellt Informationen zum Stapel Rahmen und Funktionsrückgabewert bereit.</span><span class="sxs-lookup"><span data-stu-id="a45e5-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a45e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a45e5-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a45e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a45e5-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="a45e5-106">in Der Bezeichner der Funktion, die zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a45e5-106">[in] The identifier of the function that is returning.</span></span>  
  
 `clientData`  
 <span data-ttu-id="a45e5-107">in Der neu zugeordnete Funktions Bezeichner, den der Profiler zuvor über die [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) -Funktion angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="a45e5-107">[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="a45e5-108">in Ein `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapel Rahmen zeigt.</span><span class="sxs-lookup"><span data-stu-id="a45e5-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="a45e5-109">Der Profiler sollte dies als ein undurchsichtiges Handle behandeln, das an die Ausführungs-Engine in der [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) -Methode zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="a45e5-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `retvalRange`  
 <span data-ttu-id="a45e5-110">in Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) -Struktur, die die Speicherposition des Rückgabewerts der Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="a45e5-110">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>  
  
 <span data-ttu-id="a45e5-111">Um auf Rückgabewert Informationen zugreifen zu können, muss das `COR_PRF_ENABLE_FUNCTION_RETVAL`-Flag festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a45e5-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="a45e5-112">Der Profiler kann die [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um die Ereignisflags festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a45e5-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a45e5-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a45e5-113">Remarks</span></span>  
 <span data-ttu-id="a45e5-114">Die Werte der Parameter "`func`" und "`retvalRange`" sind nicht gültig, nachdem die `FunctionLeave2` Funktion zurückgegeben wurde, da sich die Werte ändern oder gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="a45e5-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="a45e5-115">Die `FunctionLeave2` Funktion ist ein Rückruf. Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="a45e5-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="a45e5-116">Die-Implementierung muss das `__declspec`(`naked`)-Speicher Klassen Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="a45e5-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="a45e5-117">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="a45e5-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="a45e5-118">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="a45e5-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="a45e5-119">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="a45e5-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="a45e5-120">Die Implementierung von `FunctionLeave2` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="a45e5-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="a45e5-121">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="a45e5-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="a45e5-122">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis `FunctionLeave2` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a45e5-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="a45e5-123">Außerdem darf die `FunctionLeave2` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="a45e5-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a45e5-124">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a45e5-124">Requirements</span></span>  
 <span data-ttu-id="a45e5-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a45e5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a45e5-126">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="a45e5-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a45e5-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a45e5-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a45e5-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a45e5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a45e5-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a45e5-129">See also</span></span>

- [<span data-ttu-id="a45e5-130">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="a45e5-130">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="a45e5-131">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="a45e5-131">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="a45e5-132">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="a45e5-132">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="a45e5-133">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="a45e5-133">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
