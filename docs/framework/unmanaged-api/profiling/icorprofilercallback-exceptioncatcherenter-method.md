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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9b47e1d1bfa1d8f6c970e95fe25f62a690d3b91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143863"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="361a0-102">ICorProfilerCallback::ExceptionCatcherEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="361a0-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="361a0-103">Benachrichtigt den Profiler, das Steuerelement an den entsprechenden übergebenen `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="361a0-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="361a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="361a0-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="361a0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="361a0-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="361a0-106">[in] Der Bezeichner der Funktion mit dem `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="361a0-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="361a0-107">[in] Der Bezeichner der Ausnahme behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="361a0-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="361a0-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="361a0-108">Remarks</span></span>  
 <span data-ttu-id="361a0-109">Die `ExceptionCatcherEnter` Methode wird aufgerufen, nur dann, wenn der Catch-Punkt im Code, der mit dem Compiler just-in-Time (JIT) kompiliert ist.</span><span class="sxs-lookup"><span data-stu-id="361a0-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="361a0-110">Kein Aufruf eine Ausnahme, die in nicht verwaltetem Code oder in den internen Code der Laufzeit abgefangen wird diese Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="361a0-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="361a0-111">Die `objectId` erneut Wert übergeben wird, da eine Garbagecollection verschoben wurden, das Objekt seit konnte die `ExceptionThrown` Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="361a0-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="361a0-112">Der Profiler sollte die Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="361a0-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="361a0-113">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="361a0-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="361a0-114">Der Profiler Implementierung dieser Methode sollte nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="361a0-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="361a0-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="361a0-115">Requirements</span></span>  
 <span data-ttu-id="361a0-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="361a0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="361a0-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="361a0-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="361a0-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="361a0-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="361a0-119">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="361a0-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="361a0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="361a0-120">See also</span></span>

- [<span data-ttu-id="361a0-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="361a0-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="361a0-122">ExceptionCatcherLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="361a0-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
