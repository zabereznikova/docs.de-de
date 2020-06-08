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
ms.openlocfilehash: cd8030d6e57932a4605413fc2acc25a59de6c385
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500168"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="c2df9-102">ICorProfilerCallback::ExceptionThrown-Methode</span><span class="sxs-lookup"><span data-stu-id="c2df9-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="c2df9-103">Benachrichtigt den Profiler, dass eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="c2df9-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2df9-104">Diese Funktion wird nur aufgerufen, wenn die Ausnahme verwalteten Code erreicht.</span><span class="sxs-lookup"><span data-stu-id="c2df9-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2df9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2df9-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2df9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2df9-106">Parameters</span></span>

- `thrownObjectId`

  <span data-ttu-id="c2df9-107">\[in] die ID des Objekts, das bewirkt hat, dass die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="c2df9-107">\[in] The ID of the object that caused the exception to be thrown.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c2df9-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c2df9-108">Remarks</span></span>  
 <span data-ttu-id="c2df9-109">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c2df9-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="c2df9-110">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c2df9-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="c2df9-111">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="c2df9-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2df9-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c2df9-112">Requirements</span></span>  
 <span data-ttu-id="c2df9-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2df9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2df9-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2df9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2df9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2df9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2df9-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2df9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2df9-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c2df9-117">See also</span></span>

- [<span data-ttu-id="c2df9-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2df9-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
