---
title: ICorProfilerCallback::ExceptionUnwindFunctionLeave-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e945cad9080d14fff0b0a95c4e4d5f13981b1b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582277"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="5a3ad-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="5a3ad-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="5a3ad-103">Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung Entladung einer Funktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5a3ad-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a3ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a3ad-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5a3ad-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a3ad-105">Remarks</span></span>  
 <span data-ttu-id="5a3ad-106">Wenn die `ExceptionUnwindFunctionLeave` -Methode aufgerufen wird, die Funktionsinstanz und die Stack-Daten aus dem Stapel entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="5a3ad-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="5a3ad-107">Der Profiler sollte während dieses Aufrufs nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5a3ad-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="5a3ad-108">Wenn hier die Profiler-Blöcke und eine Garbagecollection wird versucht, blockiert die Laufzeit, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5a3ad-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="5a3ad-109">Darüber hinaus muss bei Aufruf wird der Profiler Aufrufen nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren.</span><span class="sxs-lookup"><span data-stu-id="5a3ad-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a3ad-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5a3ad-110">Requirements</span></span>  
 <span data-ttu-id="5a3ad-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a3ad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a3ad-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a3ad-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a3ad-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a3ad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a3ad-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a3ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a3ad-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a3ad-115">See also</span></span>
- [<span data-ttu-id="5a3ad-116">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a3ad-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5a3ad-117">ExceptionUnwindFunctionEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="5a3ad-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
