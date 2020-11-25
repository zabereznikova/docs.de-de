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
ms.openlocfilehash: 8eaf36579bb82d66ff356aa68afc38c70d7eaca3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720385"
---
# <a name="functionleave3-function"></a><span data-ttu-id="e9d2d-102">FunctionLeave3-Funktion</span><span class="sxs-lookup"><span data-stu-id="e9d2d-102">FunctionLeave3 Function</span></span>

<span data-ttu-id="e9d2d-103">Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d2d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9d2d-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9d2d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9d2d-105">Parameters</span></span>  

- `functionOrRemappedID`

  <span data-ttu-id="e9d2d-106">\[in] der Bezeichner der Funktion, von der das Steuerelement zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-106">\[in] The identifier of the function from which control is returned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e9d2d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9d2d-107">Remarks</span></span>  

 <span data-ttu-id="e9d2d-108">Die `FunctionLeave3` Rückruffunktion benachrichtigt den Profiler, dass Funktionen aufgerufen werden, unterstützt jedoch keine Überprüfung des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="e9d2d-109">Verwenden Sie die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3-Methode](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) , um die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="e9d2d-110">Die `FunctionLeave3` Funktion ist ein Rückruf. Sie müssen Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="e9d2d-111">Die-Implementierung muss das `__declspec(naked)` Speicher Klassen Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="e9d2d-112">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="e9d2d-113">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="e9d2d-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="e9d2d-114">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e9d2d-115">Die Implementierung von `FunctionLeave3` sollte nicht blockieren, da Garbage Collection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="e9d2d-116">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e9d2d-117">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionLeave3` .</span><span class="sxs-lookup"><span data-stu-id="e9d2d-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="e9d2d-118">Die `FunctionLeave3` Funktion darf keinen verwalteten Code anrufen oder eine verwaltete Speicher Belegung in irgendeiner Weise auslösen.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9d2d-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e9d2d-119">Requirements</span></span>  

 <span data-ttu-id="e9d2d-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9d2d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d2d-121">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="e9d2d-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e9d2d-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9d2d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9d2d-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d2d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d2d-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9d2d-124">See also</span></span>

- [<span data-ttu-id="e9d2d-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="e9d2d-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="e9d2d-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="e9d2d-126">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="e9d2d-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e9d2d-127">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="e9d2d-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e9d2d-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="e9d2d-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e9d2d-129">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="e9d2d-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="e9d2d-130">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="e9d2d-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e9d2d-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="e9d2d-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="e9d2d-132">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="e9d2d-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="e9d2d-133">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="e9d2d-134">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="e9d2d-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
