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
ms.openlocfilehash: 22274759f931da614a234efe0a6f6eb3aade027c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729563"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="71c8b-102">IHostCrst::SetSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="71c8b-102">IHostCrst::SetSpinCount Method</span></span>

<span data-ttu-id="71c8b-103">Legt die drehanzahl für die aktuelle [IHostCrst](ihostcrst-interface.md) -Instanz fest.</span><span class="sxs-lookup"><span data-stu-id="71c8b-103">Sets the spin count for the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71c8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71c8b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71c8b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71c8b-105">Parameters</span></span>  

 `dwSpinCount`  
 <span data-ttu-id="71c8b-106">in Die neue Spin-Anzahl für die aktuelle `IHostCrst` Instanz.</span><span class="sxs-lookup"><span data-stu-id="71c8b-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71c8b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="71c8b-107">Return Value</span></span>  
  
|<span data-ttu-id="71c8b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71c8b-108">HRESULT</span></span>|<span data-ttu-id="71c8b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="71c8b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71c8b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="71c8b-110">S_OK</span></span>|<span data-ttu-id="71c8b-111">`SetSpinCount` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="71c8b-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="71c8b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71c8b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71c8b-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="71c8b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71c8b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71c8b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71c8b-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="71c8b-115">The call timed out.</span></span>|  
|<span data-ttu-id="71c8b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71c8b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71c8b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="71c8b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71c8b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71c8b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71c8b-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="71c8b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71c8b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71c8b-120">E_FAIL</span></span>|<span data-ttu-id="71c8b-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="71c8b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71c8b-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="71c8b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71c8b-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="71c8b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71c8b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71c8b-124">Remarks</span></span>  

 <span data-ttu-id="71c8b-125">Wenn auf Multiprozessorsystemen der kritische, von der aktuellen Instanz dargestellte Abschnitt nicht `IHostCrst` verfügbar ist, wird ein aufrufenden Thread `dwSpinCount` vor dem Aufrufen von [IHostSemaphore:: Wait](ihostsemaphore-wait-method.md) für ein Semaphor, das dem kritischen Abschnitt zugeordnet ist, mehrmals aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="71c8b-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="71c8b-126">Wenn der kritische Abschnitt während des drehvorgangs frei wird, vermeidet der aufrufenden Thread den warte Vorgang.</span><span class="sxs-lookup"><span data-stu-id="71c8b-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="71c8b-127">Die Verwendung von `dwSpinCount` ist mit der Verwendung des-Parameters desselben Namens in der Win32- `InitializeCriticalSectionAndSpinCount` Funktion identisch.</span><span class="sxs-lookup"><span data-stu-id="71c8b-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71c8b-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="71c8b-128">Requirements</span></span>  

 <span data-ttu-id="71c8b-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71c8b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71c8b-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="71c8b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71c8b-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="71c8b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71c8b-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71c8b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c8b-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71c8b-133">See also</span></span>

- [<span data-ttu-id="71c8b-134">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71c8b-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="71c8b-135">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71c8b-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="71c8b-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71c8b-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
