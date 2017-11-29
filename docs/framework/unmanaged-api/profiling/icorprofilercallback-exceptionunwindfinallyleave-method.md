---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf373872ada8364fe755162597dc9baf5c527f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="63359-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="63359-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="63359-103">Benachrichtigt den Profiler, die der Entladephase der Behandlung verlassen hat eine `finally` Klausel.</span><span class="sxs-lookup"><span data-stu-id="63359-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63359-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63359-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="63359-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="63359-105">Remarks</span></span>  
 <span data-ttu-id="63359-106">Der Profiler sollte während dieses Aufrufs nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="63359-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="63359-107">Wenn der Profiler an dieser Stelle blockiert und eine Garbagecollection versucht wird, blockiert die Laufzeit, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63359-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="63359-108">Außerdem muss während dieses Aufrufs der Profiler Aufrufen nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren.</span><span class="sxs-lookup"><span data-stu-id="63359-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63359-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63359-109">Requirements</span></span>  
 <span data-ttu-id="63359-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63359-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63359-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63359-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63359-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63359-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63359-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63359-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63359-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63359-114">See Also</span></span>  
 [<span data-ttu-id="63359-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63359-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="63359-116">ExceptionUnwindFinallyEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="63359-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
