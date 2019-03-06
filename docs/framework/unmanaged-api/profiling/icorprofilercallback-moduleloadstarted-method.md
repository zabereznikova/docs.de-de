---
title: ICorProfilerCallback::ModuleLoadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7bc4b1a58bba592cfff408f034fb19c0c27616c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480545"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="aaaec-102">ICorProfilerCallback::ModuleLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="aaaec-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="aaaec-103">Benachrichtigt den Profiler, dass ein Modul geladen wird.</span><span class="sxs-lookup"><span data-stu-id="aaaec-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaaec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aaaec-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aaaec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aaaec-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="aaaec-106">[in] Die ID des Moduls, das geladen wird.</span><span class="sxs-lookup"><span data-stu-id="aaaec-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aaaec-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aaaec-107">Remarks</span></span>  
 <span data-ttu-id="aaaec-108">Der Wert des `moduleId` gilt nicht für eine Anforderung von Informationen bis der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="aaaec-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaaec-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aaaec-109">Requirements</span></span>  
 <span data-ttu-id="aaaec-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aaaec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaaec-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aaaec-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aaaec-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aaaec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aaaec-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaaec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaaec-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaaec-114">See also</span></span>
- [<span data-ttu-id="aaaec-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aaaec-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
