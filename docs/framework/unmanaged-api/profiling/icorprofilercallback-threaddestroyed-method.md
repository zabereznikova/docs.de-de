---
title: ICorProfilerCallback::ThreadDestroyed-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ThreadDestroyed
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d9448458930a39c0bcd3d21dc4ea6e8e7c15cf0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="25caf-102">ICorProfilerCallback::ThreadDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="25caf-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="25caf-103">Benachrichtigt den Profiler, dass ein Thread zerstört wurden.</span><span class="sxs-lookup"><span data-stu-id="25caf-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25caf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25caf-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25caf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="25caf-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="25caf-106">[in] Die ID des Threads, der zerstört wurde.</span><span class="sxs-lookup"><span data-stu-id="25caf-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25caf-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25caf-107">Remarks</span></span>  
 <span data-ttu-id="25caf-108">Die `threadId` Wert ist zum Zeitpunkt des Aufrufs nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="25caf-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25caf-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25caf-109">Requirements</span></span>  
 <span data-ttu-id="25caf-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25caf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25caf-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="25caf-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="25caf-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25caf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25caf-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25caf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25caf-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25caf-114">See Also</span></span>  
 [<span data-ttu-id="25caf-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25caf-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="25caf-116">ThreadCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="25caf-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
