---
title: ICorProfilerCallback2::HandleCreated-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type:
- apiref
ms.openlocfilehash: 772f0c00bb850e35a6f5bf7fa4df2b3052999df5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499791"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="5ea77-102">ICorProfilerCallback2::HandleCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea77-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="5ea77-103">Benachrichtigt den Codeprofiler, dass ein Garbage Collection Handle erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5ea77-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ea77-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ea77-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ea77-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ea77-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="5ea77-106">in Die ID des Handles für die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5ea77-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="5ea77-107">in Die ID des Objekts, für das das Garbage Collection Handle erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5ea77-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ea77-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5ea77-108">Requirements</span></span>  
 <span data-ttu-id="5ea77-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ea77-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ea77-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ea77-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ea77-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ea77-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ea77-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ea77-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea77-113">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="5ea77-113">See also</span></span>

- [<span data-ttu-id="5ea77-114">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ea77-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5ea77-115">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ea77-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
