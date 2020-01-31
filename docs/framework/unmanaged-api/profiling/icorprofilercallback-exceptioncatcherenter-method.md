---
title: ICorProfilerCallback::ExceptionCatcherEnter-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 534e0672820cc2509f32765274ad970fda69ec5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866506"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="39e66-102">ICorProfilerCallback::ExceptionCatcherEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="39e66-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="39e66-103">Benachrichtigt den Profiler, dass das Steuerelement an den entsprechenden `catch`-Block übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="39e66-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39e66-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39e66-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39e66-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="39e66-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="39e66-106">\[in] der Bezeichner der Funktion, die den `catch` Block enthält.</span><span class="sxs-lookup"><span data-stu-id="39e66-106">\[in] The identifier of the function containing the `catch` block.</span></span>
  
- `objectId`

  <span data-ttu-id="39e66-107">\[in] der Bezeichner der Ausnahme, die behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="39e66-107">\[in] The identifier of the exception being handled.</span></span>

## <a name="remarks"></a><span data-ttu-id="39e66-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39e66-108">Remarks</span></span>  
 <span data-ttu-id="39e66-109">Die `ExceptionCatcherEnter`-Methode wird nur aufgerufen, wenn sich der Catch-Punkt im Code befindet, der mit dem JIT-Compiler (Just-in-Time) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="39e66-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="39e66-110">Eine Ausnahme, die in nicht verwaltetem Code oder im internen Code der Laufzeit abgefangen wird, ruft diese Benachrichtigung nicht auf.</span><span class="sxs-lookup"><span data-stu-id="39e66-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="39e66-111">Der `objectId` Wert wird erneut weitergegeben, da ein Garbage Collection das Objekt seit der `ExceptionThrown` Benachrichtigung verschieben könnte.</span><span class="sxs-lookup"><span data-stu-id="39e66-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="39e66-112">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="39e66-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="39e66-113">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="39e66-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="39e66-114">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="39e66-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39e66-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="39e66-115">Requirements</span></span>  
 <span data-ttu-id="39e66-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39e66-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39e66-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39e66-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39e66-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39e66-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39e66-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39e66-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e66-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39e66-120">See also</span></span>

- [<span data-ttu-id="39e66-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39e66-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="39e66-122">ExceptionCatcherLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="39e66-122">ExceptionCatcherLeave Method</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)
