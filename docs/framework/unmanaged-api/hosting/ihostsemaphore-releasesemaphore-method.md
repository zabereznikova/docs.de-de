---
title: IHostSemaphore::ReleaseSemaphore-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSemaphore.ReleaseSemaphore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 06765d019d5443730656e7f4d6745bd8ad39ee00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="cd3cf-102">IHostSemaphore::ReleaseSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="cd3cf-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="cd3cf-103">Erhöht die Anzahl der aktuellen [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) Instanz, um den angegebenen Betrag.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd3cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd3cf-104">Syntax</span></span>  
  
```  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd3cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd3cf-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="cd3cf-106">[in] Der Betrag, erhöhen Sie die Anzahl der aktuellen `IHostSemaphore` Instanz.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="cd3cf-107">Dieser Betrag muss größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="cd3cf-108">[out] Ein Zeiger auf die vorherige Anzahl oder Null, wenn der Aufrufer nicht über die vorherige Anzahl erfordert.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd3cf-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cd3cf-109">Return Value</span></span>  
  
|<span data-ttu-id="cd3cf-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd3cf-110">HRESULT</span></span>|<span data-ttu-id="cd3cf-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd3cf-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd3cf-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd3cf-112">S_OK</span></span>|<span data-ttu-id="cd3cf-113">`ReleaseSemaphore`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="cd3cf-114">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="cd3cf-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cd3cf-115">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cd3cf-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cd3cf-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cd3cf-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-117">The call timed out.</span></span>|  
|<span data-ttu-id="cd3cf-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cd3cf-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cd3cf-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cd3cf-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cd3cf-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cd3cf-121">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cd3cf-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd3cf-122">E_FAIL</span></span>|<span data-ttu-id="cd3cf-123">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cd3cf-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cd3cf-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd3cf-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd3cf-126">Remarks</span></span>  
 <span data-ttu-id="cd3cf-127">Die CLR ruft in der Regel `ReleaseSemaphore` an den Host zu benachrichtigen, dass es abgeschlossen ist, eine Ressource, die Übergabe des Werts 1 für die `lReleaseCount` Parameter.</span><span class="sxs-lookup"><span data-stu-id="cd3cf-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd3cf-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd3cf-128">Requirements</span></span>  
 <span data-ttu-id="cd3cf-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd3cf-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd3cf-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd3cf-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd3cf-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cd3cf-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd3cf-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd3cf-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd3cf-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd3cf-133">See Also</span></span>  
 [<span data-ttu-id="cd3cf-134">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd3cf-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="cd3cf-135">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd3cf-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="cd3cf-136">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd3cf-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="cd3cf-137">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd3cf-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="cd3cf-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd3cf-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
