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
ms.openlocfilehash: dd1d1af8072ac11e37bd2eb1a47d76b12685cb31
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724779"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="37c87-102">IHostSecurityManager::ImpersonateLoggedOnUser-Methode</span><span class="sxs-lookup"><span data-stu-id="37c87-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>

<span data-ttu-id="37c87-103">Fordert die Ausführung von Code mit den Anmelde Informationen der aktuellen Benutzeridentität an.</span><span class="sxs-lookup"><span data-stu-id="37c87-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37c87-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37c87-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37c87-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="37c87-105">Parameters</span></span>  

 `hToken`  
 <span data-ttu-id="37c87-106">in Ein Token, das die Anmelde Informationen des Benutzers darstellt, dessen Identität angenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="37c87-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37c87-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="37c87-107">Return Value</span></span>  
  
|<span data-ttu-id="37c87-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37c87-108">HRESULT</span></span>|<span data-ttu-id="37c87-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="37c87-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37c87-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="37c87-110">S_OK</span></span>|<span data-ttu-id="37c87-111">`ImpersonateLoggedOnUser` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37c87-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="37c87-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37c87-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37c87-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="37c87-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37c87-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37c87-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37c87-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="37c87-115">The call timed out.</span></span>|  
|<span data-ttu-id="37c87-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37c87-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37c87-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="37c87-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37c87-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37c87-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37c87-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="37c87-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37c87-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37c87-120">E_FAIL</span></span>|<span data-ttu-id="37c87-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="37c87-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37c87-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="37c87-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37c87-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="37c87-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37c87-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="37c87-124">Remarks</span></span>  

 <span data-ttu-id="37c87-125">Ruft `LogonUser` oder eine zugehörige Win32-Funktion auf, um ein Handle für die Anmelde Informationen der aktuellen Benutzeridentität zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="37c87-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="37c87-126">Der `HANDLE` Typ ist nicht com-kompatibel, d. h. seine Größe ist für ein betriebssystemspezifisch und erfordert ein benutzerdefiniertes Marshalling.</span><span class="sxs-lookup"><span data-stu-id="37c87-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="37c87-127">Daher ist dieses Token nur für die Verwendung innerhalb des Prozesses zwischen der CLR und dem Host vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="37c87-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37c87-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="37c87-128">Requirements</span></span>  

 <span data-ttu-id="37c87-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37c87-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37c87-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="37c87-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37c87-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="37c87-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37c87-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37c87-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37c87-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37c87-133">See also</span></span>

- [<span data-ttu-id="37c87-134">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37c87-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="37c87-135">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37c87-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="37c87-136">RevertToSelf-Methode</span><span class="sxs-lookup"><span data-stu-id="37c87-136">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)
