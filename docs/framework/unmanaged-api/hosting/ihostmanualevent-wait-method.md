---
title: IHostManualEvent::Wait-Methode
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
ms.openlocfilehash: 6d0276764a07d5bb202d66b653fdf5cb96320c08
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804552"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="74246-102">IHostManualEvent::Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="74246-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="74246-103">Bewirkt, dass die aktuelle [IHostManualEvent](ihostmanualevent-interface.md) -Instanz wartet, bis Sie im Besitz ist oder eine angegebene Zeitspanne abläuft.</span><span class="sxs-lookup"><span data-stu-id="74246-103">Causes the current [IHostManualEvent](ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74246-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74246-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74246-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="74246-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="74246-106">in Die Anzahl von Millisekunden, die vor der Rückgabe gewartet werden soll, wenn die aktuelle `IHostManualEvent` Instanz nicht im Besitz ist.</span><span class="sxs-lookup"><span data-stu-id="74246-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="74246-107">in Einer der [WAIT_OPTION](wait-option-enumeration.md) -Werte, der die Aktion angibt, die der Host durchführen soll, wenn dieser Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="74246-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74246-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="74246-108">Return Value</span></span>  
  
|<span data-ttu-id="74246-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74246-109">HRESULT</span></span>|<span data-ttu-id="74246-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="74246-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74246-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="74246-111">S_OK</span></span>|<span data-ttu-id="74246-112">`Wait`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="74246-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="74246-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74246-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74246-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="74246-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="74246-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="74246-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="74246-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="74246-116">The call timed out.</span></span>|  
|<span data-ttu-id="74246-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="74246-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="74246-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="74246-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="74246-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="74246-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="74246-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="74246-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="74246-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74246-121">E_FAIL</span></span>|<span data-ttu-id="74246-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="74246-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="74246-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="74246-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="74246-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="74246-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="74246-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="74246-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="74246-126">Der Host hat während des warte Intervalls einen Deadlock erkannt, und die aktuelle `IHostManualEvent` Instanz wurde als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="74246-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74246-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74246-127">Requirements</span></span>  
 <span data-ttu-id="74246-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74246-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74246-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="74246-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74246-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="74246-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74246-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74246-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74246-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74246-132">See also</span></span>

- [<span data-ttu-id="74246-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74246-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="74246-134">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74246-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="74246-135">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74246-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="74246-136">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74246-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="74246-137">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74246-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
