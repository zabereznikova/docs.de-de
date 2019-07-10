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
ms.openlocfilehash: 24c9077863ada4d1208f29755a70d2cf8abc1208
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782696"
---
# <a name="functionenter3-function"></a><span data-ttu-id="af4e1-102">FunctionEnter3-Funktion</span><span class="sxs-lookup"><span data-stu-id="af4e1-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="af4e1-103">Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="af4e1-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af4e1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af4e1-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af4e1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af4e1-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="af4e1-106">[in] Der Bezeichner der Funktion an der Steuerelement übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="af4e1-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af4e1-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af4e1-107">Remarks</span></span>  
 <span data-ttu-id="af4e1-108">Die `FunctionEnter3` Rückruffunktion benachrichtigt den Profiler an, wie Funktionen aufgerufen werden, aber es keine Unterstützung für Argument-Überprüfung ist.</span><span class="sxs-lookup"><span data-stu-id="af4e1-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="af4e1-109">Verwenden der [ICorProfilerInfo3:: Setenterleavefunctionhooks3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) auf die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="af4e1-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="af4e1-110">Die `FunctionEnter3` Funktion ist ein Rückruf, müssen Sie sie implementieren.</span><span class="sxs-lookup"><span data-stu-id="af4e1-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="af4e1-111">Verwenden Sie die Implementierung muss die `__declspec(naked)` Storage-Class-Attribut.</span><span class="sxs-lookup"><span data-stu-id="af4e1-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="af4e1-112">Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="af4e1-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="af4e1-113">Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).</span><span class="sxs-lookup"><span data-stu-id="af4e1-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="af4e1-114">Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="af4e1-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af4e1-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af4e1-115">Requirements</span></span>  
 <span data-ttu-id="af4e1-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af4e1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af4e1-117">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="af4e1-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="af4e1-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af4e1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af4e1-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af4e1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af4e1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af4e1-120">See also</span></span>

- [<span data-ttu-id="af4e1-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="af4e1-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="af4e1-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="af4e1-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="af4e1-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af4e1-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="af4e1-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af4e1-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="af4e1-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af4e1-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="af4e1-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="af4e1-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="af4e1-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af4e1-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="af4e1-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="af4e1-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="af4e1-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="af4e1-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="af4e1-130">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="af4e1-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
