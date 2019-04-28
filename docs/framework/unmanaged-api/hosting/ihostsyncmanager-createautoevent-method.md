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
ms.openlocfilehash: b9c91a982a5f3d28b43a301f961601485639bb91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696651"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="52a6c-102">IHostSyncManager::CreateAutoEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="52a6c-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="52a6c-103">Erstellt ein automatisches Zurücksetzungsereignis-Objekt.</span><span class="sxs-lookup"><span data-stu-id="52a6c-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52a6c-104">Syntax</span></span>  
  
```  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52a6c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="52a6c-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="52a6c-106">[out] Ein Zeiger auf die Adresse einer [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) Instanz vom Host implementiert, oder null, wenn das Ereignisobjekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="52a6c-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52a6c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="52a6c-107">Return Value</span></span>  
  
|<span data-ttu-id="52a6c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52a6c-108">HRESULT</span></span>|<span data-ttu-id="52a6c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52a6c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52a6c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="52a6c-110">S_OK</span></span>|<span data-ttu-id="52a6c-111">`CreateAutoEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="52a6c-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="52a6c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52a6c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52a6c-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="52a6c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52a6c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52a6c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52a6c-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="52a6c-115">The call timed out.</span></span>|  
|<span data-ttu-id="52a6c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52a6c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52a6c-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="52a6c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52a6c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52a6c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52a6c-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="52a6c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52a6c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52a6c-120">E_FAIL</span></span>|<span data-ttu-id="52a6c-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="52a6c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52a6c-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52a6c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52a6c-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="52a6c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="52a6c-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="52a6c-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="52a6c-125">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52a6c-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52a6c-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52a6c-126">Remarks</span></span>  
 <span data-ttu-id="52a6c-127">`CreateAutoEvent` erstellt ein Auto-Event-Objekt, dessen Zustand automatisch zu geändert wird, nicht signalisiertes nach der Freigabe des wartende Threads.</span><span class="sxs-lookup"><span data-stu-id="52a6c-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="52a6c-128">Diese Methode entspricht der Win32 `CreateEvent` Funktion mit einem Wert von `false` für die `bManualReset` Parameter</span><span class="sxs-lookup"><span data-stu-id="52a6c-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52a6c-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52a6c-129">Requirements</span></span>  
 <span data-ttu-id="52a6c-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52a6c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52a6c-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="52a6c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52a6c-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="52a6c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52a6c-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52a6c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a6c-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52a6c-134">See also</span></span>

- [<span data-ttu-id="52a6c-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52a6c-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="52a6c-136">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52a6c-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="52a6c-137">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52a6c-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="52a6c-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52a6c-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
