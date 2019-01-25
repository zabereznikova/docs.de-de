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
ms.openlocfilehash: f4f6f5dd757fde9d49fe8b5a1709d6d5876ce5b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592207"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="74d7a-102">ICorProfilerCallback::ExceptionCatcherLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="74d7a-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="74d7a-103">Benachrichtigt den Profiler, das Steuerelement aus der entsprechenden übergebenen `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="74d7a-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d7a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74d7a-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="74d7a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74d7a-105">Remarks</span></span>  
 <span data-ttu-id="74d7a-106">Der Profiler sollte die Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="74d7a-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="74d7a-107">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="74d7a-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="74d7a-108">Der Profiler Implementierung dieser Methode sollte nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="74d7a-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74d7a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74d7a-109">Requirements</span></span>  
 <span data-ttu-id="74d7a-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74d7a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74d7a-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74d7a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74d7a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74d7a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74d7a-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74d7a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d7a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74d7a-114">See also</span></span>
- [<span data-ttu-id="74d7a-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74d7a-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="74d7a-116">ExceptionCatcherEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="74d7a-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
