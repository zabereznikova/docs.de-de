---
title: ICorProfilerCallback::AppDomainCreationFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainCreationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d21198253e10434b37261d34cf12ef60c26f7e71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="9b3d1-102">ICorProfilerCallback::AppDomainCreationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="9b3d1-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="9b3d1-103">Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9b3d1-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b3d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b3d1-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b3d1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b3d1-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="9b3d1-106">[in] Identifiziert die Domäne, die erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9b3d1-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="9b3d1-107">[in] Ein HRESULT, das angibt, ob die Erstellung der Anwendungsdomäne erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9b3d1-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b3d1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b3d1-108">Remarks</span></span>  
 <span data-ttu-id="9b3d1-109">Die Anwendungs-ID ist ungültig für jede Anforderung Informationen, bis die `AppDomainCreationFinished` -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9b3d1-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="9b3d1-110">Einige Teile die Anwendungsdomäne laden möglicherweise weiterhin nach dem `AppDomainCreationFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="9b3d1-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="9b3d1-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="9b3d1-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="9b3d1-112">Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil des Erstellens der Anwendungsdomäne erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="9b3d1-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b3d1-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b3d1-113">Requirements</span></span>  
 <span data-ttu-id="9b3d1-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b3d1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b3d1-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9b3d1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9b3d1-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b3d1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b3d1-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b3d1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b3d1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b3d1-118">See Also</span></span>  
 [<span data-ttu-id="9b3d1-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b3d1-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
