---
title: ICLRSyncManager::CreateRWLockOwnerIterator-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2b9c2fb2a4ddcc39c7690d832a94d772e8b82a3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497079"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="ec048-102">ICLRSyncManager::CreateRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="ec048-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="ec048-103">Fordert, dass die common Language Runtime (CLR) erstellt einen Iterator für den Host zu verwenden, um zu bestimmen, den Satz von Aufgaben, die auf eine Reader / Writer-Sperre warten.</span><span class="sxs-lookup"><span data-stu-id="ec048-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec048-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec048-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec048-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec048-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="ec048-106">[in] Das Cookie, das die gewünschte Reader / Writer-Sperre zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ec048-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="ec048-107">[out] Ein Zeiger auf ein Iterator, der übergeben werden kann die [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) und [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) Methoden.</span><span class="sxs-lookup"><span data-stu-id="ec048-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec048-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ec048-108">Return Value</span></span>  
  
|<span data-ttu-id="ec048-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec048-109">HRESULT</span></span>|<span data-ttu-id="ec048-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec048-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec048-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec048-111">S_OK</span></span>|<span data-ttu-id="ec048-112">`CreateRWLockOwnerIterator` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ec048-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="ec048-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ec048-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ec048-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ec048-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ec048-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ec048-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ec048-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ec048-116">The call timed out.</span></span>|  
|<span data-ttu-id="ec048-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ec048-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ec048-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ec048-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ec048-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ec048-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ec048-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ec048-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ec048-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec048-121">E_FAIL</span></span>|<span data-ttu-id="ec048-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ec048-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ec048-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec048-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ec048-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ec048-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ec048-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="ec048-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="ec048-126">`CreateRWLockOwnerIterator` wurde in einem Thread aufgerufen, die derzeit auf verwalteten Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ec048-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec048-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec048-127">Remarks</span></span>  
 <span data-ttu-id="ec048-128">Rufen Sie die Hosts in der Regel die `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, und `GetRWLockOwnerNext` Methoden während der Deadlockerkennung.</span><span class="sxs-lookup"><span data-stu-id="ec048-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="ec048-129">Der Host ist dafür verantwortlich, sicherzustellen, dass die Reader / Writer-Sperre noch gültig ist, ist, da die CLR versucht nicht, die die Lese-/ Schreibsperre beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="ec048-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="ec048-130">Es stehen verschiedene Strategien für den Host aus, um sicherzustellen, dass die Gültigkeit der Sperre zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="ec048-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
-   <span data-ttu-id="ec048-131">Der Host kann Freigabeaufrufe für den Lese-/ Schreibsperre (z. B. [IHostSemaphore:: ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) und gleichzeitig sicherstellen, dass dieser Block keinen Deadlock verursacht.</span><span class="sxs-lookup"><span data-stu-id="ec048-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
-   <span data-ttu-id="ec048-132">Der Host kann das Warten auf das Ereignisobjekt, das der Reader / Writer-Sperre zugeordneten beenden blockieren und wieder sicherstellen, dass dieser Block keinen Deadlock verursacht.</span><span class="sxs-lookup"><span data-stu-id="ec048-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec048-133">`CreateRWLockOwnerIterator` muss nur auf Threads aufgerufen werden, die derzeit nicht verwalteten Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec048-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec048-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec048-134">Requirements</span></span>  
 <span data-ttu-id="ec048-135">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec048-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec048-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ec048-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec048-137">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ec048-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec048-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec048-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec048-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec048-139">See also</span></span>
- [<span data-ttu-id="ec048-140">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec048-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="ec048-141">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec048-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
