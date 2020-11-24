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
ms.openlocfilehash: e340dcb5dc093f965e6c08a24a3d65ed0aa6e07a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680823"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="dff32-102">IHostControl::GetHostManager-Methode</span><span class="sxs-lookup"><span data-stu-id="dff32-102">IHostControl::GetHostManager Method</span></span>

<span data-ttu-id="dff32-103">Ruft einen Schnittstellen Zeiger auf die Implementierung der-Schnittstelle des Hosts mit dem angegebenen ab `IID` .</span><span class="sxs-lookup"><span data-stu-id="dff32-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dff32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dff32-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dff32-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dff32-105">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="dff32-106">in Der `IID` der Schnittstelle, für die der Common Language Runtime (CLR) eine Abfrage durchläuft.</span><span class="sxs-lookup"><span data-stu-id="dff32-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="dff32-107">vorgenommen Ein Zeiger auf die vom Host implementierte Schnittstelle oder NULL, wenn der Host diese Schnittstelle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dff32-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dff32-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dff32-108">Return Value</span></span>  
  
|<span data-ttu-id="dff32-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dff32-109">HRESULT</span></span>|<span data-ttu-id="dff32-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dff32-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dff32-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dff32-111">S_OK</span></span>|<span data-ttu-id="dff32-112">`GetHostManager` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dff32-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="dff32-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dff32-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dff32-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="dff32-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dff32-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dff32-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dff32-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="dff32-116">The call timed out.</span></span>|  
|<span data-ttu-id="dff32-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dff32-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dff32-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="dff32-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dff32-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dff32-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dff32-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="dff32-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dff32-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dff32-121">E_FAIL</span></span>|<span data-ttu-id="dff32-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="dff32-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dff32-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="dff32-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dff32-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="dff32-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dff32-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dff32-125">E_INVALIDARG</span></span>|<span data-ttu-id="dff32-126">Der angeforderte `IID` ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="dff32-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="dff32-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="dff32-127">E_NOINTERFACE</span></span>|<span data-ttu-id="dff32-128">Die angeforderte Schnittstelle wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dff32-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dff32-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dff32-129">Remarks</span></span>  

 <span data-ttu-id="dff32-130">Die CLR fragt den Host ab, um zu bestimmen, ob eine oder mehrere der folgenden Schnittstellen unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="dff32-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="dff32-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="dff32-131">IHostMemoryManager</span></span>](ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="dff32-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="dff32-132">IHostTaskManager</span></span>](ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="dff32-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="dff32-133">IHostThreadPoolManager</span></span>](ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="dff32-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="dff32-134">IHostIoCompletionManager</span></span>](ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="dff32-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="dff32-135">IHostSyncManager</span></span>](ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="dff32-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="dff32-136">IHostAssemblyManager</span></span>](ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="dff32-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="dff32-137">IHostGCManager</span></span>](ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="dff32-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="dff32-138">IHostPolicyManager</span></span>](ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="dff32-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="dff32-139">IHostSecurityManager</span></span>](ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="dff32-140">Wenn der Host die angegebene Schnittstelle unterstützt, legt er die `ppObject` Implementierung dieser Schnittstelle fest.</span><span class="sxs-lookup"><span data-stu-id="dff32-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="dff32-141">Andernfalls wird `ppObject` auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dff32-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="dff32-142">Die CLR ruft `Release` auf Host-Managern nicht auf, auch wenn Sie Sie Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="dff32-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dff32-143">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dff32-143">Requirements</span></span>  

 <span data-ttu-id="dff32-144">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dff32-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dff32-145">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="dff32-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dff32-146">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dff32-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dff32-147">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dff32-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff32-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dff32-148">See also</span></span>

- [<span data-ttu-id="dff32-149">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dff32-149">IHostControl Interface</span></span>](ihostcontrol-interface.md)
