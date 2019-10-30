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
ms.openlocfilehash: a8642235cda359b849c49a35ab565397402c37d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130516"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="b28d5-102">IHostCrst::SetSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="b28d5-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="b28d5-103">Legt die drehanzahl für die aktuelle [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) -Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="b28d5-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b28d5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b28d5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b28d5-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="b28d5-106">in Die neue Spin-Anzahl für die aktuelle `IHostCrst` Instanz.</span><span class="sxs-lookup"><span data-stu-id="b28d5-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b28d5-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b28d5-107">Return Value</span></span>  
  
|<span data-ttu-id="b28d5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b28d5-108">HRESULT</span></span>|<span data-ttu-id="b28d5-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b28d5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b28d5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b28d5-110">S_OK</span></span>|<span data-ttu-id="b28d5-111">`SetSpinCount` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b28d5-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="b28d5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b28d5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b28d5-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b28d5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b28d5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b28d5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b28d5-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="b28d5-115">The call timed out.</span></span>|  
|<span data-ttu-id="b28d5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b28d5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b28d5-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b28d5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b28d5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b28d5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b28d5-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="b28d5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b28d5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b28d5-120">E_FAIL</span></span>|<span data-ttu-id="b28d5-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b28d5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b28d5-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b28d5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b28d5-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b28d5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b28d5-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b28d5-124">Remarks</span></span>  
 <span data-ttu-id="b28d5-125">Wenn auf Multiprozessorsystemen der kritische Abschnitt, der durch die aktuelle `IHostCrst` Instanz dargestellt wird, nicht verfügbar ist, wird `dwSpinCount` Zeiten von einem aufrufenden Thread aufgerufen, bevor [IHostSemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) für ein Semaphor aufgerufen wird, das mit dem kritischen Abschnitt verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="b28d5-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="b28d5-126">Wenn der kritische Abschnitt während des drehvorgangs frei wird, vermeidet der aufrufenden Thread den warte Vorgang.</span><span class="sxs-lookup"><span data-stu-id="b28d5-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="b28d5-127">Die Verwendung von `dwSpinCount` ist mit der Verwendung des-Parameters desselben Namens in der Win32-`InitializeCriticalSectionAndSpinCount` Funktion identisch.</span><span class="sxs-lookup"><span data-stu-id="b28d5-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b28d5-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b28d5-128">Requirements</span></span>  
 <span data-ttu-id="b28d5-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b28d5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b28d5-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b28d5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b28d5-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b28d5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b28d5-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b28d5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28d5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b28d5-133">See also</span></span>

- [<span data-ttu-id="b28d5-134">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b28d5-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="b28d5-135">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b28d5-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="b28d5-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b28d5-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
