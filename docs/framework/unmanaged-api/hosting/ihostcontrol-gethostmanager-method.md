---
title: IHostControl::GetHostManager-Methode
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
ms.openlocfilehash: c23773dce448c8c98d4926dff3fa51100e683fd0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192048"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="83a4e-102">IHostControl::GetHostManager-Methode</span><span class="sxs-lookup"><span data-stu-id="83a4e-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="83a4e-103">Ruft einen Schnittstellen Zeiger auf die Implementierung der-Schnittstelle des Hosts mit dem angegebenen `IID`ab.</span><span class="sxs-lookup"><span data-stu-id="83a4e-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a4e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83a4e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83a4e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="83a4e-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="83a4e-106">in Der `IID` der Schnittstelle, für die der Common Language Runtime (CLR) eine Abfrage durchläuft.</span><span class="sxs-lookup"><span data-stu-id="83a4e-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="83a4e-107">vorgenommen Ein Zeiger auf die vom Host implementierte Schnittstelle oder NULL, wenn der Host diese Schnittstelle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="83a4e-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83a4e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="83a4e-108">Return Value</span></span>  
  
|<span data-ttu-id="83a4e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="83a4e-109">HRESULT</span></span>|<span data-ttu-id="83a4e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83a4e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83a4e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="83a4e-111">S_OK</span></span>|<span data-ttu-id="83a4e-112">`GetHostManager` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="83a4e-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="83a4e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="83a4e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="83a4e-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="83a4e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="83a4e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="83a4e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="83a4e-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="83a4e-116">The call timed out.</span></span>|  
|<span data-ttu-id="83a4e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="83a4e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="83a4e-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="83a4e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="83a4e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="83a4e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="83a4e-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="83a4e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="83a4e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="83a4e-121">E_FAIL</span></span>|<span data-ttu-id="83a4e-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="83a4e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="83a4e-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83a4e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="83a4e-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="83a4e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="83a4e-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="83a4e-125">E_INVALIDARG</span></span>|<span data-ttu-id="83a4e-126">Der angeforderte `IID` ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="83a4e-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="83a4e-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="83a4e-127">E_NOINTERFACE</span></span>|<span data-ttu-id="83a4e-128">Die angeforderte Schnittstelle wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="83a4e-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83a4e-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83a4e-129">Remarks</span></span>  
 <span data-ttu-id="83a4e-130">Die CLR fragt den Host ab, um zu bestimmen, ob eine oder mehrere der folgenden Schnittstellen unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="83a4e-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="83a4e-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="83a4e-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="83a4e-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="83a4e-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="83a4e-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="83a4e-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="83a4e-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="83a4e-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="83a4e-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="83a4e-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="83a4e-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="83a4e-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="83a4e-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="83a4e-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="83a4e-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="83a4e-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="83a4e-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="83a4e-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="83a4e-140">Wenn der Host die angegebene Schnittstelle unterstützt, legt er `ppObject` auf die Implementierung dieser Schnittstelle fest.</span><span class="sxs-lookup"><span data-stu-id="83a4e-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="83a4e-141">Andernfalls wird `ppObject` auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="83a4e-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="83a4e-142">Die CLR ruft `Release` auf Host-Managern nicht auf, auch wenn Sie Sie Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="83a4e-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83a4e-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83a4e-143">Requirements</span></span>  
 <span data-ttu-id="83a4e-144">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83a4e-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83a4e-145">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="83a4e-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83a4e-146">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="83a4e-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83a4e-147">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83a4e-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a4e-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83a4e-148">See also</span></span>

- [<span data-ttu-id="83a4e-149">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83a4e-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
