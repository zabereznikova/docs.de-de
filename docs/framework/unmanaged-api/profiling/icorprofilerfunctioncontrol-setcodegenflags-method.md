---
title: ICorProfilerFunctionControl::SetCodegenFlags-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9264e717da62c88b6f2f6eca262b5635fc928741
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="3764a-102">ICorProfilerFunctionControl::SetCodegenFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="3764a-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="3764a-103">Legt ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) Steuerelement codegenerierung für eine just-in-Time (JIT)-Enumeration kompiliert Funktion.</span><span class="sxs-lookup"><span data-stu-id="3764a-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3764a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3764a-104">Syntax</span></span>  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3764a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3764a-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="3764a-106">[in] Ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="3764a-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3764a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3764a-107">Remarks</span></span>  
 <span data-ttu-id="3764a-108">Der Profiler Ruft eine Instanz dieser Schnittstelle durch den [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="3764a-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="3764a-109">`SetCodegenFlags`ermöglicht es dem Profiler zum Steuern der codegenerierung für die neu kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="3764a-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="3764a-110">Wie bei allen anderen JIT-Neukompilierung Parametern, wenden die codeerstellungskennzeichen auf alle Instanzen der Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="3764a-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="3764a-111">Der JIT-Compiler berücksichtigt diese Flags Kompilierung zusammen mit anderen Flags, die mit anderen Datenquellen angegeben werden, wenn eine Funktion zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="3764a-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="3764a-112">Die anderen Quellen umfassen den Debugger, globale Kennzeichen festgelegt, indem der Profiler beim Start von mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode (mit den Werten `COR_PRF_DISABLE_INLINING` und `COR_PRF_DISABLE_OPTIMIZATIONS`), und des Profilers [ ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="3764a-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="3764a-113">Der JIT-Compiler gibt Vorrang einer Quelle, die am wenigsten optimieren anfordert.</span><span class="sxs-lookup"><span data-stu-id="3764a-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="3764a-114">Z. B., wenn der Profiler gibt `COR_PRF_DISABLE_INLINING` auf Start, aber nicht an `COR_PRF_CODEGEN_DISABLE_INLINING` in der [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) Rückruf inlining ist immer noch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3764a-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="3764a-115">Auf ähnliche Weise, wenn der Profiler keine `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, aber anschließend deaktiviert inlining mithilfe der [ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) Rückruf inlining ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3764a-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3764a-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3764a-116">Requirements</span></span>  
 <span data-ttu-id="3764a-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3764a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3764a-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3764a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3764a-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3764a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3764a-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3764a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3764a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3764a-121">See Also</span></span>  
 [<span data-ttu-id="3764a-122">ICorProfilerFunctionControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3764a-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
