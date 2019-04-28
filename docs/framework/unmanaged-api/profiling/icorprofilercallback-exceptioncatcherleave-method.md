---
title: ICorProfilerCallback::ExceptionCatcherLeave-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7f1b2756dd180cb0a701429978a34ea80447a86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598011"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="b362b-102">ICorProfilerCallback::ExceptionCatcherLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="b362b-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="b362b-103">Benachrichtigt den Profiler, das Steuerelement aus der entsprechenden übergebenen `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="b362b-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b362b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b362b-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b362b-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b362b-105">Remarks</span></span>  
 <span data-ttu-id="b362b-106">Der Profiler sollte die Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b362b-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="b362b-107">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b362b-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="b362b-108">Der Profiler Implementierung dieser Methode sollte nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b362b-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b362b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b362b-109">Requirements</span></span>  
 <span data-ttu-id="b362b-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b362b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b362b-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b362b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b362b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b362b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b362b-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b362b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b362b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b362b-114">See also</span></span>

- [<span data-ttu-id="b362b-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b362b-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b362b-116">ExceptionCatcherEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="b362b-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
