---
title: FunctionTailcall3-Funktion
ms.date: 03/30/2017
api_name:
- FunctionTailcall3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3
helpviewer_keywords:
- FunctionTailcall3 function [.NET Framework profiling]
ms.assetid: 1e48243f-5de6-4bd6-a1d0-e1d248bca4b8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aec2304e00d5328fcf55adbf5521c08865c05c56
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763304"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="51f49-102">FunctionTailcall3-Funktion</span><span class="sxs-lookup"><span data-stu-id="51f49-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="51f49-103">Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="51f49-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f49-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51f49-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51f49-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="51f49-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="51f49-106">[in] Der Bezeichner der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="51f49-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51f49-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51f49-107">Remarks</span></span>  
 <span data-ttu-id="51f49-108">Die `FunctionTailcall3` Rückruffunktion benachrichtigt den Profiler an, wie Funktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="51f49-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="51f49-109">Verwenden der [ICorProfilerInfo3:: Setenterleavefunctionhooks3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) auf die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="51f49-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="51f49-110">Die `FunctionTailcall3` Funktion ist ein Rückruf, müssen Sie sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="51f49-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="51f49-111">Verwenden Sie die Implementierung muss die `__declspec(naked)` Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="51f49-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="51f49-112">Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="51f49-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="51f49-113">Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="51f49-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="51f49-114">Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="51f49-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="51f49-115">Die Implementierung der `FunctionTailcall3` sollten nicht blockiert werden, da die Garbagecollection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="51f49-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="51f49-116">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand.</span><span class="sxs-lookup"><span data-stu-id="51f49-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="51f49-117">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionTailcall3` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="51f49-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="51f49-118">Die `FunctionTailcall3` Funktion muss nicht verwalteten Code aufrufen oder dazu führen, dass eine verwaltete speicherbelegung in keiner Weise.</span><span class="sxs-lookup"><span data-stu-id="51f49-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51f49-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51f49-119">Requirements</span></span>  
 <span data-ttu-id="51f49-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51f49-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51f49-121">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="51f49-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="51f49-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51f49-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51f49-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51f49-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f49-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51f49-124">See also</span></span>

- [<span data-ttu-id="51f49-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="51f49-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="51f49-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="51f49-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="51f49-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="51f49-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="51f49-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="51f49-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="51f49-129">FunctionTailcall3WithInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="51f49-129">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="51f49-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="51f49-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="51f49-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="51f49-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="51f49-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="51f49-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="51f49-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="51f49-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="51f49-134">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="51f49-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
