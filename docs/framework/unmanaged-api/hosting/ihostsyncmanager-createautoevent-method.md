---
title: IHostSyncManager::CreateAutoEvent-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad704ff1e38d59df9e26d34b6dc62c40522aa728
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753460"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="1d77a-102">IHostSyncManager::CreateAutoEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="1d77a-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="1d77a-103">Erstellt ein automatisches Zurücksetzungsereignis-Objekt.</span><span class="sxs-lookup"><span data-stu-id="1d77a-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d77a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d77a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d77a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d77a-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="1d77a-106">[out] Ein Zeiger auf die Adresse einer [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) Instanz vom Host implementiert, oder null, wenn das Ereignisobjekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="1d77a-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d77a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1d77a-107">Return Value</span></span>  
  
|<span data-ttu-id="1d77a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d77a-108">HRESULT</span></span>|<span data-ttu-id="1d77a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d77a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d77a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d77a-110">S_OK</span></span>|<span data-ttu-id="1d77a-111">`CreateAutoEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1d77a-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="1d77a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d77a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d77a-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1d77a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d77a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d77a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d77a-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1d77a-115">The call timed out.</span></span>|  
|<span data-ttu-id="1d77a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d77a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d77a-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1d77a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d77a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d77a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d77a-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1d77a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d77a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d77a-120">E_FAIL</span></span>|<span data-ttu-id="1d77a-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1d77a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d77a-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d77a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d77a-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1d77a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1d77a-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1d77a-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1d77a-125">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d77a-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d77a-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d77a-126">Remarks</span></span>  
 <span data-ttu-id="1d77a-127">`CreateAutoEvent` erstellt ein Auto-Event-Objekt, dessen Zustand automatisch zu geändert wird, nicht signalisiertes nach der Freigabe des wartende Threads.</span><span class="sxs-lookup"><span data-stu-id="1d77a-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="1d77a-128">Diese Methode entspricht der Win32 `CreateEvent` Funktion mit einem Wert von `false` für die `bManualReset` Parameter</span><span class="sxs-lookup"><span data-stu-id="1d77a-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d77a-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d77a-129">Requirements</span></span>  
 <span data-ttu-id="1d77a-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d77a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d77a-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1d77a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d77a-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1d77a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d77a-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d77a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d77a-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d77a-134">See also</span></span>

- [<span data-ttu-id="1d77a-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d77a-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="1d77a-136">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d77a-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="1d77a-137">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d77a-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="1d77a-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d77a-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
