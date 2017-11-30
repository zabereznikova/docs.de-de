---
title: IHostSecurityManager::SetThreadToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.SetThreadToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49a505af3ef7d0208af7c65713e615fd44253e93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="4b1cc-102">IHostSecurityManager::SetThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="4b1cc-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="4b1cc-103">Legt einen Handle für den gerade ausgeführten Thread fest.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b1cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b1cc-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b1cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b1cc-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="4b1cc-106">[in] Ein Handle für das Token für den gerade ausgeführten Thread festlegen.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b1cc-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4b1cc-107">Return Value</span></span>  
  
|<span data-ttu-id="4b1cc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b1cc-108">HRESULT</span></span>|<span data-ttu-id="4b1cc-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b1cc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b1cc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b1cc-110">S_OK</span></span>|<span data-ttu-id="4b1cc-111">`SetThreadToken`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="4b1cc-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="4b1cc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4b1cc-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4b1cc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4b1cc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4b1cc-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-115">The call timed out.</span></span>|  
|<span data-ttu-id="4b1cc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4b1cc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4b1cc-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4b1cc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4b1cc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4b1cc-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4b1cc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b1cc-120">E_FAIL</span></span>|<span data-ttu-id="4b1cc-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4b1cc-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4b1cc-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b1cc-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b1cc-124">Remarks</span></span>  
 <span data-ttu-id="4b1cc-125">`IHostSecurityManager::SetThreadToken`verhält sich ähnlich wie die entsprechenden Win32-Funktion mit dem gleichen Namen, außer dass die Win32-Funktion zulässt, dass den Aufrufer ein Handle zu einem beliebigen Thread übergeben, während `IHostSecurityManager::SetThreadToken` können ein Token nur mit den gerade ausgeführten Thread zuordnen.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="4b1cc-126">Die `HANDLE` ist keine COM-kompatiblen; d. h. seine Größe ist spezifisch für ein Betriebssystem installiert ist und erfordert benutzerdefiniertes Marshalling geht.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="4b1cc-127">Daher ist dieses Token für die Verwendung nur innerhalb des Prozesses zwischen CLR und dem Host.</span><span class="sxs-lookup"><span data-stu-id="4b1cc-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b1cc-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b1cc-128">Requirements</span></span>  
 <span data-ttu-id="4b1cc-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b1cc-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b1cc-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4b1cc-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b1cc-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4b1cc-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b1cc-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b1cc-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b1cc-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b1cc-133">See Also</span></span>  
 [<span data-ttu-id="4b1cc-134">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b1cc-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="4b1cc-135">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b1cc-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
