---
title: ICLROnEventManager::RegisterActionOnEvent-Methode
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c12e1fff4910458a17c09e482ba8ede9c1625c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434015"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="b417e-102">ICLROnEventManager::RegisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="b417e-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="b417e-103">Registriert einen Rückrufzeiger für das angegebene Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="b417e-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b417e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b417e-104">Syntax</span></span>  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b417e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b417e-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="b417e-106">[in] Eines der [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) Werte, der das Ereignis für die registriert des Rückrufzeigers beschriebenen `pAction`.</span><span class="sxs-lookup"><span data-stu-id="b417e-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="b417e-107">[in] Ein Zeiger auf ein [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) -Objekt, das aufgerufen wird, wenn das registrierte Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="b417e-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b417e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b417e-108">Return Value</span></span>  
  
|<span data-ttu-id="b417e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b417e-109">HRESULT</span></span>|<span data-ttu-id="b417e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b417e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b417e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b417e-111">S_OK</span></span>|<span data-ttu-id="b417e-112">`RegisterActionOnEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b417e-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="b417e-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="b417e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b417e-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b417e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b417e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b417e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b417e-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b417e-116">The call timed out.</span></span>|  
|<span data-ttu-id="b417e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b417e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b417e-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b417e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b417e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b417e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b417e-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="b417e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b417e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b417e-121">E_FAIL</span></span>|<span data-ttu-id="b417e-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b417e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b417e-123">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b417e-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b417e-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b417e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b417e-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b417e-125">Remarks</span></span>  
 <span data-ttu-id="b417e-126">Der Host kann Registrieren von Rückrufen für eine oder beide der zwei Ereignistypen beschrieben, die von `EClrEvent`.</span><span class="sxs-lookup"><span data-stu-id="b417e-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="b417e-127">Der Host Ruft ab die `ICLROnEventManager` Schnittstelle durch Aufrufen der [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b417e-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b417e-128">Die Ereignisse, die `RegisterActionOnEvent` Register können ausgelöst werden, mehr als einmal und von anderen Threads um ein Entladen oder das Deaktivieren der CLR zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="b417e-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b417e-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b417e-129">Requirements</span></span>  
 <span data-ttu-id="b417e-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b417e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b417e-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b417e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b417e-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b417e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b417e-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b417e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b417e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b417e-134">See Also</span></span>  
 [<span data-ttu-id="b417e-135">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b417e-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="b417e-136">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b417e-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="b417e-137">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b417e-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="b417e-138">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b417e-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
