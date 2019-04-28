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
ms.openlocfilehash: e9cdbc2234519c0dba1a5004246492e7609ea2b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597894"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="ecbee-102">ICorProfilerCallback::ExceptionThrown-Methode</span><span class="sxs-lookup"><span data-stu-id="ecbee-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="ecbee-103">Benachrichtigt den Profiler an, dass eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="ecbee-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecbee-104">Diese Funktion wird aufgerufen, nur dann, wenn die Ausnahme über verwalteten Code erreicht.</span><span class="sxs-lookup"><span data-stu-id="ecbee-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecbee-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecbee-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecbee-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ecbee-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="ecbee-107">[in] Die ID des Objekts, das die auszulösende Ausnahme verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="ecbee-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecbee-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecbee-108">Remarks</span></span>  
 <span data-ttu-id="ecbee-109">Der Profiler sollte die Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ecbee-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="ecbee-110">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ecbee-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="ecbee-111">Der Profiler Implementierung dieser Methode sollte nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ecbee-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecbee-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ecbee-112">Requirements</span></span>  
 <span data-ttu-id="ecbee-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecbee-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecbee-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ecbee-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ecbee-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecbee-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecbee-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecbee-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbee-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecbee-117">See also</span></span>

- [<span data-ttu-id="ecbee-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ecbee-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
