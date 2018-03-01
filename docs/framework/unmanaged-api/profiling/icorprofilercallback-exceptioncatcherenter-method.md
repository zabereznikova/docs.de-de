---
title: ICorProfilerCallback::ExceptionCatcherEnter-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a72b2e75ee622bab357046ff29fac4aa9223d7a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="4187e-102">ICorProfilerCallback::ExceptionCatcherEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="4187e-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="4187e-103">Benachrichtigt den Profiler, der in das entsprechende Steuerelement übergeben wird `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="4187e-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4187e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4187e-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4187e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4187e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4187e-106">[in] Der Bezeichner von die Funktion mit dem `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="4187e-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="4187e-107">[in] Der Bezeichner für die Ausnahme verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="4187e-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4187e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4187e-108">Remarks</span></span>  
 <span data-ttu-id="4187e-109">Die `ExceptionCatcherEnter` Methode wird nur aufgerufen, wenn der Catch-Punkt im Code mit der Just-in-Time (JIT)-Compiler kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="4187e-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="4187e-110">Eine Ausnahme, die in nicht verwaltetem Code oder im internen Code der Laufzeit abgefangen wird wird diese Benachrichtigung nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4187e-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="4187e-111">Die `objectId` erneut Wert übergeben wird, da eine Garbagecollection verschoben haben, das Objekt seit konnte die `ExceptionThrown` Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="4187e-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="4187e-112">Der Profiler sollte in ihrer Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4187e-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="4187e-113">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4187e-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="4187e-114">Der Profiler Implementierung dieser Methode sollten nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4187e-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4187e-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4187e-115">Requirements</span></span>  
 <span data-ttu-id="4187e-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4187e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4187e-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4187e-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4187e-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4187e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4187e-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4187e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4187e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4187e-120">See Also</span></span>  
 [<span data-ttu-id="4187e-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4187e-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="4187e-122">ExceptionCatcherLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="4187e-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
