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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f260e1351c8aa14961a10e0f7087bd076752785d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763772"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="9c2f9-102">IHostCrst::Leave-Methode</span><span class="sxs-lookup"><span data-stu-id="9c2f9-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="9c2f9-103">Verlässt den kritischen Abschnitt, die von der aktuellen Instanz der dargestellt wird [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9c2f9-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c2f9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c2f9-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9c2f9-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9c2f9-105">Return Value</span></span>  
  
|<span data-ttu-id="9c2f9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c2f9-106">HRESULT</span></span>|<span data-ttu-id="9c2f9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c2f9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c2f9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c2f9-108">S_OK</span></span>|<span data-ttu-id="9c2f9-109">`Leave` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9c2f9-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="9c2f9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9c2f9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9c2f9-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9c2f9-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9c2f9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9c2f9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9c2f9-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9c2f9-113">The call timed out.</span></span>|  
|<span data-ttu-id="9c2f9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9c2f9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9c2f9-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9c2f9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9c2f9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9c2f9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9c2f9-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9c2f9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9c2f9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9c2f9-118">E_FAIL</span></span>|<span data-ttu-id="9c2f9-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9c2f9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9c2f9-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9c2f9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9c2f9-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9c2f9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c2f9-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c2f9-122">Remarks</span></span>  
 <span data-ttu-id="9c2f9-123">`Leave` ermöglicht der CLR kommunizieren direkt mit Host threading-Implementierung, anstatt die entsprechenden Win32 `LeaveCriticalSection` Funktion.</span><span class="sxs-lookup"><span data-stu-id="9c2f9-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="9c2f9-124">Ein Thread, in dessen Besitz der des kritischen Abschnitts, die vom aktuellen `IHostCrst` Instanz muss Aufrufen `Leave` Sobald jedes Mal es diese kritischen Abschnitt betritt.</span><span class="sxs-lookup"><span data-stu-id="9c2f9-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c2f9-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c2f9-125">Requirements</span></span>  
 <span data-ttu-id="9c2f9-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c2f9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c2f9-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9c2f9-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c2f9-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9c2f9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c2f9-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c2f9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2f9-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c2f9-130">See also</span></span>

- [<span data-ttu-id="9c2f9-131">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c2f9-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9c2f9-132">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c2f9-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="9c2f9-133">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c2f9-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
