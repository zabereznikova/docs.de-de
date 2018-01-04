---
title: ICorProfilerCallback::ExceptionThrown-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionThrown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65fdd8f2912dc2854ba7801244ba489426d05e47
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="118a7-102">ICorProfilerCallback::ExceptionThrown-Methode</span><span class="sxs-lookup"><span data-stu-id="118a7-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="118a7-103">Benachrichtigt den Profiler, dass eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="118a7-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="118a7-104">Diese Funktion wird aufgerufen, nur dann, wenn die Ausnahme über verwalteten Code erreicht.</span><span class="sxs-lookup"><span data-stu-id="118a7-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="118a7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="118a7-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="118a7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="118a7-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="118a7-107">[in] Die ID des Objekts, das die Ausnahme ausgelöst wird, verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="118a7-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="118a7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="118a7-108">Remarks</span></span>  
 <span data-ttu-id="118a7-109">Der Profiler sollte in ihrer Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="118a7-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="118a7-110">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="118a7-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="118a7-111">Der Profiler Implementierung dieser Methode sollten nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="118a7-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="118a7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="118a7-112">Requirements</span></span>  
 <span data-ttu-id="118a7-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="118a7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="118a7-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="118a7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="118a7-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="118a7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="118a7-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="118a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118a7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="118a7-117">See Also</span></span>  
 [<span data-ttu-id="118a7-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="118a7-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
