---
title: ICorProfilerCallback::ModuleLoadFinished-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9eb5b4ec4b3bb99de4755a5b64398e989df379b7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478829"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="df3f3-102">ICorProfilerCallback::ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="df3f3-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="df3f3-103">Benachrichtigt den Profiler, dass ein Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="df3f3-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df3f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df3f3-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df3f3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df3f3-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="df3f3-106">[in] Die ID des Moduls, das geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="df3f3-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="df3f3-107">[in] Ein HRESULT, der angibt, ob das Modul erfolgreich geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="df3f3-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df3f3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df3f3-108">Remarks</span></span>  
 <span data-ttu-id="df3f3-109">Der Wert des `moduleId` gilt nicht für eine Anforderung von Informationen bis der `ModuleLoadFinished` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="df3f3-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="df3f3-110">Laden Sie das Modul möglicherweise weiterhin nach den `ModuleLoadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="df3f3-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="df3f3-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="df3f3-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="df3f3-112">Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil beim Laden des Moduls erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="df3f3-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df3f3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df3f3-113">Requirements</span></span>  
 <span data-ttu-id="df3f3-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df3f3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df3f3-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="df3f3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="df3f3-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df3f3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df3f3-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df3f3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3f3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df3f3-118">See also</span></span>
- [<span data-ttu-id="df3f3-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df3f3-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="df3f3-120">ModuleLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="df3f3-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
