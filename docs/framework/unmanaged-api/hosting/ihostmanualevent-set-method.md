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
ms.openlocfilehash: 1114fc744ac1811585f2c5a94858b75eda00815c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136760"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="c7d4d-102">IHostManualEvent::Set-Methode</span><span class="sxs-lookup"><span data-stu-id="c7d4d-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="c7d4d-103">Legt die aktuelle [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) -Instanz auf einen signalisierten Zustand fest.</span><span class="sxs-lookup"><span data-stu-id="c7d4d-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7d4d-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c7d4d-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c7d4d-105">Return Value</span></span>  
  
|<span data-ttu-id="c7d4d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7d4d-106">HRESULT</span></span>|<span data-ttu-id="c7d4d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7d4d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7d4d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7d4d-108">S_OK</span></span>|<span data-ttu-id="c7d4d-109">`Set` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c7d4d-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="c7d4d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c7d4d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c7d4d-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c7d4d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c7d4d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c7d4d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c7d4d-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c7d4d-113">The call timed out.</span></span>|  
|<span data-ttu-id="c7d4d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c7d4d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c7d4d-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c7d4d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c7d4d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c7d4d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c7d4d-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c7d4d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c7d4d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7d4d-118">E_FAIL</span></span>|<span data-ttu-id="c7d4d-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c7d4d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7d4d-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7d4d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c7d4d-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c7d4d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7d4d-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7d4d-122">Requirements</span></span>  
 <span data-ttu-id="c7d4d-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7d4d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7d4d-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c7d4d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7d4d-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c7d4d-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7d4d-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7d4d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d4d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7d4d-127">See also</span></span>

- [<span data-ttu-id="c7d4d-128">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7d4d-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c7d4d-129">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7d4d-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="c7d4d-130">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7d4d-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="c7d4d-131">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7d4d-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="c7d4d-132">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7d4d-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
