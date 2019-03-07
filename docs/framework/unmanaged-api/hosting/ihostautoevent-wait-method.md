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
ms.openlocfilehash: b282ca35135fd16dceb92e6a0eeab15837d9b10d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491450"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="eafb6-102">IHostAutoEvent::Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="eafb6-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="eafb6-103">Bewirkt, dass die aktuelle [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) zu warten, bis sie einen Besitzer hat-Instanz oder einen bestimmten Zeitraum abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="eafb6-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eafb6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eafb6-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eafb6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eafb6-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="eafb6-106">[in] Die Anzahl der Millisekunden der aktuellen `IHostAutoEvent` Instanz warten soll, vor dem zurückgeben, wenn kein Thread oder Fiber übernimmt den Besitz.</span><span class="sxs-lookup"><span data-stu-id="eafb6-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="eafb6-107">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte angeben der Aktion, die der Host ausführen sollten, wenn dieser Vorgang blockiert.</span><span class="sxs-lookup"><span data-stu-id="eafb6-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eafb6-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eafb6-108">Return Value</span></span>  
  
|<span data-ttu-id="eafb6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eafb6-109">HRESULT</span></span>|<span data-ttu-id="eafb6-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eafb6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eafb6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="eafb6-111">S_OK</span></span>|<span data-ttu-id="eafb6-112">`Wait` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eafb6-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="eafb6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eafb6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eafb6-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="eafb6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eafb6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eafb6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eafb6-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="eafb6-116">The call timed out.</span></span>|  
|<span data-ttu-id="eafb6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eafb6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eafb6-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="eafb6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eafb6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eafb6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eafb6-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="eafb6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eafb6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eafb6-121">E_FAIL</span></span>|<span data-ttu-id="eafb6-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="eafb6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eafb6-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eafb6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eafb6-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="eafb6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="eafb6-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="eafb6-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="eafb6-126">Der Host die Wartezeit einen Deadlock aufgetreten, und wählen Sie das Ereignis, das vom aktuellen `IHostAutoEvent` Instanz als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="eafb6-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eafb6-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eafb6-127">Requirements</span></span>  
 <span data-ttu-id="eafb6-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eafb6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eafb6-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eafb6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eafb6-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="eafb6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eafb6-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eafb6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eafb6-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eafb6-132">See also</span></span>
- [<span data-ttu-id="eafb6-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eafb6-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="eafb6-134">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eafb6-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="eafb6-135">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eafb6-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="eafb6-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eafb6-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
