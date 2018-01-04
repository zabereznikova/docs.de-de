---
title: IHostSyncManager::CreateManualEvent-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateManualEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 347eaa64b8a5e5b5c9494a779e3d583b10d80052
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="e55e1-102">IHostSyncManager::CreateManualEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="e55e1-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="e55e1-103">Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt.</span><span class="sxs-lookup"><span data-stu-id="e55e1-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e55e1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e55e1-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e55e1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e55e1-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="e55e1-106">[in] `true`, wenn das Objekt signalisiert, und andernfalls wird `false`.</span><span class="sxs-lookup"><span data-stu-id="e55e1-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="e55e1-107">[out] Ein Zeiger auf die Adresse des ein [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) -Instanz oder null, wenn das Ereignis konnte nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e55e1-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e55e1-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e55e1-108">Return Value</span></span>  
  
|<span data-ttu-id="e55e1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e55e1-109">HRESULT</span></span>|<span data-ttu-id="e55e1-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e55e1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e55e1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e55e1-111">S_OK</span></span>|<span data-ttu-id="e55e1-112">`CreateManualEvent`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e55e1-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="e55e1-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="e55e1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e55e1-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e55e1-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e55e1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e55e1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e55e1-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e55e1-116">The call timed out.</span></span>|  
|<span data-ttu-id="e55e1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e55e1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e55e1-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e55e1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e55e1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e55e1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e55e1-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="e55e1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e55e1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e55e1-121">E_FAIL</span></span>|<span data-ttu-id="e55e1-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e55e1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e55e1-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="e55e1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e55e1-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e55e1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e55e1-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e55e1-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e55e1-126">Es war nicht genügend Arbeitsspeicher zum Erstellen des angeforderten Ereignisses-Objekts verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e55e1-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e55e1-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e55e1-127">Remarks</span></span>  
 <span data-ttu-id="e55e1-128">`CreateManualEvent`erstellt ein `IHostManualEvent`, ein Ereignis für manuelles Zurücksetzen-Objekt, das einen Aufruf erfordert die [IHostManualEvent:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) Methode, um es auf einen nicht signalisierten Zustand festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e55e1-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="e55e1-129">`CreateManualEvent`spiegelt die Win32- `CreateEvent` Funktion mit einem Wert von `true` angegeben für die `bManualReset` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e55e1-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e55e1-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e55e1-130">Requirements</span></span>  
 <span data-ttu-id="e55e1-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e55e1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e55e1-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e55e1-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e55e1-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e55e1-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e55e1-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e55e1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55e1-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e55e1-135">See Also</span></span>  
 [<span data-ttu-id="e55e1-136">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e55e1-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="e55e1-137">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e55e1-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="e55e1-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e55e1-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
