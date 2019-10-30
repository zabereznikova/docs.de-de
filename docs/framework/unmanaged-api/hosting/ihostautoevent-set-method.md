---
title: IHostAutoEvent::Set-Methode
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
ms.openlocfilehash: 792b735522580eb7460da703899a00781e525419
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124450"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="8a887-102">IHostAutoEvent::Set-Methode</span><span class="sxs-lookup"><span data-stu-id="8a887-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="8a887-103">Legt die aktuelle [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) -Instanz auf einen signalisierten Zustand fest.</span><span class="sxs-lookup"><span data-stu-id="8a887-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a887-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a887-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8a887-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8a887-105">Return Value</span></span>  
  
|<span data-ttu-id="8a887-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a887-106">HRESULT</span></span>|<span data-ttu-id="8a887-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a887-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a887-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a887-108">S_OK</span></span>|<span data-ttu-id="8a887-109">`Set` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8a887-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="8a887-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a887-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a887-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8a887-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a887-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8a887-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8a887-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8a887-113">The call timed out.</span></span>|  
|<span data-ttu-id="8a887-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8a887-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8a887-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8a887-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8a887-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8a887-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8a887-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8a887-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8a887-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a887-118">E_FAIL</span></span>|<span data-ttu-id="8a887-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8a887-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a887-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a887-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a887-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8a887-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a887-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a887-122">Requirements</span></span>  
 <span data-ttu-id="8a887-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a887-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a887-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8a887-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a887-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8a887-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a887-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a887-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a887-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a887-127">See also</span></span>

- [<span data-ttu-id="8a887-128">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a887-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="8a887-129">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a887-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="8a887-130">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a887-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="8a887-131">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a887-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
