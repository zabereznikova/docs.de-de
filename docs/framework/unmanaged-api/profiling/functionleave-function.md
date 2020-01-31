---
title: FunctionLeave-Funktion
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: a9ab8c81c995bbec41db217c904e03dd70351aee
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866883"
---
# <a name="functionleave-function"></a><span data-ttu-id="3f187-102">FunctionLeave-Funktion</span><span class="sxs-lookup"><span data-stu-id="3f187-102">FunctionLeave Function</span></span>
<span data-ttu-id="3f187-103">Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="3f187-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f187-104">Die `FunctionLeave`-Funktion ist in der .NET Framework 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="3f187-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="3f187-105">Es wird weiterhin funktionieren, führt jedoch zu einer Leistungs Einbuße.</span><span class="sxs-lookup"><span data-stu-id="3f187-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="3f187-106">Verwenden Sie stattdessen die [FunctionLeave2](functionleave2-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="3f187-106">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f187-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f187-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f187-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="3f187-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="3f187-109">\[in] der Bezeichner der Funktion, die zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f187-109">\[in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f187-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f187-110">Remarks</span></span>  
 <span data-ttu-id="3f187-111">Die `FunctionLeave` Funktion ist ein Rückruf. Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="3f187-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="3f187-112">Die-Implementierung muss das `__declspec`(`naked`)-Speicher Klassen Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f187-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="3f187-113">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="3f187-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="3f187-114">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="3f187-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="3f187-115">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="3f187-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="3f187-116">Die Implementierung von `FunctionLeave` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="3f187-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="3f187-117">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="3f187-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="3f187-118">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis `FunctionLeave` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f187-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="3f187-119">Außerdem darf die `FunctionLeave` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="3f187-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f187-120">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3f187-120">Requirements</span></span>  
 <span data-ttu-id="3f187-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f187-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f187-122">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="3f187-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3f187-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f187-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f187-124">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="3f187-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f187-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f187-125">See also</span></span>

- [<span data-ttu-id="3f187-126">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="3f187-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="3f187-127">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="3f187-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="3f187-128">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="3f187-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="3f187-129">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="3f187-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="3f187-130">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="3f187-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
