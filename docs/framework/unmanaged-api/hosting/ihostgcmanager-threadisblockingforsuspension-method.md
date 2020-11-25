---
title: IHostGCManager::ThreadIsBlockingForSuspension-Methode
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
ms.openlocfilehash: 9120085f6a241bcda04946a843799987bf82bb84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723882"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="483a7-102">IHostGCManager::ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="483a7-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>

<span data-ttu-id="483a7-103">Benachrichtigt den Host, dass der Thread, von dem der Methoden aufrufging, für eine Garbage Collection blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="483a7-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="483a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="483a7-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="483a7-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="483a7-105">Return Value</span></span>  
  
|<span data-ttu-id="483a7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="483a7-106">HRESULT</span></span>|<span data-ttu-id="483a7-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="483a7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="483a7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="483a7-108">S_OK</span></span>|<span data-ttu-id="483a7-109">`ThreadIsBlockingForSuspension` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="483a7-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="483a7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="483a7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="483a7-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="483a7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="483a7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="483a7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="483a7-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="483a7-113">The call timed out.</span></span>|  
|<span data-ttu-id="483a7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="483a7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="483a7-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="483a7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="483a7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="483a7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="483a7-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="483a7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="483a7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="483a7-118">E_FAIL</span></span>|<span data-ttu-id="483a7-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="483a7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="483a7-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="483a7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="483a7-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="483a7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="483a7-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="483a7-122">Remarks</span></span>  

 <span data-ttu-id="483a7-123">Die CLR ruft die- `ThreadIsBlockForSuspension` Methode in der Regel als Vorbereitung für eine Garbage Collection auf, um dem Host die Möglichkeit zu geben, den Thread für nicht verwaltete Aufgaben neu zu planen.</span><span class="sxs-lookup"><span data-stu-id="483a7-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="483a7-124">Der Host kann Aufgaben erst nach einem-Rückruf neu planen `ThreadIsBlockingForSuspension` .</span><span class="sxs-lookup"><span data-stu-id="483a7-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="483a7-125">Nach dem Aufruf von [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md)durch die Laufzeit darf der Host eine Aufgabe nicht neu planen.</span><span class="sxs-lookup"><span data-stu-id="483a7-125">After the runtime calls [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="483a7-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="483a7-126">Requirements</span></span>  

 <span data-ttu-id="483a7-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="483a7-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="483a7-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="483a7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="483a7-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="483a7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="483a7-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="483a7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="483a7-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="483a7-131">See also</span></span>

- [<span data-ttu-id="483a7-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="483a7-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="483a7-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="483a7-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="483a7-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="483a7-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="483a7-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="483a7-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="483a7-136">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="483a7-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
