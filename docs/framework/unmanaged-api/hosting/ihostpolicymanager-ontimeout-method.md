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
ms.openlocfilehash: 75e6ff3b2b7c8f4b8611630092203aace0ce3136
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781014"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="5b3af-102">IHostPolicyManager::OnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="5b3af-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="5b3af-103">Benachrichtigt den Host, der die common Language Runtime (CLR) angegeben, die durch einen Aufruf der Aktion der [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) -Methode in der Antwort auf ein Timeout.</span><span class="sxs-lookup"><span data-stu-id="5b3af-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b3af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b3af-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b3af-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b3af-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="5b3af-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der die Art des Vorgangs, bei denen Timeout.</span><span class="sxs-lookup"><span data-stu-id="5b3af-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="5b3af-107">[in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) -Werte, der angibt, der die CLR-Aktion in Anspruch nimmt als Reaktion auf das Timeout.</span><span class="sxs-lookup"><span data-stu-id="5b3af-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b3af-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5b3af-108">Return Value</span></span>  
  
|<span data-ttu-id="5b3af-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b3af-109">HRESULT</span></span>|<span data-ttu-id="5b3af-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b3af-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b3af-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b3af-111">S_OK</span></span>|<span data-ttu-id="5b3af-112">`OnTimeout` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5b3af-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="5b3af-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5b3af-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5b3af-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5b3af-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5b3af-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5b3af-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5b3af-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5b3af-116">The call timed out.</span></span>|  
|<span data-ttu-id="5b3af-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5b3af-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5b3af-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="5b3af-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5b3af-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5b3af-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5b3af-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="5b3af-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5b3af-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5b3af-121">E_FAIL</span></span>|<span data-ttu-id="5b3af-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5b3af-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5b3af-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b3af-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5b3af-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5b3af-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b3af-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b3af-125">Requirements</span></span>  
 <span data-ttu-id="5b3af-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b3af-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b3af-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5b3af-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b3af-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5b3af-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b3af-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b3af-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b3af-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b3af-130">See also</span></span>

- [<span data-ttu-id="5b3af-131">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b3af-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="5b3af-132">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b3af-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="5b3af-133">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b3af-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="5b3af-134">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b3af-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
