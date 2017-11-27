---
title: ICorProfilerCallback::ModuleLoadStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleLoadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ad525b44169a85e61140c9e2a8d83c967945b2f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="8584f-102">ICorProfilerCallback::ModuleLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="8584f-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="8584f-103">Benachrichtigt den Profiler, dass ein Modul geladen wird.</span><span class="sxs-lookup"><span data-stu-id="8584f-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8584f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8584f-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8584f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8584f-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="8584f-106">[in] Die ID des Moduls, das geladen wird.</span><span class="sxs-lookup"><span data-stu-id="8584f-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8584f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8584f-107">Remarks</span></span>  
 <span data-ttu-id="8584f-108">Der Wert der `moduleId` gilt nicht für eine Anforderung Informationen, bis die [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8584f-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8584f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8584f-109">Requirements</span></span>  
 <span data-ttu-id="8584f-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8584f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8584f-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8584f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8584f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8584f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8584f-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8584f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8584f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8584f-114">See Also</span></span>  
 [<span data-ttu-id="8584f-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8584f-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
