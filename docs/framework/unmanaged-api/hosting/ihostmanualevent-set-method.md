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
ms.openlocfilehash: b5cd02f54a930942e1892f88fb3d8e926a6f3e1b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804569"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="ccdea-102">IHostManualEvent::Set-Methode</span><span class="sxs-lookup"><span data-stu-id="ccdea-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="ccdea-103">Legt die aktuelle [IHostManualEvent](ihostmanualevent-interface.md) -Instanz auf einen signalisierten Zustand fest.</span><span class="sxs-lookup"><span data-stu-id="ccdea-103">Sets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccdea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccdea-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ccdea-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ccdea-105">Return Value</span></span>  
  
|<span data-ttu-id="ccdea-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ccdea-106">HRESULT</span></span>|<span data-ttu-id="ccdea-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ccdea-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ccdea-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ccdea-108">S_OK</span></span>|<span data-ttu-id="ccdea-109">`Set`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ccdea-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="ccdea-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ccdea-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ccdea-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ccdea-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ccdea-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ccdea-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ccdea-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="ccdea-113">The call timed out.</span></span>|  
|<span data-ttu-id="ccdea-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ccdea-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ccdea-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ccdea-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ccdea-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ccdea-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ccdea-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="ccdea-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ccdea-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ccdea-118">E_FAIL</span></span>|<span data-ttu-id="ccdea-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ccdea-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ccdea-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="ccdea-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ccdea-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ccdea-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ccdea-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ccdea-122">Requirements</span></span>  
 <span data-ttu-id="ccdea-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccdea-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccdea-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ccdea-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccdea-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ccdea-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccdea-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccdea-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccdea-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccdea-127">See also</span></span>

- [<span data-ttu-id="ccdea-128">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccdea-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="ccdea-129">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccdea-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="ccdea-130">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccdea-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="ccdea-131">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccdea-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="ccdea-132">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccdea-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
