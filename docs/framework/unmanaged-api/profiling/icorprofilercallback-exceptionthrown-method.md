---
title: ICorProfilerCallback::ExceptionThrown-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
ms.openlocfilehash: 049339f7aecd0ababb74539e60395eff67d1c837
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723804"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="a7a63-102">ICorProfilerCallback::ExceptionThrown-Methode</span><span class="sxs-lookup"><span data-stu-id="a7a63-102">ICorProfilerCallback::ExceptionThrown Method</span></span>

<span data-ttu-id="a7a63-103">Benachrichtigt den Profiler, dass eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="a7a63-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a7a63-104">Diese Funktion wird nur aufgerufen, wenn die Ausnahme verwalteten Code erreicht.</span><span class="sxs-lookup"><span data-stu-id="a7a63-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7a63-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7a63-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7a63-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7a63-106">Parameters</span></span>

- `thrownObjectId`

  <span data-ttu-id="a7a63-107">\[in] die ID des Objekts, das bewirkt hat, dass die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="a7a63-107">\[in] The ID of the object that caused the exception to be thrown.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a7a63-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7a63-108">Remarks</span></span>  

 <span data-ttu-id="a7a63-109">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a7a63-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="a7a63-110">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a7a63-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="a7a63-111">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="a7a63-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7a63-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a7a63-112">Requirements</span></span>  

 <span data-ttu-id="a7a63-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7a63-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7a63-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7a63-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7a63-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7a63-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7a63-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7a63-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a63-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7a63-117">See also</span></span>

- [<span data-ttu-id="a7a63-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7a63-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
