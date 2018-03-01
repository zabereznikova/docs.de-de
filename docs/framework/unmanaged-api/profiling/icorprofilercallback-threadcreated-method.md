---
title: ICorProfilerCallback::ThreadCreated-Methode
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
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 01062931e64cf8daa698fd99d4e6318a7a8f6a5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="dd731-102">ICorProfilerCallback::ThreadCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="dd731-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="dd731-103">Benachrichtigt den Profiler, dass ein Thread erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="dd731-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd731-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd731-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd731-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dd731-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="dd731-106">[in] Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="dd731-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd731-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd731-107">Remarks</span></span>  
 <span data-ttu-id="dd731-108">Die `threadId` Wert sofort gültig ist.</span><span class="sxs-lookup"><span data-stu-id="dd731-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd731-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd731-109">Requirements</span></span>  
 <span data-ttu-id="dd731-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd731-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd731-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dd731-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dd731-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd731-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd731-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd731-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd731-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd731-114">See Also</span></span>  
 [<span data-ttu-id="dd731-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd731-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="dd731-116">ThreadDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="dd731-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
