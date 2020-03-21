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
ms.openlocfilehash: d5b5fa5198ae2c0bba30ae0f8d6d3834f2891672
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178003"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="08d8a-102">IHostPolicyManager::OnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="08d8a-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="08d8a-103">Benachrichtigt den Host, dass die Common Language Runtime (CLR) die durch einen Aufruf der [ICLRPolicyManager::SetActionOnTimeout-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) als Reaktion auf ein Timeout angegebene Aktion ausführen wird.</span><span class="sxs-lookup"><span data-stu-id="08d8a-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08d8a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08d8a-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08d8a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08d8a-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="08d8a-106">[in] Einer der [EClrOperation-Werte,](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) der die Art des Vorgangs angibt, bei dem das Zeitüberschreitungszeitzeichen angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="08d8a-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="08d8a-107">[in] Einer der [EPolicyAction-Werte,](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) der die Aktion angibt, die die CLR als Reaktion auf das Timeout ausführt.</span><span class="sxs-lookup"><span data-stu-id="08d8a-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08d8a-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="08d8a-108">Return Value</span></span>  
  
|<span data-ttu-id="08d8a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08d8a-109">HRESULT</span></span>|<span data-ttu-id="08d8a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08d8a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08d8a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="08d8a-111">S_OK</span></span>|<span data-ttu-id="08d8a-112">`OnTimeout`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="08d8a-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="08d8a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08d8a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08d8a-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="08d8a-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08d8a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08d8a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08d8a-116">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="08d8a-116">The call timed out.</span></span>|  
|<span data-ttu-id="08d8a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08d8a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08d8a-118">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="08d8a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08d8a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08d8a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08d8a-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="08d8a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08d8a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08d8a-121">E_FAIL</span></span>|<span data-ttu-id="08d8a-122">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="08d8a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08d8a-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="08d8a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08d8a-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="08d8a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08d8a-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="08d8a-125">Requirements</span></span>  
 <span data-ttu-id="08d8a-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08d8a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08d8a-127">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08d8a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08d8a-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="08d8a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08d8a-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08d8a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d8a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08d8a-130">See also</span></span>

- [<span data-ttu-id="08d8a-131">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="08d8a-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="08d8a-132">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="08d8a-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="08d8a-133">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08d8a-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="08d8a-134">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08d8a-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
