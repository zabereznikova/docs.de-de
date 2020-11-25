---
title: IHostTask::Join-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
ms.openlocfilehash: 37156b03b184d06e0c7b03d7d7a9a018793bbb98
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721633"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="14fbf-102">IHostTask::Join-Methode</span><span class="sxs-lookup"><span data-stu-id="14fbf-102">IHostTask::Join Method</span></span>

<span data-ttu-id="14fbf-103">Blockiert die aufrufende Aufgabe, bis die durch die aktuelle [IHostTask](ihosttask-interface.md) -Instanz dargestellte Aufgabe abgeschlossen ist, das angegebene Zeitintervall abgelaufen ist oder [IHostTask:: Alert](ihosttask-alert-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="14fbf-103">Blocks the calling task until the task represented by the current [IHostTask](ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14fbf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14fbf-104">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14fbf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="14fbf-105">Parameters</span></span>  

 `milliseconds`  
 <span data-ttu-id="14fbf-106">in Das Zeitintervall (in Millisekunden), das gewartet werden soll, bis die Aufgabe beendet wird.</span><span class="sxs-lookup"><span data-stu-id="14fbf-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="14fbf-107">Wenn dieses Intervall abläuft, bevor der Task beendet wird, wird die Blockierung der aufrufenden Aufgabe aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="14fbf-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="14fbf-108">in Einer der [WAIT_OPTION](wait-option-enumeration.md) -Werte.</span><span class="sxs-lookup"><span data-stu-id="14fbf-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values.</span></span> <span data-ttu-id="14fbf-109">Der Wert WAIT_ALERTABLE weist den Host an, die Aufgabe zu aktivieren, wenn `Alert` aufgerufen wird, bevor `milliseconds` abläuft.</span><span class="sxs-lookup"><span data-stu-id="14fbf-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14fbf-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="14fbf-110">Return Value</span></span>  
  
|<span data-ttu-id="14fbf-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14fbf-111">HRESULT</span></span>|<span data-ttu-id="14fbf-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="14fbf-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14fbf-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="14fbf-113">S_OK</span></span>|<span data-ttu-id="14fbf-114">`Join` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="14fbf-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="14fbf-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="14fbf-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="14fbf-116">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="14fbf-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="14fbf-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14fbf-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="14fbf-118">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="14fbf-118">The call timed out.</span></span>|  
|<span data-ttu-id="14fbf-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="14fbf-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="14fbf-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="14fbf-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="14fbf-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="14fbf-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="14fbf-122">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf gewartet hat, oder die aktuelle `IHostTask` Instanz ist keiner Aufgabe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="14fbf-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="14fbf-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14fbf-123">E_FAIL</span></span>|<span data-ttu-id="14fbf-124">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="14fbf-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="14fbf-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="14fbf-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="14fbf-126">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="14fbf-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14fbf-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="14fbf-127">Requirements</span></span>  

 <span data-ttu-id="14fbf-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14fbf-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14fbf-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="14fbf-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14fbf-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="14fbf-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14fbf-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14fbf-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14fbf-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14fbf-132">See also</span></span>

- [<span data-ttu-id="14fbf-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14fbf-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="14fbf-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14fbf-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="14fbf-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14fbf-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="14fbf-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14fbf-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="14fbf-137">WAIT_OPTION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="14fbf-137">WAIT_OPTION Enumeration</span></span>](wait-option-enumeration.md)
