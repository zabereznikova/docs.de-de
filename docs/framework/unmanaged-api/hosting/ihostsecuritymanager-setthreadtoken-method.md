---
title: IHostSecurityManager::SetThreadToken-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c67471c0d88ccffbfe9b7c77809124452ccc2e5b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208071"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="d6959-102">IHostSecurityManager::SetThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="d6959-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="d6959-103">Legt einen Handle für den aktuell ausgeführten Thread fest.</span><span class="sxs-lookup"><span data-stu-id="d6959-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6959-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6959-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6959-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6959-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="d6959-106">[in] Ein Handle für das Token für den aktuell ausgeführten Thread festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d6959-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6959-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d6959-107">Return Value</span></span>  
  
|<span data-ttu-id="d6959-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6959-108">HRESULT</span></span>|<span data-ttu-id="d6959-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6959-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d6959-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d6959-110">S_OK</span></span>|`SetThreadToken` <span data-ttu-id="d6959-111">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6959-111">returned successfully.</span></span>|  
|<span data-ttu-id="d6959-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d6959-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d6959-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d6959-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d6959-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d6959-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d6959-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d6959-115">The call timed out.</span></span>|  
|<span data-ttu-id="d6959-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d6959-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d6959-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d6959-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d6959-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d6959-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d6959-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d6959-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d6959-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d6959-120">E_FAIL</span></span>|<span data-ttu-id="d6959-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d6959-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d6959-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6959-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d6959-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d6959-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6959-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6959-124">Remarks</span></span>  
 `IHostSecurityManager::SetThreadToken` <span data-ttu-id="d6959-125">verhält sich ähnlich wie die entsprechenden Win32-Funktion mit dem gleichen Namen, mit dem Unterschied, dass die Win32-Funktion den Aufrufer übergibt ein Handle an einen beliebigen Thread ermöglicht, während `IHostSecurityManager::SetThreadToken` können ein Token nur mit dem aktuell ausgeführten Thread zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d6959-125">behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="d6959-126">Die `HANDLE` Typ ist nicht in der COM-kompatibel; d. h. seine Größe ist spezifisch für ein Betriebssystem installiert ist und benutzerdefiniertes Marshalling erfordert.</span><span class="sxs-lookup"><span data-stu-id="d6959-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="d6959-127">Daher ist dieses Token für die Verwendung nur innerhalb des Prozesses, zwischen der CLR und dem Host ein.</span><span class="sxs-lookup"><span data-stu-id="d6959-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6959-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d6959-128">Requirements</span></span>  
 <span data-ttu-id="d6959-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6959-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6959-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d6959-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d6959-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d6959-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d6959-132">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d6959-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d6959-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6959-133">See also</span></span>

- [<span data-ttu-id="d6959-134">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d6959-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="d6959-135">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d6959-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
