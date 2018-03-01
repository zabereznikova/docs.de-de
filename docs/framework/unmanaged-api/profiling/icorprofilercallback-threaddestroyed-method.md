---
title: ICorProfilerCallback::ThreadDestroyed-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 419a8a0797761429f41f7472d812aaebdbbf706c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="040a8-102">ICorProfilerCallback::ThreadDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="040a8-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="040a8-103">Benachrichtigt den Profiler, dass ein Thread zerstört wurden.</span><span class="sxs-lookup"><span data-stu-id="040a8-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="040a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="040a8-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="040a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="040a8-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="040a8-106">[in] Die ID des Threads, der zerstört wurde.</span><span class="sxs-lookup"><span data-stu-id="040a8-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="040a8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="040a8-107">Remarks</span></span>  
 <span data-ttu-id="040a8-108">Die `threadId` Wert ist zum Zeitpunkt des Aufrufs nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="040a8-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="040a8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="040a8-109">Requirements</span></span>  
 <span data-ttu-id="040a8-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="040a8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="040a8-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="040a8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="040a8-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="040a8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="040a8-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="040a8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="040a8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="040a8-114">See Also</span></span>  
 [<span data-ttu-id="040a8-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="040a8-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="040a8-116">ThreadCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="040a8-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
