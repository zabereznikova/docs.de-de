---
title: FunctionTailcall3WithInfo-Funktion
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f1c64615dae205161583c7a79575204932cd17b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586867"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="61154-102">FunctionTailcall3WithInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="61154-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="61154-103">Benachrichtigt den Profiler, der aktuell ausgeführte Funktion einen Endeaufruf an eine andere Funktion auszuführen, und stellt ein Handle übergeben werden kann, die die [ICorProfilerInfo3:: Getfunctiontailcall3info-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) zum Abrufen der Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="61154-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61154-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61154-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61154-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61154-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="61154-106">[in] Der Bezeichner der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="61154-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="61154-107">[in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="61154-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="61154-108">Dieses Handle ist gültig nur während des Rückrufs, der an den er übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="61154-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61154-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61154-109">Remarks</span></span>  
 <span data-ttu-id="61154-110">Die `FunctionTailcall3WithInfo` Rückrufmethode benachrichtigt den Profiler an, wie Funktionen aufgerufen werden, und ermöglicht es dem Profiler mit den [ICorProfilerInfo3:: Getfunctiontailcall3info-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) , den Stapelrahmen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="61154-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="61154-111">Informationen über Stapelrahmen, den Zugriff auf die `COR_PRF_ENABLE_FRAME_INFO` Flag muss festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="61154-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="61154-112">Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) die Ereignisflags festlegen, und klicken Sie dann die [ICorProfilerInfo3:: Setenterleavefunctionhooks3withinfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) zum Registrieren Ihrer die Implementierung dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="61154-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="61154-113">Die `FunctionTailcall3WithInfo` Funktion ist ein Rückruf, müssen Sie sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="61154-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="61154-114">Verwenden Sie die Implementierung muss die `__declspec(naked)` Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="61154-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="61154-115">Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="61154-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="61154-116">Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="61154-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="61154-117">Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="61154-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="61154-118">Die Implementierung der `FunctionTailcall3WithInfo` sollten nicht blockiert werden, da die Garbagecollection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="61154-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="61154-119">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand.</span><span class="sxs-lookup"><span data-stu-id="61154-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="61154-120">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionTailcall3WithInfo` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="61154-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="61154-121">Die FunctionTailcall3WithInfo-Funktion muss außerdem nicht verwalteten Code aufrufen oder dazu führen, dass eine verwaltete speicherbelegung in keiner Weise.</span><span class="sxs-lookup"><span data-stu-id="61154-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61154-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61154-122">Requirements</span></span>  
 <span data-ttu-id="61154-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61154-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61154-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="61154-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="61154-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61154-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61154-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61154-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61154-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61154-127">See also</span></span>

- [<span data-ttu-id="61154-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="61154-128">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="61154-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="61154-129">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="61154-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="61154-130">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="61154-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="61154-131">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="61154-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="61154-132">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="61154-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="61154-133">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="61154-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="61154-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="61154-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="61154-135">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="61154-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="61154-136">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="61154-137">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="61154-137">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
