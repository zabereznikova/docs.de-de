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
ms.openlocfilehash: f076044b44859cc39d90be528ee6648f5eaa626c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500584"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="cacfe-102">FunctionTailcall3WithInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="cacfe-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="cacfe-103">Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Tail-Aufruf einer anderen Funktion ausführt, und stellt ein Handle bereit, das an die [ICorProfilerInfo3:: GetFunctionTailcall3Info-Methode](icorprofilerinfo3-getfunctiontailcall3info-method.md) zum Abrufen des Stapel Rahmens übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cacfe-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cacfe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cacfe-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cacfe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cacfe-105">Parameters</span></span>  

- `functionIDOrClientID`

  <span data-ttu-id="cacfe-106">\[in] der Bezeichner der aktuell ausgeführten Funktion, die einen Tail-Aufruf durchführen soll.</span><span class="sxs-lookup"><span data-stu-id="cacfe-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `eltInfo`

  <span data-ttu-id="cacfe-107">\[in] ein undurchsichtiges handle, das Informationen zu einem angegebenen Stapel Rahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="cacfe-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="cacfe-108">Dieses Handle ist nur während des Rückrufs gültig, an den er übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="cacfe-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="cacfe-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cacfe-109">Remarks</span></span>  
 <span data-ttu-id="cacfe-110">Die `FunctionTailcall3WithInfo` Rückruf Methode benachrichtigt den Profiler, wenn Funktionen aufgerufen werden, und ermöglicht es dem Profiler, mithilfe der [ICorProfilerInfo3:: GetFunctionTailcall3Info-Methode](icorprofilerinfo3-getfunctiontailcall3info-method.md) den Stapel Rahmen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cacfe-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="cacfe-111">Für den Zugriff auf Stapel Rahmen Informationen `COR_PRF_ENABLE_FRAME_INFO` muss das-Flag festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cacfe-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="cacfe-112">Der Profiler kann die [ICorProfilerInfo:: SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md) verwenden, um die Ereignisflags festzulegen, und dann die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo-Methode](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) verwenden, um die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="cacfe-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="cacfe-113">Die `FunctionTailcall3WithInfo` Funktion ist ein Rückruf. Sie müssen Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="cacfe-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="cacfe-114">Die-Implementierung muss das `__declspec(naked)` Speicher Klassen Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="cacfe-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="cacfe-115">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="cacfe-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="cacfe-116">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="cacfe-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="cacfe-117">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="cacfe-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="cacfe-118">Die Implementierung von `FunctionTailcall3WithInfo` sollte nicht blockieren, da Garbage Collection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="cacfe-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="cacfe-119">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="cacfe-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="cacfe-120">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionTailcall3WithInfo` .</span><span class="sxs-lookup"><span data-stu-id="cacfe-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="cacfe-121">Außerdem darf die FunctionTailcall3WithInfo-Funktion keinen verwalteten Code abrufen oder eine verwaltete Speicher Belegung in irgendeiner Weise auslösen.</span><span class="sxs-lookup"><span data-stu-id="cacfe-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cacfe-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cacfe-122">Requirements</span></span>  
 <span data-ttu-id="cacfe-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cacfe-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cacfe-124">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="cacfe-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="cacfe-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cacfe-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cacfe-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cacfe-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cacfe-127">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="cacfe-127">See also</span></span>

- [<span data-ttu-id="cacfe-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="cacfe-128">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="cacfe-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="cacfe-129">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="cacfe-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="cacfe-130">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="cacfe-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="cacfe-131">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="cacfe-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="cacfe-132">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="cacfe-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="cacfe-133">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="cacfe-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="cacfe-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="cacfe-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="cacfe-135">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="cacfe-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="cacfe-136">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="cacfe-137">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="cacfe-137">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
