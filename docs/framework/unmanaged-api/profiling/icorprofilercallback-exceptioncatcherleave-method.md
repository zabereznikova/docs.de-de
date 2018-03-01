---
title: ICorProfilerCallback::ExceptionCatcherLeave-Methode
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
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d5d46b2388621deffdad4b10d7d2376cb42ee262
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="69c3f-102">ICorProfilerCallback::ExceptionCatcherLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="69c3f-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="69c3f-103">Benachrichtigt den Profiler, der aus der entsprechenden Steuerelement übergeben wird `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="69c3f-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69c3f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69c3f-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="69c3f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69c3f-105">Remarks</span></span>  
 <span data-ttu-id="69c3f-106">Der Profiler sollte in ihrer Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="69c3f-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="69c3f-107">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="69c3f-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="69c3f-108">Der Profiler Implementierung dieser Methode sollten nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="69c3f-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69c3f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69c3f-109">Requirements</span></span>  
 <span data-ttu-id="69c3f-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69c3f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69c3f-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69c3f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69c3f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69c3f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69c3f-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69c3f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c3f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69c3f-114">See Also</span></span>  
 [<span data-ttu-id="69c3f-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69c3f-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="69c3f-116">ExceptionCatcherEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="69c3f-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
