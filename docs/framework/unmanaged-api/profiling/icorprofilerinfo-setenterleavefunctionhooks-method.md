---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
ms.openlocfilehash: 45593e7e30e1c8f8036489936aab3c607b01dd52
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438650"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="b294c-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks-Methode</span><span class="sxs-lookup"><span data-stu-id="b294c-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="b294c-103">Gibt vom Profiler implementierte Funktionen an, die für die "Enter"-, "Leave"-und "Tailcall"-Hooks von verwalteten Funktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b294c-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b294c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b294c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b294c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b294c-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="b294c-106">in Ein Zeiger auf die-Implementierung, die als [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) -Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b294c-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="b294c-107">in Ein Zeiger auf die-Implementierung, die als [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) -Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b294c-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="b294c-108">in Ein Zeiger auf die-Implementierung, die als [functiontailcallrückruf](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b294c-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b294c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b294c-109">Remarks</span></span>  
 <span data-ttu-id="b294c-110">In der .NET Framework Version 1,0 kann jeder Funktionszeiger NULL sein, um den entsprechenden Rückruf zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b294c-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="b294c-111">Es kann jeweils nur ein Satz von Rückrufen aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="b294c-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="b294c-112">Wenn ein Profiler sowohl `SetEnterLeaveFunctionHooks` als auch [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)aufruft, hat `SetEnterLeaveFunctionHooks2` Vorrang.</span><span class="sxs-lookup"><span data-stu-id="b294c-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="b294c-113">Die `SetEnterLeaveFunctionHooks`-Methode kann nur aus dem [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b294c-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b294c-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b294c-114">Requirements</span></span>  
 <span data-ttu-id="b294c-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b294c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b294c-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b294c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b294c-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b294c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b294c-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b294c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b294c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b294c-119">See also</span></span>

- [<span data-ttu-id="b294c-120">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b294c-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
