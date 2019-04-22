---
title: ICorProfilerCallback2::HandleDestroyed-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc6b086b444a769afbf01369b50c69e242a21050
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090484"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="badaf-102">ICorProfilerCallback2::HandleDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="badaf-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="badaf-103">Benachrichtigt den Profiler, dass eine Garbage Collection-Handle zerstört wurde.</span><span class="sxs-lookup"><span data-stu-id="badaf-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="badaf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="badaf-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="badaf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="badaf-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="badaf-106">[in] Die ID des Handles für die Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="badaf-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="badaf-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="badaf-107">Requirements</span></span>  
 <span data-ttu-id="badaf-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="badaf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="badaf-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="badaf-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="badaf-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="badaf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="badaf-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="badaf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="badaf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="badaf-112">See also</span></span>

- [<span data-ttu-id="badaf-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="badaf-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="badaf-114">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="badaf-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
