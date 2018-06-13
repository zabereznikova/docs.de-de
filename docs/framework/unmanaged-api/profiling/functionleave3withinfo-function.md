---
title: FunctionLeave3WithInfo-Funktion
ms.date: 03/30/2017
api_name:
- FunctionLeave3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3WithInfo
helpviewer_keywords:
- FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd87709a9e8b0e943bcf89aa528872d465526218
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454282"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="2edf5-102">FunctionLeave3WithInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="2edf5-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="2edf5-103">Benachrichtigt den Profiler, Steuerung von einer Funktion zurückgegeben wird, und stellt ein Handle, das übergeben werden kann die [ICorProfilerInfo3:: Getfunctionleave3info-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) auf den Stapelrahmen und den Rückgabewert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2edf5-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2edf5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2edf5-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2edf5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2edf5-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="2edf5-106">[in] Der Bezeichner der Funktion, von der die Steuerung zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="2edf5-106">[in] The identifier of the function from which control is returned.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="2edf5-107">[in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="2edf5-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="2edf5-108">Dieses Handle ist nur während des Rückrufs, an den er übergeben ist, gültig.</span><span class="sxs-lookup"><span data-stu-id="2edf5-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2edf5-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2edf5-109">Remarks</span></span>  
 <span data-ttu-id="2edf5-110">Die `FunctionLeave3WithInfo` Rückrufmethode benachrichtigt den Profiler, wie Funktionen aufgerufen werden, und ermöglicht es dem Profiler zum Verwenden der [ICorProfilerInfo3:: Getfunctionleave3info-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) , den Rückgabewert zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2edf5-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="2edf5-111">Informationen zum Rückgabewert, den Zugriff auf die `COR_PRF_ENABLE_FUNCTION_RETVAL` Flag muss festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2edf5-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="2edf5-112">Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) die Ereignisflags festlegen und dann mithilfe der [ICorProfilerInfo3:: Setenterleavefunctionhooks3withinfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) zum Registrieren Ihrer die Implementierung dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="2edf5-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="2edf5-113">Die `FunctionLeave3WithInfo` Funktion ist ein Rückruf; Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="2edf5-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="2edf5-114">Verwenden Sie die Implementierung muss die `__declspec(naked)` Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="2edf5-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="2edf5-115">Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="2edf5-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="2edf5-116">Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="2edf5-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="2edf5-117">Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="2edf5-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="2edf5-118">Die Implementierung der `FunctionLeave3WithInfo` sollte nicht blockiert werden, da es die Garbagecollection verzögert.</span><span class="sxs-lookup"><span data-stu-id="2edf5-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="2edf5-119">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection-freundliche-Status.</span><span class="sxs-lookup"><span data-stu-id="2edf5-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="2edf5-120">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionLeave3WithInfo` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2edf5-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="2edf5-121">Die `FunctionLeave3WithInfo` Funktion muss nicht verwalteten Code aufrufen oder dazu führen, dass eine verwaltete speicherbelegung in keiner Weise.</span><span class="sxs-lookup"><span data-stu-id="2edf5-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2edf5-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2edf5-122">Requirements</span></span>  
 <span data-ttu-id="2edf5-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2edf5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2edf5-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="2edf5-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2edf5-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2edf5-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2edf5-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2edf5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2edf5-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2edf5-127">See Also</span></span>  
 [<span data-ttu-id="2edf5-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="2edf5-128">GetFunctionLeave3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)  
 [<span data-ttu-id="2edf5-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="2edf5-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="2edf5-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="2edf5-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="2edf5-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="2edf5-131">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="2edf5-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2edf5-132">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="2edf5-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2edf5-133">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="2edf5-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="2edf5-134">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="2edf5-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2edf5-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="2edf5-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="2edf5-136">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="2edf5-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="2edf5-137">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="2edf5-138">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="2edf5-138">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
