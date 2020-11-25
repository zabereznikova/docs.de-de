---
title: FunctionTailcall2-Funktion
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: e1cd3ef78d303aaa325699e1bcdec95f077fef21
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703979"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="a2e98-102">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="a2e98-102">FunctionTailcall2 Function</span></span>

<span data-ttu-id="a2e98-103">Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt und Informationen über den Stapel Rahmen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a2e98-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2e98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2e98-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2e98-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2e98-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="a2e98-106">\[in] der Bezeichner der aktuell ausgeführten Funktion, die einen Tail-Aufruf durchführen soll.</span><span class="sxs-lookup"><span data-stu-id="a2e98-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `clientData`

  <span data-ttu-id="a2e98-107">\[in] der neu zugeordnete Funktions Bezeichner, den der Profiler zuvor über [FunctionIDMapper](functionidmapper-function.md)angegeben hat, der aktuell ausgeführten Funktion, die einen Tail-Aufruf durchführen soll.</span><span class="sxs-lookup"><span data-stu-id="a2e98-107">\[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>
  
- `func`

  <span data-ttu-id="a2e98-108">\[in] ein- `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapel Rahmen zeigt.</span><span class="sxs-lookup"><span data-stu-id="a2e98-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="a2e98-109">Der Profiler sollte dies als ein undurchsichtiges Handle behandeln, das an die Ausführungs-Engine in der [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) -Methode zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="a2e98-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2e98-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2e98-110">Remarks</span></span>  

 <span data-ttu-id="a2e98-111">Die Zielfunktion des Tail-Aufrufs verwendet den aktuellen Stapel Rahmen und kehrt direkt zum Aufrufer der Funktion zurück, die den Tail-Aufruf durchgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="a2e98-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="a2e98-112">Dies bedeutet, dass ein [FunctionLeave2](functionleave2-function.md) -Rückruf nicht für eine Funktion ausgegeben wird, die das Ziel eines Tail-Aufrufs ist.</span><span class="sxs-lookup"><span data-stu-id="a2e98-112">This means that a [FunctionLeave2](functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="a2e98-113">Der Wert des- `func` Parameters ist nicht gültig, nachdem die Funktion zurückgegeben wurde, `FunctionTailcall2` da sich der Wert ändern oder zerstört werden kann.</span><span class="sxs-lookup"><span data-stu-id="a2e98-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="a2e98-114">Die `FunctionTailcall2` Funktion ist ein Rückruf. Sie müssen Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="a2e98-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="a2e98-115">Die-Implementierung muss das `__declspec` `naked` Speicher Klassen Attribut () verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2e98-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="a2e98-116">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="a2e98-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="a2e98-117">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="a2e98-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="a2e98-118">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="a2e98-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="a2e98-119">Die Implementierung von `FunctionTailcall2` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="a2e98-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="a2e98-120">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="a2e98-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="a2e98-121">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionTailcall2` .</span><span class="sxs-lookup"><span data-stu-id="a2e98-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="a2e98-122">Außerdem darf die `FunctionTailcall2` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="a2e98-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2e98-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a2e98-123">Requirements</span></span>  

 <span data-ttu-id="a2e98-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2e98-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2e98-125">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="a2e98-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a2e98-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2e98-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2e98-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2e98-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e98-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2e98-128">See also</span></span>

- [<span data-ttu-id="a2e98-129">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="a2e98-129">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="a2e98-130">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="a2e98-130">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="a2e98-131">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="a2e98-131">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="a2e98-132">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="a2e98-132">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
