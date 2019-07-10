---
title: IHostManualEvent::Wait-Methode
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2242395a02254268c9492e534309c690a343ffbe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767262"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="a0755-102">IHostManualEvent::Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="a0755-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="a0755-103">Bewirkt, dass die aktuelle [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) Instanz warten, bis sie gehört, oder einen bestimmten Zeitraum abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="a0755-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0755-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0755-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0755-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0755-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="a0755-106">[in] Die Anzahl der Millisekunden vor dem zurückgeben, wenn die aktuelle `IHostManualEvent` Instanz hat keinen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="a0755-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="a0755-107">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte, der angibt, der Aktion, die der Host ausführen sollten, wenn dieser Vorgang blockiert.</span><span class="sxs-lookup"><span data-stu-id="a0755-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0755-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0755-108">Return Value</span></span>  
  
|<span data-ttu-id="a0755-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0755-109">HRESULT</span></span>|<span data-ttu-id="a0755-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0755-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0755-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0755-111">S_OK</span></span>|<span data-ttu-id="a0755-112">`Wait` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0755-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="a0755-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0755-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0755-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a0755-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0755-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0755-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0755-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a0755-116">The call timed out.</span></span>|  
|<span data-ttu-id="a0755-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0755-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0755-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a0755-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0755-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0755-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0755-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="a0755-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0755-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0755-121">E_FAIL</span></span>|<span data-ttu-id="a0755-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a0755-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0755-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0755-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0755-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a0755-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0755-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="a0755-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="a0755-126">Der Host die Wartezeit einen Deadlock aufgetreten, und wählen Sie die aktuelle `IHostManualEvent` Instanz als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="a0755-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0755-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0755-127">Requirements</span></span>  
 <span data-ttu-id="a0755-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0755-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0755-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0755-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0755-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a0755-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0755-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0755-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0755-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0755-132">See also</span></span>

- [<span data-ttu-id="a0755-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0755-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a0755-134">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0755-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="a0755-135">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0755-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="a0755-136">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0755-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="a0755-137">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0755-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
