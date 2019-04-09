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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b3de70e6bdecba6370174ee825d2dec7c14270e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148563"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="3a7a6-102">IHostManualEvent::Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="3a7a6-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="3a7a6-103">Setzt die aktuelle [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) Instanz in einen nicht signalisierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="3a7a6-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a7a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a7a6-104">Syntax</span></span>  
  
```  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3a7a6-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3a7a6-105">Return Value</span></span>  
  
|<span data-ttu-id="3a7a6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a7a6-106">HRESULT</span></span>|<span data-ttu-id="3a7a6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a7a6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a7a6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a7a6-108">S_OK</span></span>|`Reset` <span data-ttu-id="3a7a6-109">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3a7a6-109">returned successfully.</span></span>|  
|<span data-ttu-id="3a7a6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3a7a6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3a7a6-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3a7a6-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3a7a6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3a7a6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3a7a6-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3a7a6-113">The call timed out.</span></span>|  
|<span data-ttu-id="3a7a6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3a7a6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3a7a6-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3a7a6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3a7a6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3a7a6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3a7a6-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3a7a6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3a7a6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3a7a6-118">E_FAIL</span></span>|<span data-ttu-id="3a7a6-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3a7a6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3a7a6-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a7a6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3a7a6-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3a7a6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a7a6-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a7a6-122">Requirements</span></span>  
 <span data-ttu-id="3a7a6-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a7a6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a7a6-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3a7a6-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a7a6-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3a7a6-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3a7a6-126">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3a7a6-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3a7a6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a7a6-127">See also</span></span>

- [<span data-ttu-id="3a7a6-128">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a7a6-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3a7a6-129">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a7a6-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="3a7a6-130">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a7a6-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="3a7a6-131">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a7a6-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="3a7a6-132">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a7a6-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
