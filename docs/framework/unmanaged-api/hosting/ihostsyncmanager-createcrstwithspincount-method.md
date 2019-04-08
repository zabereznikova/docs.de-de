---
title: IHostSyncManager::CreateCrstWithSpinCount-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a288edc89029804de277484741c1895af7859b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081527"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="3c781-102">IHostSyncManager::CreateCrstWithSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="3c781-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="3c781-103">Erstellt ein kritisches Abschnittsobjekt mit Spin-Anzahl für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="3c781-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c781-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c781-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c781-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c781-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="3c781-106">[in] Gibt an, die Spin-Anzahl für das Objekt des kritischen Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="3c781-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="3c781-107">[out] Ein Zeiger auf die Adresse einer [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) -Instanz oder null, wenn der kritische Abschnitt kann nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3c781-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c781-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3c781-108">Return Value</span></span>  
  
|<span data-ttu-id="3c781-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c781-109">HRESULT</span></span>|<span data-ttu-id="3c781-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c781-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c781-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c781-111">S_OK</span></span>|`CreateCrstWithSpinCount` <span data-ttu-id="3c781-112">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3c781-112">returned successfully.</span></span>|  
|<span data-ttu-id="3c781-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c781-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c781-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3c781-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c781-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c781-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c781-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3c781-116">The call timed out.</span></span>|  
|<span data-ttu-id="3c781-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c781-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c781-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3c781-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c781-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c781-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c781-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3c781-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c781-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c781-121">E_FAIL</span></span>|<span data-ttu-id="3c781-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3c781-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c781-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c781-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c781-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3c781-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3c781-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3c781-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3c781-126">Es war nicht genügend Arbeitsspeicher verfügbar, um den angeforderten kritischen Abschnitt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c781-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c781-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c781-127">Remarks</span></span>  
 <span data-ttu-id="3c781-128">Eine Spinninganzahl wird nur auf einem System mit mehreren Prozessoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="3c781-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="3c781-129">Die Spin-Anzahl gibt die Anzahl der Häufigkeit, mit die ein aufrufenden Thread starten muss, bevor sie eine "Wait"-Vorgang für einen Semaphore ausführt, die mit einer nicht verfügbaren kritischen Abschnitt verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="3c781-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="3c781-130">Wenn während des Vorgangs Starten der kritische Abschnitt frei wird, wird der aufrufende Thread den Wartevorgang vermieden.</span><span class="sxs-lookup"><span data-stu-id="3c781-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> `CreateCrstWithSpinCount` <span data-ttu-id="3c781-131">spiegelt die Win32- `InitializeCriticalSectionAndSpinCount` Funktion.</span><span class="sxs-lookup"><span data-stu-id="3c781-131">mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c781-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c781-132">Requirements</span></span>  
 <span data-ttu-id="3c781-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c781-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c781-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3c781-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c781-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3c781-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3c781-136">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3c781-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3c781-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c781-137">See also</span></span>

- [<span data-ttu-id="3c781-138">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c781-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3c781-139">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c781-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="3c781-140">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c781-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
