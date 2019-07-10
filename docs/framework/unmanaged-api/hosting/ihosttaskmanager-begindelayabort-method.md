---
title: IHostTaskManager::BeginDelayAbort-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f5c28b7513ccfd0f1a645ed1cd6a3207a7cf0f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749790"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="33510-102">IHostTaskManager::BeginDelayAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="33510-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="33510-103">Benachrichtigt, dass der Host, der von Code verwaltetem eine Phase eintritt, in dem die aktuelle Aufgabe nicht abgebrochen werden muss.</span><span class="sxs-lookup"><span data-stu-id="33510-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33510-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33510-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="33510-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="33510-105">Return Value</span></span>  
  
|<span data-ttu-id="33510-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="33510-106">HRESULT</span></span>|<span data-ttu-id="33510-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33510-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="33510-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="33510-108">S_OK</span></span>|<span data-ttu-id="33510-109">`BeginDelayAbort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="33510-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="33510-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="33510-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="33510-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="33510-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="33510-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="33510-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="33510-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="33510-113">The call timed out.</span></span>|  
|<span data-ttu-id="33510-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="33510-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="33510-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="33510-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="33510-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="33510-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="33510-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="33510-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="33510-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="33510-118">E_FAIL</span></span>|<span data-ttu-id="33510-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="33510-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="33510-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33510-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="33510-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="33510-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="33510-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="33510-122">E_UNEXPECTED</span></span>|<span data-ttu-id="33510-123">`BeginDelayAbort` wurde bereits aufgerufen, aber die zugehörigen Aufruf an [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) wurde noch nicht empfangen.</span><span class="sxs-lookup"><span data-stu-id="33510-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33510-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33510-124">Remarks</span></span>  
 <span data-ttu-id="33510-125">Der Host muss nicht abbrechen, bis die aktuelle Aufgabe `EndDelayAbort` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="33510-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="33510-126">Wenn ein weiterer Aufruf `BeginDelayAbort` erfolgt, ohne einen zwischenzeitlichen Aufruf `EndDelayAbort`, der Host sollte E_UNEXPECTED zurückgegeben von `BeginDelayAbort`, und keine Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="33510-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33510-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33510-127">Requirements</span></span>  
 <span data-ttu-id="33510-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33510-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33510-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33510-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33510-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="33510-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33510-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33510-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33510-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33510-132">See also</span></span>

- [<span data-ttu-id="33510-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33510-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="33510-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33510-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="33510-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33510-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
