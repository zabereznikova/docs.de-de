---
title: FunctionTailcall-Funktion
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
ms.openlocfilehash: 02bc6f4bbb6754bd160fe2694f27563908f3a759
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722218"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="b7e22-102">FunctionTailcall-Funktion</span><span class="sxs-lookup"><span data-stu-id="b7e22-102">FunctionTailcall Function</span></span>

<span data-ttu-id="b7e22-103">Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="b7e22-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7e22-104">Die- `FunctionTailcall` Funktion ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="b7e22-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="b7e22-105">Es wird weiterhin funktionieren, führt jedoch zu einer Leistungs Einbuße.</span><span class="sxs-lookup"><span data-stu-id="b7e22-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="b7e22-106">Verwenden Sie stattdessen die [FunctionTailcall2](functiontailcall2-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="b7e22-106">Use the [FunctionTailcall2](functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7e22-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7e22-107">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7e22-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7e22-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="b7e22-109">\[in] der Bezeichner der aktuell ausgeführten Funktion, die einen Tail-Aufruf durchführen soll.</span><span class="sxs-lookup"><span data-stu-id="b7e22-109">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7e22-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7e22-110">Remarks</span></span>  

 <span data-ttu-id="b7e22-111">Die Zielfunktion des Tail-Aufrufs verwendet den aktuellen Stapel Rahmen und kehrt direkt zum Aufrufer der Funktion zurück, die den Tail-Aufruf durchgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="b7e22-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="b7e22-112">Dies bedeutet, dass ein [FunctionLeave](functionleave-function.md) -Rückruf nicht für eine Funktion ausgegeben wird, die das Ziel eines Tail-Aufrufs ist.</span><span class="sxs-lookup"><span data-stu-id="b7e22-112">This means that a [FunctionLeave](functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="b7e22-113">Die `FunctionTailcall` Funktion ist ein Rückruf. Sie müssen Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="b7e22-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="b7e22-114">Die-Implementierung muss das `__declspec` `naked` Speicher Klassen Attribut () verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7e22-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="b7e22-115">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="b7e22-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="b7e22-116">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="b7e22-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="b7e22-117">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="b7e22-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="b7e22-118">Die Implementierung von `FunctionTailcall` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="b7e22-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="b7e22-119">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="b7e22-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="b7e22-120">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionTailcall` .</span><span class="sxs-lookup"><span data-stu-id="b7e22-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="b7e22-121">Außerdem darf die `FunctionTailcall` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="b7e22-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7e22-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b7e22-122">Requirements</span></span>  

 <span data-ttu-id="b7e22-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7e22-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7e22-124">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="b7e22-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b7e22-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7e22-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7e22-126">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="b7e22-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e22-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7e22-127">See also</span></span>

- [<span data-ttu-id="b7e22-128">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="b7e22-128">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="b7e22-129">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="b7e22-129">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="b7e22-130">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="b7e22-130">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="b7e22-131">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="b7e22-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
