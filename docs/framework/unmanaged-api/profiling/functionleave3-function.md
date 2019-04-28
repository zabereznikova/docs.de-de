---
title: FunctionLeave3-Funktion
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b31c3045b021bd3b00d2b2e42bf7a118110305b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598830"
---
# <a name="functionleave3-function"></a><span data-ttu-id="8a7b9-102">FunctionLeave3-Funktion</span><span class="sxs-lookup"><span data-stu-id="8a7b9-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="8a7b9-103">Benachrichtigt den Profiler, dass das Steuerelement aus einer Funktion zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a7b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a7b9-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a7b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a7b9-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="8a7b9-106">[in] Der Bezeichner der Funktion, die von dem die Steuerung zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a7b9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a7b9-107">Remarks</span></span>  
 <span data-ttu-id="8a7b9-108">Die `FunctionLeave3` Callback-Funktion benachrichtigt den Profiler an, wie Funktionen aufgerufen werden, aber Rückgabewert Überprüfung wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="8a7b9-109">Verwenden der [ICorProfilerInfo3:: Setenterleavefunctionhooks3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) auf die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="8a7b9-110">Die `FunctionLeave3` Funktion ist ein Rückruf, müssen Sie sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="8a7b9-111">Verwenden Sie die Implementierung muss die `__declspec(naked)` Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="8a7b9-112">Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="8a7b9-113">Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="8a7b9-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="8a7b9-114">Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="8a7b9-115">Die Implementierung der `FunctionLeave3` sollten nicht blockiert werden, da die Garbagecollection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="8a7b9-116">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="8a7b9-117">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionLeave3` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="8a7b9-118">Die `FunctionLeave3` Funktion muss nicht verwalteten Code aufrufen oder dazu führen, dass eine verwaltete speicherbelegung in keiner Weise.</span><span class="sxs-lookup"><span data-stu-id="8a7b9-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a7b9-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a7b9-119">Requirements</span></span>  
 <span data-ttu-id="8a7b9-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a7b9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a7b9-121">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="8a7b9-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8a7b9-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a7b9-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a7b9-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a7b9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a7b9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a7b9-124">See also</span></span>

- [<span data-ttu-id="8a7b9-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="8a7b9-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="8a7b9-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="8a7b9-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="8a7b9-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8a7b9-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="8a7b9-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8a7b9-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="8a7b9-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8a7b9-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="8a7b9-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="8a7b9-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="8a7b9-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8a7b9-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="8a7b9-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="8a7b9-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="8a7b9-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="8a7b9-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="8a7b9-134">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a7b9-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
