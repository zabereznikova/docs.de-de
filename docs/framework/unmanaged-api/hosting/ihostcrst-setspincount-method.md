---
title: IHostCrst::SetSpinCount-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.SetSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76a3091102a43d17f543010be0c505157d593d2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="377c6-102">IHostCrst::SetSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="377c6-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="377c6-103">Legt die Anzahl der Drehfeld für die aktuelle [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="377c6-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="377c6-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="377c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="377c6-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="377c6-106">[in] Die neue Spinninganzahl für den aktuellen `IHostCrst` Instanz.</span><span class="sxs-lookup"><span data-stu-id="377c6-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="377c6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="377c6-107">Return Value</span></span>  
  
|<span data-ttu-id="377c6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="377c6-108">HRESULT</span></span>|<span data-ttu-id="377c6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="377c6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="377c6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="377c6-110">S_OK</span></span>|<span data-ttu-id="377c6-111">`SetSpinCount`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="377c6-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="377c6-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="377c6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="377c6-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="377c6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="377c6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="377c6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="377c6-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="377c6-115">The call timed out.</span></span>|  
|<span data-ttu-id="377c6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="377c6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="377c6-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="377c6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="377c6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="377c6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="377c6-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="377c6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="377c6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="377c6-120">E_FAIL</span></span>|<span data-ttu-id="377c6-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="377c6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="377c6-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="377c6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="377c6-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="377c6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="377c6-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="377c6-124">Remarks</span></span>  
 <span data-ttu-id="377c6-125">Für Systeme mit mehreren Prozessoren, wenn von der aktuellen kritische Abschnitt dargestellt `IHostCrst` Instanz nicht verfügbar ist, versucht ein aufrufender Thread `dwSpinCount` Mal vor dem Aufruf [IHostSemaphore:: wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) für einen Semaphore verknüpft sind mit dem kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="377c6-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="377c6-126">Wenn der kritische Abschnitt während des Vorgangs Drehfeld frei wird, wird der aufrufende Thread den Wartevorgang vermieden.</span><span class="sxs-lookup"><span data-stu-id="377c6-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="377c6-127">Die Verwendung von `dwSpinCount` ist identisch mit der Verwendung des Parameters mit dem gleichen Namen in der Win32- `InitializeCriticalSectionAndSpinCount` Funktion.</span><span class="sxs-lookup"><span data-stu-id="377c6-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377c6-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="377c6-128">Requirements</span></span>  
 <span data-ttu-id="377c6-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="377c6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="377c6-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="377c6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="377c6-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="377c6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="377c6-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="377c6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377c6-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="377c6-133">See Also</span></span>  
 [<span data-ttu-id="377c6-134">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="377c6-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="377c6-135">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="377c6-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="377c6-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="377c6-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
