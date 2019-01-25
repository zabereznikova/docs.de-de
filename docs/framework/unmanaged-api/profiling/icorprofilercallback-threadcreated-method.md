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
ms.openlocfilehash: d85dcb462df0255ab5420db94f9d055cce2c78b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616932"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="89f23-102">ICorProfilerCallback::ThreadCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="89f23-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="89f23-103">Benachrichtigt den Profiler an, dass ein Thread erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="89f23-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89f23-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="89f23-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="89f23-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="89f23-106">[in] Die ID des Threads, der erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="89f23-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89f23-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89f23-107">Remarks</span></span>  
 <span data-ttu-id="89f23-108">Die `threadId` Wert sofort gültig ist.</span><span class="sxs-lookup"><span data-stu-id="89f23-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89f23-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89f23-109">Requirements</span></span>  
 <span data-ttu-id="89f23-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89f23-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89f23-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89f23-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89f23-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89f23-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89f23-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89f23-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f23-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89f23-114">See also</span></span>
- [<span data-ttu-id="89f23-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89f23-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="89f23-116">ThreadDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="89f23-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
