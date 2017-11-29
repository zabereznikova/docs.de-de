---
title: IHostManualEvent::Wait-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Wait
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2bd584e1ada69adca7f8ef77f98533ef7a1ba16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="77069-102">IHostManualEvent::Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="77069-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="77069-103">Bewirkt, dass die aktuelle [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) Instanz warten, bis er Besitzer ist oder einen bestimmten Zeitraum verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="77069-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77069-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77069-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77069-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="77069-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="77069-106">[in] Die Anzahl der Millisekunden, die vor der Rückgabe, warten Sie, wenn die aktuelle `IHostManualEvent` Instanz ist nicht im Besitz.</span><span class="sxs-lookup"><span data-stu-id="77069-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="77069-107">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte, der die Aktion, die der Host ausführen soll, wenn dieser Vorgang blockiert.</span><span class="sxs-lookup"><span data-stu-id="77069-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77069-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="77069-108">Return Value</span></span>  
  
|<span data-ttu-id="77069-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77069-109">HRESULT</span></span>|<span data-ttu-id="77069-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77069-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77069-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="77069-111">S_OK</span></span>|<span data-ttu-id="77069-112">`Wait`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="77069-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="77069-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="77069-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="77069-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="77069-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="77069-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="77069-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="77069-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="77069-116">The call timed out.</span></span>|  
|<span data-ttu-id="77069-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="77069-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="77069-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="77069-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="77069-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="77069-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="77069-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="77069-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="77069-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="77069-121">E_FAIL</span></span>|<span data-ttu-id="77069-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="77069-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="77069-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="77069-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="77069-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="77069-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="77069-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="77069-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="77069-126">Der Host hat ein Deadlock erkannt wird, während das warteintervall und wählte das aktuelle `IHostManualEvent` Instanz als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="77069-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77069-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77069-127">Requirements</span></span>  
 <span data-ttu-id="77069-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77069-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77069-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="77069-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77069-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="77069-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77069-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77069-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77069-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77069-132">See Also</span></span>  
 [<span data-ttu-id="77069-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77069-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="77069-134">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77069-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="77069-135">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77069-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="77069-136">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77069-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="77069-137">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77069-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
