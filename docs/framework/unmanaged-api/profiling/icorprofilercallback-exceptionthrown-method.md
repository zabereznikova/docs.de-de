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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb95c11900b84b78a3f862bcb73f0700aaabeeaa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755981"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="4e100-102">ICorProfilerCallback::ExceptionThrown-Methode</span><span class="sxs-lookup"><span data-stu-id="4e100-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="4e100-103">Benachrichtigt den Profiler an, dass eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="4e100-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e100-104">Diese Funktion wird aufgerufen, nur dann, wenn die Ausnahme über verwalteten Code erreicht.</span><span class="sxs-lookup"><span data-stu-id="4e100-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e100-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e100-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e100-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e100-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="4e100-107">[in] Die ID des Objekts, das die auszulösende Ausnahme verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="4e100-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e100-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e100-108">Remarks</span></span>  
 <span data-ttu-id="4e100-109">Der Profiler sollte die Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e100-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="4e100-110">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4e100-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="4e100-111">Der Profiler Implementierung dieser Methode sollte nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4e100-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e100-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e100-112">Requirements</span></span>  
 <span data-ttu-id="4e100-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e100-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e100-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e100-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e100-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e100-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e100-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e100-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e100-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e100-117">See also</span></span>

- [<span data-ttu-id="4e100-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e100-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
