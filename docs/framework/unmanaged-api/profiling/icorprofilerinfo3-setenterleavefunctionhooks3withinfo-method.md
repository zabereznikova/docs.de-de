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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da3e51174d0b11f5cc706b7680048da519e2ed3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049491"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="f3719-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="f3719-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="f3719-103">Gibt an, die vom Profiler implementierten Funktionen, die aufgerufen werden, auf die [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), und [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) Hooks von verwalteten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="f3719-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3719-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3719-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3719-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3719-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="f3719-106">[in] Ein Zeiger auf die Implementierung, die als dienen der `FunctionEnter3WithInfo` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="f3719-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="f3719-107">[in] Ein Zeiger auf die Implementierung, die als dienen der `FunctionLeave3WithInfo` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="f3719-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="f3719-108">[in] Ein Zeiger auf die Implementierung, die als dienen der `FunctionTailcall3WithInfo` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="f3719-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3719-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3719-109">Remarks</span></span>  
 <span data-ttu-id="f3719-110">Die [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), und [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) Hooks bereitstellen Stack Stapelrahmen und Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="f3719-110">The [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="f3719-111">Zugriff auf diese Informationen, die `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, und/oder `COR_PRF_ENABLE_FRAME_INFO` Flags festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f3719-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="f3719-112">Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode, um die Ereignisflags festgelegt, und klicken Sie dann die `SetEnterLeaveFunctionHooks3WithInfo` Methode, um die Implementierung dieser Funktion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="f3719-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="f3719-113">Nur einen Satz von Rückrufen zu einem Zeitpunkt aktiv sein kann, und die neueste Version Vorrang.</span><span class="sxs-lookup"><span data-stu-id="f3719-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="f3719-114">Aus diesem Grund, wenn ein Profiler aufruft [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) und `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f3719-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="f3719-115">Die `SetEnterLeaveFunctionHooks3WithInfo` Methode aufgerufen werden kann, nur über die Profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="f3719-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3719-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3719-116">Requirements</span></span>  
 <span data-ttu-id="f3719-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3719-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3719-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3719-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f3719-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3719-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3719-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3719-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3719-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3719-121">See also</span></span>

- [<span data-ttu-id="f3719-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="f3719-122">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="f3719-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="f3719-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="f3719-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="f3719-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="f3719-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="f3719-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="f3719-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f3719-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="f3719-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f3719-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="f3719-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f3719-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="f3719-129">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="f3719-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="f3719-130">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3719-130">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f3719-131">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f3719-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f3719-132">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="f3719-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
