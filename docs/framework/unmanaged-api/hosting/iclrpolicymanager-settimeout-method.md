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
ms.openlocfilehash: b16cc6a899b1ad5c814c29a93c6125250ca8186d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133574"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="52666-102">ICLRPolicyManager::SetTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="52666-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="52666-103">Legt einen Timeoutwert für den angegebenen Vorgang fest.</span><span class="sxs-lookup"><span data-stu-id="52666-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52666-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52666-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52666-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="52666-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="52666-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der angibt, die common Language Runtime (CLR)-Vorgang für die einen Timeout festgelegt.</span><span class="sxs-lookup"><span data-stu-id="52666-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="52666-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="52666-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="52666-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="52666-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="52666-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="52666-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="52666-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="52666-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="52666-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="52666-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="52666-112">[in] Der neue Timeoutwert in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="52666-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="52666-113">Der Wert INFINITE bewirkt, dass den Vorgang nicht zu einem Timeout.</span><span class="sxs-lookup"><span data-stu-id="52666-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52666-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="52666-114">Return Value</span></span>  
  
|<span data-ttu-id="52666-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52666-115">HRESULT</span></span>|<span data-ttu-id="52666-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52666-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52666-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="52666-117">S_OK</span></span>|<span data-ttu-id="52666-118">`SetTimeout` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="52666-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="52666-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52666-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52666-120">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="52666-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52666-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52666-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52666-122">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="52666-122">The call timed out.</span></span>|  
|<span data-ttu-id="52666-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52666-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52666-124">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="52666-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52666-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52666-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52666-126">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="52666-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52666-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52666-127">E_FAIL</span></span>|<span data-ttu-id="52666-128">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="52666-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52666-129">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52666-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52666-130">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="52666-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="52666-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="52666-131">E_INVALIDARG</span></span>|<span data-ttu-id="52666-132">Ein Timeout kann nicht festgelegt werden für den angegebenen `operation`, oder es wurde ein ungültiger Wert für bereitgestellt `operation`.</span><span class="sxs-lookup"><span data-stu-id="52666-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52666-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52666-133">Requirements</span></span>  
 <span data-ttu-id="52666-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52666-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52666-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="52666-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52666-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="52666-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52666-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52666-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52666-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52666-138">See also</span></span>

- [<span data-ttu-id="52666-139">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="52666-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="52666-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52666-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="52666-141">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52666-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
