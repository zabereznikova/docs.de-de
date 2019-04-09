---
title: IHostSecurityManager::OpenThreadToken-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68ebfdcd0ef34edec724a044791d05dd48580b12
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144559"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="ee071-102">IHostSecurityManager::OpenThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="ee071-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="ee071-103">Öffnet das discretionary Access Control-Token mit dem aktuell ausgeführten Thread verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="ee071-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee071-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee071-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee071-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee071-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="ee071-106">[in] Eine Maske von Access-Werte, die die angeforderten Typen des Zugriffs auf das Threadtoken angeben.</span><span class="sxs-lookup"><span data-stu-id="ee071-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="ee071-107">Diese Werte werden definiert, in der Win32- `OpenThreadToken` Funktion.</span><span class="sxs-lookup"><span data-stu-id="ee071-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="ee071-108">Die angeforderten Zugriffstypen werden anhand des Tokens besitzerverwaltete Zugriffssteuerungsliste (DACL), um zu bestimmen, welche Arten des Zugriffs auf gewähren oder verweigern abgestimmt.</span><span class="sxs-lookup"><span data-stu-id="ee071-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="ee071-109">[in] `true` um anzugeben, dass die zugriffsprüfung mit den Sicherheitskontext des Prozesses für den aufrufenden Thread; gemacht werden sollen `false` um anzugeben, dass die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread selbst ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ee071-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="ee071-110">Wenn der Thread einen Client einen Identitätswechsel ausführt, kann der Sicherheitskontext, die von einem Clientprozess sein.</span><span class="sxs-lookup"><span data-stu-id="ee071-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="ee071-111">[out] Ein Zeiger auf das neu geöffnete Zugriffstoken.</span><span class="sxs-lookup"><span data-stu-id="ee071-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee071-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ee071-112">Return Value</span></span>  
  
|<span data-ttu-id="ee071-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee071-113">HRESULT</span></span>|<span data-ttu-id="ee071-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee071-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee071-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee071-115">S_OK</span></span>|`OpenThreadToken` <span data-ttu-id="ee071-116">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ee071-116">returned successfully.</span></span>|  
|<span data-ttu-id="ee071-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ee071-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ee071-118">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ee071-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ee071-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ee071-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ee071-120">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ee071-120">The call timed out.</span></span>|  
|<span data-ttu-id="ee071-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ee071-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ee071-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ee071-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ee071-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ee071-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ee071-124">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ee071-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ee071-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ee071-125">E_FAIL</span></span>|<span data-ttu-id="ee071-126">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ee071-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ee071-127">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee071-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ee071-128">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ee071-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee071-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee071-129">Remarks</span></span>  
 `IHostSecurityManager::OpenThreadToken` <span data-ttu-id="ee071-130">verhält sich ähnlich wie die entsprechenden Win32-Funktion mit dem gleichen Namen, mit dem Unterschied, dass die Win32-Funktion den Aufrufer übergibt ein Handle an einen beliebigen Thread ermöglicht, während `IHostSecurityManager::OpenThreadToken` öffnet nur das Token, die dem aufrufenden Thread zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ee071-130">behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="ee071-131">Die `HANDLE` Typ ist nicht in der COM-kompatibel, d. h. seine Größe ist spezifisch für das Betriebssystem und benutzerdefiniertes Marshalling erfordert.</span><span class="sxs-lookup"><span data-stu-id="ee071-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="ee071-132">Daher ist dieses Token für die Verwendung nur innerhalb des Prozesses, zwischen der CLR und dem Host ein.</span><span class="sxs-lookup"><span data-stu-id="ee071-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee071-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee071-133">Requirements</span></span>  
 <span data-ttu-id="ee071-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee071-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee071-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ee071-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee071-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ee071-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ee071-137">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ee071-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ee071-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee071-138">See also</span></span>

- [<span data-ttu-id="ee071-139">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee071-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="ee071-140">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee071-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
