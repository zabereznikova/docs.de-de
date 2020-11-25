---
title: IHostTaskManager::EndDelayAbort-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
ms.openlocfilehash: 6add3cf4d83796b2d95de46cb64f5880a835b6ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731669"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="5f679-102">IHostTaskManager::EndDelayAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="5f679-102">IHostTaskManager::EndDelayAbort Method</span></span>

<span data-ttu-id="5f679-103">Benachrichtigt den Host, dass verwalteter Code den Zeitraum, in dem die aktuelle Aufgabe nicht abgebrochen werden darf, nach einem früheren Aufrufen von [IHostTaskManager:: begindelta ayabort](ihosttaskmanager-begindelayabort-method.md)verlässt.</span><span class="sxs-lookup"><span data-stu-id="5f679-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f679-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f679-104">Syntax</span></span>  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5f679-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5f679-105">Return Value</span></span>  
  
|<span data-ttu-id="5f679-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f679-106">HRESULT</span></span>|<span data-ttu-id="5f679-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5f679-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f679-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f679-108">S_OK</span></span>|<span data-ttu-id="5f679-109">`EndDelayAbort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5f679-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="5f679-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5f679-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5f679-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5f679-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5f679-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5f679-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5f679-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="5f679-113">The call timed out.</span></span>|  
|<span data-ttu-id="5f679-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5f679-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5f679-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="5f679-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5f679-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5f679-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5f679-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="5f679-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5f679-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5f679-118">E_FAIL</span></span>|<span data-ttu-id="5f679-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5f679-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5f679-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="5f679-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5f679-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5f679-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5f679-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="5f679-122">E_UNEXPECTED</span></span>|<span data-ttu-id="5f679-123">`EndDelayAbort` wurde aufgerufen, ohne dass ein entsprechender Aufruf von aufgerufen wurde `BeginDelayAbort` .</span><span class="sxs-lookup"><span data-stu-id="5f679-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f679-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f679-124">Remarks</span></span>  

 <span data-ttu-id="5f679-125">Die CLR führt einen entsprechenden Aufruf `BeginDelayAbort` von für die aktuelle Aufgabe aus, bevor aufgerufen wird `EndDelayAbort` .</span><span class="sxs-lookup"><span data-stu-id="5f679-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="5f679-126">Wenn kein solcher entsprechender-Befehl vorhanden ist, sollte die [IHostTaskManager](ihosttaskmanager-interface.md) -Implementierung des Hosts E_UNEXPECTED von zurückgeben `EndDelayAbort` und keine Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="5f679-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f679-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5f679-127">Requirements</span></span>  

 <span data-ttu-id="5f679-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f679-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f679-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5f679-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f679-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5f679-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f679-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f679-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f679-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f679-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="5f679-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f679-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5f679-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f679-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5f679-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f679-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5f679-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f679-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
