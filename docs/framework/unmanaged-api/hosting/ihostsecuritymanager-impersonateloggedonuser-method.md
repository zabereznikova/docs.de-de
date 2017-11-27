---
title: IHostSecurityManager::ImpersonateLoggedOnUser-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.ImpersonateLoggedOnUser
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c5956dcad6908f0117de7f5ff0c6632ad3bb925
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="08ed3-102">IHostSecurityManager::ImpersonateLoggedOnUser-Methode</span><span class="sxs-lookup"><span data-stu-id="08ed3-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="08ed3-103">Anforderungen, die Code mit den Anmeldeinformationen der Identität des aktuellen Benutzers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="08ed3-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08ed3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08ed3-104">Syntax</span></span>  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08ed3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08ed3-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="08ed3-106">[in] Ein Token, das die Anmeldeinformationen des Benutzers, dessen Identität übernommen werden darstellt.</span><span class="sxs-lookup"><span data-stu-id="08ed3-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08ed3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="08ed3-107">Return Value</span></span>  
  
|<span data-ttu-id="08ed3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08ed3-108">HRESULT</span></span>|<span data-ttu-id="08ed3-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08ed3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08ed3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="08ed3-110">S_OK</span></span>|<span data-ttu-id="08ed3-111">`ImpersonateLoggedOnUser`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="08ed3-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="08ed3-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="08ed3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08ed3-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="08ed3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08ed3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08ed3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08ed3-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="08ed3-115">The call timed out.</span></span>|  
|<span data-ttu-id="08ed3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08ed3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08ed3-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="08ed3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08ed3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08ed3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08ed3-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="08ed3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08ed3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08ed3-120">E_FAIL</span></span>|<span data-ttu-id="08ed3-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="08ed3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08ed3-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="08ed3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08ed3-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="08ed3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08ed3-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08ed3-124">Remarks</span></span>  
 <span data-ttu-id="08ed3-125">Rufen Sie `LogonUser` oder eine verwandte Win32-Funktion, um ein Handle für die Anmeldeinformationen der Identität des aktuellen Benutzers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="08ed3-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="08ed3-126">Die `HANDLE` ist keine COM-kompatiblen, d. h., seine Größe ist spezifisch für ein Betriebssystem installiert ist und erfordert benutzerdefiniertes Marshalling geht.</span><span class="sxs-lookup"><span data-stu-id="08ed3-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="08ed3-127">Daher ist dieses Token für die Verwendung nur innerhalb des Prozesses zwischen CLR und dem Host.</span><span class="sxs-lookup"><span data-stu-id="08ed3-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08ed3-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08ed3-128">Requirements</span></span>  
 <span data-ttu-id="08ed3-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08ed3-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08ed3-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08ed3-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08ed3-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="08ed3-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08ed3-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08ed3-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ed3-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08ed3-133">See Also</span></span>  
 [<span data-ttu-id="08ed3-134">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ed3-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="08ed3-135">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ed3-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="08ed3-136">RevertToSelf-Methode</span><span class="sxs-lookup"><span data-stu-id="08ed3-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
