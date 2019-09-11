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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9495624f7eca57a79518036937a5fb63d01d9c4b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851211"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="67ab6-102">FunctionTailcall2-Funktion</span><span class="sxs-lookup"><span data-stu-id="67ab6-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="67ab6-103">Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt und Informationen über den Stapel Rahmen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="67ab6-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67ab6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67ab6-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67ab6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67ab6-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="67ab6-106">in Der Bezeichner der aktuell ausgeführten Funktion, die einen Tail-Aufruf durchführen soll.</span><span class="sxs-lookup"><span data-stu-id="67ab6-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="67ab6-107">in Der neu zugeordnete Funktions Bezeichner, den der Profiler zuvor über [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)angegeben hat, der aktuell ausgeführten Funktion, die einen Tail-Aufruf durchführen soll.</span><span class="sxs-lookup"><span data-stu-id="67ab6-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="67ab6-108">in Ein `COR_PRF_FRAME_INFO` -Wert, der auf Informationen über den Stapel Rahmen zeigt.</span><span class="sxs-lookup"><span data-stu-id="67ab6-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="67ab6-109">Der Profiler sollte dies als ein undurchsichtiges Handle behandeln, das an die Ausführungs-Engine in der [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) -Methode zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="67ab6-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67ab6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67ab6-110">Remarks</span></span>  
 <span data-ttu-id="67ab6-111">Die Zielfunktion des Tail-Aufrufs verwendet den aktuellen Stapel Rahmen und kehrt direkt zum Aufrufer der Funktion zurück, die den Tail-Aufruf durchgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="67ab6-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="67ab6-112">Dies bedeutet, dass ein [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) -Rückruf nicht für eine Funktion ausgegeben wird, die das Ziel eines Tail-Aufrufs ist.</span><span class="sxs-lookup"><span data-stu-id="67ab6-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="67ab6-113">Der Wert des `func` -Parameters ist nicht gültig, `FunctionTailcall2` nachdem die Funktion zurückgegeben wurde, da sich der Wert ändern oder zerstört werden kann.</span><span class="sxs-lookup"><span data-stu-id="67ab6-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="67ab6-114">Die `FunctionTailcall2` Funktion ist ein Rückruf. Sie müssen Sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="67ab6-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="67ab6-115">Die-Implementierung muss das `__declspec`Speicher`naked`Klassen Attribut () verwenden.</span><span class="sxs-lookup"><span data-stu-id="67ab6-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="67ab6-116">Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.</span><span class="sxs-lookup"><span data-stu-id="67ab6-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="67ab6-117">Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).</span><span class="sxs-lookup"><span data-stu-id="67ab6-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="67ab6-118">Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.</span><span class="sxs-lookup"><span data-stu-id="67ab6-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="67ab6-119">Die Implementierung von `FunctionTailcall2` sollte nicht blockiert werden, da Sie Garbage Collection verzögert.</span><span class="sxs-lookup"><span data-stu-id="67ab6-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="67ab6-120">Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="67ab6-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="67ab6-121">Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit `FunctionTailcall2` blockiert, bis von zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="67ab6-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="67ab6-122">Außerdem darf die `FunctionTailcall2` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="67ab6-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67ab6-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67ab6-123">Requirements</span></span>  
 <span data-ttu-id="67ab6-124">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67ab6-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67ab6-125">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="67ab6-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="67ab6-126">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67ab6-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67ab6-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67ab6-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ab6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67ab6-128">See also</span></span>

- [<span data-ttu-id="67ab6-129">FunctionEnter2-Funktion</span><span class="sxs-lookup"><span data-stu-id="67ab6-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="67ab6-130">FunctionLeave2-Funktion</span><span class="sxs-lookup"><span data-stu-id="67ab6-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="67ab6-131">SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="67ab6-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="67ab6-132">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="67ab6-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
