---
title: ICLRSyncManager::DeleteRWLockOwnerIterator-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dce6699dc625c5c867befe1bc2e307cfaea7719a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="fac52-102">ICLRSyncManager::DeleteRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="fac52-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="fac52-103">Fordert an, dass die common Language Runtime (CLR) den Iterator zerstört, die von einem Aufruf erstellt [ICLRSyncManager:: CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="fac52-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fac52-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fac52-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fac52-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="fac52-106">[in] Der Iterator, der erstellt wurde, mithilfe eines Aufrufs an `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="fac52-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fac52-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fac52-107">Return Value</span></span>  
  
|<span data-ttu-id="fac52-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fac52-108">HRESULT</span></span>|<span data-ttu-id="fac52-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fac52-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fac52-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fac52-110">S_OK</span></span>|<span data-ttu-id="fac52-111">`DeleteRWLockOwnerIterator`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fac52-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="fac52-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="fac52-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fac52-113">Die CLR wurde nicht in einen Prozess geladen oder befindet sich in einem Zustand, in dem sie nicht verwalteten Code ausführen oder den Aufruf nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="fac52-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="fac52-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fac52-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fac52-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fac52-115">The call timed out.</span></span>|  
|<span data-ttu-id="fac52-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fac52-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fac52-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="fac52-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fac52-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fac52-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fac52-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="fac52-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fac52-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fac52-120">E_FAIL</span></span>|<span data-ttu-id="fac52-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fac52-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fac52-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="fac52-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fac52-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fac52-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fac52-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fac52-124">Remarks</span></span>  
 <span data-ttu-id="fac52-125">Der Host kann diese Methode aufrufen und `CreateRWLockOwnerIterator` um sicherzustellen, dass ihre Implementierung threading synchronisiert bleibt.</span><span class="sxs-lookup"><span data-stu-id="fac52-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fac52-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fac52-126">Requirements</span></span>  
 <span data-ttu-id="fac52-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fac52-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac52-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fac52-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fac52-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fac52-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fac52-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac52-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac52-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fac52-131">See Also</span></span>  
 [<span data-ttu-id="fac52-132">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fac52-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="fac52-133">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fac52-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
