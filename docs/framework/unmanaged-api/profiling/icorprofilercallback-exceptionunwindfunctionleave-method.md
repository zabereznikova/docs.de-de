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
ms.openlocfilehash: 645c9dd9319dfdf9cb070366d2c389f879e1b1d2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448049"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="94929-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="94929-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="94929-103">Benachrichtigt den Profiler, dass die Entladephase der Ausnahmebehandlung das Entladen einer Funktion abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="94929-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94929-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94929-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="94929-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94929-105">Remarks</span></span>  
 <span data-ttu-id="94929-106">Wenn die `ExceptionUnwindFunctionLeave`-Methode aufgerufen wird, werden die Funktions Instanz und Ihre Stapel Daten aus dem Stapel entfernt.</span><span class="sxs-lookup"><span data-stu-id="94929-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="94929-107">Der Profiler sollte während dieses Aufrufes nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="94929-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="94929-108">Wenn der Profiler hier blockiert wird und ein Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="94929-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="94929-109">Außerdem darf der Profiler während dieses Aufrufes nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="94929-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94929-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="94929-110">Requirements</span></span>  
 <span data-ttu-id="94929-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94929-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94929-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="94929-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="94929-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94929-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94929-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94929-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94929-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94929-115">See also</span></span>

- [<span data-ttu-id="94929-116">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94929-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="94929-117">ExceptionUnwindFunctionEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="94929-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
