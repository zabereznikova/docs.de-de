---
title: IHostCrst::Leave-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 391aff3920e7ea2ef010ce7d97bdedb4e636dc86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="fe760-102">IHostCrst::Leave-Methode</span><span class="sxs-lookup"><span data-stu-id="fe760-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="fe760-103">Verlässt die kritischen Abschnitt die von der aktuellen Instanz der dargestellte [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="fe760-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe760-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe760-104">Syntax</span></span>  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fe760-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fe760-105">Return Value</span></span>  
  
|<span data-ttu-id="fe760-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe760-106">HRESULT</span></span>|<span data-ttu-id="fe760-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe760-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe760-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe760-108">S_OK</span></span>|<span data-ttu-id="fe760-109">`Leave`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fe760-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="fe760-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="fe760-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe760-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="fe760-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fe760-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe760-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe760-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fe760-113">The call timed out.</span></span>|  
|<span data-ttu-id="fe760-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe760-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe760-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="fe760-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe760-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe760-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe760-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="fe760-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe760-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe760-118">E_FAIL</span></span>|<span data-ttu-id="fe760-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fe760-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fe760-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="fe760-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe760-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fe760-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe760-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe760-122">Remarks</span></span>  
 <span data-ttu-id="fe760-123">`Leave`ermöglicht der CLR kommunizieren direkt mit der Hosts Implementierung threading, statt die entsprechenden Win32 `LeaveCriticalSection` Funktion.</span><span class="sxs-lookup"><span data-stu-id="fe760-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="fe760-124">Ein Thread, der Besitz der kritische Abschnitt dargestellt, die vom aktuellen übernimmt `IHostCrst` Instanz muss aufgerufen werden `Leave` Sobald jedes Mal wichtige Abschnitt eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="fe760-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe760-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe760-125">Requirements</span></span>  
 <span data-ttu-id="fe760-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe760-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe760-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fe760-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe760-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fe760-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe760-129">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe760-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe760-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe760-130">See Also</span></span>  
 [<span data-ttu-id="fe760-131">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe760-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="fe760-132">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe760-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="fe760-133">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe760-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
