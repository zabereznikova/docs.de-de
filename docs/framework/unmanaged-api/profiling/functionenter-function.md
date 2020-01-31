---
title: FunctionEnter-Funktion
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
ms.openlocfilehash: caea1d3d526017c0118f95bb138ee4ac45d2c137
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866995"
---
# <a name="functionenter-function"></a><span data-ttu-id="9dffa-102">FunctionEnter-Funktion</span><span class="sxs-lookup"><span data-stu-id="9dffa-102">FunctionEnter Function</span></span>
<span data-ttu-id="9dffa-103">Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="9dffa-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9dffa-104">Die `FunctionEnter`-Funktion ist in der .NET Framework Version 2,0 veraltet, und ihre Verwendung führt zu einer Leistungs Einbuße.</span><span class="sxs-lookup"><span data-stu-id="9dffa-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="9dffa-105">Verwenden Sie stattdessen die [FunctionEnter2](functionenter2-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="9dffa-105">Use the [FunctionEnter2](functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dffa-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9dffa-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dffa-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="9dffa-107">Parameters</span></span>

- `funcID`

  <span data-ttu-id="9dffa-108">\[in] der Bezeichner der Funktion, an die das Steuerelement übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="9dffa-108">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="9dffa-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9dffa-109">Remarks</span></span>  
 <span data-ttu-id="9dffa-110">Die `FunctionEnter` Funktion ist ein Rückruf. Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="9dffa-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="9dffa-111">Die-Implementierung muss das `__declspec`(`naked`)-Speicher Klassen Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="9dffa-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="9dffa-112">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="9dffa-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="9dffa-113">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="9dffa-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="9dffa-114">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="9dffa-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="9dffa-115">Die Implementierung von `FunctionEnter` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="9dffa-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="9dffa-116">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="9dffa-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="9dffa-117">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis `FunctionEnter` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9dffa-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="9dffa-118">Außerdem darf die `FunctionEnter` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="9dffa-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dffa-119">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9dffa-119">Requirements</span></span>  
 <span data-ttu-id="9dffa-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dffa-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dffa-121">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="9dffa-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="9dffa-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dffa-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dffa-123">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="9dffa-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dffa-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dffa-124">See also</span></span>

- [<span data-ttu-id="9dffa-125">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="9dffa-125">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="9dffa-126">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="9dffa-126">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="9dffa-127">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="9dffa-127">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="9dffa-128">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="9dffa-128">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="9dffa-129">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="9dffa-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
