---
title: ICLRPolicyManager::SetTimeout-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetTimeout
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b5042d2f06d25b2cccc81239367362313210d3c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="84a9c-102">ICLRPolicyManager::SetTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="84a9c-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="84a9c-103">Legt einen Timeoutwert für den angegebenen Vorgang fest.</span><span class="sxs-lookup"><span data-stu-id="84a9c-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84a9c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84a9c-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84a9c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84a9c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="84a9c-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der angibt, die common Language Runtime (CLR)-Vorgang für die einen Timeout festgelegt.</span><span class="sxs-lookup"><span data-stu-id="84a9c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="84a9c-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="84a9c-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="84a9c-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="84a9c-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="84a9c-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="84a9c-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="84a9c-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="84a9c-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="84a9c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="84a9c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="84a9c-112">[in] Der neue Timeoutwert in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="84a9c-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="84a9c-113">Eine UNENDLICHE führt dazu, dass den Vorgang nicht zu einem Timeout führen.</span><span class="sxs-lookup"><span data-stu-id="84a9c-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84a9c-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84a9c-114">Return Value</span></span>  
  
|<span data-ttu-id="84a9c-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84a9c-115">HRESULT</span></span>|<span data-ttu-id="84a9c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84a9c-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84a9c-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="84a9c-117">S_OK</span></span>|<span data-ttu-id="84a9c-118">`SetTimeout`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="84a9c-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="84a9c-119">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="84a9c-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84a9c-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="84a9c-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84a9c-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84a9c-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84a9c-122">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="84a9c-122">The call timed out.</span></span>|  
|<span data-ttu-id="84a9c-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84a9c-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84a9c-124">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="84a9c-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84a9c-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84a9c-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84a9c-126">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="84a9c-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84a9c-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84a9c-127">E_FAIL</span></span>|<span data-ttu-id="84a9c-128">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="84a9c-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84a9c-129">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="84a9c-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84a9c-130">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="84a9c-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="84a9c-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="84a9c-131">E_INVALIDARG</span></span>|<span data-ttu-id="84a9c-132">Ein Timeout kann nicht festgelegt werden für den angegebenen `operation`, oder es wurde ein ungültiger Wert für bereitgestellt `operation`.</span><span class="sxs-lookup"><span data-stu-id="84a9c-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84a9c-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84a9c-133">Requirements</span></span>  
 <span data-ttu-id="84a9c-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84a9c-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a9c-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="84a9c-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84a9c-136">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="84a9c-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84a9c-137">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a9c-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a9c-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84a9c-138">See Also</span></span>  
 [<span data-ttu-id="84a9c-139">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="84a9c-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="84a9c-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84a9c-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="84a9c-141">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84a9c-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
