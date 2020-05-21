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
ms.openlocfilehash: a4094a64d27072ce257341398bb49419bef9b8bb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763149"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="1ddd7-102">ICLRSyncManager::DeleteRWLockOwnerIterator-Methode</span><span class="sxs-lookup"><span data-stu-id="1ddd7-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="1ddd7-103">Fordert an, dass die Common Language Runtime (CLR) einen Iterator zerstört, der durch einen [ICLRSyncManager:: foraterwlockowneriterator](iclrsyncmanager-createrwlockowneriterator-method.md)erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1ddd7-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ddd7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ddd7-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ddd7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ddd7-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="1ddd7-106">in Der Iterator, der mithilfe eines Aufrufes erstellt wurde `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="1ddd7-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ddd7-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1ddd7-107">Return Value</span></span>  
  
|<span data-ttu-id="1ddd7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ddd7-108">HRESULT</span></span>|<span data-ttu-id="1ddd7-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ddd7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ddd7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ddd7-110">S_OK</span></span>|<span data-ttu-id="1ddd7-111">`DeleteRWLockOwnerIterator`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1ddd7-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="1ddd7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1ddd7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1ddd7-113">Die CLR wurde nicht in einen Prozess geladen, oder Sie befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="1ddd7-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="1ddd7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1ddd7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1ddd7-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="1ddd7-115">The call timed out.</span></span>|  
|<span data-ttu-id="1ddd7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1ddd7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1ddd7-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1ddd7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1ddd7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1ddd7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1ddd7-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="1ddd7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1ddd7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1ddd7-120">E_FAIL</span></span>|<span data-ttu-id="1ddd7-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1ddd7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1ddd7-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="1ddd7-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1ddd7-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1ddd7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ddd7-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ddd7-124">Remarks</span></span>  
 <span data-ttu-id="1ddd7-125">Der Host kann diese Methode abrufen und `CreateRWLockOwnerIterator` sicherstellen, dass die Threading Implementierung synchronisiert bleibt.</span><span class="sxs-lookup"><span data-stu-id="1ddd7-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ddd7-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1ddd7-126">Requirements</span></span>  
 <span data-ttu-id="1ddd7-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ddd7-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ddd7-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1ddd7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ddd7-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1ddd7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ddd7-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ddd7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ddd7-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddd7-131">See also</span></span>

- [<span data-ttu-id="1ddd7-132">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ddd7-132">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="1ddd7-133">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ddd7-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
