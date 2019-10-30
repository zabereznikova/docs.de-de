---
title: IHostSecurityManager::RevertToSelf-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
ms.openlocfilehash: b896c5509cc4862a6416381f89bc04a28959e091
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121454"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="e32a0-102">IHostSecurityManager::RevertToSelf-Methode</span><span class="sxs-lookup"><span data-stu-id="e32a0-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="e32a0-103">Beendet den Identitätswechsel der aktuellen Benutzeridentität und gibt das ursprüngliche Thread Token zurück.</span><span class="sxs-lookup"><span data-stu-id="e32a0-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e32a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e32a0-104">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e32a0-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e32a0-105">Return Value</span></span>  
  
|<span data-ttu-id="e32a0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e32a0-106">HRESULT</span></span>|<span data-ttu-id="e32a0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e32a0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e32a0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e32a0-108">S_OK</span></span>|<span data-ttu-id="e32a0-109">`RevertToSelf` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e32a0-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="e32a0-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e32a0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e32a0-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e32a0-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e32a0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e32a0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e32a0-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="e32a0-113">The call timed out.</span></span>|  
|<span data-ttu-id="e32a0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e32a0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e32a0-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e32a0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e32a0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e32a0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e32a0-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="e32a0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e32a0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e32a0-118">E_FAIL</span></span>|<span data-ttu-id="e32a0-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e32a0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e32a0-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e32a0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e32a0-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e32a0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e32a0-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e32a0-122">Remarks</span></span>  
 <span data-ttu-id="e32a0-123">`RevertToSelf` nach einem früheren Aufruf der Identität [ateloggedonuser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) -Methode aufgerufen, um zum ursprünglichen Thread Token zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e32a0-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e32a0-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e32a0-124">Requirements</span></span>  
 <span data-ttu-id="e32a0-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e32a0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e32a0-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e32a0-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e32a0-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e32a0-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e32a0-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e32a0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32a0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e32a0-129">See also</span></span>

- [<span data-ttu-id="e32a0-130">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e32a0-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="e32a0-131">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e32a0-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="e32a0-132">ImpersonateLoggedOnUser-Methode</span><span class="sxs-lookup"><span data-stu-id="e32a0-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
