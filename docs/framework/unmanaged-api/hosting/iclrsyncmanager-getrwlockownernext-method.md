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
ms.openlocfilehash: 860a818b08cb88b0fa17adccdfac5c81c0ec502c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130560"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="7b86e-102">ICLRSyncManager::GetRWLockOwnerNext-Methode</span><span class="sxs-lookup"><span data-stu-id="7b86e-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="7b86e-103">Ruft die nächste [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz ab, die für die aktuelle Lese-/Schreibsperre blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="7b86e-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b86e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b86e-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b86e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b86e-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="7b86e-106">in Der Iterator, der mit einem Aufrufen von " [foraterwlockowneriterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)" erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7b86e-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="7b86e-107">vorgenommen Ein Zeiger auf den nächsten `IHostTask`, der auf die Sperre wartet, oder NULL, wenn keine Aufgabe wartet.</span><span class="sxs-lookup"><span data-stu-id="7b86e-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b86e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7b86e-108">Return Value</span></span>  
  
|<span data-ttu-id="7b86e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b86e-109">HRESULT</span></span>|<span data-ttu-id="7b86e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b86e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b86e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b86e-111">S_OK</span></span>|<span data-ttu-id="7b86e-112">`GetRWLockOwnerNext` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7b86e-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="7b86e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7b86e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7b86e-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7b86e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7b86e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7b86e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7b86e-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7b86e-116">The call timed out.</span></span>|  
|<span data-ttu-id="7b86e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7b86e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7b86e-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7b86e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7b86e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7b86e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7b86e-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7b86e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7b86e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7b86e-121">E_FAIL</span></span>|<span data-ttu-id="7b86e-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7b86e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7b86e-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b86e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7b86e-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7b86e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b86e-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b86e-125">Remarks</span></span>  
 <span data-ttu-id="7b86e-126">Wenn `ppOwnerHostTask` auf NULL festgelegt ist, wird die Iterationen beendet, und der Host sollte die [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7b86e-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b86e-127">Die CLR ruft `AddRef` für die `IHostTask` auf, auf die `ppOwnerHostTask` zeigt, um zu verhindern, dass diese Aufgabe beendet wird, während der Host den Zeiger enthält.</span><span class="sxs-lookup"><span data-stu-id="7b86e-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="7b86e-128">Der Host muss `Release` aufzurufen, um den Verweis Zähler zu verringern, wenn er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7b86e-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b86e-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b86e-129">Requirements</span></span>  
 <span data-ttu-id="7b86e-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b86e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b86e-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7b86e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b86e-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7b86e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b86e-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b86e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b86e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b86e-134">See also</span></span>

- [<span data-ttu-id="7b86e-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b86e-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="7b86e-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b86e-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
