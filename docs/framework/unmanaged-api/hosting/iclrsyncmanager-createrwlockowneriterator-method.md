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
ms.openlocfilehash: f8fde4905c41dffde90c6361b5a8cdffa15deb4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503964"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="37093-102">ICLRSyncManager::CreateRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="37093-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="37093-103">Fordert an, dass die Common Language Runtime (CLR) einen Iterator erstellt, mit dem der Host den Satz von Tasks bestimmt, die auf eine Lese-/Schreibsperre warten.</span><span class="sxs-lookup"><span data-stu-id="37093-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37093-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37093-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37093-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="37093-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="37093-106">in Das Cookie, das der gewünschten Lese-/Schreibsperre zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="37093-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="37093-107">vorgenommen Ein Zeiger auf einen Iterator, der an die Methoden [getrwlockbesitznext](iclrsyncmanager-getrwlockownernext-method.md) und [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) weitergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="37093-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37093-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="37093-108">Return Value</span></span>  
  
|<span data-ttu-id="37093-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37093-109">HRESULT</span></span>|<span data-ttu-id="37093-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="37093-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37093-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="37093-111">S_OK</span></span>|<span data-ttu-id="37093-112">`CreateRWLockOwnerIterator`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37093-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="37093-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37093-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37093-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="37093-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37093-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37093-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37093-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="37093-116">The call timed out.</span></span>|  
|<span data-ttu-id="37093-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37093-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37093-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="37093-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37093-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37093-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37093-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="37093-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37093-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37093-121">E_FAIL</span></span>|<span data-ttu-id="37093-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="37093-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37093-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="37093-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37093-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="37093-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="37093-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="37093-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="37093-126">`CreateRWLockOwnerIterator`wurde in einem Thread aufgerufen, der derzeit verwalteten Code ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="37093-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37093-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="37093-127">Remarks</span></span>  
 <span data-ttu-id="37093-128">Hosts ruft in der Regel die `CreateRWLockOwnerIterator` `DeleteRWLockOwnerIterator` Methoden, und während der `GetRWLockOwnerNext` Deadlockerkennung auf.</span><span class="sxs-lookup"><span data-stu-id="37093-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="37093-129">Der Host ist dafür verantwortlich, sicherzustellen, dass die Lese-/Schreibsperre weiterhin gültig ist, da die CLR keinen Versuch macht, die Lese-/Schreibsperre aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="37093-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="37093-130">Es stehen mehrere Strategien für den Host zur Verfügung, um die Gültigkeit der Sperre sicherzustellen:</span><span class="sxs-lookup"><span data-stu-id="37093-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
- <span data-ttu-id="37093-131">Der Host kann Freigabe Aufrufe für die Reader-Writer-Sperre blockieren (z. b. [IHostSemaphore:: ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)) und gleichzeitig sicherstellen, dass dieser Block keinen Deadlock verursacht.</span><span class="sxs-lookup"><span data-stu-id="37093-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
- <span data-ttu-id="37093-132">Der Host kann das warten auf das Ereignis Objekt, das der Lese-/Schreibsperre zugeordnet ist, blockieren und sicherstellen, dass dieser Block keinen Deadlock verursacht.</span><span class="sxs-lookup"><span data-stu-id="37093-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37093-133">`CreateRWLockOwnerIterator`muss nur für Threads aufgerufen werden, die derzeit nicht verwalteten Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="37093-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37093-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="37093-134">Requirements</span></span>  
 <span data-ttu-id="37093-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37093-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37093-136">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="37093-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37093-137">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="37093-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37093-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37093-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37093-139">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="37093-139">See also</span></span>

- [<span data-ttu-id="37093-140">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37093-140">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="37093-141">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37093-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
