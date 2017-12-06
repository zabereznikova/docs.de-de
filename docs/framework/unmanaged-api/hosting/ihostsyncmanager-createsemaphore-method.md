---
title: IHostSyncManager::CreateSemaphore-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateSemaphore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c7e33e4f178a4fd51ae27912959d0e4edf30ecb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="9436e-102">IHostSyncManager::CreateSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="9436e-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="9436e-103">Erstellt ein [IHostSemaphore](./../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) Objekt für die common Language Runtime (CLR) als Semaphor für Wait-Ereignisse verwendet.</span><span class="sxs-lookup"><span data-stu-id="9436e-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9436e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9436e-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9436e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9436e-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="9436e-106">[in] Die anfängliche Anzahl für `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="9436e-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="9436e-107">[in] Die maximale Anzahl für `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="9436e-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="9436e-108">[out] Ein Zeiger auf die Adresse des ein `IHostSemaphore` -Instanz oder null, wenn das Semaphor nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="9436e-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9436e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9436e-109">Return Value</span></span>  
  
|<span data-ttu-id="9436e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9436e-110">HRESULT</span></span>|<span data-ttu-id="9436e-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9436e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9436e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9436e-112">S_OK</span></span>|<span data-ttu-id="9436e-113">`CreateSemaphore`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9436e-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="9436e-114">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="9436e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9436e-115">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9436e-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9436e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9436e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9436e-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9436e-117">The call timed out.</span></span>|  
|<span data-ttu-id="9436e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9436e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9436e-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9436e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9436e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9436e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9436e-121">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9436e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9436e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9436e-122">E_FAIL</span></span>|<span data-ttu-id="9436e-123">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9436e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9436e-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="9436e-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9436e-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9436e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9436e-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9436e-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9436e-127">Es war nicht genügend Arbeitsspeicher zum Erstellen des angeforderten Ereignisses-Objekts verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9436e-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9436e-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9436e-128">Remarks</span></span>  
 <span data-ttu-id="9436e-129">`CreateSemaphore`spiegelt die Win32-Funktion, die den gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="9436e-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="9436e-130">Die `dwInitial` und `dwMax` Parameter verwenden dieselbe Semantik für die Semaphorenanzahl als die Win32- `lInitialCount` und `lMaximumCount` Parameter bzw.</span><span class="sxs-lookup"><span data-stu-id="9436e-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="9436e-131">`dwInitial`muss liegen zwischen 0 (null) und `dwMax`(einschließlich).</span><span class="sxs-lookup"><span data-stu-id="9436e-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="9436e-132">`dwMax`muss größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="9436e-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9436e-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9436e-133">Requirements</span></span>  
 <span data-ttu-id="9436e-134">**Plattformen:** finden Sie unter [Systemanforderungen](./../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9436e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9436e-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9436e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9436e-136">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9436e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9436e-137">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](./../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9436e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9436e-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9436e-138">See Also</span></span>  
 <span data-ttu-id="9436e-139">[[ICLRSyncManager-Schnittstelle](./../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9436e-139">[ICLRSyncManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)</span></span>  
 <span data-ttu-id="9436e-140">[[IHostSemaphore-Schnittstelle](./../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9436e-140">[IHostSemaphore Interface](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)</span></span>  
 <span data-ttu-id="9436e-141">[[IHostSyncManager-Schnittstelle](./../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9436e-141">[IHostSyncManager Interface](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)</span></span>
