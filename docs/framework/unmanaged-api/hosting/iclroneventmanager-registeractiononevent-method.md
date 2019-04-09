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
ms.openlocfilehash: 68a8493a9eb5177844e81ef7a9612f979ffe89c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216495"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="63265-102">ICLROnEventManager::RegisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="63265-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="63265-103">Registriert einen Rückrufzeiger für das angegebene Ereignis.</span><span class="sxs-lookup"><span data-stu-id="63265-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63265-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63265-104">Syntax</span></span>  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63265-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="63265-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="63265-106">[in] Eines der [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) Werte, der das Ereignis für die Sie registrieren den Rückrufzeiger beschriebenen `pAction`.</span><span class="sxs-lookup"><span data-stu-id="63265-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="63265-107">[in] Ein Zeiger auf ein [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) -Objekt, das aufgerufen wird, wenn das registrierte Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="63265-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63265-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="63265-108">Return Value</span></span>  
  
|<span data-ttu-id="63265-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63265-109">HRESULT</span></span>|<span data-ttu-id="63265-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="63265-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63265-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="63265-111">S_OK</span></span>|`RegisterActionOnEvent` <span data-ttu-id="63265-112">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63265-112">returned successfully.</span></span>|  
|<span data-ttu-id="63265-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63265-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63265-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="63265-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63265-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63265-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63265-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="63265-116">The call timed out.</span></span>|  
|<span data-ttu-id="63265-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63265-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63265-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="63265-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63265-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63265-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63265-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="63265-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63265-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63265-121">E_FAIL</span></span>|<span data-ttu-id="63265-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="63265-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63265-123">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="63265-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="63265-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="63265-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63265-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="63265-125">Remarks</span></span>  
 <span data-ttu-id="63265-126">Der Host kann Registrieren von Rückrufen für eine oder beide der zwei Ereignistypen beschrieben `EClrEvent`.</span><span class="sxs-lookup"><span data-stu-id="63265-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="63265-127">Der Host Ruft ab die `ICLROnEventManager` Schnittstelle durch Aufrufen der [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="63265-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63265-128">Die Ereignisse, die `RegisterActionOnEvent` Register können ausgelöst werden, mehr als einmal und von verschiedenen Threads ein Entladen oder das Deaktivieren der CLR signalisiert.</span><span class="sxs-lookup"><span data-stu-id="63265-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63265-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63265-129">Requirements</span></span>  
 <span data-ttu-id="63265-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63265-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63265-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63265-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63265-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="63265-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="63265-133">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="63265-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63265-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63265-134">See also</span></span>

- [<span data-ttu-id="63265-135">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="63265-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="63265-136">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63265-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="63265-137">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63265-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="63265-138">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63265-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
