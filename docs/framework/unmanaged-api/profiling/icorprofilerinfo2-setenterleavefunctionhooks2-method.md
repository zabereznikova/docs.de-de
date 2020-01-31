---
title: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
ms.openlocfilehash: 7eac42e1d8132ca9e6d6c6b43efd43b88c1e5d3d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868576"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="4fef1-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="4fef1-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="4fef1-103">Gibt vom Profiler implementierte Funktionen an, die für die aktualisierten Versionen der Hooks "Enter", "Leave" und "Tailcall" von verwalteten Funktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4fef1-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fef1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fef1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fef1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4fef1-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="4fef1-106">in Ein Zeiger auf die-Implementierung, die als [FunctionEnter2](functionenter2-function.md) -Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4fef1-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="4fef1-107">in Ein Zeiger auf die-Implementierung, die als [FunctionLeave2](functionleave2-function.md) -Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4fef1-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="4fef1-108">in Ein Zeiger auf die-Implementierung, die als [FunctionTailcall2](functiontailcall2-function.md) -Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4fef1-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fef1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4fef1-109">Remarks</span></span>  
 <span data-ttu-id="4fef1-110">Die `SetEnterLeaveFunctionHooks2`-Methode ähnelt der [ICorProfilerInfo:: abtenterleavefunctionhooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="4fef1-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="4fef1-111">Verwenden Sie das erste, um Funktionen anzugeben, die als neuere Versionen der Eingabe-/Rückruf-Rückrufe verwendet werden sollen, und letztere zum Angeben von Funktionen, die als ältere Versionen der Eingabe-/Rückruf-Rückrufe verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4fef1-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="4fef1-112">Es kann jeweils nur ein Satz von Rückrufen aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="4fef1-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="4fef1-113">Wenn ein Profiler sowohl `ICorProfilerInfo::SetEnterLeaveFunctionHooks` als auch `SetEnterLeaveFunctionHooks2`aufruft, wird `SetEnterLeaveFunctionHooks2` verwendet.</span><span class="sxs-lookup"><span data-stu-id="4fef1-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="4fef1-114">Die `SetEnterLeaveFunctionHooks2`-Methode kann nur aus dem [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4fef1-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fef1-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4fef1-115">Requirements</span></span>  
 <span data-ttu-id="4fef1-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fef1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fef1-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4fef1-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4fef1-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fef1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fef1-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fef1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fef1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fef1-120">See also</span></span>

- [<span data-ttu-id="4fef1-121">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4fef1-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="4fef1-122">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4fef1-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
