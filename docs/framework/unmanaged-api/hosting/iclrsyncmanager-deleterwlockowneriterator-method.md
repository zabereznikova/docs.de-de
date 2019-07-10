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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a30ac0ab8c985af04709ddd8e8e5dd9bca776dcb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759095"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="3890b-102">ICLRSyncManager::DeleteRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="3890b-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="3890b-103">Fordert an, dass die common Language Runtime (CLR) den Iterator, der durch einen Aufruf erstellt wurde zerstört [ICLRSyncManager:: CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="3890b-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3890b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3890b-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3890b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3890b-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="3890b-106">[in] Der Iterator, der erstellt wurde, mit einem Aufruf von `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="3890b-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3890b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3890b-107">Return Value</span></span>  
  
|<span data-ttu-id="3890b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3890b-108">HRESULT</span></span>|<span data-ttu-id="3890b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3890b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3890b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3890b-110">S_OK</span></span>|<span data-ttu-id="3890b-111">`DeleteRWLockOwnerIterator` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3890b-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="3890b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3890b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3890b-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf nicht erfolgreich verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3890b-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="3890b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3890b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3890b-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3890b-115">The call timed out.</span></span>|  
|<span data-ttu-id="3890b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3890b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3890b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3890b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3890b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3890b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3890b-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3890b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3890b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3890b-120">E_FAIL</span></span>|<span data-ttu-id="3890b-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3890b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3890b-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3890b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3890b-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3890b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3890b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3890b-124">Remarks</span></span>  
 <span data-ttu-id="3890b-125">Der Host kann diese Methode aufrufen und `CreateRWLockOwnerIterator` , stellen Sie sicher, dass die threadingimplementierung synchronisiert bleibt.</span><span class="sxs-lookup"><span data-stu-id="3890b-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3890b-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3890b-126">Requirements</span></span>  
 <span data-ttu-id="3890b-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3890b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3890b-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3890b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3890b-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3890b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3890b-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3890b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3890b-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3890b-131">See also</span></span>

- [<span data-ttu-id="3890b-132">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3890b-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3890b-133">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3890b-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
