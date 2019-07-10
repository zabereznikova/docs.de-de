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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6187da564a62b8c30abdc6a150f0df45d565615
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763871"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="c1bd2-102">IHostControl::GetHostManager-Methode</span><span class="sxs-lookup"><span data-stu-id="c1bd2-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="c1bd2-103">Ruft einen Schnittstellenzeiger auf den Host für die Implementierung der Schnittstelle ab, mit dem angegebenen `IID`.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1bd2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1bd2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1bd2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c1bd2-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="c1bd2-106">[in] Die `IID` der Schnittstelle, die für die common Language Runtime (CLR) abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="c1bd2-107">[out] Ein Zeiger auf den Host implementierte Schnittstelle oder Null, wenn der Host diese Schnittstelle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1bd2-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c1bd2-108">Return Value</span></span>  
  
|<span data-ttu-id="c1bd2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1bd2-109">HRESULT</span></span>|<span data-ttu-id="c1bd2-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1bd2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1bd2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c1bd2-111">S_OK</span></span>|<span data-ttu-id="c1bd2-112">`GetHostManager` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="c1bd2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c1bd2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c1bd2-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c1bd2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c1bd2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c1bd2-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-116">The call timed out.</span></span>|  
|<span data-ttu-id="c1bd2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c1bd2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c1bd2-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c1bd2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c1bd2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c1bd2-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c1bd2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c1bd2-121">E_FAIL</span></span>|<span data-ttu-id="c1bd2-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c1bd2-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c1bd2-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c1bd2-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c1bd2-125">E_INVALIDARG</span></span>|<span data-ttu-id="c1bd2-126">Die angeforderte `IID` ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="c1bd2-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="c1bd2-127">E_NOINTERFACE</span></span>|<span data-ttu-id="c1bd2-128">Die angeforderte Schnittstelle wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1bd2-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1bd2-129">Remarks</span></span>  
 <span data-ttu-id="c1bd2-130">Die CLR fragt den Host, um zu bestimmen, ob es sich um eine oder mehrere der folgenden Schnittstellen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c1bd2-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="c1bd2-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="c1bd2-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="c1bd2-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c1bd2-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="c1bd2-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="c1bd2-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="c1bd2-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c1bd2-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="c1bd2-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="c1bd2-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="c1bd2-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="c1bd2-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="c1bd2-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="c1bd2-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="c1bd2-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c1bd2-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="c1bd2-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="c1bd2-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="c1bd2-140">Wenn der Host die angegebene Schnittstelle unterstützt, wird `ppObject` an seine Implementierung dieser Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="c1bd2-141">Andernfalls wird `ppObject` auf Null.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="c1bd2-142">Die CLR ruft nicht `Release` auf Hostmanager, auch wenn er heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="c1bd2-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1bd2-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1bd2-143">Requirements</span></span>  
 <span data-ttu-id="c1bd2-144">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1bd2-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1bd2-145">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1bd2-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1bd2-146">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c1bd2-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1bd2-147">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1bd2-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1bd2-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1bd2-148">See also</span></span>

- [<span data-ttu-id="c1bd2-149">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1bd2-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
