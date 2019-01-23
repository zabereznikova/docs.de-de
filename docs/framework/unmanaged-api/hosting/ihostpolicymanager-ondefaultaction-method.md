---
title: IHostPolicyManager::OnDefaultAction-Methode
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1497f1e08ab514c20fa82602f523aadb425303d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556469"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="ce4c1-102">IHostPolicyManager::OnDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="ce4c1-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="ce4c1-103">Benachrichtigt den Host, der die common Language Runtime (CLR) die Standardaktion, die durch einen Aufruf festgelegt wurde die [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) -Methode in der Antwort auf den Abbruch eines Threads oder <xref:System.AppDomain> nicht entladen.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce4c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce4c1-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce4c1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce4c1-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="ce4c1-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der die Art des Ereignisses, der die CLR reagiert.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="ce4c1-107">[in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, der die Aktion, die die CLR in Reaktion auf das Ereignis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce4c1-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ce4c1-108">Return Value</span></span>  
  
|<span data-ttu-id="ce4c1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce4c1-109">HRESULT</span></span>|<span data-ttu-id="ce4c1-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce4c1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce4c1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce4c1-111">S_OK</span></span>|<span data-ttu-id="ce4c1-112">`OnDefaultAction` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="ce4c1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce4c1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce4c1-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="ce4c1-115">erfolgreich</span><span class="sxs-lookup"><span data-stu-id="ce4c1-115">successfully</span></span>|  
|<span data-ttu-id="ce4c1-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce4c1-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce4c1-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-117">The call timed out.</span></span>|  
|<span data-ttu-id="ce4c1-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce4c1-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce4c1-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce4c1-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce4c1-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce4c1-121">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce4c1-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce4c1-122">E_FAIL</span></span>|<span data-ttu-id="ce4c1-123">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce4c1-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce4c1-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce4c1-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce4c1-126">Requirements</span></span>  
 <span data-ttu-id="ce4c1-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce4c1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce4c1-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce4c1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce4c1-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ce4c1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce4c1-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce4c1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce4c1-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce4c1-131">See also</span></span>
- [<span data-ttu-id="ce4c1-132">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ce4c1-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="ce4c1-133">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ce4c1-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="ce4c1-134">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce4c1-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="ce4c1-135">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce4c1-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
