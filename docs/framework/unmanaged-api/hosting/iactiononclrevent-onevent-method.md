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
ms.openlocfilehash: bbf5e299285071ba6d43fd2c40fc724d19bc7b2a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504354"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="84946-102">IActionOnCLREvent::OnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="84946-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="84946-103">Führt Rückrufe für Ereignisse aus, die mit einem Aufruf der [ICLROnEventManager:: registeraktiononevent](iclroneventmanager-registeractiononevent-method.md) -Methode registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="84946-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84946-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84946-104">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84946-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84946-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="84946-106">in Einer der [EClrEvent](eclrevent-enumeration.md) -Werte, der den Ereignistyp angibt.</span><span class="sxs-lookup"><span data-stu-id="84946-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="84946-107">in Ein Zeiger auf ein Objekt, das Details zu enthält `event` .</span><span class="sxs-lookup"><span data-stu-id="84946-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84946-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84946-108">Return Value</span></span>  
  
|<span data-ttu-id="84946-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84946-109">HRESULT</span></span>|<span data-ttu-id="84946-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="84946-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84946-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="84946-111">S_OK</span></span>|<span data-ttu-id="84946-112">`OnEvent`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="84946-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="84946-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84946-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84946-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="84946-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84946-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84946-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84946-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="84946-116">The call timed out.</span></span>|  
|<span data-ttu-id="84946-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84946-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84946-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="84946-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84946-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84946-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84946-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="84946-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84946-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84946-121">E_FAIL</span></span>|<span data-ttu-id="84946-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="84946-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84946-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="84946-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84946-124">Nachfolgende Aufrufe einer beliebigen Hostingmethode geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="84946-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84946-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="84946-125">Remarks</span></span>  
 <span data-ttu-id="84946-126">Der- `data` Parameter ist ein Zeiger auf ein Objekt des nicht angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="84946-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="84946-127">Wenn der- `event` Parameter ist `Event_DomainUnload` , `data` ist der numerische Bezeichner für das <xref:System.AppDomain> , das entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="84946-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="84946-128">Der Host kann mithilfe dieses Bezeichners als Schlüssel geeignete Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="84946-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="84946-129">Wenn `event` ist `Event_MDAFired` , `data` ist ein Zeiger auf eine [MDAInfo](mdainfo-structure.md) -Instanz, die die Nachrichten Ausgabe eines Assistenten für verwaltetes Debuggen (MDA) enthält.</span><span class="sxs-lookup"><span data-stu-id="84946-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="84946-130">MDAs sind eine Funktion der CLR, die Entwickler beim Debuggen unterstützt, indem XML-Meldungen zu Ereignissen erzeugt werden, die andernfalls schwierig zu Trap laufen sind.</span><span class="sxs-lookup"><span data-stu-id="84946-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="84946-131">Solche Nachrichten können besonders beim Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="84946-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="84946-132">Weitere Informationen finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="84946-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84946-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="84946-133">Requirements</span></span>  
 <span data-ttu-id="84946-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84946-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84946-135">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="84946-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84946-136">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="84946-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84946-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84946-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84946-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84946-138">See also</span></span>

- [<span data-ttu-id="84946-139">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="84946-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="84946-140">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="84946-140">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="84946-141">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84946-141">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="84946-142">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84946-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="84946-143">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84946-143">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="84946-144">MDAInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="84946-144">MDAInfo Structure</span></span>](mdainfo-structure.md)
