---
title: ICorProfilerCallback::ClassUnloadFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9801113e23474fa0aae461d356e4aa57a203bd6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="bd766-102">ICorProfilerCallback::ClassUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="bd766-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="bd766-103">Benachrichtigt den Profiler, dass eine Klasse entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd766-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd766-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd766-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd766-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd766-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="bd766-106">[in] Identifiziert die Klasse, die entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd766-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="bd766-107">[in] Ein HRESULT, das angibt, ob die Klasse erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd766-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd766-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd766-108">Remarks</span></span>  
 <span data-ttu-id="bd766-109">Einige Teile der Entladen der Klasse möglicherweise weiterhin nach dem `ClassUnloadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="bd766-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="bd766-110">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="bd766-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="bd766-111">Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil, das Entladen der Klasse erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bd766-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd766-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd766-112">Requirements</span></span>  
 <span data-ttu-id="bd766-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd766-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd766-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd766-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd766-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd766-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd766-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd766-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd766-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd766-117">See Also</span></span>  
 [<span data-ttu-id="bd766-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd766-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="bd766-119">ClassUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="bd766-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
