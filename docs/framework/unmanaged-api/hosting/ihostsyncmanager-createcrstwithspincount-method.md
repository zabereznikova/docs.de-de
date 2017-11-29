---
title: IHostSyncManager::CreateCrstWithSpinCount-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateCrstWithSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41031a5e3d423f0c1d7459250073634592e0291e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="3334f-102">IHostSyncManager::CreateCrstWithSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="3334f-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="3334f-103">Erstellt ein kritisches Abschnittsobjekt mit Spin-Anzahl für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="3334f-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3334f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3334f-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3334f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3334f-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="3334f-106">[in] Gibt die Anzahl der Drehfeld für die kritischen Abschnittsobjekt an.</span><span class="sxs-lookup"><span data-stu-id="3334f-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="3334f-107">[out] Ein Zeiger auf die Adresse des ein [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) -Instanz oder null, wenn der kritische Abschnitt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="3334f-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3334f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3334f-108">Return Value</span></span>  
  
|<span data-ttu-id="3334f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3334f-109">HRESULT</span></span>|<span data-ttu-id="3334f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3334f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3334f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3334f-111">S_OK</span></span>|<span data-ttu-id="3334f-112">`CreateCrstWithSpinCount`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3334f-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="3334f-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="3334f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3334f-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3334f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3334f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3334f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3334f-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3334f-116">The call timed out.</span></span>|  
|<span data-ttu-id="3334f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3334f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3334f-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3334f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3334f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3334f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3334f-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3334f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3334f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3334f-121">E_FAIL</span></span>|<span data-ttu-id="3334f-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3334f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3334f-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="3334f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3334f-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3334f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3334f-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3334f-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3334f-126">Es war nicht genügend Arbeitsspeicher verfügbar, um den angeforderten kritischen Abschnitt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3334f-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3334f-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3334f-127">Remarks</span></span>  
 <span data-ttu-id="3334f-128">Eine Drehfeld Anzahl wird nur auf Systemen mit mehreren Prozessoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="3334f-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="3334f-129">Die Spinninganzahl gibt die Anzahl der Häufigkeit, mit die ein aufrufenden Thread starten muss, bevor sie eine "Wait"-Vorgang für einen Semaphore ausführt, die einen nicht verfügbaren kritischen Abschnitt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3334f-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="3334f-130">Wenn der kritische Abschnitt während des Vorgangs Drehfeld frei wird, wird der aufrufende Thread den Wartevorgang vermieden.</span><span class="sxs-lookup"><span data-stu-id="3334f-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="3334f-131">`CreateCrstWithSpinCount`spiegelt die Win32- `InitializeCriticalSectionAndSpinCount` Funktion.</span><span class="sxs-lookup"><span data-stu-id="3334f-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3334f-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3334f-132">Requirements</span></span>  
 <span data-ttu-id="3334f-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3334f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3334f-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3334f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3334f-135">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3334f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3334f-136">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3334f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3334f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3334f-137">See Also</span></span>  
 [<span data-ttu-id="3334f-138">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3334f-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="3334f-139">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3334f-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="3334f-140">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3334f-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
