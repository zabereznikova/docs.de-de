---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
ms.openlocfilehash: d40cb424306535cc502d930dd61e6a1e254667da
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496177"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="f245e-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="f245e-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="f245e-103">Gibt die vom Profiler implementierten Funktionen an, die für die [FunctionEnter3WithInfo](functionenter3withinfo-function.md)-, [FunctionLeave3WithInfo](functionleave3withinfo-function.md)-und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) -Hooks von verwalteten Funktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f245e-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f245e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f245e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f245e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f245e-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="f245e-106">in Ein Zeiger auf die-Implementierung, die als Rückruf verwendet werden soll `FunctionEnter3WithInfo` .</span><span class="sxs-lookup"><span data-stu-id="f245e-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="f245e-107">in Ein Zeiger auf die-Implementierung, die als Rückruf verwendet werden soll `FunctionLeave3WithInfo` .</span><span class="sxs-lookup"><span data-stu-id="f245e-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="f245e-108">in Ein Zeiger auf die-Implementierung, die als Rückruf verwendet werden soll `FunctionTailcall3WithInfo` .</span><span class="sxs-lookup"><span data-stu-id="f245e-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f245e-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f245e-109">Remarks</span></span>  
 <span data-ttu-id="f245e-110">Die Hooks [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) stellen Stapel Rahmen und Argument Untersuchung bereit.</span><span class="sxs-lookup"><span data-stu-id="f245e-110">The [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="f245e-111">Um auf diese Informationen zuzugreifen, `COR_PRF_ENABLE_FUNCTION_ARGS` `COR_PRF_ENABLE_FUNCTION_RETVAL` müssen die-,-und/oder- `COR_PRF_ENABLE_FRAME_INFO` Flags festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f245e-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="f245e-112">Der Profiler kann die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um die Ereignisflags festzulegen, und dann die-Methode verwenden, `SetEnterLeaveFunctionHooks3WithInfo` um die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="f245e-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="f245e-113">Es kann jeweils nur ein Satz von Rückrufen aktiv sein, und die neueste Version hat Vorrang.</span><span class="sxs-lookup"><span data-stu-id="f245e-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="f245e-114">Wenn ein Profiler sowohl [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) als auch aufruft `SetEnterLeaveFunctionHooks3WithInfo` , wird daher `SetEnterLeaveFunctionHooks3WithInfo` verwendet.</span><span class="sxs-lookup"><span data-stu-id="f245e-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="f245e-115">Die `SetEnterLeaveFunctionHooks3WithInfo` -Methode kann nur vom [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f245e-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f245e-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f245e-116">Requirements</span></span>  
 <span data-ttu-id="f245e-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f245e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f245e-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f245e-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f245e-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f245e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f245e-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f245e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f245e-121">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="f245e-121">See also</span></span>

- [<span data-ttu-id="f245e-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="f245e-122">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="f245e-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="f245e-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="f245e-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="f245e-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="f245e-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="f245e-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="f245e-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f245e-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="f245e-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f245e-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="f245e-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f245e-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="f245e-129">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="f245e-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="f245e-130">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f245e-130">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f245e-131">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f245e-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="f245e-132">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="f245e-132">Profiling</span></span>](index.md)
