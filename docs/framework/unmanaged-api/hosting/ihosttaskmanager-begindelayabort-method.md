---
title: IHostTaskManager::BeginDelayAbort-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
ms.openlocfilehash: f72cc15904d098e159dd7f75f673d43ae987998d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727327"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="c361d-102">IHostTaskManager::BeginDelayAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="c361d-102">IHostTaskManager::BeginDelayAbort Method</span></span>

<span data-ttu-id="c361d-103">Benachrichtigt den Host, dass verwalteter Code in einen Zeitraum wechselt, in dem die aktuelle Aufgabe nicht abgebrochen werden darf.</span><span class="sxs-lookup"><span data-stu-id="c361d-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c361d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c361d-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c361d-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c361d-105">Return Value</span></span>  
  
|<span data-ttu-id="c361d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c361d-106">HRESULT</span></span>|<span data-ttu-id="c361d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c361d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c361d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c361d-108">S_OK</span></span>|<span data-ttu-id="c361d-109">`BeginDelayAbort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c361d-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="c361d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c361d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c361d-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c361d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c361d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c361d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c361d-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c361d-113">The call timed out.</span></span>|  
|<span data-ttu-id="c361d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c361d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c361d-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c361d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c361d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c361d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c361d-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c361d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c361d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c361d-118">E_FAIL</span></span>|<span data-ttu-id="c361d-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c361d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c361d-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c361d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c361d-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c361d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c361d-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="c361d-122">E_UNEXPECTED</span></span>|<span data-ttu-id="c361d-123">`BeginDelayAbort` wurde bereits aufgerufen, aber der entsprechende Aufruf von [enddelta-Abort](ihosttaskmanager-enddelayabort-method.md) wurde noch nicht empfangen.</span><span class="sxs-lookup"><span data-stu-id="c361d-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c361d-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c361d-124">Remarks</span></span>  

 <span data-ttu-id="c361d-125">Der Host muss die aktuelle Aufgabe erst abbrechen, wenn `EndDelayAbort` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c361d-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="c361d-126">Wenn ein anderer-Vorgang `BeginDelayAbort` ohne einen dazwischen liegenden-Aufrufvorgang durchgeführt wird `EndDelayAbort` , sollte der Host E_UNEXPECTED von zurückgeben `BeginDelayAbort` und keine Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="c361d-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c361d-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c361d-127">Requirements</span></span>  

 <span data-ttu-id="c361d-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c361d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c361d-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c361d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c361d-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c361d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c361d-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c361d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c361d-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c361d-132">See also</span></span>

- [<span data-ttu-id="c361d-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c361d-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c361d-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c361d-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c361d-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c361d-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
