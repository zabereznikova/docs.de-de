---
title: ICLRSyncManager::CreateRWLockOwnerIterator-Methode
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
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f74a15bb58f0ee62b56204e2b145ae64ff7dd59
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="18aca-102">ICLRSyncManager::CreateRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="18aca-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="18aca-103">Fordert, dass die common Language Runtime (CLR) erstellt einen Iterator für den Host zum Bestimmen des Satz von Aufgaben, die auf eine Reader / Writer-Sperre warten.</span><span class="sxs-lookup"><span data-stu-id="18aca-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18aca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18aca-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18aca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="18aca-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="18aca-106">[in] Das Cookie, das die gewünschte Lese-/Schreibsperre zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="18aca-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="18aca-107">[out] Ein Zeiger auf ein Iterator, der übergeben werden kann die [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) und [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) Methoden.</span><span class="sxs-lookup"><span data-stu-id="18aca-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18aca-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="18aca-108">Return Value</span></span>  
  
|<span data-ttu-id="18aca-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18aca-109">HRESULT</span></span>|<span data-ttu-id="18aca-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18aca-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="18aca-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="18aca-111">S_OK</span></span>|<span data-ttu-id="18aca-112">`CreateRWLockOwnerIterator`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="18aca-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="18aca-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="18aca-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="18aca-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="18aca-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="18aca-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="18aca-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="18aca-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="18aca-116">The call timed out.</span></span>|  
|<span data-ttu-id="18aca-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="18aca-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="18aca-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="18aca-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="18aca-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="18aca-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="18aca-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="18aca-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="18aca-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="18aca-121">E_FAIL</span></span>|<span data-ttu-id="18aca-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="18aca-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="18aca-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="18aca-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="18aca-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="18aca-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="18aca-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="18aca-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="18aca-126">`CreateRWLockOwnerIterator`wurde in einem Thread aufgerufen, die derzeit verwalteten Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="18aca-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18aca-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18aca-127">Remarks</span></span>  
 <span data-ttu-id="18aca-128">Rufen Sie die Hosts in der Regel die `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, und `GetRWLockOwnerNext` Methoden, die während der Deadlockerkennung.</span><span class="sxs-lookup"><span data-stu-id="18aca-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="18aca-129">Der Host ist dafür verantwortlich, dass die Lese-/Schreibsperre noch gültig ist, da die CLR versucht nicht, um den Lese-/Schreibsperre aufrechtzuerhalten führt.</span><span class="sxs-lookup"><span data-stu-id="18aca-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="18aca-130">Mehrere Strategien sind verfügbar für den Host aus, um sicherzustellen, dass die Gültigkeit der Sperre:</span><span class="sxs-lookup"><span data-stu-id="18aca-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
-   <span data-ttu-id="18aca-131">Der Host kann die Release-Aufrufe an die Lese-/Schreibsperre blockieren (z. B. [IHostSemaphore:: ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) und gleichzeitig sicherstellen, dass dieser Block nicht Deadlock führt.</span><span class="sxs-lookup"><span data-stu-id="18aca-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
-   <span data-ttu-id="18aca-132">Der Host kann das Warten auf das Ereignisobjekt, das der Reader / Writer-Sperre zugeordneten beenden blockieren und erneut sicherstellen, dass dieser Block nicht Deadlock führt.</span><span class="sxs-lookup"><span data-stu-id="18aca-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18aca-133">`CreateRWLockOwnerIterator`muss nur auf Threads aufgerufen werden, die derzeit nicht verwalteten Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="18aca-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18aca-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18aca-134">Requirements</span></span>  
 <span data-ttu-id="18aca-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18aca-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18aca-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="18aca-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="18aca-137">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="18aca-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18aca-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18aca-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18aca-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18aca-139">See Also</span></span>  
 [<span data-ttu-id="18aca-140">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18aca-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="18aca-141">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18aca-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
