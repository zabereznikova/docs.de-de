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
ms.openlocfilehash: f71d0b5c77d4a514001bcbe6904ed912be388d18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681547"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="08ae6-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2-Methode</span><span class="sxs-lookup"><span data-stu-id="08ae6-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>

<span data-ttu-id="08ae6-103">Gibt vom Profiler implementierte Funktionen an, die für die aktualisierten Versionen der Hooks "Enter", "Leave" und "Tailcall" von verwalteten Funktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="08ae6-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08ae6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08ae6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08ae6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08ae6-105">Parameters</span></span>  

 `pFuncEnter`  
 <span data-ttu-id="08ae6-106">in Ein Zeiger auf die-Implementierung, die als [FunctionEnter2](functionenter2-function.md) -Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08ae6-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="08ae6-107">in Ein Zeiger auf die-Implementierung, die als [FunctionLeave2](functionleave2-function.md) -Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08ae6-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="08ae6-108">in Ein Zeiger auf die-Implementierung, die als [FunctionTailcall2](functiontailcall2-function.md) -Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08ae6-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08ae6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08ae6-109">Remarks</span></span>  

 <span data-ttu-id="08ae6-110">Die- `SetEnterLeaveFunctionHooks2` Methode ähnelt der [ICorProfilerInfo:: abtenterleavefunctionhooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="08ae6-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="08ae6-111">Verwenden Sie das erste, um Funktionen anzugeben, die als neuere Versionen der Eingabe-/Rückruf-Rückrufe verwendet werden sollen, und letztere zum Angeben von Funktionen, die als ältere Versionen der Eingabe-/Rückruf-Rückrufe verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="08ae6-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="08ae6-112">Es kann jeweils nur ein Satz von Rückrufen aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="08ae6-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="08ae6-113">Wenn ein Profiler sowohl `ICorProfilerInfo::SetEnterLeaveFunctionHooks` als auch aufruft `SetEnterLeaveFunctionHooks2` , wird daher `SetEnterLeaveFunctionHooks2` verwendet.</span><span class="sxs-lookup"><span data-stu-id="08ae6-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="08ae6-114">Die `SetEnterLeaveFunctionHooks2` -Methode kann nur vom [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="08ae6-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08ae6-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="08ae6-115">Requirements</span></span>  

 <span data-ttu-id="08ae6-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08ae6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08ae6-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08ae6-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08ae6-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08ae6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08ae6-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08ae6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ae6-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08ae6-120">See also</span></span>

- [<span data-ttu-id="08ae6-121">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ae6-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="08ae6-122">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ae6-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
