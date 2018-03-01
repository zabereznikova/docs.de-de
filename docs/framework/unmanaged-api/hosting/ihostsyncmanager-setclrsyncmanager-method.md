---
title: IHostSyncManager::SetCLRSyncManager-Methode
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
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fca59f0d2617c6fb244b2b1ed7b5cf46a7d5869f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="3d72d-102">IHostSyncManager::SetCLRSyncManager-Methode</span><span class="sxs-lookup"><span data-stu-id="3d72d-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="3d72d-103">Legt die [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) Instanz zuordnen zu den aktuellen [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="3d72d-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d72d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d72d-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d72d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d72d-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="3d72d-106">[in] Ein Zeiger auf eine `ICLRSyncManager` Instanz, die von der common Language Runtime (CLR) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3d72d-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d72d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3d72d-107">Return Value</span></span>  
  
|<span data-ttu-id="3d72d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d72d-108">HRESULT</span></span>|<span data-ttu-id="3d72d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d72d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d72d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d72d-110">S_OK</span></span>|<span data-ttu-id="3d72d-111">`SetCLRSyncManager`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3d72d-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="3d72d-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="3d72d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3d72d-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3d72d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3d72d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3d72d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3d72d-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3d72d-115">The call timed out.</span></span>|  
|<span data-ttu-id="3d72d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3d72d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3d72d-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3d72d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3d72d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3d72d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3d72d-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3d72d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3d72d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3d72d-120">E_FAIL</span></span>|<span data-ttu-id="3d72d-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3d72d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3d72d-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="3d72d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3d72d-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3d72d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d72d-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d72d-124">Remarks</span></span>  
 <span data-ttu-id="3d72d-125">Zur Vereinfachung der Kommunikation zwischen dem Host und der CLR, treten Hostingschnittstellen in der Regel paarweise zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="3d72d-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="3d72d-126">Ein Element des Paars wird vom Host implementiert, und das andere Element wird von der CLR implementiert.</span><span class="sxs-lookup"><span data-stu-id="3d72d-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="3d72d-127">Als hostseitige Implementierung die `IHostSyncManager` -Schnittstelle entspricht der `ICLRSyncManager` Schnittstelle, die von der CLR implementiert.</span><span class="sxs-lookup"><span data-stu-id="3d72d-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="3d72d-128">Die CLR ruft `SetCLRSyncManager` angeben einer `ICLRSyncManager` Instanz für den Host mit dem aktuellen zuordnen `IHostSyncManager` Instanz.</span><span class="sxs-lookup"><span data-stu-id="3d72d-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d72d-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d72d-129">Requirements</span></span>  
 <span data-ttu-id="3d72d-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d72d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d72d-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3d72d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d72d-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3d72d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d72d-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d72d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d72d-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d72d-134">See Also</span></span>  
 [<span data-ttu-id="3d72d-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d72d-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="3d72d-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d72d-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
