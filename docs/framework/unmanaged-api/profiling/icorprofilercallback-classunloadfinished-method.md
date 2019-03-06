---
title: ICorProfilerCallback::ClassUnloadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6330267c580901c62a74bf6d8ee8716c4fd3b1cb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468142"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="6a5ea-102">ICorProfilerCallback::ClassUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="6a5ea-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="6a5ea-103">Benachrichtigt den Profiler, dass eine Klasse vollständig entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="6a5ea-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a5ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a5ea-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a5ea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a5ea-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="6a5ea-106">[in] Identifiziert die Klasse, die entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="6a5ea-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="6a5ea-107">[in] Ein HRESULT, der angibt, ob die Klasse erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="6a5ea-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a5ea-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a5ea-108">Remarks</span></span>  
 <span data-ttu-id="6a5ea-109">Das Entladen der Klasse möglicherweise weiterhin nach den `ClassUnloadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="6a5ea-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="6a5ea-110">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="6a5ea-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="6a5ea-111">Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil, das Entladen der Klasse erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6a5ea-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a5ea-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a5ea-112">Requirements</span></span>  
 <span data-ttu-id="6a5ea-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a5ea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a5ea-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a5ea-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a5ea-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a5ea-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a5ea-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a5ea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a5ea-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a5ea-117">See also</span></span>
- [<span data-ttu-id="6a5ea-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a5ea-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="6a5ea-119">ClassUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="6a5ea-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
