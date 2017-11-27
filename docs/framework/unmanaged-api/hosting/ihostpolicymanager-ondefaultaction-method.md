---
title: IHostPolicyManager::OnDefaultAction-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager.OnDefaultAction
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5eb767c08733980c9156d04526594c62349624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="6bf66-102">IHostPolicyManager::OnDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="6bf66-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="6bf66-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) die Standardaktion, die durch einen Aufruf von festgelegt wurde, nehmen die [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) Methode als Reaktion auf eine Threadabbruchs oder <xref:System.AppDomain> entladen.</span><span class="sxs-lookup"><span data-stu-id="6bf66-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bf66-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bf66-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bf66-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6bf66-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="6bf66-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der die Art des Ereignisses, der die CLR reagiert.</span><span class="sxs-lookup"><span data-stu-id="6bf66-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="6bf66-107">[in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, der die Aktion, die die CLR in Reaktion auf das Ereignis benötigt.</span><span class="sxs-lookup"><span data-stu-id="6bf66-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bf66-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6bf66-108">Return Value</span></span>  
  
|<span data-ttu-id="6bf66-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6bf66-109">HRESULT</span></span>|<span data-ttu-id="6bf66-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bf66-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6bf66-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6bf66-111">S_OK</span></span>|<span data-ttu-id="6bf66-112">`OnDefaultAction`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6bf66-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="6bf66-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="6bf66-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6bf66-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="6bf66-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="6bf66-115">erfolgreich</span><span class="sxs-lookup"><span data-stu-id="6bf66-115">successfully</span></span>|  
|<span data-ttu-id="6bf66-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6bf66-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6bf66-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6bf66-117">The call timed out.</span></span>|  
|<span data-ttu-id="6bf66-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6bf66-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6bf66-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="6bf66-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6bf66-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6bf66-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6bf66-121">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="6bf66-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6bf66-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6bf66-122">E_FAIL</span></span>|<span data-ttu-id="6bf66-123">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6bf66-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6bf66-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="6bf66-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6bf66-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="6bf66-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6bf66-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6bf66-126">Requirements</span></span>  
 <span data-ttu-id="6bf66-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bf66-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bf66-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6bf66-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bf66-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6bf66-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bf66-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bf66-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf66-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bf66-131">See Also</span></span>  
 [<span data-ttu-id="6bf66-132">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6bf66-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="6bf66-133">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6bf66-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="6bf66-134">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6bf66-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="6bf66-135">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6bf66-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
