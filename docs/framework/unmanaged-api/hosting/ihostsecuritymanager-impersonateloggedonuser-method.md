---
title: IHostSecurityManager::ImpersonateLoggedOnUser-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.ImpersonateLoggedOnUser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ebf9ad72f7a1b0dd7ac54afa104089182f122ef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109888"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="a1abd-102">IHostSecurityManager::ImpersonateLoggedOnUser-Methode</span><span class="sxs-lookup"><span data-stu-id="a1abd-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="a1abd-103">Anforderungen, die Code mit den Anmeldeinformationen der Identität des aktuellen Benutzers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a1abd-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1abd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1abd-104">Syntax</span></span>  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1abd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1abd-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="a1abd-106">[in] Ein Token, das die Anmeldeinformationen des Benutzers, dessen Identität übernommen werden darstellt.</span><span class="sxs-lookup"><span data-stu-id="a1abd-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1abd-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a1abd-107">Return Value</span></span>  
  
|<span data-ttu-id="a1abd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1abd-108">HRESULT</span></span>|<span data-ttu-id="a1abd-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1abd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1abd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1abd-110">S_OK</span></span>|`ImpersonateLoggedOnUser` <span data-ttu-id="a1abd-111">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a1abd-111">returned successfully.</span></span>|  
|<span data-ttu-id="a1abd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a1abd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a1abd-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a1abd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a1abd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a1abd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a1abd-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a1abd-115">The call timed out.</span></span>|  
|<span data-ttu-id="a1abd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a1abd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a1abd-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a1abd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a1abd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a1abd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a1abd-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="a1abd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a1abd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a1abd-120">E_FAIL</span></span>|<span data-ttu-id="a1abd-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a1abd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a1abd-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a1abd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a1abd-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a1abd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1abd-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1abd-124">Remarks</span></span>  
 <span data-ttu-id="a1abd-125">Rufen Sie `LogonUser` oder einer entsprechenden Win32-Funktion, ein Handle für die Anmeldeinformationen der Identität des aktuellen Benutzers ab.</span><span class="sxs-lookup"><span data-stu-id="a1abd-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="a1abd-126">Die `HANDLE` Typ ist nicht in der COM-kompatibel, d. h. seine Größe ist spezifisch für ein Betriebssystem installiert ist und benutzerdefiniertes Marshalling erfordert.</span><span class="sxs-lookup"><span data-stu-id="a1abd-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="a1abd-127">Daher ist dieses Token für die Verwendung nur innerhalb des Prozesses, zwischen der CLR und dem Host ein.</span><span class="sxs-lookup"><span data-stu-id="a1abd-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1abd-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1abd-128">Requirements</span></span>  
 <span data-ttu-id="a1abd-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1abd-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1abd-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a1abd-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1abd-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a1abd-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a1abd-132">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a1abd-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a1abd-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1abd-133">See also</span></span>

- [<span data-ttu-id="a1abd-134">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1abd-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="a1abd-135">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1abd-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="a1abd-136">RevertToSelf-Methode</span><span class="sxs-lookup"><span data-stu-id="a1abd-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
