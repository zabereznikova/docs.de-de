---
title: ICorProfilerInfo::SetFunctionIDMapper-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
ms.openlocfilehash: 3a9ab64730feaa372f9b5d9ad7cefcb86580ca5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671173"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="5ae11-102">ICorProfilerInfo::SetFunctionIDMapper-Methode</span><span class="sxs-lookup"><span data-stu-id="5ae11-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>

<span data-ttu-id="5ae11-103">Gibt die vom Profiler implementierte Funktion an, die aufgerufen wird, um die `FunctionID`-Werte alternativen Werten zuzuordnen, die an die Funktionseinstiegs-/-exithooks des Profilers übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5ae11-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ae11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ae11-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ae11-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ae11-105">Parameters</span></span>  

 `pFunc`  
 <span data-ttu-id="5ae11-106">in Ein Zeiger auf die [FunctionIDMapper](functionidmapper-function.md) -Implementierung, die aufgerufen wird, um die `FunctionID` Werte ihren alternativen Werten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="5ae11-106">[in] A pointer to the [FunctionIDMapper](functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ae11-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ae11-107">Remarks</span></span>  

 <span data-ttu-id="5ae11-108">Die Alternativen für die `FunctionID` Werte werden an die Funktions Einstiegs-/Beendigungs Hooks des Profilers ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)und [FunctionTailcall2](functiontailcall2-function.md)) übermittelt, die von der [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) -Methode angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5ae11-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="5ae11-109">Der `FunctionIDMapper` kann nur ein Mal festgelegt werden, und es wird empfohlen, ihn im [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5ae11-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ae11-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5ae11-110">Requirements</span></span>  

 <span data-ttu-id="5ae11-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ae11-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ae11-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ae11-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ae11-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ae11-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ae11-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ae11-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae11-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ae11-115">See also</span></span>

- [<span data-ttu-id="5ae11-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ae11-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
