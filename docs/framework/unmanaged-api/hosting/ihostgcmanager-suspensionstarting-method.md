---
title: IHostGCManager::SuspensionStarting-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30f6c611dc719fa6f1162498082cc9a60fb5059b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="ac4aa-102">IHostGCManager::SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="ac4aa-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="ac4aa-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) unterbricht die Ausführung von Aufgaben auf, um eine Garbagecollection auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac4aa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac4aa-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ac4aa-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ac4aa-105">Return Value</span></span>  
  
|<span data-ttu-id="ac4aa-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac4aa-106">HRESULT</span></span>|<span data-ttu-id="ac4aa-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac4aa-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac4aa-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac4aa-108">S_OK</span></span>|<span data-ttu-id="ac4aa-109">`SuspensionStarting`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="ac4aa-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ac4aa-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac4aa-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac4aa-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac4aa-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac4aa-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-113">The call timed out.</span></span>|  
|<span data-ttu-id="ac4aa-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac4aa-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac4aa-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac4aa-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac4aa-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac4aa-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac4aa-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac4aa-118">E_FAIL</span></span>|<span data-ttu-id="ac4aa-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac4aa-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac4aa-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac4aa-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac4aa-122">Remarks</span></span>  
 <span data-ttu-id="ac4aa-123">Die CLR ruft `SuspensionStarting` auf den Host zu informieren, dass die Garbagecollection stattfindet.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac4aa-124">Planen Sie diesen Task nicht neu.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-124">Do not reschedule this task.</span></span> <span data-ttu-id="ac4aa-125">Der Host muss eine Aufgabe verlegen beim [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ac4aa-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac4aa-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac4aa-126">Requirements</span></span>  
 <span data-ttu-id="ac4aa-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac4aa-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac4aa-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac4aa-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac4aa-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ac4aa-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac4aa-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac4aa-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac4aa-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac4aa-131">See Also</span></span>  
 [<span data-ttu-id="ac4aa-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac4aa-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ac4aa-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac4aa-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ac4aa-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac4aa-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ac4aa-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac4aa-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="ac4aa-136">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac4aa-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
