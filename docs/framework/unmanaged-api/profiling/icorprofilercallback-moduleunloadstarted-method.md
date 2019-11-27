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
ms.openlocfilehash: f0000e9b063022e828e52b9b940ec6f4e0ce4165
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445903"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="cbc68-102">ICorProfilerCallback::ModuleUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="cbc68-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="cbc68-103">Benachrichtigt den Profiler, dass ein Modul entladen wird.</span><span class="sxs-lookup"><span data-stu-id="cbc68-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbc68-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="cbc68-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cbc68-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="cbc68-106">in Die ID des Moduls, das entladen wird.</span><span class="sxs-lookup"><span data-stu-id="cbc68-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbc68-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cbc68-107">Remarks</span></span>  
 <span data-ttu-id="cbc68-108">Der Wert `moduleId` ist für eine Informationsanforderung nicht gültig, nachdem die `ModuleUnloadStarted`-Methode zurückgegeben wurde – dies ist die letzte Möglichkeit des Profilers, Informationen zu diesem Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cbc68-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbc68-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cbc68-109">Requirements</span></span>  
 <span data-ttu-id="cbc68-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbc68-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbc68-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cbc68-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cbc68-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbc68-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbc68-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbc68-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc68-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbc68-114">See also</span></span>

- [<span data-ttu-id="cbc68-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cbc68-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cbc68-116">ModuleUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="cbc68-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
