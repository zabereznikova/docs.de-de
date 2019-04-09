---
title: IHostManualEvent::Wait-Methode
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f90bf2b7472af3f9125edbd29f6924ddec9c1530
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219992"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="1ce8d-102">IHostManualEvent::Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="1ce8d-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="1ce8d-103">Bewirkt, dass die aktuelle [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) Instanz warten, bis sie gehört, oder einen bestimmten Zeitraum abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce8d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ce8d-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ce8d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ce8d-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="1ce8d-106">[in] Die Anzahl der Millisekunden vor dem zurückgeben, wenn die aktuelle `IHostManualEvent` Instanz hat keinen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="1ce8d-107">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte, der angibt, der Aktion, die der Host ausführen sollten, wenn dieser Vorgang blockiert.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ce8d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1ce8d-108">Return Value</span></span>  
  
|<span data-ttu-id="1ce8d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ce8d-109">HRESULT</span></span>|<span data-ttu-id="1ce8d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ce8d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ce8d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ce8d-111">S_OK</span></span>|`Wait` <span data-ttu-id="1ce8d-112">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-112">returned successfully.</span></span>|  
|<span data-ttu-id="1ce8d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1ce8d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1ce8d-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1ce8d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1ce8d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1ce8d-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-116">The call timed out.</span></span>|  
|<span data-ttu-id="1ce8d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1ce8d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1ce8d-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1ce8d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1ce8d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1ce8d-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1ce8d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1ce8d-121">E_FAIL</span></span>|<span data-ttu-id="1ce8d-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1ce8d-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1ce8d-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1ce8d-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="1ce8d-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="1ce8d-126">Der Host die Wartezeit einen Deadlock aufgetreten, und wählen Sie die aktuelle `IHostManualEvent` Instanz als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="1ce8d-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ce8d-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ce8d-127">Requirements</span></span>  
 <span data-ttu-id="1ce8d-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ce8d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ce8d-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ce8d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ce8d-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1ce8d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1ce8d-131">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1ce8d-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1ce8d-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ce8d-132">See also</span></span>

- [<span data-ttu-id="1ce8d-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ce8d-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="1ce8d-134">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ce8d-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="1ce8d-135">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ce8d-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="1ce8d-136">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ce8d-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="1ce8d-137">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ce8d-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
