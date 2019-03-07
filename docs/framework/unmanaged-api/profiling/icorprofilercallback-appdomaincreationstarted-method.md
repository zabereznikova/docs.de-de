---
title: ICorProfilerCallback::AppDomainCreationStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bffa383734a96a32595b018fd6d9b3dc62d5526
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484757"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="80c52-102">ICorProfilerCallback::AppDomainCreationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="80c52-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="80c52-103">Benachrichtigt den Profiler an, dass eine Anwendungsdomäne erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="80c52-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80c52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80c52-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80c52-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="80c52-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="80c52-106">[in] Gibt die Domäne, die erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="80c52-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80c52-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80c52-107">Remarks</span></span>  
 <span data-ttu-id="80c52-108">Die ID ist ungültig für jede informationsanforderung, bis die [ICorProfilerCallback:: AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="80c52-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80c52-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80c52-109">Requirements</span></span>  
 <span data-ttu-id="80c52-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80c52-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80c52-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="80c52-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="80c52-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80c52-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80c52-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80c52-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c52-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80c52-114">See also</span></span>
- [<span data-ttu-id="80c52-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80c52-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
