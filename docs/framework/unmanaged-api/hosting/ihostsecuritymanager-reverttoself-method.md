---
title: IHostSecurityManager::RevertToSelf-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.RevertToSelf
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0fad325bc3df54f412a797e9944f5b1f38615786
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="f5194-102">IHostSecurityManager::RevertToSelf-Methode</span><span class="sxs-lookup"><span data-stu-id="f5194-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="f5194-103">Beendet den Identitätswechsel der Identität des aktuellen Benutzers und der ursprüngliche Threadtoken zurück.</span><span class="sxs-lookup"><span data-stu-id="f5194-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5194-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5194-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f5194-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f5194-105">Return Value</span></span>  
  
|<span data-ttu-id="f5194-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5194-106">HRESULT</span></span>|<span data-ttu-id="f5194-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5194-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5194-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5194-108">S_OK</span></span>|<span data-ttu-id="f5194-109">`RevertToSelf`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f5194-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="f5194-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="f5194-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5194-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f5194-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5194-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5194-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5194-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f5194-113">The call timed out.</span></span>|  
|<span data-ttu-id="f5194-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5194-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5194-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f5194-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5194-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5194-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5194-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="f5194-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f5194-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5194-118">E_FAIL</span></span>|<span data-ttu-id="f5194-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f5194-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5194-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="f5194-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5194-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f5194-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5194-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5194-122">Remarks</span></span>  
 <span data-ttu-id="f5194-123">`RevertToSelf`wird aufgerufen, um zurück zum ursprünglichen Threadtoken nach einem vorhergegangenen Aufruf von der [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f5194-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5194-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5194-124">Requirements</span></span>  
 <span data-ttu-id="f5194-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5194-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5194-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f5194-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5194-127">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f5194-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5194-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5194-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5194-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5194-129">See Also</span></span>  
 [<span data-ttu-id="f5194-130">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5194-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="f5194-131">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5194-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="f5194-132">ImpersonateLoggedOnUser-Methode</span><span class="sxs-lookup"><span data-stu-id="f5194-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
