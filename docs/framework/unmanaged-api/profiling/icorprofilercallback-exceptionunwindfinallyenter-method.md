---
title: ICorProfilerCallback::ExceptionUnwindFinallyEnter-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
ms.openlocfilehash: 1f16add7b5a9d18e0c1eb33209b609e9bf7e18b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445315"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="c156f-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="c156f-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="c156f-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span><span class="sxs-lookup"><span data-stu-id="c156f-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c156f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c156f-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c156f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c156f-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c156f-106">[in] The ID of the function that contains the `finally` clause.</span><span class="sxs-lookup"><span data-stu-id="c156f-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c156f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c156f-107">Remarks</span></span>  
 <span data-ttu-id="c156f-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span><span class="sxs-lookup"><span data-stu-id="c156f-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="c156f-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span><span class="sxs-lookup"><span data-stu-id="c156f-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="c156f-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span><span class="sxs-lookup"><span data-stu-id="c156f-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c156f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c156f-111">Requirements</span></span>  
 <span data-ttu-id="c156f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c156f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c156f-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c156f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c156f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c156f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c156f-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c156f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c156f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c156f-116">See also</span></span>

- [<span data-ttu-id="c156f-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c156f-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c156f-118">GetNotifiedExceptionClauseInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="c156f-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="c156f-119">ExceptionUnwindFinallyLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="c156f-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
