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
ms.openlocfilehash: 60276327617ae24e9bdcebf958613c21d3808429
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175186"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="5ff10-102">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="5ff10-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="5ff10-103">Benachrichtigt den Profiler, dass die aktuell ausgeführte Funktion einen Tail-Aufruf für eine andere Funktion ausführen wird, und stellt Informationen zum Stapelrahmen bereit.</span><span class="sxs-lookup"><span data-stu-id="5ff10-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff10-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ff10-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ff10-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ff10-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="5ff10-106">\[in] Der Bezeichner der aktuell ausgeführten Funktion, die im Begriff ist, einen Tail-Aufruf zu machen.</span><span class="sxs-lookup"><span data-stu-id="5ff10-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `clientData`

  <span data-ttu-id="5ff10-107">\[in] Der neu zugeordnete Funktionsbezeichner, den der Profiler zuvor über [FunctionIDMapper](functionidmapper-function.md)angegeben hat, der aktuell ausgeführten Funktion, die gerade einen Endaufruf ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="5ff10-107">\[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>
  
- `func`

  <span data-ttu-id="5ff10-108">\[in] `COR_PRF_FRAME_INFO` Ein Wert, der auf Informationen über den Stapelrahmen verweist.</span><span class="sxs-lookup"><span data-stu-id="5ff10-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="5ff10-109">Der Profiler sollte dies als undurchsichtiges Handle behandeln, das an das Ausführungsmodul in der [ICorProfilerInfo2::GetFunctionInfo2-Methode](icorprofilerinfo2-getfunctioninfo2-method.md) zurückübergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ff10-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ff10-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5ff10-110">Remarks</span></span>  
 <span data-ttu-id="5ff10-111">Die Zielfunktion des Tail-Aufrufs verwendet den aktuellen Stapelrahmen und kehrt direkt zum Aufrufer der Funktion zurück, die den Tail-Aufruf gemacht hat.</span><span class="sxs-lookup"><span data-stu-id="5ff10-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="5ff10-112">Dies bedeutet, dass ein [FunctionLeave2-Rückruf](functionleave2-function.md) nicht für eine Funktion ausgegeben wird, die das Ziel eines Tail-Aufrufs ist.</span><span class="sxs-lookup"><span data-stu-id="5ff10-112">This means that a [FunctionLeave2](functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="5ff10-113">Der Wert `func` des Parameters ist `FunctionTailcall2` ungültig, nachdem die Funktion zurückgegeben wurde, da sich der Wert ändern oder zerstören kann.</span><span class="sxs-lookup"><span data-stu-id="5ff10-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="5ff10-114">Die `FunctionTailcall2` Funktion ist ein Rückruf; Sie müssen es implementieren.</span><span class="sxs-lookup"><span data-stu-id="5ff10-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="5ff10-115">Die Implementierung muss `__declspec``naked`das ( ) Storage-Class-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ff10-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="5ff10-116">Das Ausführungsmodul speichert keine Register, bevor diese Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5ff10-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="5ff10-117">Beim Eintrag müssen Sie alle Register speichern, die Sie verwenden, einschließlich der Register in der Gleitkommaeinheit (FPU).</span><span class="sxs-lookup"><span data-stu-id="5ff10-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="5ff10-118">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter deaktivieren, die vom Aufrufer gedrückt wurden.</span><span class="sxs-lookup"><span data-stu-id="5ff10-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="5ff10-119">Die Implementierung `FunctionTailcall2` von sollte nicht blockiert werden, da die Garbage Collection verzögert wird.</span><span class="sxs-lookup"><span data-stu-id="5ff10-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="5ff10-120">Die Implementierung sollte keine Garbage Collection versuchen, da sich der Stapel möglicherweise nicht in einem Garbage Collection-freundlichen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="5ff10-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="5ff10-121">Wenn versucht wird, eine Garbage Collection zu `FunctionTailcall2` sammeln, wird die Laufzeit blockiert, bis sie zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5ff10-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="5ff10-122">Außerdem darf `FunctionTailcall2` die Funktion keinen verwalteten Code aufrufen oder in irgendeiner Weise eine verwaltete Speicherzuweisung verursachen.</span><span class="sxs-lookup"><span data-stu-id="5ff10-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff10-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5ff10-123">Requirements</span></span>  
 <span data-ttu-id="5ff10-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ff10-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff10-125">**Kopfzeile:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="5ff10-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5ff10-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ff10-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ff10-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ff10-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff10-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ff10-128">See also</span></span>

- [<span data-ttu-id="5ff10-129">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="5ff10-129">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="5ff10-130">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="5ff10-130">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="5ff10-131">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="5ff10-131">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="5ff10-132">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="5ff10-132">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
