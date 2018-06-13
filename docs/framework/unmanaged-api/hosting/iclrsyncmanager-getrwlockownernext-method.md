---
title: ICLRSyncManager::GetRWLockOwnerNext-Methode
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4725feff4645ec207be6e6afc7d1e1d38eca36ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435209"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="72cd4-102">ICLRSyncManager::GetRWLockOwnerNext-Methode</span><span class="sxs-lookup"><span data-stu-id="72cd4-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="72cd4-103">Ruft den nächsten [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz, die auf dem aktuellen Lese-/Schreibsperre blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="72cd4-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72cd4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72cd4-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72cd4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="72cd4-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="72cd4-106">[in] Der Iterator, der erstellt wurde, mithilfe eines Aufrufs an [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="72cd4-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="72cd4-107">[out] Ein Zeiger auf den nächsten `IHostTask` , die wartet auf die Sperre oder Null, wenn kein Task darauf wartet, wird.</span><span class="sxs-lookup"><span data-stu-id="72cd4-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72cd4-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="72cd4-108">Return Value</span></span>  
  
|<span data-ttu-id="72cd4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72cd4-109">HRESULT</span></span>|<span data-ttu-id="72cd4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72cd4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72cd4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="72cd4-111">S_OK</span></span>|<span data-ttu-id="72cd4-112">`GetRWLockOwnerNext` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="72cd4-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="72cd4-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="72cd4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="72cd4-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="72cd4-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="72cd4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="72cd4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="72cd4-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="72cd4-116">The call timed out.</span></span>|  
|<span data-ttu-id="72cd4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="72cd4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="72cd4-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="72cd4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="72cd4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="72cd4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="72cd4-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="72cd4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="72cd4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="72cd4-121">E_FAIL</span></span>|<span data-ttu-id="72cd4-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="72cd4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="72cd4-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="72cd4-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="72cd4-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="72cd4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72cd4-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72cd4-125">Remarks</span></span>  
 <span data-ttu-id="72cd4-126">Wenn `ppOwnerHostTask` auf festgelegt ist null, die Iteration beendet wurde, und der Host sollte Aufrufen der [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="72cd4-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72cd4-127">Die CLR ruft `AddRef` auf die `IHostTask` , `ppOwnerHostTask` verweist auf diese Aufgabe beenden verhindern während der Host den Zeiger enthält.</span><span class="sxs-lookup"><span data-stu-id="72cd4-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="72cd4-128">Der Host muss Aufrufen `Release` auf den Verweiszähler zu verringern, wenn er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="72cd4-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72cd4-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72cd4-129">Requirements</span></span>  
 <span data-ttu-id="72cd4-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72cd4-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72cd4-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="72cd4-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72cd4-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="72cd4-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72cd4-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72cd4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72cd4-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72cd4-134">See Also</span></span>  
 [<span data-ttu-id="72cd4-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72cd4-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="72cd4-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72cd4-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
