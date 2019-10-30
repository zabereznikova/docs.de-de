---
title: IHostSyncManager::SetCLRSyncManager-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 9c08a790d4dad748e5d09271bd870add22255b4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132610"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="daf3b-102">IHostSyncManager::SetCLRSyncManager-Methode</span><span class="sxs-lookup"><span data-stu-id="daf3b-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="daf3b-103">Legt die [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) -Instanz fest, die der aktuellen [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) -Instanz zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="daf3b-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="daf3b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daf3b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="daf3b-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="daf3b-106">in Ein Zeiger auf eine `ICLRSyncManager`-Instanz, die vom Common Language Runtime (CLR) bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="daf3b-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="daf3b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="daf3b-107">Return Value</span></span>  
  
|<span data-ttu-id="daf3b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="daf3b-108">HRESULT</span></span>|<span data-ttu-id="daf3b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="daf3b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="daf3b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="daf3b-110">S_OK</span></span>|<span data-ttu-id="daf3b-111">`SetCLRSyncManager` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="daf3b-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="daf3b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="daf3b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="daf3b-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="daf3b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="daf3b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="daf3b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="daf3b-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="daf3b-115">The call timed out.</span></span>|  
|<span data-ttu-id="daf3b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="daf3b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="daf3b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="daf3b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="daf3b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="daf3b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="daf3b-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="daf3b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="daf3b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="daf3b-120">E_FAIL</span></span>|<span data-ttu-id="daf3b-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="daf3b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="daf3b-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="daf3b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="daf3b-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="daf3b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="daf3b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="daf3b-124">Remarks</span></span>  
 <span data-ttu-id="daf3b-125">Um die Kommunikation zwischen dem Host und der CLR zu vereinfachen, sind Hostingschnittstellen in der Regel paarweise.</span><span class="sxs-lookup"><span data-stu-id="daf3b-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="daf3b-126">Ein Member des Paars wird vom Host implementiert, und der andere Member wird von der CLR implementiert.</span><span class="sxs-lookup"><span data-stu-id="daf3b-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="daf3b-127">Als Host seitige Implementierung entspricht die `IHostSyncManager`-Schnittstelle der von der CLR implementierten `ICLRSyncManager` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="daf3b-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="daf3b-128">Die CLR ruft `SetCLRSyncManager` auf, um eine `ICLRSyncManager`-Instanz bereitzustellen, die der Host der aktuellen `IHostSyncManager` Instanz zuordnen soll.</span><span class="sxs-lookup"><span data-stu-id="daf3b-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daf3b-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="daf3b-129">Requirements</span></span>  
 <span data-ttu-id="daf3b-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daf3b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf3b-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="daf3b-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="daf3b-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="daf3b-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="daf3b-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf3b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf3b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daf3b-134">See also</span></span>

- [<span data-ttu-id="daf3b-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="daf3b-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="daf3b-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="daf3b-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
