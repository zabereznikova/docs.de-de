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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 238a5f19bd8cbd89a5537b2b9297bfa9e1f54613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952874"
---
# <a name="functionleave-function"></a><span data-ttu-id="7cc4a-102">FunctionLeave-Funktion</span><span class="sxs-lookup"><span data-stu-id="7cc4a-102">FunctionLeave Function</span></span>
<span data-ttu-id="7cc4a-103">Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7cc4a-104">Die `FunctionLeave` -Funktion ist in der .NET Framework 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="7cc4a-105">Es wird weiterhin funktionieren, führt jedoch zu einer Leistungs Einbuße.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="7cc4a-106">Verwenden Sie stattdessen die [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cc4a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cc4a-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cc4a-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="7cc4a-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="7cc4a-109">in Der Bezeichner der Funktion, die zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cc4a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cc4a-110">Remarks</span></span>  
 <span data-ttu-id="7cc4a-111">Die `FunctionLeave` Funktion ist ein Rückruf. Sie müssen Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="7cc4a-112">Die-Implementierung muss das `__declspec`Speicher`naked`Klassen Attribut () verwenden.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="7cc4a-113">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="7cc4a-114">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="7cc4a-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="7cc4a-115">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="7cc4a-116">Die Implementierung von `FunctionLeave` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="7cc4a-117">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="7cc4a-118">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit `FunctionLeave` blockiert, bis von zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="7cc4a-119">Außerdem darf die `FunctionLeave` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="7cc4a-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cc4a-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7cc4a-120">Requirements</span></span>  
 <span data-ttu-id="7cc4a-121">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cc4a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cc4a-122">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7cc4a-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7cc4a-123">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cc4a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cc4a-124">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="7cc4a-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc4a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cc4a-125">See also</span></span>

- [<span data-ttu-id="7cc4a-126">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7cc4a-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="7cc4a-127">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7cc4a-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="7cc4a-128">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7cc4a-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="7cc4a-129">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="7cc4a-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="7cc4a-130">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="7cc4a-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
