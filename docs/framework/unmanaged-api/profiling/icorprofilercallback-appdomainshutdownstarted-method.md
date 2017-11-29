---
title: ICorProfilerCallback::AppDomainShutdownStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainShutdownStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5eff8807b5f50708b8d8e4935052de89f59eb5d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="d8407-102">ICorProfilerCallback::AppDomainShutdownStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="d8407-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="d8407-103">Benachrichtigt den Profiler, dass von einem Prozess eine Anwendungsdomäne entladen wird.</span><span class="sxs-lookup"><span data-stu-id="d8407-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8407-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8407-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8407-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8407-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="d8407-106">[in] Identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="d8407-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8407-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8407-107">Remarks</span></span>  
 <span data-ttu-id="d8407-108">Der Wert der `appDomainId` gilt nicht für jede Anforderung Informationen nach der `AppDomainShutdownStarted` -Methode zurückkehrt – Dies ist der Profiler die letzte Möglichkeit zum Abrufen von Informationen zu dieser Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="d8407-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8407-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d8407-109">Requirements</span></span>  
 <span data-ttu-id="d8407-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8407-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8407-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8407-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8407-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8407-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8407-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8407-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8407-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8407-114">See Also</span></span>  
 [<span data-ttu-id="d8407-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8407-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
