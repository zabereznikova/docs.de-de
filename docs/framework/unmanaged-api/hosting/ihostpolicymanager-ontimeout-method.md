---
title: IHostPolicyManager::OnTimeout-Methode
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f6257cdf966850a17d5cf58ef1ac2e6ab7103b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439373"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="34230-102">IHostPolicyManager::OnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="34230-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="34230-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) die Aktionen angegeben, die durch einen Aufruf der [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) Methode als Reaktion auf ein Timeout.</span><span class="sxs-lookup"><span data-stu-id="34230-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34230-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34230-104">Syntax</span></span>  
  
```  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34230-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34230-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="34230-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der die Art des Vorgangs, der ein Timeout angibt.</span><span class="sxs-lookup"><span data-stu-id="34230-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="34230-107">[in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, der angibt, der die CLR-Aktion als Antwort auf das Timeout dauert.</span><span class="sxs-lookup"><span data-stu-id="34230-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34230-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="34230-108">Return Value</span></span>  
  
|<span data-ttu-id="34230-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34230-109">HRESULT</span></span>|<span data-ttu-id="34230-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34230-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34230-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="34230-111">S_OK</span></span>|<span data-ttu-id="34230-112">`OnTimeout` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="34230-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="34230-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="34230-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="34230-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="34230-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="34230-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="34230-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="34230-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="34230-116">The call timed out.</span></span>|  
|<span data-ttu-id="34230-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="34230-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="34230-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="34230-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="34230-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="34230-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="34230-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="34230-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="34230-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="34230-121">E_FAIL</span></span>|<span data-ttu-id="34230-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="34230-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="34230-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="34230-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="34230-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="34230-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34230-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34230-125">Requirements</span></span>  
 <span data-ttu-id="34230-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34230-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34230-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="34230-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34230-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="34230-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34230-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34230-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34230-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34230-130">See Also</span></span>  
 [<span data-ttu-id="34230-131">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="34230-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="34230-132">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="34230-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="34230-133">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34230-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="34230-134">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34230-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
