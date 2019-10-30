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
ms.openlocfilehash: 98807717fc913052dae15f9f3cbd462d4f537ad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126921"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="9ac38-102">IActionOnCLREvent::OnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="9ac38-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="9ac38-103">Führt Rückrufe für Ereignisse aus, die mit einem Aufruf der [ICLROnEventManager:: registeraktiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) -Methode registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="9ac38-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac38-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ac38-104">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ac38-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ac38-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="9ac38-106">in Einer der [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) -Werte, der den Ereignistyp angibt.</span><span class="sxs-lookup"><span data-stu-id="9ac38-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="9ac38-107">in Ein Zeiger auf ein Objekt, das Details über `event`enthält.</span><span class="sxs-lookup"><span data-stu-id="9ac38-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ac38-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9ac38-108">Return Value</span></span>  
  
|<span data-ttu-id="9ac38-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ac38-109">HRESULT</span></span>|<span data-ttu-id="9ac38-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ac38-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ac38-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ac38-111">S_OK</span></span>|<span data-ttu-id="9ac38-112">`OnEvent` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9ac38-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="9ac38-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ac38-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ac38-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="9ac38-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ac38-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ac38-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ac38-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="9ac38-116">The call timed out.</span></span>|  
|<span data-ttu-id="9ac38-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ac38-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ac38-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9ac38-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ac38-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ac38-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ac38-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="9ac38-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ac38-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ac38-121">E_FAIL</span></span>|<span data-ttu-id="9ac38-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9ac38-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ac38-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ac38-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ac38-124">Nachfolgende Aufrufe einer beliebigen Hostingmethode geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9ac38-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ac38-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ac38-125">Remarks</span></span>  
 <span data-ttu-id="9ac38-126">Der `data`-Parameter ist ein Zeiger auf ein Objekt des nicht angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="9ac38-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="9ac38-127">Wenn der `event`-Parameter `Event_DomainUnload`ist, ist `data` der numerische Bezeichner für die entladene <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="9ac38-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="9ac38-128">Der Host kann mithilfe dieses Bezeichners als Schlüssel geeignete Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="9ac38-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="9ac38-129">Wenn `event` `Event_MDAFired`ist, ist `data` ein Zeiger auf eine [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) -Instanz, die die Nachrichten Ausgabe eines Assistenten für verwaltetes Debuggen (MDA) enthält.</span><span class="sxs-lookup"><span data-stu-id="9ac38-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="9ac38-130">MDAs sind eine Funktion der CLR, die Entwickler beim Debuggen unterstützt, indem XML-Meldungen zu Ereignissen erzeugt werden, die andernfalls schwierig zu Trap laufen sind.</span><span class="sxs-lookup"><span data-stu-id="9ac38-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="9ac38-131">Solche Nachrichten können besonders beim Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="9ac38-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="9ac38-132">Weitere Informationen finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="9ac38-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ac38-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ac38-133">Requirements</span></span>  
 <span data-ttu-id="9ac38-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ac38-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ac38-135">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9ac38-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ac38-136">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9ac38-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ac38-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ac38-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac38-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ac38-138">See also</span></span>

- [<span data-ttu-id="9ac38-139">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="9ac38-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="9ac38-140">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9ac38-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="9ac38-141">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ac38-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="9ac38-142">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ac38-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9ac38-143">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ac38-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="9ac38-144">MDAInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="9ac38-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
