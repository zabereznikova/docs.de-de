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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1c40b27cd2899b5c3142364958b18144b8d4fee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709701"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="01fc3-102">IHostManualEvent::Set-Methode</span><span class="sxs-lookup"><span data-stu-id="01fc3-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="01fc3-103">Legt die aktuelle [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) Instanz in einem signalisierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="01fc3-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01fc3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01fc3-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="01fc3-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="01fc3-105">Return Value</span></span>  
  
|<span data-ttu-id="01fc3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01fc3-106">HRESULT</span></span>|<span data-ttu-id="01fc3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01fc3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01fc3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="01fc3-108">S_OK</span></span>|<span data-ttu-id="01fc3-109">`Set` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="01fc3-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="01fc3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01fc3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01fc3-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="01fc3-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01fc3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01fc3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01fc3-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="01fc3-113">The call timed out.</span></span>|  
|<span data-ttu-id="01fc3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01fc3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01fc3-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="01fc3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01fc3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01fc3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01fc3-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="01fc3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01fc3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01fc3-118">E_FAIL</span></span>|<span data-ttu-id="01fc3-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="01fc3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01fc3-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01fc3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01fc3-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="01fc3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01fc3-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01fc3-122">Requirements</span></span>  
 <span data-ttu-id="01fc3-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01fc3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01fc3-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01fc3-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01fc3-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="01fc3-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01fc3-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01fc3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01fc3-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01fc3-127">See also</span></span>
- [<span data-ttu-id="01fc3-128">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01fc3-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="01fc3-129">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01fc3-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="01fc3-130">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01fc3-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="01fc3-131">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01fc3-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="01fc3-132">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01fc3-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
