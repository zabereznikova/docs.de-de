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
ms.openlocfilehash: dc97a4173e384622fefa7de528a9725b68923ff2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="4baeb-102">ICorProfilerCallback::ModuleUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="4baeb-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="4baeb-103">Benachrichtigt den Profiler, dass ein Modul entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4baeb-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4baeb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4baeb-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4baeb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4baeb-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4baeb-106">[in] Die ID des Moduls, der entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4baeb-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="4baeb-107">[in] Ein HRESULT, das angibt, ob das Modul erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4baeb-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4baeb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4baeb-108">Remarks</span></span>  
 <span data-ttu-id="4baeb-109">Der Wert der `moduleId` gilt nicht für eine Anforderung Informationen nach der [ICorProfilerCallback:: ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) -Methode zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="4baeb-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="4baeb-110">Einige Teile der Entladen der Klasse möglicherweise weiterhin nach dem `ModuleUnloadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="4baeb-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="4baeb-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="4baeb-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="4baeb-112">Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil des Moduls entladen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="4baeb-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4baeb-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4baeb-113">Requirements</span></span>  
 <span data-ttu-id="4baeb-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4baeb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4baeb-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4baeb-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4baeb-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4baeb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4baeb-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4baeb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4baeb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4baeb-118">See Also</span></span>  
 [<span data-ttu-id="4baeb-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4baeb-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
