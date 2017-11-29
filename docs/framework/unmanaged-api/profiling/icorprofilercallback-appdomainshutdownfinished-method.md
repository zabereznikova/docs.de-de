---
title: ICorProfilerCallback::AppDomainShutdownFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainShutdownFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 443f5cd48693d6ac3ce732746666bd2d5e3786fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="fd02d-102">ICorProfilerCallback::AppDomainShutdownFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="fd02d-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="fd02d-103">Benachrichtigt den Profiler, dass eine Anwendungsdomäne aus einem Prozess entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fd02d-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd02d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd02d-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd02d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd02d-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="fd02d-106">[in] Identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="fd02d-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="fd02d-107">[in] Ein HRESULT, das angibt, ob die Anwendungsdomäne erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fd02d-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd02d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd02d-108">Remarks</span></span>  
 <span data-ttu-id="fd02d-109">Der Wert der `appDomainId` gilt nicht für eine Anforderung Informationen nach der [ICorProfilerCallback:: AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) -Methode zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="fd02d-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="fd02d-110">Einige Teile der Entladen der Anwendungsdomäne möglicherweise weiterhin nach dem `AppDomainCreationFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="fd02d-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="fd02d-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="fd02d-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="fd02d-112">Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil des Entladen der Anwendungsdomäne erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="fd02d-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd02d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd02d-113">Requirements</span></span>  
 <span data-ttu-id="fd02d-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd02d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd02d-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd02d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd02d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd02d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd02d-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd02d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd02d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd02d-118">See Also</span></span>  
 [<span data-ttu-id="fd02d-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd02d-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
