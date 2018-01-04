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
ms.workload: dotnet
ms.openlocfilehash: bf01ca07544fcce59eef81707bb1ff2d1f375feb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="0028b-102">IHostSecurityManager::ImpersonateLoggedOnUser-Methode</span><span class="sxs-lookup"><span data-stu-id="0028b-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="0028b-103">Anforderungen, die Code mit den Anmeldeinformationen der Identität des aktuellen Benutzers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0028b-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0028b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0028b-104">Syntax</span></span>  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0028b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0028b-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="0028b-106">[in] Ein Token, das die Anmeldeinformationen des Benutzers, dessen Identität übernommen werden darstellt.</span><span class="sxs-lookup"><span data-stu-id="0028b-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0028b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0028b-107">Return Value</span></span>  
  
|<span data-ttu-id="0028b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0028b-108">HRESULT</span></span>|<span data-ttu-id="0028b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0028b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0028b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0028b-110">S_OK</span></span>|<span data-ttu-id="0028b-111">`ImpersonateLoggedOnUser`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0028b-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="0028b-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="0028b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0028b-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0028b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0028b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0028b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0028b-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0028b-115">The call timed out.</span></span>|  
|<span data-ttu-id="0028b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0028b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0028b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0028b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0028b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0028b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0028b-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0028b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0028b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0028b-120">E_FAIL</span></span>|<span data-ttu-id="0028b-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0028b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0028b-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="0028b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0028b-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0028b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0028b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0028b-124">Remarks</span></span>  
 <span data-ttu-id="0028b-125">Rufen Sie `LogonUser` oder eine verwandte Win32-Funktion, um ein Handle für die Anmeldeinformationen der Identität des aktuellen Benutzers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0028b-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="0028b-126">Die `HANDLE` ist keine COM-kompatiblen, d. h., seine Größe ist spezifisch für ein Betriebssystem installiert ist und erfordert benutzerdefiniertes Marshalling geht.</span><span class="sxs-lookup"><span data-stu-id="0028b-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="0028b-127">Daher ist dieses Token für die Verwendung nur innerhalb des Prozesses zwischen CLR und dem Host.</span><span class="sxs-lookup"><span data-stu-id="0028b-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0028b-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0028b-128">Requirements</span></span>  
 <span data-ttu-id="0028b-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0028b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0028b-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0028b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0028b-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0028b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0028b-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0028b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0028b-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0028b-133">See Also</span></span>  
 [<span data-ttu-id="0028b-134">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0028b-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="0028b-135">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0028b-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="0028b-136">RevertToSelf-Methode</span><span class="sxs-lookup"><span data-stu-id="0028b-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
