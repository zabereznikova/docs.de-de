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
ms.openlocfilehash: f7a945fb7ef10f995be2d779a88b98bbce2fdfb3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866842"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="8bce8-102">FunctionLeave3WithInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="8bce8-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="8bce8-103">Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird, und stellt ein Handle bereit, das an die [ICorProfilerInfo3:: GetFunctionLeave3Info-Methode](icorprofilerinfo3-getfunctionleave3info-method.md) zum Abrufen des Stapel Rahmens und des Rückgabewerts übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bce8-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bce8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8bce8-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bce8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8bce8-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="8bce8-106">\[in] der Bezeichner der Funktion, von der das Steuerelement zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8bce8-106">\[in] The identifier of the function from which control is returned.</span></span>

- `eltInfo`

  <span data-ttu-id="8bce8-107">\[in] ein undurchsichtiges handle, das Informationen zu einem angegebenen Stapel Rahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="8bce8-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="8bce8-108">Dieses Handle ist nur während des Rückrufs gültig, an den er übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="8bce8-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="8bce8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8bce8-109">Remarks</span></span>  
 <span data-ttu-id="8bce8-110">Die `FunctionLeave3WithInfo` Rückruf Methode benachrichtigt den Profiler, wenn Funktionen aufgerufen werden, und ermöglicht es dem Profiler, die [ICorProfilerInfo3:: GetFunctionLeave3Info-Methode](icorprofilerinfo3-getfunctionleave3info-method.md) zu verwenden, um den Rückgabewert zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8bce8-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="8bce8-111">Für den Zugriff auf Rückgabewert Informationen muss das `COR_PRF_ENABLE_FUNCTION_RETVAL`-Flag festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8bce8-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="8bce8-112">Der Profiler kann die [ICorProfilerInfo:: SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md) verwenden, um die Ereignisflags festzulegen, und dann die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo-Methode](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) verwenden, um die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="8bce8-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="8bce8-113">Die `FunctionLeave3WithInfo` Funktion ist ein Rückruf. Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="8bce8-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="8bce8-114">Die-Implementierung muss das `__declspec(naked)`-Speicher Klassen Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bce8-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="8bce8-115">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="8bce8-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="8bce8-116">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="8bce8-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="8bce8-117">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="8bce8-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="8bce8-118">Die Implementierung von `FunctionLeave3WithInfo` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="8bce8-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="8bce8-119">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="8bce8-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="8bce8-120">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis `FunctionLeave3WithInfo` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8bce8-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="8bce8-121">Die `FunctionLeave3WithInfo` Funktion darf keinen verwalteten Code abrufen oder eine verwaltete Speicher Belegung in irgendeiner Weise auslösen.</span><span class="sxs-lookup"><span data-stu-id="8bce8-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bce8-122">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8bce8-122">Requirements</span></span>  
 <span data-ttu-id="8bce8-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bce8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bce8-124">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="8bce8-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8bce8-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bce8-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bce8-126">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bce8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bce8-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bce8-127">See also</span></span>

- [<span data-ttu-id="8bce8-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="8bce8-128">GetFunctionLeave3Info</span></span>](icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="8bce8-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="8bce8-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="8bce8-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="8bce8-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="8bce8-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="8bce8-131">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="8bce8-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8bce8-132">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="8bce8-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8bce8-133">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="8bce8-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="8bce8-134">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="8bce8-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8bce8-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="8bce8-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="8bce8-136">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="8bce8-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="8bce8-137">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="8bce8-138">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="8bce8-138">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
