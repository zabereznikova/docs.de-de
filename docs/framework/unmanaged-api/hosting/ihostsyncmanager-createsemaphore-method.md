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
ms.openlocfilehash: 9af38a58ce8786c56d9f50089605dc994167497e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722127"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="c057a-102">IHostSyncManager::CreateSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="c057a-102">IHostSyncManager::CreateSemaphore Method</span></span>

<span data-ttu-id="c057a-103">Erstellt ein [IHostSemaphore](ihostsemaphore-interface.md) -Objekt für die Common Language Runtime (CLR), die als Semaphor für warte Ereignisse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c057a-103">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c057a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c057a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c057a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c057a-105">Parameters</span></span>  

 `dwInitial`  
 <span data-ttu-id="c057a-106">in Die anfängliche Anzahl für `ppSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="c057a-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="c057a-107">in Die maximale Anzahl für `ppSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="c057a-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="c057a-108">vorgenommen Ein Zeiger auf die Adresse einer `IHostSemaphore` Instanz oder NULL, wenn das Semaphor nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="c057a-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c057a-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c057a-109">Return Value</span></span>  
  
|<span data-ttu-id="c057a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c057a-110">HRESULT</span></span>|<span data-ttu-id="c057a-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c057a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c057a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c057a-112">S_OK</span></span>|<span data-ttu-id="c057a-113">`CreateSemaphore` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c057a-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="c057a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c057a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c057a-115">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c057a-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c057a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c057a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c057a-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c057a-117">The call timed out.</span></span>|  
|<span data-ttu-id="c057a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c057a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c057a-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c057a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c057a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c057a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c057a-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c057a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c057a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c057a-122">E_FAIL</span></span>|<span data-ttu-id="c057a-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c057a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c057a-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c057a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c057a-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c057a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c057a-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c057a-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c057a-127">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c057a-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c057a-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c057a-128">Remarks</span></span>  

 <span data-ttu-id="c057a-129">`CreateSemaphore` spiegelt die Win32-Funktion mit dem gleichen Namen wider.</span><span class="sxs-lookup"><span data-stu-id="c057a-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="c057a-130">Der `dwInitial` -Parameter und der- `dwMax` Parameter verwenden die gleiche Semantik für die Semaphor-Anzahl wie die Win32 `lInitialCount` - `lMaximumCount` bzw.-Parameter.</span><span class="sxs-lookup"><span data-stu-id="c057a-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="c057a-131">`dwInitial` muss zwischen 0 (null) und (einschließlich) liegen `dwMax` .</span><span class="sxs-lookup"><span data-stu-id="c057a-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="c057a-132">`dwMax` muss größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="c057a-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c057a-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c057a-133">Requirements</span></span>  

 <span data-ttu-id="c057a-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c057a-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c057a-135">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c057a-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c057a-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c057a-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c057a-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c057a-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c057a-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c057a-138">See also</span></span>

- [<span data-ttu-id="c057a-139">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c057a-139">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="c057a-140">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c057a-140">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="c057a-141">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c057a-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
