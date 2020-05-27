---
title: IHostTaskManager::EndThreadAffinity-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
ms.openlocfilehash: 2e857f951a837e1385d02dfc810fc12cfefd0d2b
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841957"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="7a4e6-102">IHostTaskManager::EndThreadAffinity-Methode</span><span class="sxs-lookup"><span data-stu-id="7a4e6-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="7a4e6-103">Benachrichtigt den Host, dass verwalteter Code den Zeitraum verlässt, in dem die aktuelle Aufgabe nach einem früheren [IHostTaskManager:: beginthreadaffinität](ihosttaskmanager-beginthreadaffinity-method.md)nicht in einen anderen Betriebssystem Thread verschoben werden darf.</span><span class="sxs-lookup"><span data-stu-id="7a4e6-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a4e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a4e6-104">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7a4e6-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7a4e6-105">Return Value</span></span>  
  
|<span data-ttu-id="7a4e6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a4e6-106">HRESULT</span></span>|<span data-ttu-id="7a4e6-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7a4e6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a4e6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a4e6-108">S_OK</span></span>|<span data-ttu-id="7a4e6-109">`EndThreadAffinity`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7a4e6-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="7a4e6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7a4e6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7a4e6-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7a4e6-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7a4e6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7a4e6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7a4e6-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7a4e6-113">The call timed out.</span></span>|  
|<span data-ttu-id="7a4e6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a4e6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7a4e6-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7a4e6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7a4e6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7a4e6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7a4e6-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7a4e6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7a4e6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a4e6-118">E_FAIL</span></span>|<span data-ttu-id="7a4e6-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7a4e6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a4e6-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="7a4e6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7a4e6-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7a4e6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7a4e6-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="7a4e6-122">E_UNEXPECTED</span></span>|<span data-ttu-id="7a4e6-123">`EndThreadAffinity`wurde ohne einen früheren Aufruf von aufgerufen `BeginThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="7a4e6-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a4e6-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a4e6-124">Remarks</span></span>  
 <span data-ttu-id="7a4e6-125">Die CLR führt einen entsprechenden Aufruf `BeginThreadAffinity` von für die aktuelle Aufgabe aus, bevor aufgerufen wird `EndThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="7a4e6-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="7a4e6-126">Wenn kein solcher entsprechender-Befehl vorhanden ist, sollte die [IHostTaskManager](ihosttaskmanager-interface.md) -Implementierung des Hosts E_UNEXPECTED zurückgeben und keine Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="7a4e6-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a4e6-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a4e6-127">Requirements</span></span>  
 <span data-ttu-id="7a4e6-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a4e6-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a4e6-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7a4e6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a4e6-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7a4e6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a4e6-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a4e6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a4e6-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a4e6-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="7a4e6-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a4e6-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="7a4e6-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a4e6-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="7a4e6-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a4e6-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="7a4e6-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a4e6-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
