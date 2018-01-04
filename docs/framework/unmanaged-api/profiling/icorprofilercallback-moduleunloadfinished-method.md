---
title: ICorProfilerCallback::ModuleUnloadFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6f9f048d60d2d463e3d846fadda91932a9a2a091
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="7c75d-102">ICorProfilerCallback::ModuleUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="7c75d-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="7c75d-103">Benachrichtigt den Profiler, dass ein Modul entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7c75d-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c75d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c75d-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c75d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c75d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="7c75d-106">[in] Die ID des Moduls, der entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7c75d-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="7c75d-107">[in] Ein HRESULT, das angibt, ob das Modul erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7c75d-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c75d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c75d-108">Remarks</span></span>  
 <span data-ttu-id="7c75d-109">Der Wert der `moduleId` gilt nicht für eine Anforderung Informationen nach der [ICorProfilerCallback:: ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) -Methode zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="7c75d-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="7c75d-110">Einige Teile der Entladen der Klasse möglicherweise weiterhin nach dem `ModuleUnloadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="7c75d-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="7c75d-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="7c75d-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="7c75d-112">Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil des Moduls entladen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7c75d-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c75d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c75d-113">Requirements</span></span>  
 <span data-ttu-id="7c75d-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c75d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c75d-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c75d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c75d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c75d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c75d-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c75d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c75d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c75d-118">See Also</span></span>  
 [<span data-ttu-id="7c75d-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c75d-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
