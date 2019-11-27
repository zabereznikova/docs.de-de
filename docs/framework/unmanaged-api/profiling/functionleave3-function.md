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
ms.openlocfilehash: 104a6c3c42c310513040cb45db7f51ffe729c19d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427440"
---
# <a name="functionleave3-function"></a><span data-ttu-id="7ec9e-102">FunctionLeave3-Funktion</span><span class="sxs-lookup"><span data-stu-id="7ec9e-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="7ec9e-103">Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ec9e-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ec9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ec9e-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="7ec9e-106">in Der Bezeichner der Funktion, von der das Steuerelement zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ec9e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ec9e-107">Remarks</span></span>  
 <span data-ttu-id="7ec9e-108">Die `FunctionLeave3` Callback-Funktion benachrichtigt den Profiler, dass Funktionen aufgerufen werden, unterstützt jedoch keine Überprüfung des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="7ec9e-109">Verwenden Sie die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) , um die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="7ec9e-110">Die `FunctionLeave3` Funktion ist ein Rückruf. Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="7ec9e-111">Die-Implementierung muss das `__declspec(naked)`-Speicher Klassen Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="7ec9e-112">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="7ec9e-113">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="7ec9e-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="7ec9e-114">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="7ec9e-115">Die Implementierung von `FunctionLeave3` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="7ec9e-116">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="7ec9e-117">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis `FunctionLeave3` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="7ec9e-118">Die `FunctionLeave3` Funktion darf keinen verwalteten Code abrufen oder eine verwaltete Speicher Belegung in irgendeiner Weise auslösen.</span><span class="sxs-lookup"><span data-stu-id="7ec9e-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ec9e-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7ec9e-119">Requirements</span></span>  
 <span data-ttu-id="7ec9e-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ec9e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ec9e-121">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="7ec9e-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7ec9e-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ec9e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ec9e-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ec9e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec9e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ec9e-124">See also</span></span>

- [<span data-ttu-id="7ec9e-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="7ec9e-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="7ec9e-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="7ec9e-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="7ec9e-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7ec9e-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="7ec9e-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7ec9e-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="7ec9e-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7ec9e-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="7ec9e-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="7ec9e-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="7ec9e-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7ec9e-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="7ec9e-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="7ec9e-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="7ec9e-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="7ec9e-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="7ec9e-134">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="7ec9e-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
