---
title: IHostCrst::SetSpinCount-Methode
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdbce5e61f2013513d2079b5a958270319d34857
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763755"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="6c59a-102">IHostCrst::SetSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="6c59a-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="6c59a-103">Legt die Spin-Anzahl für den aktuellen [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="6c59a-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c59a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c59a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c59a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c59a-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="6c59a-106">[in] Die neue Spin-Anzahl für den aktuellen `IHostCrst` Instanz.</span><span class="sxs-lookup"><span data-stu-id="6c59a-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c59a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6c59a-107">Return Value</span></span>  
  
|<span data-ttu-id="6c59a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c59a-108">HRESULT</span></span>|<span data-ttu-id="6c59a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c59a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c59a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c59a-110">S_OK</span></span>|<span data-ttu-id="6c59a-111">`SetSpinCount` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6c59a-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="6c59a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6c59a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6c59a-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6c59a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6c59a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6c59a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6c59a-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6c59a-115">The call timed out.</span></span>|  
|<span data-ttu-id="6c59a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6c59a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6c59a-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="6c59a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6c59a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6c59a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6c59a-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="6c59a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6c59a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6c59a-120">E_FAIL</span></span>|<span data-ttu-id="6c59a-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6c59a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6c59a-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c59a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6c59a-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="6c59a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c59a-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c59a-124">Remarks</span></span>  
 <span data-ttu-id="6c59a-125">Für Systeme mit mehreren Prozessoren, der kritische Abschnitt durch die aktuelle dargestellt `IHostCrst` Instanz nicht verfügbar ist, versucht ein aufrufender Thread `dwSpinCount` Mal vor dem Aufruf [IHostSemaphore:: wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) für einen Semaphore verknüpft ist mit den kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="6c59a-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="6c59a-126">Wenn während des Vorgangs Starten der kritische Abschnitt frei wird, wird der aufrufende Thread den Wartevorgang vermieden.</span><span class="sxs-lookup"><span data-stu-id="6c59a-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="6c59a-127">Die Verwendung von `dwSpinCount` ist identisch mit der Syntax des Parameters mit dem gleichen Namen in der Win32- `InitializeCriticalSectionAndSpinCount` Funktion.</span><span class="sxs-lookup"><span data-stu-id="6c59a-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c59a-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c59a-128">Requirements</span></span>  
 <span data-ttu-id="6c59a-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c59a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c59a-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c59a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c59a-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6c59a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c59a-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c59a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c59a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c59a-133">See also</span></span>

- [<span data-ttu-id="6c59a-134">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c59a-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="6c59a-135">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c59a-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="6c59a-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c59a-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
