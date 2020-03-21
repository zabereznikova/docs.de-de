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
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176265"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="974b5-102">IHostSecurityManager::OpenThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="974b5-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="974b5-103">Öffnet das diskretionäre Zugriffstoken, das dem aktuell ausgeführten Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="974b5-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="974b5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="974b5-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="974b5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="974b5-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="974b5-106">[in] Eine Maske von Zugriffswerten, die die angeforderten Zugriffstypen für das Threadtoken angeben.</span><span class="sxs-lookup"><span data-stu-id="974b5-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="974b5-107">Diese Werte werden in der `OpenThreadToken` Win32-Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="974b5-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="974b5-108">Die angeforderten Zugriffstypen werden mit der DACL (Discretionary Access Control List) des Tokens abgeglichen, um zu bestimmen, welche Zugriffstypen gewährt oder verweigert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="974b5-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="974b5-109">[in] `true` angabe, ob die Zugriffsüberprüfung mithilfe des Sicherheitskontexts des Prozesses für den aufrufenden Thread erfolgen soll; `false` , um anzugeben, dass die Zugriffsüberprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread selbst durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="974b5-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="974b5-110">Wenn der Thread die Identität eines Clients annimmt, kann der Sicherheitskontext der eines Clientprozesses sein.</span><span class="sxs-lookup"><span data-stu-id="974b5-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="974b5-111">[out] Ein Zeiger auf das neu geöffnete Zugriffstoken.</span><span class="sxs-lookup"><span data-stu-id="974b5-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="974b5-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="974b5-112">Return Value</span></span>  
  
|<span data-ttu-id="974b5-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="974b5-113">HRESULT</span></span>|<span data-ttu-id="974b5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="974b5-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="974b5-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="974b5-115">S_OK</span></span>|<span data-ttu-id="974b5-116">`OpenThreadToken`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="974b5-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="974b5-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="974b5-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="974b5-118">Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="974b5-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="974b5-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="974b5-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="974b5-120">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="974b5-120">The call timed out.</span></span>|  
|<span data-ttu-id="974b5-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="974b5-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="974b5-122">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="974b5-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="974b5-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="974b5-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="974b5-124">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="974b5-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="974b5-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="974b5-125">E_FAIL</span></span>|<span data-ttu-id="974b5-126">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="974b5-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="974b5-127">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="974b5-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="974b5-128">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="974b5-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="974b5-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="974b5-129">Remarks</span></span>  
 <span data-ttu-id="974b5-130">`IHostSecurityManager::OpenThreadToken`verhält sich ähnlich wie die entsprechende Win32-Funktion mit demselben Namen, mit der Ausnahme, dass die Win32-Funktion dem Aufrufer erlaubt, ein Handle an einen beliebigen Thread zu übergeben, während `IHostSecurityManager::OpenThreadToken` nur das Token geöffnet wird, das dem aufrufenden Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="974b5-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="974b5-131">Der `HANDLE` Typ ist nicht COM-kompatibel, d. h. seine Größe ist systemspezifisch und erfordert ein benutzerdefiniertes Marshalling.</span><span class="sxs-lookup"><span data-stu-id="974b5-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="974b5-132">Daher ist dieses Token nur für die Verwendung innerhalb des Prozesses zwischen der CLR und dem Host.</span><span class="sxs-lookup"><span data-stu-id="974b5-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="974b5-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="974b5-133">Requirements</span></span>  
 <span data-ttu-id="974b5-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="974b5-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="974b5-135">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="974b5-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="974b5-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="974b5-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="974b5-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="974b5-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="974b5-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="974b5-138">See also</span></span>

- [<span data-ttu-id="974b5-139">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="974b5-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="974b5-140">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="974b5-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
