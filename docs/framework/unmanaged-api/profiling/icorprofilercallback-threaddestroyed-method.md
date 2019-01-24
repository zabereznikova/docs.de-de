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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 40bbde940538d7b06aa74ab55986da2dca3ec225
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599503"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="77671-102">ICorProfilerCallback::ThreadDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="77671-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="77671-103">Benachrichtigt den Profiler, dass ein Thread zerstört wurde.</span><span class="sxs-lookup"><span data-stu-id="77671-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77671-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77671-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77671-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="77671-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="77671-106">[in] Die ID des Threads, die zerstört wurde.</span><span class="sxs-lookup"><span data-stu-id="77671-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77671-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77671-107">Remarks</span></span>  
 <span data-ttu-id="77671-108">Die `threadId` Wert ist zum Zeitpunkt des Aufrufs nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="77671-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77671-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77671-109">Requirements</span></span>  
 <span data-ttu-id="77671-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77671-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77671-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="77671-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="77671-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77671-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77671-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77671-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77671-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77671-114">See also</span></span>
- [<span data-ttu-id="77671-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77671-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="77671-116">ThreadCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="77671-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
