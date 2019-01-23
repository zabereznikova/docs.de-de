---
title: ICorProfilerCallback::RuntimeThreadResumed-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d1198a931b79cb469048bf5afd48f5172a45721
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517707"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="7f91b-102">ICorProfilerCallback::RuntimeThreadResumed-Methode</span><span class="sxs-lookup"><span data-stu-id="7f91b-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="7f91b-103">Benachrichtigt den Profiler an, der angegebene Thread fortgesetzt wurde, nachdem er angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="7f91b-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f91b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f91b-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f91b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7f91b-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="7f91b-106">[in] Die ID des Threads, der fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="7f91b-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f91b-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7f91b-107">Requirements</span></span>  
 <span data-ttu-id="7f91b-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f91b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f91b-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7f91b-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7f91b-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f91b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f91b-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f91b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f91b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f91b-112">See also</span></span>
- [<span data-ttu-id="7f91b-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f91b-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7f91b-114">RuntimeThreadSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="7f91b-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
