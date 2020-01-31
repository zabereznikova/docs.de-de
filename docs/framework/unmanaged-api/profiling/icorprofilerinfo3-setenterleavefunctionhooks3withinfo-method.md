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
ms.openlocfilehash: 4fe18b4f07e6f282571b13faff5ce51b66ce416b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868485"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="accd4-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="accd4-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="accd4-103">Gibt die vom Profiler implementierten Funktionen an, die für die [FunctionEnter3WithInfo](functionenter3withinfo-function.md)-, [FunctionLeave3WithInfo](functionleave3withinfo-function.md)-und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) -Hooks von verwalteten Funktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="accd4-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="accd4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="accd4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="accd4-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="accd4-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="accd4-106">in Ein Zeiger auf die-Implementierung, die als `FunctionEnter3WithInfo` Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="accd4-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="accd4-107">in Ein Zeiger auf die-Implementierung, die als `FunctionLeave3WithInfo` Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="accd4-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="accd4-108">in Ein Zeiger auf die-Implementierung, die als `FunctionTailcall3WithInfo` Rückruf verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="accd4-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="accd4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="accd4-109">Remarks</span></span>  
 <span data-ttu-id="accd4-110">Die Hooks [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)und [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) stellen Stapel Rahmen und Argument Untersuchung bereit.</span><span class="sxs-lookup"><span data-stu-id="accd4-110">The [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="accd4-111">Um auf diese Informationen zuzugreifen, müssen die `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`und/oder `COR_PRF_ENABLE_FRAME_INFO` Flags festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="accd4-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="accd4-112">Der Profiler kann die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um die Ereignisflags festzulegen, und dann die `SetEnterLeaveFunctionHooks3WithInfo`-Methode verwenden, um die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="accd4-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="accd4-113">Es kann jeweils nur ein Satz von Rückrufen aktiv sein, und die neueste Version hat Vorrang.</span><span class="sxs-lookup"><span data-stu-id="accd4-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="accd4-114">Wenn ein Profiler sowohl [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) als auch `SetEnterLeaveFunctionHooks3WithInfo`aufruft, wird daher `SetEnterLeaveFunctionHooks3WithInfo` verwendet.</span><span class="sxs-lookup"><span data-stu-id="accd4-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="accd4-115">Die `SetEnterLeaveFunctionHooks3WithInfo`-Methode kann nur aus dem [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Rückruf des Profilers aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="accd4-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="accd4-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="accd4-116">Requirements</span></span>  
 <span data-ttu-id="accd4-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="accd4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="accd4-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="accd4-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="accd4-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="accd4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="accd4-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="accd4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="accd4-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="accd4-121">See also</span></span>

- [<span data-ttu-id="accd4-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="accd4-122">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="accd4-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="accd4-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="accd4-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="accd4-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="accd4-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="accd4-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="accd4-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="accd4-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="accd4-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="accd4-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="accd4-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="accd4-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="accd4-129">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="accd4-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="accd4-130">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="accd4-130">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="accd4-131">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="accd4-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="accd4-132">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="accd4-132">Profiling</span></span>](index.md)
