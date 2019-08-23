---
title: IHostGCManager::SuspensionStarting-Methode
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3e808c7ed03d7b4cc9dfe77389df6b2eff491f7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937723"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="44bb2-102">IHostGCManager::SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="44bb2-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="44bb2-103">Benachrichtigt den Host darüber, dass die Common Language Runtime (CLR) die Ausführung von Aufgaben angehalten, um eine Garbage Collection auszuführen.</span><span class="sxs-lookup"><span data-stu-id="44bb2-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44bb2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44bb2-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="44bb2-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="44bb2-105">Return Value</span></span>  
  
|<span data-ttu-id="44bb2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="44bb2-106">HRESULT</span></span>|<span data-ttu-id="44bb2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44bb2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="44bb2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="44bb2-108">S_OK</span></span>|<span data-ttu-id="44bb2-109">`SuspensionStarting`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="44bb2-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="44bb2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="44bb2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="44bb2-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="44bb2-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="44bb2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="44bb2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="44bb2-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="44bb2-113">The call timed out.</span></span>|  
|<span data-ttu-id="44bb2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="44bb2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="44bb2-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="44bb2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="44bb2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="44bb2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="44bb2-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="44bb2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="44bb2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="44bb2-118">E_FAIL</span></span>|<span data-ttu-id="44bb2-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="44bb2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="44bb2-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44bb2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="44bb2-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="44bb2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44bb2-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44bb2-122">Remarks</span></span>  
 <span data-ttu-id="44bb2-123">Die CLR ruft `SuspensionStarting` auf, um den Host darüber zu informieren, dass Garbage Collection auftritt.</span><span class="sxs-lookup"><span data-stu-id="44bb2-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="44bb2-124">Planen Sie diese Aufgabe nicht neu.</span><span class="sxs-lookup"><span data-stu-id="44bb2-124">Do not reschedule this task.</span></span> <span data-ttu-id="44bb2-125">Der Host muss einen Task neu planen, wenn [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="44bb2-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44bb2-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44bb2-126">Requirements</span></span>  
 <span data-ttu-id="44bb2-127">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44bb2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44bb2-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="44bb2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44bb2-129">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="44bb2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44bb2-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44bb2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44bb2-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44bb2-131">See also</span></span>

- [<span data-ttu-id="44bb2-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44bb2-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="44bb2-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44bb2-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="44bb2-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44bb2-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="44bb2-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44bb2-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="44bb2-136">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44bb2-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
