---
title: ICLRSyncManager::DeleteRWLockOwnerIterator-Methode
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.DeleteRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type:
- apiref
ms.openlocfilehash: fb02b5c941e15d172140565e8efb625234947cd7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130577"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="84586-102">ICLRSyncManager::DeleteRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="84586-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="84586-103">Fordert an, dass die Common Language Runtime (CLR) einen Iterator zerstört, der durch einen [ICLRSyncManager:: foraterwlockowneriterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="84586-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84586-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84586-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84586-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84586-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="84586-106">in Der Iterator, der mit einem-`CreateRWLockOwnerIterator`erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="84586-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84586-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84586-107">Return Value</span></span>  
  
|<span data-ttu-id="84586-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84586-108">HRESULT</span></span>|<span data-ttu-id="84586-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84586-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84586-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="84586-110">S_OK</span></span>|<span data-ttu-id="84586-111">`DeleteRWLockOwnerIterator` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="84586-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="84586-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84586-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84586-113">Die CLR wurde nicht in einen Prozess geladen, oder Sie befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="84586-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="84586-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84586-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84586-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="84586-115">The call timed out.</span></span>|  
|<span data-ttu-id="84586-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84586-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84586-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="84586-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84586-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84586-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84586-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="84586-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84586-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84586-120">E_FAIL</span></span>|<span data-ttu-id="84586-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="84586-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84586-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84586-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84586-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="84586-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84586-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84586-124">Remarks</span></span>  
 <span data-ttu-id="84586-125">Der Host kann diese Methode aufzurufen und `CreateRWLockOwnerIterator`, um sicherzustellen, dass die Threading Implementierung synchronisiert bleibt.</span><span class="sxs-lookup"><span data-stu-id="84586-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84586-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84586-126">Requirements</span></span>  
 <span data-ttu-id="84586-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84586-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84586-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="84586-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84586-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="84586-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84586-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84586-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84586-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84586-131">See also</span></span>

- [<span data-ttu-id="84586-132">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84586-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="84586-133">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84586-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
