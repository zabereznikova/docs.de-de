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
ms.openlocfilehash: ea3269d06fdd3f5a2e365465d45ba6e569127b0a
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842373"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="3f0eb-102">IHostTaskManager::BeginDelayAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="3f0eb-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="3f0eb-103">Benachrichtigt den Host, dass verwalteter Code in einen Zeitraum wechselt, in dem die aktuelle Aufgabe nicht abgebrochen werden darf.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f0eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f0eb-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3f0eb-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3f0eb-105">Return Value</span></span>  
  
|<span data-ttu-id="3f0eb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f0eb-106">HRESULT</span></span>|<span data-ttu-id="3f0eb-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3f0eb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f0eb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f0eb-108">S_OK</span></span>|<span data-ttu-id="3f0eb-109">`BeginDelayAbort`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="3f0eb-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3f0eb-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3f0eb-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3f0eb-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3f0eb-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3f0eb-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-113">The call timed out.</span></span>|  
|<span data-ttu-id="3f0eb-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f0eb-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3f0eb-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3f0eb-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3f0eb-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3f0eb-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3f0eb-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3f0eb-118">E_FAIL</span></span>|<span data-ttu-id="3f0eb-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3f0eb-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3f0eb-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3f0eb-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="3f0eb-122">E_UNEXPECTED</span></span>|<span data-ttu-id="3f0eb-123">`BeginDelayAbort`wurde bereits aufgerufen, aber der entsprechende Aufruf von [enddelta-Abort](ihosttaskmanager-enddelayabort-method.md) wurde noch nicht empfangen.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f0eb-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f0eb-124">Remarks</span></span>  
 <span data-ttu-id="3f0eb-125">Der Host muss die aktuelle Aufgabe erst abbrechen, wenn `EndDelayAbort` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="3f0eb-126">Wenn ein anderer-Vorgang `BeginDelayAbort` ohne einen dazwischen liegenden-Aufrufvorgang durchgeführt wird `EndDelayAbort` , sollte der Host E_UNEXPECTED von zurückgeben `BeginDelayAbort` und keine Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="3f0eb-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f0eb-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3f0eb-127">Requirements</span></span>  
 <span data-ttu-id="3f0eb-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f0eb-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f0eb-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="3f0eb-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f0eb-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3f0eb-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f0eb-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f0eb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0eb-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f0eb-132">See also</span></span>

- [<span data-ttu-id="3f0eb-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f0eb-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="3f0eb-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f0eb-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="3f0eb-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f0eb-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
