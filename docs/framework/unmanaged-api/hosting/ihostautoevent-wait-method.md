---
title: IHostAutoEvent::Wait-Methode
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
ms.openlocfilehash: 7baabafc61e14d127ff3f0cdb7453be6f1a2abeb
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804973"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="a4b44-102">IHostAutoEvent::Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="a4b44-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="a4b44-103">Bewirkt, dass die aktuelle [IHostAutoEvent](ihostautoevent-interface.md) -Instanz wartet, bis Sie im Besitz ist oder eine angegebene Zeitspanne abläuft.</span><span class="sxs-lookup"><span data-stu-id="a4b44-103">Causes the current [IHostAutoEvent](ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b44-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4b44-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4b44-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a4b44-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="a4b44-106">in Die Anzahl der Millisekunden, die die aktuelle `IHostAutoEvent` Instanz warten soll, bevor Sie zurückgegeben wird, wenn kein Thread oder keine Fiber den Besitz übernimmt.</span><span class="sxs-lookup"><span data-stu-id="a4b44-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="a4b44-107">in Einer der [WAIT_OPTION](wait-option-enumeration.md) -Werte, der die Aktion angibt, die der Host durchführen soll, wenn dieser Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="a4b44-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4b44-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a4b44-108">Return Value</span></span>  
  
|<span data-ttu-id="a4b44-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4b44-109">HRESULT</span></span>|<span data-ttu-id="a4b44-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a4b44-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4b44-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4b44-111">S_OK</span></span>|<span data-ttu-id="a4b44-112">`Wait`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a4b44-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="a4b44-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4b44-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4b44-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a4b44-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4b44-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4b44-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4b44-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="a4b44-116">The call timed out.</span></span>|  
|<span data-ttu-id="a4b44-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4b44-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4b44-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a4b44-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4b44-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4b44-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4b44-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="a4b44-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4b44-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4b44-121">E_FAIL</span></span>|<span data-ttu-id="a4b44-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a4b44-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4b44-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="a4b44-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4b44-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a4b44-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a4b44-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="a4b44-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="a4b44-126">Der Host hat während des warte Intervalls einen Deadlock erkannt und das Ereignis, das von der aktuellen Instanz dargestellt wird, `IHostAutoEvent` als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="a4b44-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4b44-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4b44-127">Requirements</span></span>  
 <span data-ttu-id="a4b44-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4b44-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4b44-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a4b44-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4b44-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a4b44-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4b44-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b44-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b44-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4b44-132">See also</span></span>

- [<span data-ttu-id="a4b44-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4b44-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a4b44-134">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4b44-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="a4b44-135">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4b44-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="a4b44-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4b44-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
