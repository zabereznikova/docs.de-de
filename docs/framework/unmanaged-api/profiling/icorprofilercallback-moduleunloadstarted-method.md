---
title: ICorProfilerCallback::ModuleUnloadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb00a56b0d80b78867f70e64c1c9bdf0fc49e1be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041937"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="5e25f-102">ICorProfilerCallback::ModuleUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="5e25f-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="5e25f-103">Benachrichtigt den Profiler an, dass ein Modul entladen wird.</span><span class="sxs-lookup"><span data-stu-id="5e25f-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e25f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e25f-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="5e25f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e25f-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="5e25f-106">[in] Die ID des Moduls, das entladen wird.</span><span class="sxs-lookup"><span data-stu-id="5e25f-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e25f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e25f-107">Remarks</span></span>  
 <span data-ttu-id="5e25f-108">Der Wert des `moduleId` gilt nicht für eine informationsanforderung nach der `ModuleUnloadStarted` Methodenrückgabe – Dies ist der Profiler letzte Gelegenheit zum Abrufen von Informationen zu diesem Modul.</span><span class="sxs-lookup"><span data-stu-id="5e25f-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e25f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e25f-109">Requirements</span></span>  
 <span data-ttu-id="5e25f-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e25f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e25f-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e25f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e25f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e25f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e25f-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e25f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e25f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e25f-114">See also</span></span>

- [<span data-ttu-id="5e25f-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e25f-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5e25f-116">ModuleUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="5e25f-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
