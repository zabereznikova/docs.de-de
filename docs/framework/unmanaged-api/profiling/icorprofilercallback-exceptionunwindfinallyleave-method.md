---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave-Methode
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
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 969bc0723929dffd16b3119a9c9b74499f35b0e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="c01cd-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="c01cd-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="c01cd-103">Benachrichtigt den Profiler, die der Entladephase der Behandlung verlassen hat eine `finally` Klausel.</span><span class="sxs-lookup"><span data-stu-id="c01cd-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c01cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c01cd-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c01cd-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c01cd-105">Remarks</span></span>  
 <span data-ttu-id="c01cd-106">Der Profiler sollte während dieses Aufrufs nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c01cd-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="c01cd-107">Wenn der Profiler an dieser Stelle blockiert und eine Garbagecollection versucht wird, blockiert die Laufzeit, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c01cd-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="c01cd-108">Außerdem muss während dieses Aufrufs der Profiler Aufrufen nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren.</span><span class="sxs-lookup"><span data-stu-id="c01cd-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c01cd-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c01cd-109">Requirements</span></span>  
 <span data-ttu-id="c01cd-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c01cd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c01cd-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c01cd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c01cd-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c01cd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c01cd-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c01cd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c01cd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c01cd-114">See Also</span></span>  
 [<span data-ttu-id="c01cd-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c01cd-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c01cd-116">ExceptionUnwindFinallyEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="c01cd-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
