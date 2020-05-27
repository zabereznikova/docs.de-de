---
title: IHostSyncManager::CreateCrst-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
ms.openlocfilehash: 3566907544c72da2735e155d9088fe09fea4a728
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803474"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="98227-102">IHostSyncManager::CreateCrst-Methode</span><span class="sxs-lookup"><span data-stu-id="98227-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="98227-103">Erstellt ein kritisches Abschnitts Objekt für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="98227-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98227-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98227-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98227-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="98227-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="98227-106">vorgenommen Ein Zeiger auf die Adresse einer vom Host implementierten [IHostCrst](ihostcrst-interface.md) -Instanz oder NULL, wenn der kritische Abschnitt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="98227-106">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98227-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="98227-107">Return Value</span></span>  
  
|<span data-ttu-id="98227-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98227-108">HRESULT</span></span>|<span data-ttu-id="98227-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="98227-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98227-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="98227-110">S_OK</span></span>|<span data-ttu-id="98227-111">`CreateCrst`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="98227-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="98227-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="98227-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="98227-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="98227-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="98227-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="98227-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="98227-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="98227-115">The call timed out.</span></span>|  
|<span data-ttu-id="98227-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="98227-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="98227-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="98227-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="98227-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="98227-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="98227-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="98227-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="98227-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="98227-120">E_FAIL</span></span>|<span data-ttu-id="98227-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="98227-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="98227-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="98227-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="98227-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="98227-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="98227-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="98227-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="98227-125">Es war nicht genügend Arbeitsspeicher verfügbar, um den angeforderten kritischen Abschnitt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="98227-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98227-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="98227-126">Remarks</span></span>  
 <span data-ttu-id="98227-127">Kritische Abschnitts Objekte ermöglichen eine Synchronisierung ähnlich der von einem Mutex-Objekt, mit dem Unterschied, dass wichtige Abschnitte nur von den Threads eines einzelnen Prozesses verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="98227-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="98227-128">`CreateCrst`spiegelt die Win32- `InitializeCriticalSection` Funktion wider.</span><span class="sxs-lookup"><span data-stu-id="98227-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98227-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="98227-129">Requirements</span></span>  
 <span data-ttu-id="98227-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98227-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98227-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="98227-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98227-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="98227-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98227-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98227-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98227-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98227-134">See also</span></span>

- [<span data-ttu-id="98227-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98227-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="98227-136">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98227-136">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="98227-137">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98227-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="98227-138">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98227-138">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="98227-139">Mutexe</span><span class="sxs-lookup"><span data-stu-id="98227-139">Mutexes</span></span>](../../../standard/threading/mutexes.md)
- [<span data-ttu-id="98227-140">Semaphore und SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="98227-140">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
