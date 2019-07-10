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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e443ec3f743d56f0fe7e4e1c794f16bab2db8314
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763962"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="1aefd-102">IHostAutoEvent::Set-Methode</span><span class="sxs-lookup"><span data-stu-id="1aefd-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="1aefd-103">Legt die aktuelle [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) Instanz in einem signalisierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="1aefd-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aefd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1aefd-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1aefd-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1aefd-105">Return Value</span></span>  
  
|<span data-ttu-id="1aefd-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1aefd-106">HRESULT</span></span>|<span data-ttu-id="1aefd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1aefd-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1aefd-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1aefd-108">S_OK</span></span>|<span data-ttu-id="1aefd-109">`Set` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1aefd-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="1aefd-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1aefd-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1aefd-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1aefd-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1aefd-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1aefd-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1aefd-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1aefd-113">The call timed out.</span></span>|  
|<span data-ttu-id="1aefd-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1aefd-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1aefd-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1aefd-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1aefd-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1aefd-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1aefd-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1aefd-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1aefd-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1aefd-118">E_FAIL</span></span>|<span data-ttu-id="1aefd-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1aefd-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1aefd-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1aefd-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1aefd-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1aefd-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1aefd-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1aefd-122">Requirements</span></span>  
 <span data-ttu-id="1aefd-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aefd-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aefd-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1aefd-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1aefd-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1aefd-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1aefd-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aefd-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aefd-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1aefd-127">See also</span></span>

- [<span data-ttu-id="1aefd-128">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1aefd-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="1aefd-129">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1aefd-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="1aefd-130">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1aefd-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="1aefd-131">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1aefd-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
