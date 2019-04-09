---
title: ICorProfilerCallback::ThreadCreated-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f8eca3e8eb755e31e704e557ae614a6e5c1f534
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107769"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="bc0f4-102">ICorProfilerCallback::ThreadCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="bc0f4-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="bc0f4-103">Benachrichtigt den Profiler an, dass ein Thread erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bc0f4-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc0f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc0f4-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="bc0f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc0f4-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="bc0f4-106">[in] Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bc0f4-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc0f4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc0f4-107">Remarks</span></span>  
 <span data-ttu-id="bc0f4-108">Die `threadId` Wert sofort gültig ist.</span><span class="sxs-lookup"><span data-stu-id="bc0f4-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc0f4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc0f4-109">Requirements</span></span>  
 <span data-ttu-id="bc0f4-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc0f4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc0f4-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc0f4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc0f4-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc0f4-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bc0f4-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="bc0f4-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bc0f4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc0f4-114">See also</span></span>

- [<span data-ttu-id="bc0f4-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc0f4-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="bc0f4-116">ThreadDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="bc0f4-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
