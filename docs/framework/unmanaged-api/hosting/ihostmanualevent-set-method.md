---
title: IHostManualEvent::Set-Methode
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
ms.openlocfilehash: bc2b178c6c26a6de62982c35d5aeb9ea5359c2bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679129"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="dc5ec-102">IHostManualEvent::Set-Methode</span><span class="sxs-lookup"><span data-stu-id="dc5ec-102">IHostManualEvent::Set Method</span></span>

<span data-ttu-id="dc5ec-103">Legt die aktuelle [IHostManualEvent](ihostmanualevent-interface.md) -Instanz auf einen signalisierten Zustand fest.</span><span class="sxs-lookup"><span data-stu-id="dc5ec-103">Sets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc5ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc5ec-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dc5ec-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dc5ec-105">Return Value</span></span>  
  
|<span data-ttu-id="dc5ec-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc5ec-106">HRESULT</span></span>|<span data-ttu-id="dc5ec-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dc5ec-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc5ec-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc5ec-108">S_OK</span></span>|<span data-ttu-id="dc5ec-109">`Set` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc5ec-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="dc5ec-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc5ec-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc5ec-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="dc5ec-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dc5ec-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc5ec-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc5ec-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="dc5ec-113">The call timed out.</span></span>|  
|<span data-ttu-id="dc5ec-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc5ec-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc5ec-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="dc5ec-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc5ec-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc5ec-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc5ec-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="dc5ec-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc5ec-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc5ec-118">E_FAIL</span></span>|<span data-ttu-id="dc5ec-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="dc5ec-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc5ec-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="dc5ec-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc5ec-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="dc5ec-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dc5ec-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dc5ec-122">Requirements</span></span>  

 <span data-ttu-id="dc5ec-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc5ec-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc5ec-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="dc5ec-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc5ec-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dc5ec-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc5ec-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc5ec-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc5ec-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc5ec-127">See also</span></span>

- [<span data-ttu-id="dc5ec-128">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc5ec-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="dc5ec-129">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc5ec-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="dc5ec-130">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc5ec-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="dc5ec-131">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc5ec-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="dc5ec-132">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc5ec-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
