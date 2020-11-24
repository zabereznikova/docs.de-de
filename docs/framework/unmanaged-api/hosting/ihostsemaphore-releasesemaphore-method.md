---
title: IHostSemaphore::ReleaseSemaphore-Methode
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
ms.openlocfilehash: 660062fb69bb8fe0a06bbca9046d65175fb72f9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683029"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="50e09-102">IHostSemaphore::ReleaseSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="50e09-102">IHostSemaphore::ReleaseSemaphore Method</span></span>

<span data-ttu-id="50e09-103">Erhöht die Anzahl der aktuellen [IHostSemaphore](ihostsemaphore-interface.md) -Instanz um den angegebenen Betrag.</span><span class="sxs-lookup"><span data-stu-id="50e09-103">Increases the count of the current [IHostSemaphore](ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50e09-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50e09-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50e09-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="50e09-105">Parameters</span></span>  

 `lReleaseCount`  
 <span data-ttu-id="50e09-106">in Der Betrag, um den die Anzahl der aktuellen Instanz vergrößert werden soll `IHostSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="50e09-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="50e09-107">Dieser Wert muss größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="50e09-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="50e09-108">vorgenommen Ein Zeiger auf die vorherige Anzahl oder NULL, wenn der Aufrufer die vorherige Anzahl nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="50e09-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50e09-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="50e09-109">Return Value</span></span>  
  
|<span data-ttu-id="50e09-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50e09-110">HRESULT</span></span>|<span data-ttu-id="50e09-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="50e09-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50e09-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="50e09-112">S_OK</span></span>|<span data-ttu-id="50e09-113">`ReleaseSemaphore` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50e09-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="50e09-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50e09-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50e09-115">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="50e09-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50e09-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50e09-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50e09-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="50e09-117">The call timed out.</span></span>|  
|<span data-ttu-id="50e09-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50e09-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50e09-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="50e09-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50e09-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50e09-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50e09-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="50e09-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50e09-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50e09-122">E_FAIL</span></span>|<span data-ttu-id="50e09-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="50e09-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50e09-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="50e09-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50e09-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="50e09-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50e09-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50e09-126">Remarks</span></span>  

 <span data-ttu-id="50e09-127">Die CLR ruft in der Regel `ReleaseSemaphore` auf, um den Host zu benachrichtigen, dass die Verwendung einer Ressource abgeschlossen ist, und übergibt den Wert 1 für den `lReleaseCount` Parameter.</span><span class="sxs-lookup"><span data-stu-id="50e09-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50e09-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="50e09-128">Requirements</span></span>  

 <span data-ttu-id="50e09-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50e09-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50e09-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="50e09-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50e09-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="50e09-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50e09-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50e09-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e09-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50e09-133">See also</span></span>

- [<span data-ttu-id="50e09-134">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50e09-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="50e09-135">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50e09-135">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="50e09-136">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50e09-136">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="50e09-137">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50e09-137">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="50e09-138">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50e09-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
