---
title: IHostSecurityManager::OpenThreadToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.OpenThreadToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d3b5ec31944b58bec6268de6e54503141880e6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="62043-102">IHostSecurityManager::OpenThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="62043-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="62043-103">Öffnet das freigegebene Zugriffstoken, die den gerade ausgeführten Thread zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="62043-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62043-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62043-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62043-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="62043-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="62043-106">[in] Eine Maske von Access-Werte, die die angeforderten Zugriffstypen Zugriff auf das Threadtoken angeben.</span><span class="sxs-lookup"><span data-stu-id="62043-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="62043-107">Diese Werte werden definiert, in der Win32- `OpenThreadToken` Funktion.</span><span class="sxs-lookup"><span data-stu-id="62043-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="62043-108">Die angeforderten Zugriffstypen werden abgestimmt für das Token besitzerverwaltete Zugriffssteuerungsliste (DACL), um zu bestimmen, welche Typen von Zugriff gewährt oder verweigert.</span><span class="sxs-lookup"><span data-stu-id="62043-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="62043-109">[in] `true` um anzugeben, dass die zugriffsprüfung unter Verwendung des Sicherheitskontexts des Prozesses für den aufrufenden Thread vorgenommen werden sollten `false` um anzugeben, dass die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="62043-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="62043-110">Wenn der Thread den Identitätswechsel eines Clients ist, kann der Sicherheitskontext einer Client-Prozess sein.</span><span class="sxs-lookup"><span data-stu-id="62043-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="62043-111">[out] Ein Zeiger auf das neu geöffnete Zugriffstoken.</span><span class="sxs-lookup"><span data-stu-id="62043-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62043-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="62043-112">Return Value</span></span>  
  
|<span data-ttu-id="62043-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62043-113">HRESULT</span></span>|<span data-ttu-id="62043-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62043-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62043-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="62043-115">S_OK</span></span>|<span data-ttu-id="62043-116">`OpenThreadToken`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="62043-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="62043-117">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="62043-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62043-118">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="62043-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62043-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62043-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62043-120">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="62043-120">The call timed out.</span></span>|  
|<span data-ttu-id="62043-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62043-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62043-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="62043-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62043-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62043-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62043-124">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="62043-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62043-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62043-125">E_FAIL</span></span>|<span data-ttu-id="62043-126">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="62043-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62043-127">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="62043-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62043-128">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="62043-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62043-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62043-129">Remarks</span></span>  
 <span data-ttu-id="62043-130">`IHostSecurityManager::OpenThreadToken`verhält sich ähnlich wie die entsprechenden Win32-Funktion mit dem gleichen Namen, außer dass die Win32-Funktion zulässt, dass den Aufrufer ein Handle zu einem beliebigen Thread übergeben, während `IHostSecurityManager::OpenThreadToken` öffnet nur die Token, die den aufrufenden Thread zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="62043-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="62043-131">Die `HANDLE` ist keine COM-kompatiblen, d. h., seine Größe ist spezifisch für das Betriebssystem und erfordert benutzerdefiniertes Marshalling geht.</span><span class="sxs-lookup"><span data-stu-id="62043-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="62043-132">Daher ist dieses Token für die Verwendung nur innerhalb des Prozesses zwischen CLR und dem Host.</span><span class="sxs-lookup"><span data-stu-id="62043-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62043-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62043-133">Requirements</span></span>  
 <span data-ttu-id="62043-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62043-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62043-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="62043-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62043-136">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="62043-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62043-137">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62043-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62043-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62043-138">See Also</span></span>  
 [<span data-ttu-id="62043-139">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62043-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="62043-140">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62043-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
