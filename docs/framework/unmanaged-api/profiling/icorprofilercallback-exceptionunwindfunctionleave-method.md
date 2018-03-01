---
title: ICorProfilerCallback::ExceptionUnwindFunctionLeave-Methode
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
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eba7f6e5123108a7040bd2185eb57fc703c72c30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="d0736-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="d0736-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="d0736-103">Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung Entladung einer funktionsrückgabewerts abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d0736-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0736-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0736-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d0736-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d0736-105">Remarks</span></span>  
 <span data-ttu-id="d0736-106">Wenn die `ExceptionUnwindFunctionLeave` -Methode aufgerufen wird, die Funktionsinstanz und die Stack-Daten werden aus dem Stapel entfernt.</span><span class="sxs-lookup"><span data-stu-id="d0736-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="d0736-107">Der Profiler sollte während dieses Aufrufs nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d0736-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="d0736-108">Wenn der Profiler an dieser Stelle blockiert und eine Garbagecollection versucht wird, blockiert die Laufzeit, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d0736-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="d0736-109">Außerdem muss während dieses Aufrufs der Profiler Aufrufen nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren.</span><span class="sxs-lookup"><span data-stu-id="d0736-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0736-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0736-110">Requirements</span></span>  
 <span data-ttu-id="d0736-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0736-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0736-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0736-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0736-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0736-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0736-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0736-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0736-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0736-115">See Also</span></span>  
 [<span data-ttu-id="d0736-116">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0736-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="d0736-117">ExceptionUnwindFunctionEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="d0736-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
