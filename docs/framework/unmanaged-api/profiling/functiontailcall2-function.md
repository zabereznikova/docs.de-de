---
title: FunctionTailcall2-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall2
helpviewer_keywords: FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c1f9b0f6a83b774f6b308f7d4daa068eadebcce4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="75dfd-102">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="75dfd-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="75dfd-103">Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen und enthält Informationen über den Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="75dfd-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75dfd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75dfd-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75dfd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="75dfd-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="75dfd-106">[in] Der Bezeichner der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="75dfd-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="75dfd-107">[in] Der Funktionsbezeichner, die der Profiler zuvor über angegeben [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="75dfd-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="75dfd-108">[in] Ein `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapelrahmen verweist.</span><span class="sxs-lookup"><span data-stu-id="75dfd-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="75dfd-109">Der Profiler sollte dies als ein nicht transparentes Handle, das an das Ausführungsmodul in zurückgegeben werden kann behandeln die [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="75dfd-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75dfd-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75dfd-110">Remarks</span></span>  
 <span data-ttu-id="75dfd-111">Der Zielfunktion des Endaufrufs verwendet den aktuellen Stapelrahmen und direkt an den Aufrufer der Funktion, die den Endeaufruf vorgenommen zurück.</span><span class="sxs-lookup"><span data-stu-id="75dfd-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="75dfd-112">Dies bedeutet, dass eine [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) Rückruf wird nicht für eine Funktion, die das Ziel ein Endeaufruf ist ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="75dfd-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="75dfd-113">Der Wert von der `func` -Parameter ist ungültig, nachdem die `FunctionTailcall2` zurückgegeben, da der Wert möglicherweise geändert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="75dfd-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="75dfd-114">Die `FunctionTailcall2` Funktion ist ein Rückruf; Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="75dfd-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="75dfd-115">Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="75dfd-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="75dfd-116">Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="75dfd-116">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="75dfd-117">Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="75dfd-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="75dfd-118">Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="75dfd-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="75dfd-119">Die Implementierung der `FunctionTailcall2` sollte nicht blockiert werden, da es die Garbagecollection verzögert.</span><span class="sxs-lookup"><span data-stu-id="75dfd-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="75dfd-120">Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection-freundliche-Status.</span><span class="sxs-lookup"><span data-stu-id="75dfd-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="75dfd-121">Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionTailcall2` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="75dfd-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="75dfd-122">Darüber hinaus die `FunctionTailcall2` muss nicht Funktionsaufruf in verwaltetem Code oder auch eine verwaltete speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="75dfd-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75dfd-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75dfd-123">Requirements</span></span>  
 <span data-ttu-id="75dfd-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75dfd-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75dfd-125">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="75dfd-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="75dfd-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75dfd-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75dfd-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75dfd-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75dfd-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75dfd-128">See Also</span></span>  
 [<span data-ttu-id="75dfd-129">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="75dfd-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="75dfd-130">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="75dfd-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="75dfd-131">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="75dfd-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="75dfd-132">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="75dfd-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
