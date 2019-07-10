---
title: IHostSemaphore::ReleaseSemaphore-Methode
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e977133d722edc7d090d07cd117ee282a8d29cb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753581"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="91861-102">IHostSemaphore::ReleaseSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="91861-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="91861-103">Erhöht die Anzahl der aktuellen [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) Instanz, um den angegebenen Betrag.</span><span class="sxs-lookup"><span data-stu-id="91861-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91861-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91861-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91861-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="91861-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="91861-106">[in] Der Betrag, um die Anzahl der aktuellen erhöht `IHostSemaphore` Instanz.</span><span class="sxs-lookup"><span data-stu-id="91861-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="91861-107">Dieser Wert muss größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="91861-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="91861-108">[out] Ein Zeiger auf die vorherige Anzahl oder Null, wenn der Aufrufer nicht über die vorherige Anzahl erfordert.</span><span class="sxs-lookup"><span data-stu-id="91861-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91861-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="91861-109">Return Value</span></span>  
  
|<span data-ttu-id="91861-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91861-110">HRESULT</span></span>|<span data-ttu-id="91861-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91861-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91861-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="91861-112">S_OK</span></span>|<span data-ttu-id="91861-113">`ReleaseSemaphore` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="91861-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="91861-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="91861-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="91861-115">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="91861-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="91861-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="91861-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="91861-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="91861-117">The call timed out.</span></span>|  
|<span data-ttu-id="91861-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="91861-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="91861-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="91861-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="91861-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="91861-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="91861-121">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="91861-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="91861-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="91861-122">E_FAIL</span></span>|<span data-ttu-id="91861-123">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="91861-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="91861-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91861-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="91861-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="91861-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91861-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91861-126">Remarks</span></span>  
 <span data-ttu-id="91861-127">Die CLR in der Regel ruft `ReleaseSemaphore` auf den Host zu benachrichtigen, dass es abgeschlossen ist, verwenden eine Ressource, und übergeben den Wert 1 für die `lReleaseCount` Parameter.</span><span class="sxs-lookup"><span data-stu-id="91861-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91861-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91861-128">Requirements</span></span>  
 <span data-ttu-id="91861-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91861-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91861-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="91861-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91861-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="91861-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91861-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91861-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91861-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91861-133">See also</span></span>

- [<span data-ttu-id="91861-134">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91861-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="91861-135">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91861-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="91861-136">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91861-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="91861-137">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91861-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="91861-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91861-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
