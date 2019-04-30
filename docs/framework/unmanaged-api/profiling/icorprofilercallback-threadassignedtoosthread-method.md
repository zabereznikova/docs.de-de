---
title: ICorProfilerCallback::ThreadAssignedToOSThread-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eefcd4436a28fdf52cbe55da5d4bb7eea4449463
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041721"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="c3438-102">ICorProfilerCallback::ThreadAssignedToOSThread-Methode</span><span class="sxs-lookup"><span data-stu-id="c3438-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="c3438-103">Benachrichtigt den Profiler an, ein verwalteter Thread mit einem bestimmten Betriebssystemthread implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c3438-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3438-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3438-104">Syntax</span></span>  
  
```  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3438-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3438-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="c3438-106">[in] Der Bezeichner des verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="c3438-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="c3438-107">[in] Der Bezeichner des Threads Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="c3438-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3438-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3438-108">Remarks</span></span>  
 <span data-ttu-id="c3438-109">Die `ThreadAssignedToOSThread` Rückruf vorhanden ist, damit der Profiler die genaue Zuordnung für Fibers von Betriebssystemthreads an verwaltete Threads verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="c3438-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3438-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c3438-110">Requirements</span></span>  
 <span data-ttu-id="c3438-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3438-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3438-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3438-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3438-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3438-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3438-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3438-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3438-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3438-115">See also</span></span>

- [<span data-ttu-id="c3438-116">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c3438-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
