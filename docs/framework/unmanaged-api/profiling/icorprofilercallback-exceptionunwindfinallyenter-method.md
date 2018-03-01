---
title: ICorProfilerCallback::ExceptionUnwindFinallyEnter-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f3480761c2708fa2f15454a7a99c34e84ee34eb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="ecfc2-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="ecfc2-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="ecfc2-103">Benachrichtigt den Profiler, die die Ausnahme behandeln Entladephase ist eine `finally` Klausel in der angegebenen Funktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="ecfc2-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecfc2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecfc2-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecfc2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ecfc2-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ecfc2-106">[in] Die ID der Funktion, enthält die `finally` Klausel.</span><span class="sxs-lookup"><span data-stu-id="ecfc2-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecfc2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecfc2-107">Remarks</span></span>  
 <span data-ttu-id="ecfc2-108">Der Profiler sollte in ihrer Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ecfc2-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="ecfc2-109">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ecfc2-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="ecfc2-110">Der Profiler Implementierung dieser Methode sollten nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ecfc2-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecfc2-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ecfc2-111">Requirements</span></span>  
 <span data-ttu-id="ecfc2-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecfc2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecfc2-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ecfc2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ecfc2-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecfc2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecfc2-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecfc2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecfc2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecfc2-116">See Also</span></span>  
 [<span data-ttu-id="ecfc2-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ecfc2-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ecfc2-118">GetNotifiedExceptionClauseInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="ecfc2-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)  
 [<span data-ttu-id="ecfc2-119">ExceptionUnwindFinallyLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="ecfc2-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
