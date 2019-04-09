---
title: IHostSemaphore::Wait-Methode
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d9fcbca92b1615679be57fb4c9b872339fef8a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118214"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="7b435-102">IHostSemaphore::Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="7b435-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="7b435-103">Bewirkt, dass die aktuelle [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) Instanz warten, bis sie einen Besitzer hat oder die angegebene Zeitspanne verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="7b435-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b435-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b435-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b435-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b435-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="7b435-106">[in] Die Anzahl der Millisekunden vor dem zurückgeben, wenn die aktuelle `IHostSemaphore` Instanz hat keinen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="7b435-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="7b435-107">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte, welche Aktion der Host sollte durchführen, wenn diese Angabe blockiert.</span><span class="sxs-lookup"><span data-stu-id="7b435-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b435-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7b435-108">Return Value</span></span>  
  
|<span data-ttu-id="7b435-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b435-109">HRESULT</span></span>|<span data-ttu-id="7b435-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b435-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b435-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b435-111">S_OK</span></span>|`Wait` <span data-ttu-id="7b435-112">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7b435-112">returned successfully.</span></span>|  
|<span data-ttu-id="7b435-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7b435-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7b435-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7b435-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7b435-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7b435-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7b435-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7b435-116">The call timed out.</span></span>|  
|<span data-ttu-id="7b435-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7b435-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7b435-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7b435-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7b435-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7b435-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7b435-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="7b435-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7b435-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7b435-121">E_FAIL</span></span>|<span data-ttu-id="7b435-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7b435-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7b435-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b435-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7b435-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7b435-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7b435-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="7b435-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="7b435-126">Der Host die Wartezeit einen Deadlock aufgetreten, und wählen Sie die aktuelle `IHostSemaphore` Instanz als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="7b435-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b435-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b435-127">Requirements</span></span>  
 <span data-ttu-id="7b435-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b435-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b435-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7b435-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b435-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7b435-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7b435-131">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7b435-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b435-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b435-132">See also</span></span>

- [<span data-ttu-id="7b435-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b435-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="7b435-134">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b435-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="7b435-135">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b435-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="7b435-136">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b435-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="7b435-137">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b435-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
