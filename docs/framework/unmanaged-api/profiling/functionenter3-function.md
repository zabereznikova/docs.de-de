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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 466b90f814d267fb289b2804beccd58fc442e341
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451879"
---
# <a name="functionenter3-function"></a><span data-ttu-id="44264-102">FunctionEnter3-Funktion</span><span class="sxs-lookup"><span data-stu-id="44264-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="44264-103">Benachrichtigt den Profiler, dass Steuerelement an eine Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="44264-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44264-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44264-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44264-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44264-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="44264-106">[in] Der Bezeichner der Funktion an der Steuerelement übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="44264-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44264-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44264-107">Remarks</span></span>  
 <span data-ttu-id="44264-108">Die `FunctionEnter3` Rückruffunktion benachrichtigt den Profiler, wie Funktionen aufgerufen werden, aber keine Unterstützung Argument Inspektion ist.</span><span class="sxs-lookup"><span data-stu-id="44264-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="44264-109">Verwenden der [ICorProfilerInfo3:: Setenterleavefunctionhooks3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) auf die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="44264-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="44264-110">Die `FunctionEnter3` Funktion ist ein Rückruf; Sie müssen ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="44264-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="44264-111">Verwenden Sie die Implementierung muss die `__declspec(naked)` Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="44264-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="44264-112">Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="44264-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="44264-113">Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="44264-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="44264-114">Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="44264-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44264-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44264-115">Requirements</span></span>  
 <span data-ttu-id="44264-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44264-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44264-117">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="44264-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="44264-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44264-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44264-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44264-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44264-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44264-120">See Also</span></span>  
 [<span data-ttu-id="44264-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="44264-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="44264-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="44264-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="44264-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="44264-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="44264-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="44264-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="44264-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="44264-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="44264-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="44264-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="44264-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="44264-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="44264-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="44264-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="44264-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="44264-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="44264-130">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="44264-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
