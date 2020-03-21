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
ms.openlocfilehash: 8d987614c1a5a2c90ccb3faa11c605767ae5cfda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178019"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="fe64a-102">IHostPolicyManager::OnDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="fe64a-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="fe64a-103">Benachrichtigt den Host, dass die Common Language Runtime (CLR) im Begriff ist, die Standardaktion auszuführen, die durch einen Aufruf der <xref:System.AppDomain> [ICLRPolicyManager::SetDefaultAction-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) als Reaktion auf einen Threadabbruch oder -entladung festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="fe64a-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe64a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe64a-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe64a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe64a-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="fe64a-106">[in] Einer der [EClrOperation-Werte,](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) der die Art des Ereignisses angibt, auf das die CLR reagiert.</span><span class="sxs-lookup"><span data-stu-id="fe64a-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="fe64a-107">[in] Einer der [EPolicyAction-Werte,](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) der die Aktion angibt, die die CLR als Reaktion auf das Ereignis ausführt.</span><span class="sxs-lookup"><span data-stu-id="fe64a-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe64a-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fe64a-108">Return Value</span></span>  
  
|<span data-ttu-id="fe64a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe64a-109">HRESULT</span></span>|<span data-ttu-id="fe64a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe64a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe64a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe64a-111">S_OK</span></span>|<span data-ttu-id="fe64a-112">`OnDefaultAction`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fe64a-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="fe64a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fe64a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe64a-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="fe64a-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="fe64a-115">Erfolgreich</span><span class="sxs-lookup"><span data-stu-id="fe64a-115">successfully</span></span>|  
|<span data-ttu-id="fe64a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe64a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe64a-117">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="fe64a-117">The call timed out.</span></span>|  
|<span data-ttu-id="fe64a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe64a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe64a-119">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="fe64a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe64a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe64a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe64a-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="fe64a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe64a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe64a-122">E_FAIL</span></span>|<span data-ttu-id="fe64a-123">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fe64a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fe64a-124">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe64a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe64a-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fe64a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe64a-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fe64a-126">Requirements</span></span>  
 <span data-ttu-id="fe64a-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe64a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe64a-128">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fe64a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe64a-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fe64a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe64a-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe64a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe64a-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe64a-131">See also</span></span>

- [<span data-ttu-id="fe64a-132">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fe64a-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="fe64a-133">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fe64a-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="fe64a-134">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe64a-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="fe64a-135">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe64a-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
