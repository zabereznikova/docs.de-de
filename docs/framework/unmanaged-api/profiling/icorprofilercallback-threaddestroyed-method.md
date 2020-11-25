---
title: ICorProfilerCallback::ThreadDestroyed-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
ms.openlocfilehash: 0cef868861155d553aba42fe28c3f1f1b86763b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731968"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="6f5a6-102">ICorProfilerCallback::ThreadDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="6f5a6-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>

<span data-ttu-id="6f5a6-103">Benachrichtigt den Profiler, dass ein Thread zerstört wurde.</span><span class="sxs-lookup"><span data-stu-id="6f5a6-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f5a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f5a6-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f5a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f5a6-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="6f5a6-106">in Die ID des Threads, der zerstört wurde.</span><span class="sxs-lookup"><span data-stu-id="6f5a6-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f5a6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f5a6-107">Remarks</span></span>  

 <span data-ttu-id="6f5a6-108">Der `threadId` Wert ist zum Zeitpunkt des Aufrufes nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="6f5a6-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f5a6-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f5a6-109">Requirements</span></span>  

 <span data-ttu-id="6f5a6-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f5a6-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f5a6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f5a6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f5a6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f5a6-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f5a6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5a6-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f5a6-114">See also</span></span>

- [<span data-ttu-id="6f5a6-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f5a6-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6f5a6-116">ThreadCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="6f5a6-116">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
