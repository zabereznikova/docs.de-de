---
title: ICLRPolicyManager::SetTimeout-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b5a389af718322d1e0fffebae046bf28731877b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435776"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="b79ad-102">ICLRPolicyManager::SetTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="b79ad-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="b79ad-103">Legt einen Timeoutwert für den angegebenen Vorgang fest.</span><span class="sxs-lookup"><span data-stu-id="b79ad-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b79ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b79ad-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b79ad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b79ad-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="b79ad-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der angibt, die common Language Runtime (CLR)-Vorgang für die einen Timeout festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b79ad-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="b79ad-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b79ad-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="b79ad-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="b79ad-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="b79ad-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="b79ad-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="b79ad-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b79ad-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="b79ad-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b79ad-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="b79ad-112">[in] Der neue Timeoutwert in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="b79ad-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="b79ad-113">Eine UNENDLICHE führt dazu, dass den Vorgang nicht zu einem Timeout führen.</span><span class="sxs-lookup"><span data-stu-id="b79ad-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b79ad-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b79ad-114">Return Value</span></span>  
  
|<span data-ttu-id="b79ad-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b79ad-115">HRESULT</span></span>|<span data-ttu-id="b79ad-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b79ad-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b79ad-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="b79ad-117">S_OK</span></span>|<span data-ttu-id="b79ad-118">`SetTimeout` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b79ad-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="b79ad-119">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="b79ad-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b79ad-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b79ad-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b79ad-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b79ad-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b79ad-122">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b79ad-122">The call timed out.</span></span>|  
|<span data-ttu-id="b79ad-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b79ad-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b79ad-124">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b79ad-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b79ad-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b79ad-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b79ad-126">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="b79ad-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b79ad-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b79ad-127">E_FAIL</span></span>|<span data-ttu-id="b79ad-128">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b79ad-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b79ad-129">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b79ad-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b79ad-130">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b79ad-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b79ad-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b79ad-131">E_INVALIDARG</span></span>|<span data-ttu-id="b79ad-132">Ein Timeout kann nicht festgelegt werden für den angegebenen `operation`, oder es wurde ein ungültiger Wert für bereitgestellt `operation`.</span><span class="sxs-lookup"><span data-stu-id="b79ad-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b79ad-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b79ad-133">Requirements</span></span>  
 <span data-ttu-id="b79ad-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b79ad-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b79ad-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b79ad-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b79ad-136">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b79ad-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b79ad-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b79ad-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79ad-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b79ad-138">See Also</span></span>  
 [<span data-ttu-id="b79ad-139">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b79ad-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="b79ad-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b79ad-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="b79ad-141">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b79ad-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
