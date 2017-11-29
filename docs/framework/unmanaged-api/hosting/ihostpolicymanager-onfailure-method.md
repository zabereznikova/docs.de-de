---
title: IHostPolicyManager::OnFailure-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager.OnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd8c5e071eca6b287b570006f33d7a1a43c1def9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="3bd05-102">IHostPolicyManager::OnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="3bd05-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="3bd05-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) die Aktionen angegeben, die durch einen Aufruf der [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) Methode als Reaktion auf einen Fehler bei der Reservierung oder Freigabe von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="3bd05-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bd05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bd05-104">Syntax</span></span>  
  
```  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3bd05-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3bd05-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="3bd05-106">[in] Eines der [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) Werte, der die Art des Fehlers, der die CLR reagiert.</span><span class="sxs-lookup"><span data-stu-id="3bd05-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="3bd05-107">[in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, der angibt, der die CLR-Aktion als Antwort auf dauert `failure`.</span><span class="sxs-lookup"><span data-stu-id="3bd05-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bd05-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3bd05-108">Return Value</span></span>  
  
|<span data-ttu-id="3bd05-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3bd05-109">HRESULT</span></span>|<span data-ttu-id="3bd05-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bd05-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3bd05-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3bd05-111">S_OK</span></span>|<span data-ttu-id="3bd05-112">`OnFailure`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3bd05-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="3bd05-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="3bd05-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3bd05-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3bd05-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3bd05-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3bd05-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3bd05-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3bd05-116">The call timed out.</span></span>|  
|<span data-ttu-id="3bd05-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3bd05-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3bd05-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3bd05-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3bd05-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3bd05-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3bd05-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3bd05-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3bd05-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3bd05-121">E_FAIL</span></span>|<span data-ttu-id="3bd05-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3bd05-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3bd05-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="3bd05-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3bd05-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3bd05-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3bd05-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3bd05-125">Requirements</span></span>  
 <span data-ttu-id="3bd05-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bd05-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bd05-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3bd05-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bd05-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3bd05-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bd05-129">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bd05-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd05-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bd05-130">See Also</span></span>  
 [<span data-ttu-id="3bd05-131">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3bd05-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="3bd05-132">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3bd05-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="3bd05-133">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bd05-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="3bd05-134">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bd05-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
