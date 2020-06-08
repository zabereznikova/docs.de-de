---
title: ICorProfilerInfo3::SetFunctionIDMapper2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 723cb277a7df592e0494505018f7422e4e40f5f6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496151"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="c75c3-102">ICorProfilerInfo3::SetFunctionIDMapper2-Methode</span><span class="sxs-lookup"><span data-stu-id="c75c3-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="c75c3-103">Gibt die vom Profiler implementierte Funktion an, die aufgerufen wird, um die `FunctionID`-Werte alternativen Werten zuzuordnen, die an die Funktionseinstiegs-/-exithooks des Profilers übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c75c3-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="c75c3-104">Diese Methode erweitert die [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) -Methode mit einem zusätzlichen Daten Parameter, den Profiler verwenden können, um die Unterschiede Zwischenlauf Zeiten zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c75c3-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75c3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c75c3-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c75c3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c75c3-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="c75c3-107">in Ein Zeiger auf eine [FunctionIDMapper2](functionidmapper2-function.md) -Implementierung, die aufgerufen wird, um die `FunctionID` Werte ihren alternativen Werten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c75c3-107">[in] A pointer to a [FunctionIDMapper2](functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="c75c3-108">in Ein Zeiger, der an jeden von der aktuellen Laufzeit an jeden [FunctionIDMapper2](functionidmapper2-function.md) -Funktions aufrufenen aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c75c3-108">[in] A pointer that is passed to every [FunctionIDMapper2](functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="c75c3-109">Der Profiler kann diese Informationen verwenden, um die Unterschiede Zwischenlauf Zeiten zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c75c3-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c75c3-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c75c3-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c75c3-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c75c3-111">Remarks</span></span>  
 <span data-ttu-id="c75c3-112">Die Alternativen für die FunctionID-Werte werden an die Funktions-und Beendigungs Hooks des Profiler ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)und [FunctionTailcall3](functiontailcall3-function.md); oder [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)), die durch die [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) -Methode oder die [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) -Methode angegeben werden, übermittelt.</span><span class="sxs-lookup"><span data-stu-id="c75c3-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md); or [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="c75c3-113">Die- `FunctionIDMapper2` Methode kann nur einmal festgelegt werden. es wird empfohlen, Sie im [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c75c3-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c75c3-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c75c3-114">Requirements</span></span>  
 <span data-ttu-id="c75c3-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c75c3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c75c3-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c75c3-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c75c3-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c75c3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c75c3-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c75c3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75c3-119">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c75c3-119">See also</span></span>

- [<span data-ttu-id="c75c3-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="c75c3-120">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="c75c3-121">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c75c3-121">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="c75c3-122">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c75c3-122">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="c75c3-123">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="c75c3-123">Profiling</span></span>](index.md)
