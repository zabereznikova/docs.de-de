---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
ms.openlocfilehash: a7272d55771620db129125ce543d12d19a0b4dfb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697843"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="b4ef1-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3-Methode</span><span class="sxs-lookup"><span data-stu-id="b4ef1-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>

<span data-ttu-id="b4ef1-103">Gibt die vom Profiler implementierten Funktionen an, die für die Funktionen [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)und [FunctionTailcall3](functiontailcall3-function.md) aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ef1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4ef1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4ef1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4ef1-105">Parameters</span></span>  

 `pFuncEnter3`  
 <span data-ttu-id="b4ef1-106">in Ein Zeiger auf die-Implementierung, die als Rückruf verwendet werden soll `FunctionEnter3` .</span><span class="sxs-lookup"><span data-stu-id="b4ef1-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="b4ef1-107">in Ein Zeiger auf die-Implementierung, die als Rückruf verwendet werden soll `FunctionLeave3` .</span><span class="sxs-lookup"><span data-stu-id="b4ef1-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="b4ef1-108">in Ein Zeiger auf die-Implementierung, die als Rückruf verwendet werden soll `FunctionTailcall3` .</span><span class="sxs-lookup"><span data-stu-id="b4ef1-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4ef1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4ef1-109">Remarks</span></span>  

 <span data-ttu-id="b4ef1-110">[FunctionEnter3](functionenter3-function.md)-, [FunctionLeave3](functionleave3-function.md)-und [FunctionTailcall3](functiontailcall3-function.md) -Hooks bieten keine Stapel Rahmen-und Argument Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-110">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="b4ef1-111">Um auf diese Informationen zuzugreifen, `COR_PRF_ENABLE_FUNCTION_ARGS` `COR_PRF_ENABLE_FUNCTION_RETVAL` müssen die-,-und/oder-  `COR_PRF_ENABLE_FRAME_INFO` Flags festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="b4ef1-112">Der Profiler kann die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um die Ereignisflags festzulegen, und dann die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) -Methode verwenden, um die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="b4ef1-113">Es kann jeweils nur ein Satz von Rückrufen aktiv sein, und die neueste Version hat Vorrang.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="b4ef1-114">Wenn ein Profiler sowohl die [SetEnterLeaveFunctionHooks2-Methode](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) als auch die- `SetEnterLeaveFunctionHooks3` Methode aufruft, `SetEnterLeaveFunctionHooks3` wird daher verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="b4ef1-115">Die `SetEnterLeaveFunctionHooks3` -Methode kann nur vom [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4ef1-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b4ef1-116">Requirements</span></span>  

 <span data-ttu-id="b4ef1-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4ef1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4ef1-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b4ef1-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4ef1-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4ef1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4ef1-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4ef1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ef1-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4ef1-121">See also</span></span>

- [<span data-ttu-id="b4ef1-122">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b4ef1-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="b4ef1-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="b4ef1-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="b4ef1-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="b4ef1-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="b4ef1-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="b4ef1-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="b4ef1-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b4ef1-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="b4ef1-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b4ef1-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="b4ef1-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b4ef1-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="b4ef1-129">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="b4ef1-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="b4ef1-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="b4ef1-130">ICorProfilerInfo3</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b4ef1-131">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b4ef1-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b4ef1-132">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="b4ef1-132">Profiling</span></span>](index.md)
