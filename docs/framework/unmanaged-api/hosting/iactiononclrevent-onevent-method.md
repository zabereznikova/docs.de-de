---
title: IActionOnCLREvent::OnEvent-Methode
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e7045d3b095b6a35be8b55e1066b459e9583c93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970234"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="af10f-102">IActionOnCLREvent::OnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="af10f-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="af10f-103">Führt Rückrufe für Ereignisse, die mit einem Aufruf von registriert wurden die [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="af10f-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af10f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af10f-104">Syntax</span></span>  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af10f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af10f-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="af10f-106">[in] Eines der [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) Werte, die den Typ des Ereignisses angibt.</span><span class="sxs-lookup"><span data-stu-id="af10f-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="af10f-107">[in] Ein Zeiger auf ein Objekt, das Details zum enthält `event`.</span><span class="sxs-lookup"><span data-stu-id="af10f-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af10f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="af10f-108">Return Value</span></span>  
  
|<span data-ttu-id="af10f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af10f-109">HRESULT</span></span>|<span data-ttu-id="af10f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af10f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af10f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="af10f-111">S_OK</span></span>|<span data-ttu-id="af10f-112">`OnEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="af10f-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="af10f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="af10f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="af10f-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="af10f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="af10f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="af10f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="af10f-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="af10f-116">The call timed out.</span></span>|  
|<span data-ttu-id="af10f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="af10f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="af10f-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="af10f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="af10f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="af10f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="af10f-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="af10f-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="af10f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="af10f-121">E_FAIL</span></span>|<span data-ttu-id="af10f-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="af10f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="af10f-123">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af10f-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="af10f-124">Nachfolgende Aufrufe von jedem hostingmethode HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="af10f-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af10f-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af10f-125">Remarks</span></span>  
 <span data-ttu-id="af10f-126">Die `data` Parameter ist ein Zeiger auf ein Objekt vom nicht angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="af10f-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="af10f-127">Wenn die `event` Parameter `Event_DomainUnload`, `data` ist der numerische Bezeichner für die <xref:System.AppDomain> , die entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="af10f-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="af10f-128">Der Host kann es sich um entsprechende Maßnahmen, die mit diesem Bezeichner als ein Schlüssel dauern.</span><span class="sxs-lookup"><span data-stu-id="af10f-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="af10f-129">Wenn `event` ist `Event_MDAFired`, `data` ist ein Zeiger auf ein [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) -Instanz, die die Ausgabe der Nachricht aus einer verwalteten Debugging-Assistenten (MDA) enthält.</span><span class="sxs-lookup"><span data-stu-id="af10f-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="af10f-130">MDAs sind ein Feature von der CLR, mit deren Hilfe Entwickler beim Debuggen, durch Generieren von XML-Nachrichten über Ereignisse, die andernfalls nur schwer abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="af10f-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="af10f-131">Diese Nachrichten können besonders hilfreich beim Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code sein.</span><span class="sxs-lookup"><span data-stu-id="af10f-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="af10f-132">Weitere Informationen finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="af10f-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af10f-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af10f-133">Requirements</span></span>  
 <span data-ttu-id="af10f-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af10f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af10f-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af10f-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af10f-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="af10f-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af10f-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af10f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af10f-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af10f-138">See also</span></span>

- [<span data-ttu-id="af10f-139">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="af10f-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="af10f-140">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="af10f-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="af10f-141">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af10f-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="af10f-142">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af10f-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="af10f-143">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af10f-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="af10f-144">MDAInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="af10f-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
