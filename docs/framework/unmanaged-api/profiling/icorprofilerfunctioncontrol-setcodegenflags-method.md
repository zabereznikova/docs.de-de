---
title: ICorProfilerFunctionControl::SetCodegenFlags-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 88c9f552b73af69ea4e1f64b75ed74ea762dcdfb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429942"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="fba0f-102">ICorProfilerFunctionControl::SetCodegenFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="fba0f-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="fba0f-103">Legt ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) -Enumeration fest, um die Codegenerierung für die neu kompilierte Just-in-time (JIT)-Funktion zu steuern.</span><span class="sxs-lookup"><span data-stu-id="fba0f-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fba0f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fba0f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fba0f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fba0f-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="fba0f-106">in Ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="fba0f-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fba0f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fba0f-107">Remarks</span></span>  
 <span data-ttu-id="fba0f-108">Der Profiler Ruft eine Instanz dieser Schnittstelle über den [ICorProfilerCallback4:: getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) -Rückruf ab.</span><span class="sxs-lookup"><span data-stu-id="fba0f-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="fba0f-109">`SetCodegenFlags` ermöglicht es dem Profiler, die Codegenerierung für die neu kompilierte Funktion zu steuern.</span><span class="sxs-lookup"><span data-stu-id="fba0f-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="fba0f-110">Wie bei allen anderen JIT-neukompilierungs Parametern gelten die Code Generierungs Flags für alle Instanzen der Funktion.</span><span class="sxs-lookup"><span data-stu-id="fba0f-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="fba0f-111">Der JIT-Compiler berücksichtigt diese Kompilierungs Flags zusammen mit anderen Flags, die von anderen Quellen angegeben werden, wenn eine Funktion kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="fba0f-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="fba0f-112">Die anderen Quellen enthalten den Debugger, globale Flags, die vom Profiler beim Start festgelegt werden, mit der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) -Methode (mit den Werten `COR_PRF_DISABLE_INLINING` und `COR_PRF_DISABLE_OPTIMIZATIONS`) und dem [ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) -Rückruf des Profilers.</span><span class="sxs-lookup"><span data-stu-id="fba0f-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="fba0f-113">Der JIT-Compiler hat Vorrang vor einer Quelle, die den geringsten Optimierungs Aufwand anfordert.</span><span class="sxs-lookup"><span data-stu-id="fba0f-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="fba0f-114">Wenn der Profiler z. b. `COR_PRF_DISABLE_INLINING` beim Start angibt, aber keine `COR_PRF_CODEGEN_DISABLE_INLINING` im [icorprofilerfunctioncontrol:: setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) -Rückruf angibt, ist Inlining weiterhin deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fba0f-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="fba0f-115">Wenn der Profiler in `SetCodegenFlags`keine `COR_PRF_CODEGEN_DISABLE_INLINING` angibt, sondern das Inlining mithilfe des [ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) -Rückrufs deaktiviert, ist Inlining deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fba0f-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fba0f-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fba0f-116">Requirements</span></span>  
 <span data-ttu-id="fba0f-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fba0f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fba0f-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fba0f-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fba0f-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fba0f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fba0f-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fba0f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba0f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fba0f-121">See also</span></span>

- [<span data-ttu-id="fba0f-122">ICorProfilerFunctionControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fba0f-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
