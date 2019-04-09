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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b63b283a28ed27a70698c45bdc87d63fef0daf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117941"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="1284e-102">IHostSyncManager::CreateCrst-Methode</span><span class="sxs-lookup"><span data-stu-id="1284e-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="1284e-103">Erstellt ein Kritischer Abschnitt-Objekt, für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="1284e-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1284e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1284e-104">Syntax</span></span>  
  
```  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1284e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1284e-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="1284e-106">[out] Ein Zeiger auf die Adresse einer [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) Instanz vom Host implementiert, oder null, wenn der kritische Abschnitt kann nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1284e-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1284e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1284e-107">Return Value</span></span>  
  
|<span data-ttu-id="1284e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1284e-108">HRESULT</span></span>|<span data-ttu-id="1284e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1284e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1284e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1284e-110">S_OK</span></span>|`CreateCrst` <span data-ttu-id="1284e-111">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1284e-111">returned successfully.</span></span>|  
|<span data-ttu-id="1284e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1284e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1284e-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1284e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1284e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1284e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1284e-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1284e-115">The call timed out.</span></span>|  
|<span data-ttu-id="1284e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1284e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1284e-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1284e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1284e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1284e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1284e-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1284e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1284e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1284e-120">E_FAIL</span></span>|<span data-ttu-id="1284e-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1284e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1284e-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1284e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1284e-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1284e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1284e-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1284e-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1284e-125">Es war nicht genügend Arbeitsspeicher verfügbar, um den angeforderten kritischen Abschnitt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1284e-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1284e-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1284e-126">Remarks</span></span>  
 <span data-ttu-id="1284e-127">Kritische Abschnittsobjekte bieten Synchronisierung ähnelt, die durch ein Mutex-Objekt bereitgestellt, mit dem Unterschied, dass kritische Abschnitte, die nur von den Threads eines einzelnen Prozesses verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1284e-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> `CreateCrst` <span data-ttu-id="1284e-128">spiegelt die Win32- `InitializeCriticalSection` Funktion.</span><span class="sxs-lookup"><span data-stu-id="1284e-128">mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1284e-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1284e-129">Requirements</span></span>  
 <span data-ttu-id="1284e-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1284e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1284e-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1284e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1284e-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1284e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1284e-133">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1284e-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1284e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1284e-134">See also</span></span>

- [<span data-ttu-id="1284e-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1284e-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="1284e-136">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1284e-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="1284e-137">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1284e-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="1284e-138">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1284e-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="1284e-139">Mutexe</span><span class="sxs-lookup"><span data-stu-id="1284e-139">Mutexes</span></span>](../../../../docs/standard/threading/mutexes.md)
- [<span data-ttu-id="1284e-140">Semaphore und SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="1284e-140">Semaphore and SemaphoreSlim</span></span>](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
