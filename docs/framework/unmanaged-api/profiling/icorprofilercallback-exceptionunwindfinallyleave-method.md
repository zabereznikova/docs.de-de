---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ba62ab2c4df73b570fb1c76adaee44a2a2ce8c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117805"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="51f18-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="51f18-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="51f18-103">Benachrichtigt den Profiler, die der Entladephase der Behandlung verlassen hat eine `finally` Klausel.</span><span class="sxs-lookup"><span data-stu-id="51f18-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f18-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51f18-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="51f18-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51f18-105">Remarks</span></span>  
 <span data-ttu-id="51f18-106">Der Profiler sollte während dieses Aufrufs nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="51f18-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="51f18-107">Wenn hier die Profiler-Blöcke und eine Garbagecollection wird versucht, blockiert die Laufzeit, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="51f18-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="51f18-108">Darüber hinaus muss bei Aufruf wird der Profiler Aufrufen nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren.</span><span class="sxs-lookup"><span data-stu-id="51f18-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51f18-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51f18-109">Requirements</span></span>  
 <span data-ttu-id="51f18-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51f18-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51f18-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51f18-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51f18-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51f18-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="51f18-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="51f18-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51f18-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51f18-114">See also</span></span>

- [<span data-ttu-id="51f18-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51f18-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="51f18-116">ExceptionUnwindFinallyEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="51f18-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
