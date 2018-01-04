---
title: ICorProfilerCallback::ModuleUnloadStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 384d655254cc79283f93ff2e608b0429c4a84ae8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="b37a6-102">ICorProfilerCallback::ModuleUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="b37a6-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="b37a6-103">Benachrichtigt den Profiler, dass ein Modul entladen wird.</span><span class="sxs-lookup"><span data-stu-id="b37a6-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b37a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b37a6-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="b37a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b37a6-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="b37a6-106">[in] Die ID des Moduls, das entladen wird.</span><span class="sxs-lookup"><span data-stu-id="b37a6-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b37a6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b37a6-107">Remarks</span></span>  
 <span data-ttu-id="b37a6-108">Der Wert der `moduleId` gilt nicht für eine Anforderung Informationen nach der `ModuleUnloadStarted` -Methode zurückkehrt – Dies ist der Profiler die letzte Möglichkeit zum Abrufen von Informationen zu diesem Modul.</span><span class="sxs-lookup"><span data-stu-id="b37a6-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b37a6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b37a6-109">Requirements</span></span>  
 <span data-ttu-id="b37a6-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b37a6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b37a6-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b37a6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b37a6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b37a6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b37a6-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b37a6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b37a6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b37a6-114">See Also</span></span>  
 [<span data-ttu-id="b37a6-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b37a6-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b37a6-116">ModuleUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="b37a6-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
