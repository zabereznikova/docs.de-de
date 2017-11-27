---
title: IHostControl::GetHostManager-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl.GetHostManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c711fb2ddf5d21cd8e122a35ebd0b8a5ce0e752f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="2d42f-102">IHostControl::GetHostManager-Methode</span><span class="sxs-lookup"><span data-stu-id="2d42f-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="2d42f-103">Ruft einen Schnittstellenzeiger auf dem Host-Implementierung der Schnittstelle mit dem angegebenen `IID`.</span><span class="sxs-lookup"><span data-stu-id="2d42f-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d42f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d42f-104">Syntax</span></span>  
  
```  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d42f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d42f-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="2d42f-106">[in] Die `IID` der Schnittstelle, die die common Language Runtime (CLR) abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="2d42f-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="2d42f-107">[out] Ein Zeiger auf den Host implementierte Schnittstelle oder Null, wenn der Host diese Schnittstelle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d42f-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d42f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2d42f-108">Return Value</span></span>  
  
|<span data-ttu-id="2d42f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d42f-109">HRESULT</span></span>|<span data-ttu-id="2d42f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d42f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d42f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d42f-111">S_OK</span></span>|<span data-ttu-id="2d42f-112">`GetHostManager`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d42f-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="2d42f-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="2d42f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d42f-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="2d42f-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d42f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d42f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d42f-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2d42f-116">The call timed out.</span></span>|  
|<span data-ttu-id="2d42f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d42f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d42f-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2d42f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d42f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d42f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d42f-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="2d42f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d42f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d42f-121">E_FAIL</span></span>|<span data-ttu-id="2d42f-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2d42f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d42f-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="2d42f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d42f-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2d42f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2d42f-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2d42f-125">E_INVALIDARG</span></span>|<span data-ttu-id="2d42f-126">Der angeforderte `IID` ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="2d42f-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="2d42f-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="2d42f-127">E_NOINTERFACE</span></span>|<span data-ttu-id="2d42f-128">Die angeforderte Schnittstelle wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d42f-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d42f-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d42f-129">Remarks</span></span>  
 <span data-ttu-id="2d42f-130">Die CLR fragt den Host aus, um zu bestimmen, ob es sich um eine oder mehrere der folgenden Schnittstellen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2d42f-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
-   [<span data-ttu-id="2d42f-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="2d42f-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
-   [<span data-ttu-id="2d42f-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2d42f-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
-   [<span data-ttu-id="2d42f-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="2d42f-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
-   [<span data-ttu-id="2d42f-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="2d42f-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
-   [<span data-ttu-id="2d42f-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="2d42f-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
-   [<span data-ttu-id="2d42f-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="2d42f-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
-   [<span data-ttu-id="2d42f-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="2d42f-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
-   [<span data-ttu-id="2d42f-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="2d42f-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
-   [<span data-ttu-id="2d42f-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="2d42f-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="2d42f-140">Wenn der Host die angegebene Schnittstelle unterstützt, wird `ppObject` an seine Implementierung dieser Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2d42f-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="2d42f-141">Andernfalls wird `ppObject` auf Null.</span><span class="sxs-lookup"><span data-stu-id="2d42f-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="2d42f-142">Ruft die CLR nicht `Release` auf Hostmanager verwenden, selbst wenn er heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="2d42f-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d42f-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d42f-143">Requirements</span></span>  
 <span data-ttu-id="2d42f-144">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d42f-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d42f-145">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d42f-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d42f-146">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2d42f-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d42f-147">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d42f-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d42f-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d42f-148">See Also</span></span>  
 [<span data-ttu-id="2d42f-149">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d42f-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
