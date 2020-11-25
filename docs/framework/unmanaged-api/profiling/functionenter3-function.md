---
title: FunctionEnter3-Funktion
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
ms.openlocfilehash: 98a821eabb393d8b5042647e6ef6ffce7ab10783
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722881"
---
# <a name="functionenter3-function"></a><span data-ttu-id="4cb20-102">FunctionEnter3-Funktion</span><span class="sxs-lookup"><span data-stu-id="4cb20-102">FunctionEnter3 Function</span></span>

<span data-ttu-id="4cb20-103">Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="4cb20-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cb20-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cb20-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4cb20-105">Parameters</span></span>

- `functionOrRemappedID`

  <span data-ttu-id="4cb20-106">\[in] der Bezeichner der Funktion, an die das Steuerelement übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="4cb20-106">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="4cb20-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4cb20-107">Remarks</span></span>  

 <span data-ttu-id="4cb20-108">Die `FunctionEnter3` Rückruffunktion benachrichtigt den Profiler, dass Funktionen aufgerufen werden, unterstützt jedoch keine Argument Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="4cb20-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="4cb20-109">Verwenden Sie die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3-Methode](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) , um die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4cb20-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="4cb20-110">Die `FunctionEnter3` Funktion ist ein Rückruf. Sie müssen Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="4cb20-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="4cb20-111">Die-Implementierung muss das `__declspec(naked)` Speicher Klassen Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cb20-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="4cb20-112">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="4cb20-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="4cb20-113">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="4cb20-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="4cb20-114">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="4cb20-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb20-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4cb20-115">Requirements</span></span>  

 <span data-ttu-id="4cb20-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cb20-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb20-117">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="4cb20-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4cb20-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cb20-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cb20-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb20-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb20-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4cb20-120">See also</span></span>

- [<span data-ttu-id="4cb20-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="4cb20-121">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="4cb20-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="4cb20-122">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="4cb20-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4cb20-123">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="4cb20-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4cb20-124">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="4cb20-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4cb20-125">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="4cb20-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="4cb20-126">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="4cb20-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4cb20-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="4cb20-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="4cb20-128">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="4cb20-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="4cb20-129">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="4cb20-130">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="4cb20-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
