---
title: FunctionLeave2-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave2
helpviewer_keywords: FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86ffb6cc18de0b0b7b68b418477c1e8cdd6e6cc7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="functionleave2-function"></a><span data-ttu-id="ea619-102">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="ea619-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="ea619-103">Benachrichtigt den Profiler, dass eine Funktion an den Aufrufer zurückgegeben wird, und Informationen über den Stapel und -Rückgabewert enthält.</span><span class="sxs-lookup"><span data-stu-id="ea619-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea619-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea619-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea619-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea619-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="ea619-106">[in] Der Bezeichner der Funktion, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ea619-106">[in] The identifier of the function that is returning.</span></span>  
  
 `clientData`  
 <span data-ttu-id="ea619-107">[in] Der Funktionsbezeichner, die zuvor angegeben haben der Profiler über den [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="ea619-107">[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="ea619-108">[in] Ein `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapelrahmen verweist.</span><span class="sxs-lookup"><span data-stu-id="ea619-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="ea619-109">Der Profiler sollte dies als ein nicht transparentes Handle, das an das Ausführungsmodul in zurückgegeben werden kann behandeln die [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="ea619-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `retvalRange`  
 <span data-ttu-id="ea619-110">[in] Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) -Struktur, die Speicheradresse des Rückgabewerts der Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="ea619-110">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>  
  
 <span data-ttu-id="ea619-111">Zugriff auf Informationen zum Rückgabewert, der `COR_PRF_ENABLE_FUNCTION_RETVAL` Flag muss festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ea619-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="ea619-112">Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode, um die Ereignisflags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ea619-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea619-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea619-113">Remarks</span></span>  
 <span data-ttu-id="ea619-114">Die Werte der `func` und `retvalRange` Parameter sind nicht gültig, nachdem die `FunctionLeave2` zurückgegeben, da die Werte möglicherweise geändert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ea619-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="ea619-115">Die `FunctionLeave2` Funktion ist ein Rückruf; Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="ea619-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="ea619-116">Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="ea619-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ea619-117">Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="ea619-117">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="ea619-118">Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="ea619-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="ea619-119">Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="ea619-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ea619-120">Die Implementierung der `FunctionLeave2` sollte nicht blockiert werden, da es die Garbagecollection verzögert.</span><span class="sxs-lookup"><span data-stu-id="ea619-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ea619-121">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection-freundliche-Status.</span><span class="sxs-lookup"><span data-stu-id="ea619-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ea619-122">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionLeave2` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ea619-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="ea619-123">Darüber hinaus die `FunctionLeave2` muss nicht Funktionsaufruf in verwaltetem Code oder auch eine verwaltete speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="ea619-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea619-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea619-124">Requirements</span></span>  
 <span data-ttu-id="ea619-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea619-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea619-126">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ea619-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ea619-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea619-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea619-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea619-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea619-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea619-129">See Also</span></span>  
 [<span data-ttu-id="ea619-130">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="ea619-130">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="ea619-131">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="ea619-131">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="ea619-132">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="ea619-132">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="ea619-133">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="ea619-133">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
