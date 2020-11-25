---
title: FunctionIDMapper2-Funktion
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
ms.openlocfilehash: 7aa90b92d129f1269d901f1cbb5c6a0750de9a90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728536"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="1e2a4-102">FunctionIDMapper2-Funktion</span><span class="sxs-lookup"><span data-stu-id="1e2a4-102">FunctionIDMapper2 Function</span></span>

<span data-ttu-id="1e2a4-103">Benachrichtigt den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zugeordnet werden kann, die in den [FunctionEnter3](functionenter3-function.md)-, [FunctionLeave3](functionleave3-function.md)-und [FunctionTailcall3](functiontailcall3-function.md)-und[FunctionEnter3WithInfo](functionenter3withinfo-function.md)-, [FunctionLeave3WithInfo](functionleave3withinfo-function.md)-und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) -Rückrufe für diese Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1e2a4-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="1e2a4-104">Mit `FunctionIDMapper2`kann der Profiler auch angeben, ob er Rückrufe für diese Funktion empfangen will.</span><span class="sxs-lookup"><span data-stu-id="1e2a4-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e2a4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e2a4-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e2a4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e2a4-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="1e2a4-107">\[in] der Funktions Bezeichner, der neu zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1e2a4-107">\[in] The function identifier to be remapped.</span></span>

- `clientData`

  <span data-ttu-id="1e2a4-108">\[in] ein Zeiger auf Daten, die zur Unterscheidung Zwischenlauf Zeiten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e2a4-108">\[in] A pointer to data that is used to disambiguate among runtimes.</span></span>

- `pbHookFunction`

  <span data-ttu-id="1e2a4-109">\[out] ein Zeiger auf einen Wert, den der Profiler auf festlegt `true` , wenn er die Rückrufe `FunctionEnter3` , `FunctionLeave3` , und `FunctionTailcall3` , oder `FunctionEnter3WithInfo` , und empfangen möchte `FunctionLeave3WithInfo` `FunctionTailcall3WithInfo` . andernfalls wird dieser Wert auf festgelegt `false` .</span><span class="sxs-lookup"><span data-stu-id="1e2a4-109">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="1e2a4-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1e2a4-110">Return Value</span></span>  

 <span data-ttu-id="1e2a4-111">Der Profiler gibt einen Wert zurück, den die Ausführungs-Engine als alternativen Funktionsbezeichner verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e2a4-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="1e2a4-112">Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1e2a4-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="1e2a4-113">Andernfalls führt ein Rückgabewert von NULL zu unvorhersehbaren Ergebnissen, einschließlich des möglichen Anhaltens des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="1e2a4-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e2a4-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e2a4-114">Remarks</span></span>  

 <span data-ttu-id="1e2a4-115">Diese Methode erweitert die [FunctionIDMapper](functionidmapper-function.md) -Funktion mit einem zusätzlichen Parameter, der verwendet wird, um Client Daten zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="1e2a4-115">This method extends the [FunctionIDMapper](functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="1e2a4-116">Die Clientdaten werden verwendet, um Mehrdeutigkeiten zwischen Laufzeiten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="1e2a4-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e2a4-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1e2a4-117">Requirements</span></span>  

 <span data-ttu-id="1e2a4-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e2a4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e2a4-119">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="1e2a4-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="1e2a4-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e2a4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e2a4-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e2a4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e2a4-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e2a4-122">See also</span></span>

- [<span data-ttu-id="1e2a4-123">ICorProfilerInfo:: SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="1e2a4-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="1e2a4-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="1e2a4-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="1e2a4-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="1e2a4-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="1e2a4-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="1e2a4-126">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="1e2a4-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="1e2a4-127">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="1e2a4-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1e2a4-128">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="1e2a4-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1e2a4-129">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="1e2a4-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1e2a4-130">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="1e2a4-131">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="1e2a4-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
