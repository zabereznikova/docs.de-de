---
title: IHostManualEvent::Reset-Methode
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
ms.openlocfilehash: 049a0ae6d860c7c431d08af8ba4539656b8e5592
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804586"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="1d3a5-102">IHostManualEvent::Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="1d3a5-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="1d3a5-103">Setzt die aktuelle [IHostManualEvent](ihostmanualevent-interface.md) -Instanz auf einen nicht signalisierten Zustand zurück.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-103">Resets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d3a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d3a5-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1d3a5-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1d3a5-105">Return Value</span></span>  
  
|<span data-ttu-id="1d3a5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d3a5-106">HRESULT</span></span>|<span data-ttu-id="1d3a5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1d3a5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d3a5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d3a5-108">S_OK</span></span>|<span data-ttu-id="1d3a5-109">`Reset`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="1d3a5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d3a5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d3a5-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d3a5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d3a5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d3a5-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-113">The call timed out.</span></span>|  
|<span data-ttu-id="1d3a5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d3a5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d3a5-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d3a5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d3a5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d3a5-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d3a5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d3a5-118">E_FAIL</span></span>|<span data-ttu-id="1d3a5-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d3a5-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d3a5-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1d3a5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d3a5-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d3a5-122">Requirements</span></span>  
 <span data-ttu-id="1d3a5-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d3a5-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d3a5-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1d3a5-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d3a5-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1d3a5-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d3a5-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d3a5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d3a5-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d3a5-127">See also</span></span>

- [<span data-ttu-id="1d3a5-128">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d3a5-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="1d3a5-129">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d3a5-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="1d3a5-130">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d3a5-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="1d3a5-131">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d3a5-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="1d3a5-132">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d3a5-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
