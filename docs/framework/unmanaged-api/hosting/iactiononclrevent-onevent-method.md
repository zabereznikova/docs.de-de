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
ms.openlocfilehash: 28178cca27c257e480a7c5ec87c1925af7de4f78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436415"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="ff548-102">IActionOnCLREvent::OnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="ff548-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="ff548-103">Führt Rückrufe für Ereignisse, die registriert wurden, mithilfe eines Aufrufs an die [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="ff548-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff548-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff548-104">Syntax</span></span>  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff548-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff548-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="ff548-106">[in] Eines der [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) Werte, die den Typ des Ereignisses angibt.</span><span class="sxs-lookup"><span data-stu-id="ff548-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="ff548-107">[in] Ein Zeiger auf ein Objekt, das Details zum enthält `event`.</span><span class="sxs-lookup"><span data-stu-id="ff548-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff548-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ff548-108">Return Value</span></span>  
  
|<span data-ttu-id="ff548-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff548-109">HRESULT</span></span>|<span data-ttu-id="ff548-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff548-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff548-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff548-111">S_OK</span></span>|<span data-ttu-id="ff548-112">`OnEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ff548-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="ff548-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ff548-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ff548-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ff548-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ff548-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ff548-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ff548-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ff548-116">The call timed out.</span></span>|  
|<span data-ttu-id="ff548-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff548-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ff548-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ff548-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ff548-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ff548-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ff548-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ff548-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ff548-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ff548-121">E_FAIL</span></span>|<span data-ttu-id="ff548-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ff548-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ff548-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ff548-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ff548-124">Nachfolgende Aufrufe von einer beliebigen Hostmethode HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ff548-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff548-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff548-125">Remarks</span></span>  
 <span data-ttu-id="ff548-126">Die `data` Parameter ist ein Zeiger auf ein Objekt vom angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="ff548-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="ff548-127">Wenn die `event` Parameter ist `Event_DomainUnload`, `data` wird von der numerische Bezeichner für die <xref:System.AppDomain> entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ff548-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="ff548-128">Der Host kann mit diesem Bezeichner als Schlüssel eine geeignete Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="ff548-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="ff548-129">Wenn `event` ist `Event_MDAFired`, `data` ist ein Zeiger auf ein [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) Instanz, die die Meldungsausgabe aus einer verwalteten Debugging-Assistent (MDA) enthält.</span><span class="sxs-lookup"><span data-stu-id="ff548-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="ff548-130">MDAs sind eine Funktion der CLR, mit deren Hilfe Entwickler beim Debuggen, durch Generieren von XML-Nachrichten zu Ereignissen, die andernfalls schwer abfangen.</span><span class="sxs-lookup"><span data-stu-id="ff548-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="ff548-131">Solche Nachrichten können vor allem hilfreich bei Übergängen zwischen verwaltetem und nicht verwaltetem Code zu debuggen sein.</span><span class="sxs-lookup"><span data-stu-id="ff548-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="ff548-132">Weitere Informationen finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="ff548-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff548-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff548-133">Requirements</span></span>  
 <span data-ttu-id="ff548-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff548-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff548-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ff548-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff548-136">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ff548-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff548-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff548-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff548-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff548-138">See Also</span></span>  
 [<span data-ttu-id="ff548-139">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="ff548-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="ff548-140">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ff548-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="ff548-141">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff548-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="ff548-142">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff548-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="ff548-143">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff548-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="ff548-144">MDAInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="ff548-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
