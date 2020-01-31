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
ms.openlocfilehash: f7bc1954d11134a4515d2e29e9e0eb1626ae5d26
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863427"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="2f497-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks-Methode</span><span class="sxs-lookup"><span data-stu-id="2f497-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="2f497-103">Gibt vom Profiler implementierte Funktionen an, die für die "Enter"-, "Leave"-und "Tailcall"-Hooks von verwalteten Funktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2f497-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f497-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f497-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f497-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2f497-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="2f497-106">in Ein Zeiger auf die-Implementierung, die als [FunctionEnter](functionenter-function.md) -Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f497-106">[in] A pointer to the implementation to be used as the [FunctionEnter](functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="2f497-107">in Ein Zeiger auf die-Implementierung, die als [FunctionLeave](functionleave-function.md) -Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f497-107">[in] A pointer to the implementation to be used as the [FunctionLeave](functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="2f497-108">in Ein Zeiger auf die-Implementierung, die als [functiontailcallrückruf](functiontailcall-function.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f497-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f497-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f497-109">Remarks</span></span>  
 <span data-ttu-id="2f497-110">In der .NET Framework Version 1,0 kann jeder Funktionszeiger NULL sein, um den entsprechenden Rückruf zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2f497-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="2f497-111">Es kann jeweils nur ein Satz von Rückrufen aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="2f497-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="2f497-112">Wenn ein Profiler sowohl `SetEnterLeaveFunctionHooks` als auch [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)aufruft, hat `SetEnterLeaveFunctionHooks2` Vorrang.</span><span class="sxs-lookup"><span data-stu-id="2f497-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="2f497-113">Die `SetEnterLeaveFunctionHooks`-Methode kann nur aus dem [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2f497-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f497-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f497-114">Requirements</span></span>  
 <span data-ttu-id="2f497-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f497-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f497-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f497-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f497-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f497-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f497-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f497-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f497-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f497-119">See also</span></span>

- [<span data-ttu-id="2f497-120">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f497-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
