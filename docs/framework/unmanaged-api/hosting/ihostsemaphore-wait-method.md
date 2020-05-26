---
title: IHostSemaphore::Wait-Methode
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
ms.openlocfilehash: 22d570711c293dd8c0cc6fefd198dd46d6489bea
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803541"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="e4473-102">IHostSemaphore::Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="e4473-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="e4473-103">Bewirkt, dass die aktuelle [IHostSemaphore](ihostsemaphore-interface.md) -Instanz wartet, bis Sie im Besitz ist oder die angegebene Zeitspanne verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="e4473-103">Causes the current [IHostSemaphore](ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4473-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4473-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4473-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4473-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="e4473-106">in Die Anzahl von Millisekunden, die vor der Rückgabe gewartet werden soll, wenn die aktuelle `IHostSemaphore` Instanz nicht im Besitz ist.</span><span class="sxs-lookup"><span data-stu-id="e4473-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="e4473-107">in Einer der [WAIT_OPTION](wait-option-enumeration.md) -Werte, der angibt, welche Aktion der Host durchführen soll, wenn dieser Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="e4473-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4473-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e4473-108">Return Value</span></span>  
  
|<span data-ttu-id="e4473-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e4473-109">HRESULT</span></span>|<span data-ttu-id="e4473-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e4473-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4473-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e4473-111">S_OK</span></span>|<span data-ttu-id="e4473-112">`Wait`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e4473-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="e4473-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e4473-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e4473-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e4473-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e4473-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e4473-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e4473-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="e4473-116">The call timed out.</span></span>|  
|<span data-ttu-id="e4473-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4473-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e4473-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e4473-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e4473-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e4473-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e4473-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="e4473-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e4473-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e4473-121">E_FAIL</span></span>|<span data-ttu-id="e4473-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e4473-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e4473-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="e4473-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e4473-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e4473-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e4473-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="e4473-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="e4473-126">Der Host hat während des warte Intervalls einen Deadlock erkannt, und die aktuelle `IHostSemaphore` Instanz wurde als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e4473-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e4473-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4473-127">Requirements</span></span>  
 <span data-ttu-id="e4473-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4473-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4473-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e4473-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4473-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e4473-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4473-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4473-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4473-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4473-132">See also</span></span>

- [<span data-ttu-id="e4473-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4473-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="e4473-134">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4473-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="e4473-135">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4473-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="e4473-136">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4473-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="e4473-137">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4473-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
