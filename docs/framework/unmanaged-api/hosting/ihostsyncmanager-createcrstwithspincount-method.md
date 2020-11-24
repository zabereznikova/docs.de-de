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
ms.openlocfilehash: 6b2f57c7147cc8ff2abff848bd1e4661c2f5e728
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682880"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="023e9-102">IHostSyncManager::CreateCrstWithSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="023e9-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>

<span data-ttu-id="023e9-103">Erstellt ein kritisches Abschnitts Objekt mit der Drehzahl für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="023e9-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="023e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="023e9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="023e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="023e9-105">Parameters</span></span>  

 `dwSpinCount`  
 <span data-ttu-id="023e9-106">in Gibt die drehanzahl für das kritische Abschnitts Objekt an.</span><span class="sxs-lookup"><span data-stu-id="023e9-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="023e9-107">vorgenommen Ein Zeiger auf die Adresse einer [IHostCrst](ihostcrst-interface.md) -Instanz oder NULL, wenn der kritische Abschnitt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="023e9-107">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="023e9-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="023e9-108">Return Value</span></span>  
  
|<span data-ttu-id="023e9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="023e9-109">HRESULT</span></span>|<span data-ttu-id="023e9-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="023e9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="023e9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="023e9-111">S_OK</span></span>|<span data-ttu-id="023e9-112">`CreateCrstWithSpinCount` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="023e9-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="023e9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="023e9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="023e9-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="023e9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="023e9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="023e9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="023e9-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="023e9-116">The call timed out.</span></span>|  
|<span data-ttu-id="023e9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="023e9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="023e9-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="023e9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="023e9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="023e9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="023e9-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="023e9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="023e9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="023e9-121">E_FAIL</span></span>|<span data-ttu-id="023e9-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="023e9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="023e9-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="023e9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="023e9-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="023e9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="023e9-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="023e9-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="023e9-126">Es war nicht genügend Arbeitsspeicher verfügbar, um den angeforderten kritischen Abschnitt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="023e9-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="023e9-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="023e9-127">Remarks</span></span>  

 <span data-ttu-id="023e9-128">Eine drehanzahl wird nur auf einem System mit mehreren Prozessoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="023e9-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="023e9-129">Der drehwert gibt an, wie oft ein aufrufende Thread gedreht werden muss, bevor er einen Warte Vorgang für ein Semaphor ausführt, das einem nicht verfügbaren kritischen Abschnitt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="023e9-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="023e9-130">Wenn der kritische Abschnitt während des drehvorgangs frei wird, vermeidet der aufrufenden Thread den warte Vorgang.</span><span class="sxs-lookup"><span data-stu-id="023e9-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="023e9-131">`CreateCrstWithSpinCount` spiegelt die Win32- `InitializeCriticalSectionAndSpinCount` Funktion wider.</span><span class="sxs-lookup"><span data-stu-id="023e9-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="023e9-132">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="023e9-132">Requirements</span></span>  

 <span data-ttu-id="023e9-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="023e9-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="023e9-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="023e9-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="023e9-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="023e9-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="023e9-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="023e9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023e9-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="023e9-137">See also</span></span>

- [<span data-ttu-id="023e9-138">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="023e9-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="023e9-139">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="023e9-139">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="023e9-140">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="023e9-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
