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
ms.openlocfilehash: 93a8b3884d831b7da412b6c53dd599af216cbbf2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728315"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="7cad3-102">ICLRSyncManager::GetRWLockOwnerNext-Methode</span><span class="sxs-lookup"><span data-stu-id="7cad3-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>

<span data-ttu-id="7cad3-103">Ruft die nächste [IHostTask](ihosttask-interface.md) -Instanz ab, die für die aktuelle Lese-/Schreibsperre blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="7cad3-103">Gets the next [IHostTask](ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cad3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cad3-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cad3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7cad3-105">Parameters</span></span>  

 `Iterator`  
 <span data-ttu-id="7cad3-106">in Der Iterator, der mit einem Aufrufen von " [foraterwlockowneriterator](iclrsyncmanager-createrwlockowneriterator-method.md)" erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7cad3-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="7cad3-107">vorgenommen Ein Zeiger auf den nächsten, der `IHostTask` auf die Sperre wartet, oder NULL, wenn keine Aufgabe wartet.</span><span class="sxs-lookup"><span data-stu-id="7cad3-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cad3-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7cad3-108">Return Value</span></span>  
  
|<span data-ttu-id="7cad3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7cad3-109">HRESULT</span></span>|<span data-ttu-id="7cad3-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7cad3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7cad3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7cad3-111">S_OK</span></span>|<span data-ttu-id="7cad3-112">`GetRWLockOwnerNext` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7cad3-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="7cad3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7cad3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7cad3-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7cad3-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7cad3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7cad3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7cad3-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7cad3-116">The call timed out.</span></span>|  
|<span data-ttu-id="7cad3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7cad3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7cad3-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7cad3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7cad3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7cad3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7cad3-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7cad3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7cad3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7cad3-121">E_FAIL</span></span>|<span data-ttu-id="7cad3-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7cad3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7cad3-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="7cad3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7cad3-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7cad3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cad3-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cad3-125">Remarks</span></span>  

 <span data-ttu-id="7cad3-126">Wenn `ppOwnerHostTask` auf NULL festgelegt ist, wird die Iterationen beendet, und der Host sollte die [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7cad3-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7cad3-127">Die CLR ruft auf der-Klasse auf, um `AddRef` `IHostTask` `ppOwnerHostTask` zu verhindern, dass diese Aufgabe beendet wird, während der Host den-Zeiger enthält.</span><span class="sxs-lookup"><span data-stu-id="7cad3-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="7cad3-128">Der Host muss aufzurufen `Release` , um den Verweis Zähler zu verringern, wenn er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7cad3-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cad3-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7cad3-129">Requirements</span></span>  

 <span data-ttu-id="7cad3-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cad3-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cad3-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7cad3-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7cad3-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7cad3-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cad3-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cad3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cad3-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7cad3-134">See also</span></span>

- [<span data-ttu-id="7cad3-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cad3-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="7cad3-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cad3-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
