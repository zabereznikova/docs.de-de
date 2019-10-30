---
title: IHostCrst::Leave-Methode
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
ms.openlocfilehash: 050af068579d84b984ed83377d0c201e281bd154
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130533"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="25623-102">IHostCrst::Leave-Methode</span><span class="sxs-lookup"><span data-stu-id="25623-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="25623-103">Verlässt den kritischen Abschnitt, der von der aktuellen Instanz von [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="25623-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25623-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25623-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="25623-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="25623-105">Return Value</span></span>  
  
|<span data-ttu-id="25623-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25623-106">HRESULT</span></span>|<span data-ttu-id="25623-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25623-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25623-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="25623-108">S_OK</span></span>|<span data-ttu-id="25623-109">`Leave` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="25623-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="25623-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="25623-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="25623-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="25623-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="25623-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="25623-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="25623-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="25623-113">The call timed out.</span></span>|  
|<span data-ttu-id="25623-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="25623-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="25623-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="25623-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="25623-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="25623-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="25623-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="25623-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="25623-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="25623-118">E_FAIL</span></span>|<span data-ttu-id="25623-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="25623-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="25623-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="25623-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="25623-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="25623-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25623-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25623-122">Remarks</span></span>  
 <span data-ttu-id="25623-123">mit `Leave` kann die CLR direkt mit der Threading Implementierung des Hosts kommunizieren, anstatt die entsprechende Win32-`LeaveCriticalSection` Funktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="25623-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="25623-124">Ein Thread, der den Besitz des kritischen Abschnitts übernimmt, der durch die aktuelle `IHostCrst` Instanz dargestellt wird, muss `Leave` einmal für jedes Mal aufgerufen werden, wenn er in diesen kritischen Abschnitt eintritt.</span><span class="sxs-lookup"><span data-stu-id="25623-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25623-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25623-125">Requirements</span></span>  
 <span data-ttu-id="25623-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25623-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25623-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="25623-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25623-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="25623-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25623-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25623-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25623-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25623-130">See also</span></span>

- [<span data-ttu-id="25623-131">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25623-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="25623-132">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25623-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="25623-133">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25623-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
