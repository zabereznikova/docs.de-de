---
title: IHostSecurityManager::RevertToSelf-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
ms.openlocfilehash: 456553e4cb5a6c6a557b5c3ac677fad12a5798bf
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803832"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="54bd1-102">IHostSecurityManager::RevertToSelf-Methode</span><span class="sxs-lookup"><span data-stu-id="54bd1-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="54bd1-103">Beendet den Identitätswechsel der aktuellen Benutzeridentität und gibt das ursprüngliche Thread Token zurück.</span><span class="sxs-lookup"><span data-stu-id="54bd1-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54bd1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="54bd1-104">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="54bd1-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="54bd1-105">Return Value</span></span>  
  
|<span data-ttu-id="54bd1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="54bd1-106">HRESULT</span></span>|<span data-ttu-id="54bd1-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="54bd1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54bd1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="54bd1-108">S_OK</span></span>|<span data-ttu-id="54bd1-109">`RevertToSelf`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="54bd1-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="54bd1-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="54bd1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="54bd1-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="54bd1-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="54bd1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="54bd1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="54bd1-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="54bd1-113">The call timed out.</span></span>|  
|<span data-ttu-id="54bd1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="54bd1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="54bd1-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="54bd1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="54bd1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="54bd1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="54bd1-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="54bd1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="54bd1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="54bd1-118">E_FAIL</span></span>|<span data-ttu-id="54bd1-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="54bd1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="54bd1-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="54bd1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="54bd1-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="54bd1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54bd1-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54bd1-122">Remarks</span></span>  
 <span data-ttu-id="54bd1-123">`RevertToSelf`wird aufgerufen, um nach einem früheren Aufruf der Identität [ateloggedonuser](ihostsecuritymanager-impersonateloggedonuser-method.md) -Methode zum ursprünglichen Thread Token zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="54bd1-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54bd1-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="54bd1-124">Requirements</span></span>  
 <span data-ttu-id="54bd1-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54bd1-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54bd1-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="54bd1-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54bd1-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="54bd1-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54bd1-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54bd1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54bd1-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54bd1-129">See also</span></span>

- [<span data-ttu-id="54bd1-130">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="54bd1-130">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="54bd1-131">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="54bd1-131">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="54bd1-132">ImpersonateLoggedOnUser-Methode</span><span class="sxs-lookup"><span data-stu-id="54bd1-132">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)
