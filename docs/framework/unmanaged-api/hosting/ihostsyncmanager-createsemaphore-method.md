---
title: IHostSyncManager::CreateSemaphore-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7c757b941b879cc63d1b3e2ec1f3b9396193f6d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479388"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="0f0da-102">IHostSyncManager::CreateSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="0f0da-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="0f0da-103">Erstellt eine [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) -Objekt für die common Language Runtime (CLR) als eine Semaphore für Wait-Events verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f0da-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f0da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f0da-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f0da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f0da-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="0f0da-106">[in] Die anfängliche Anzahl für `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="0f0da-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="0f0da-107">[in] Die maximale Anzahl für `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="0f0da-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="0f0da-108">[out] Ein Zeiger auf die Adresse einer `IHostSemaphore` -Instanz oder null, wenn das Semaphor konnte nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0f0da-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f0da-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0f0da-109">Return Value</span></span>  
  
|<span data-ttu-id="0f0da-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f0da-110">HRESULT</span></span>|<span data-ttu-id="0f0da-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f0da-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f0da-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f0da-112">S_OK</span></span>|<span data-ttu-id="0f0da-113">`CreateSemaphore` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0f0da-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="0f0da-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f0da-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f0da-115">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f0da-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f0da-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f0da-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f0da-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0f0da-117">The call timed out.</span></span>|  
|<span data-ttu-id="0f0da-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f0da-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f0da-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0f0da-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f0da-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f0da-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f0da-121">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0f0da-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f0da-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f0da-122">E_FAIL</span></span>|<span data-ttu-id="0f0da-123">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0f0da-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f0da-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f0da-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f0da-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0f0da-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0f0da-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0f0da-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0f0da-127">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f0da-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f0da-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f0da-128">Remarks</span></span>  
 <span data-ttu-id="0f0da-129">`CreateSemaphore` entspricht die Win32-Funktion, die den gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="0f0da-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="0f0da-130">Die `dwInitial` und `dwMax` Parameter verwenden die gleiche Semantik für die Semaphorenanzahl als die Win32- `lInitialCount` und `lMaximumCount` Parameter bzw.</span><span class="sxs-lookup"><span data-stu-id="0f0da-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="0f0da-131">`dwInitial` muss zwischen 0 (null) sein und `dwMax`(inklusiv) enthalten.</span><span class="sxs-lookup"><span data-stu-id="0f0da-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="0f0da-132">`dwMax` Muss größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="0f0da-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f0da-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f0da-133">Requirements</span></span>  
 <span data-ttu-id="0f0da-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f0da-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f0da-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0f0da-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f0da-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0f0da-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f0da-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f0da-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f0da-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f0da-138">See also</span></span>
- [<span data-ttu-id="0f0da-139">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f0da-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0f0da-140">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f0da-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="0f0da-141">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f0da-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
