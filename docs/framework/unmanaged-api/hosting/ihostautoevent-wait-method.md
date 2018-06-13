---
title: IHostAutoEvent::Wait-Methode
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7921f0361d7369cddf14dd1ab477529d1bbac481
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439360"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="5d399-102">IHostAutoEvent::Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="5d399-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="5d399-103">Bewirkt, dass die aktuelle [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) Instanz warten, bis er Besitzer ist oder einen bestimmten Zeitraum verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="5d399-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d399-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d399-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d399-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d399-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="5d399-106">[in] Die Anzahl der Millisekunden der aktuellen `IHostAutoEvent` Instanz warten soll, bevor zurückgeben, wenn kein Thread oder Fiber übernimmt den Besitz.</span><span class="sxs-lookup"><span data-stu-id="5d399-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="5d399-107">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte, die Aktion, die der Host abwartet, wenn diese Angabe Vorgang blockiert.</span><span class="sxs-lookup"><span data-stu-id="5d399-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d399-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d399-108">Return Value</span></span>  
  
|<span data-ttu-id="5d399-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d399-109">HRESULT</span></span>|<span data-ttu-id="5d399-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d399-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d399-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d399-111">S_OK</span></span>|<span data-ttu-id="5d399-112">`Wait` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5d399-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="5d399-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="5d399-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d399-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5d399-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d399-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d399-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d399-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5d399-116">The call timed out.</span></span>|  
|<span data-ttu-id="5d399-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d399-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d399-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="5d399-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d399-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d399-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d399-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="5d399-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d399-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d399-121">E_FAIL</span></span>|<span data-ttu-id="5d399-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5d399-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d399-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="5d399-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d399-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5d399-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5d399-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="5d399-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="5d399-126">Der Host hat ein Deadlock erkannt wird, während das warteintervall und wählte das Ereignis, das vom aktuellen `IHostAutoEvent` Instanz als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="5d399-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d399-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d399-127">Requirements</span></span>  
 <span data-ttu-id="5d399-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d399-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d399-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d399-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d399-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5d399-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d399-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d399-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d399-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d399-132">See Also</span></span>  
 [<span data-ttu-id="5d399-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d399-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="5d399-134">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d399-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="5d399-135">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d399-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="5d399-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d399-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
