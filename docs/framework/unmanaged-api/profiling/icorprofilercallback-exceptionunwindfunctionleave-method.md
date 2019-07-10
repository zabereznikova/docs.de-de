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
ms.openlocfilehash: 556048be66a7c60dd82a8d51391a86655db6802a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755926"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="462e1-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="462e1-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="462e1-103">Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung Entladung einer Funktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="462e1-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="462e1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="462e1-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="462e1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="462e1-105">Remarks</span></span>  
 <span data-ttu-id="462e1-106">Wenn die `ExceptionUnwindFunctionLeave` -Methode aufgerufen wird, die Funktionsinstanz und die Stack-Daten aus dem Stapel entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="462e1-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="462e1-107">Der Profiler sollte während dieses Aufrufs nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="462e1-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="462e1-108">Wenn hier die Profiler-Blöcke und eine Garbagecollection wird versucht, blockiert die Laufzeit, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="462e1-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="462e1-109">Darüber hinaus muss bei Aufruf wird der Profiler Aufrufen nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren.</span><span class="sxs-lookup"><span data-stu-id="462e1-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="462e1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="462e1-110">Requirements</span></span>  
 <span data-ttu-id="462e1-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="462e1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="462e1-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="462e1-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="462e1-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="462e1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="462e1-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="462e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="462e1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="462e1-115">See also</span></span>

- [<span data-ttu-id="462e1-116">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="462e1-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="462e1-117">ExceptionUnwindFunctionEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="462e1-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
