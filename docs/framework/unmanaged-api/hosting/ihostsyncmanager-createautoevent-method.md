---
title: IHostSyncManager::CreateAutoEvent-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7874839d04af89f2fa512f82213862f34408001
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="d5a20-102">IHostSyncManager::CreateAutoEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d5a20-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="d5a20-103">Erstellt ein Ereignisobjekt AutoReset.</span><span class="sxs-lookup"><span data-stu-id="d5a20-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5a20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5a20-104">Syntax</span></span>  
  
```  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5a20-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5a20-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="d5a20-106">[out] Ein Zeiger auf die Adresse des ein [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) Instanz vom Host implementiert, oder null, wenn das Ereignisobjekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="d5a20-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5a20-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d5a20-107">Return Value</span></span>  
  
|<span data-ttu-id="d5a20-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5a20-108">HRESULT</span></span>|<span data-ttu-id="d5a20-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5a20-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5a20-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5a20-110">S_OK</span></span>|<span data-ttu-id="d5a20-111">`CreateAutoEvent`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d5a20-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="d5a20-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="d5a20-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d5a20-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d5a20-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d5a20-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d5a20-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d5a20-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d5a20-115">The call timed out.</span></span>|  
|<span data-ttu-id="d5a20-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d5a20-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d5a20-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d5a20-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d5a20-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d5a20-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d5a20-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d5a20-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d5a20-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d5a20-120">E_FAIL</span></span>|<span data-ttu-id="d5a20-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d5a20-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d5a20-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="d5a20-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d5a20-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d5a20-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d5a20-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d5a20-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d5a20-125">Es war nicht genügend Arbeitsspeicher zum Erstellen des angeforderten Ereignisses-Objekts verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d5a20-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5a20-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5a20-126">Remarks</span></span>  
 <span data-ttu-id="d5a20-127">`CreateAutoEvent`erstellt ein Auto-Ereignisobjekt, deren Zustand nicht signalisierten nach der Freigabe des wartenden Threads automatisch in geändert wird.</span><span class="sxs-lookup"><span data-stu-id="d5a20-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="d5a20-128">Diese Methode spiegelt die Win32- `CreateEvent` Funktion mit einem Wert von `false` angegeben für die `bManualReset` Parameter</span><span class="sxs-lookup"><span data-stu-id="d5a20-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5a20-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5a20-129">Requirements</span></span>  
 <span data-ttu-id="d5a20-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5a20-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5a20-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5a20-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5a20-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d5a20-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5a20-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5a20-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a20-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5a20-134">See Also</span></span>  
 [<span data-ttu-id="d5a20-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5a20-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="d5a20-136">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5a20-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="d5a20-137">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5a20-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="d5a20-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5a20-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
