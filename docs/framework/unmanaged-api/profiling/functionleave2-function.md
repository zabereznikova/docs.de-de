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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bde206d56bc7e8c930e1e428512232caccfb940
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586847"
---
# <a name="functionleave2-function"></a><span data-ttu-id="82875-102">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="82875-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="82875-103">Benachrichtigt den Profiler, dass eine Funktion an den Aufrufer zurückgegeben wird, und Informationen über den Stapel Frame und Funktion-Rückgabewert enthält.</span><span class="sxs-lookup"><span data-stu-id="82875-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82875-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82875-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82875-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82875-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="82875-106">[in] Der Bezeichner der Funktion, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="82875-106">[in] The identifier of the function that is returning.</span></span>  
  
 `clientData`  
 <span data-ttu-id="82875-107">[in] Der Funktionsbezeichner, die zuvor angegeben haben der Profiler über den [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="82875-107">[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="82875-108">[in] Ein `COR_PRF_FRAME_INFO` -Wert, der auf Informationen über den Stapelrahmen verweist.</span><span class="sxs-lookup"><span data-stu-id="82875-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="82875-109">Der Profiler sollte dies als ein nicht transparentes Handle, das an die ausführungs-Engine in zurückgegeben werden kann behandeln die [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="82875-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `retvalRange`  
 <span data-ttu-id="82875-110">[in] Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) Struktur, die den Speicherort des Rückgabewerts der Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="82875-110">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>  
  
 <span data-ttu-id="82875-111">Informationen zum Rückgabewert, den Zugriff auf die `COR_PRF_ENABLE_FUNCTION_RETVAL` Flag festgelegt werden muss.</span><span class="sxs-lookup"><span data-stu-id="82875-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="82875-112">Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode, um die Ereignisflags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="82875-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82875-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82875-113">Remarks</span></span>  
 <span data-ttu-id="82875-114">Die Werte der `func` und `retvalRange` Parameter sind nicht gültig, nachdem die `FunctionLeave2` Funktion zurückgegeben werden, da die Werte möglicherweise geändert oder zerstört werden.</span><span class="sxs-lookup"><span data-stu-id="82875-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="82875-115">Die `FunctionLeave2` Funktion ist ein Rückruf, müssen Sie sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="82875-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="82875-116">Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="82875-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="82875-117">Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="82875-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="82875-118">Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="82875-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="82875-119">Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="82875-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="82875-120">Die Implementierung der `FunctionLeave2` sollten nicht blockiert werden, da die Garbagecollection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="82875-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="82875-121">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand.</span><span class="sxs-lookup"><span data-stu-id="82875-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="82875-122">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionLeave2` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="82875-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="82875-123">Darüber hinaus die `FunctionLeave2` Funktion darf keinen Aufrufen in verwaltetem Code oder auch eine verwaltete speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="82875-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82875-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82875-124">Requirements</span></span>  
 <span data-ttu-id="82875-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82875-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82875-126">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="82875-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="82875-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82875-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82875-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82875-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82875-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82875-129">See also</span></span>

- [<span data-ttu-id="82875-130">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="82875-130">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="82875-131">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="82875-131">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="82875-132">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="82875-132">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="82875-133">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="82875-133">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
