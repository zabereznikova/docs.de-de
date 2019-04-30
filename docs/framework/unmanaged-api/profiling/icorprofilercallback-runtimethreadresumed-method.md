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
ms.openlocfilehash: 810875d1b91265fe886ce3cd11970cad7fee122d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041768"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="67199-102">ICorProfilerCallback::RuntimeThreadResumed-Methode</span><span class="sxs-lookup"><span data-stu-id="67199-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="67199-103">Benachrichtigt den Profiler an, der angegebene Thread fortgesetzt wurde, nachdem er angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="67199-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67199-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67199-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67199-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67199-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="67199-106">[in] Die ID des Threads, der fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="67199-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67199-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67199-107">Requirements</span></span>  
 <span data-ttu-id="67199-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67199-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67199-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67199-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67199-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67199-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67199-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67199-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67199-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67199-112">See also</span></span>

- [<span data-ttu-id="67199-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67199-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="67199-114">RuntimeThreadSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="67199-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
