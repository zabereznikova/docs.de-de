---
title: ICorProfilerCallback::ModuleLoadFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 360c14ccdd67cb7609ffe2f9c49914fdda163389
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="f86b4-102">ICorProfilerCallback::ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="f86b4-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="f86b4-103">Benachrichtigt den Profiler, dass ein Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="f86b4-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f86b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f86b4-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f86b4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f86b4-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="f86b4-106">[in] Die ID des Moduls, das nach dem Laden.</span><span class="sxs-lookup"><span data-stu-id="f86b4-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="f86b4-107">[in] Ein HRESULT, der angibt, ob das Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="f86b4-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f86b4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f86b4-108">Remarks</span></span>  
 <span data-ttu-id="f86b4-109">Der Wert der `moduleId` gilt nicht für eine Anforderung Informationen, bis die `ModuleLoadFinished` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f86b4-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="f86b4-110">Einige Teile des Ladevorgangs für das Modul möglicherweise weiterhin nach dem `ModuleLoadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="f86b4-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="f86b4-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="f86b4-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="f86b4-112">Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil des Ladevorgangs für das Modul erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="f86b4-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f86b4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f86b4-113">Requirements</span></span>  
 <span data-ttu-id="f86b4-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f86b4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f86b4-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f86b4-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f86b4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f86b4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f86b4-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f86b4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f86b4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f86b4-118">See Also</span></span>  
 [<span data-ttu-id="f86b4-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f86b4-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f86b4-120">ModuleLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="f86b4-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
