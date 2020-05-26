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
ms.openlocfilehash: 25e931ec17cad3508d548fb4ca7e53b0ade3f119
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804952"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="d505c-102">IHostControl::GetHostManager-Methode</span><span class="sxs-lookup"><span data-stu-id="d505c-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="d505c-103">Ruft einen Schnittstellen Zeiger auf die Implementierung der-Schnittstelle des Hosts mit dem angegebenen ab `IID` .</span><span class="sxs-lookup"><span data-stu-id="d505c-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d505c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d505c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d505c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d505c-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="d505c-106">in Der `IID` der Schnittstelle, für die der Common Language Runtime (CLR) eine Abfrage durchläuft.</span><span class="sxs-lookup"><span data-stu-id="d505c-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="d505c-107">vorgenommen Ein Zeiger auf die vom Host implementierte Schnittstelle oder NULL, wenn der Host diese Schnittstelle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d505c-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d505c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d505c-108">Return Value</span></span>  
  
|<span data-ttu-id="d505c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d505c-109">HRESULT</span></span>|<span data-ttu-id="d505c-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d505c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d505c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d505c-111">S_OK</span></span>|<span data-ttu-id="d505c-112">`GetHostManager`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d505c-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="d505c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d505c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d505c-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="d505c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d505c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d505c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d505c-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="d505c-116">The call timed out.</span></span>|  
|<span data-ttu-id="d505c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d505c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d505c-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d505c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d505c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d505c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d505c-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="d505c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d505c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d505c-121">E_FAIL</span></span>|<span data-ttu-id="d505c-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d505c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d505c-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="d505c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d505c-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d505c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d505c-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d505c-125">E_INVALIDARG</span></span>|<span data-ttu-id="d505c-126">Der angeforderte `IID` ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="d505c-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="d505c-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="d505c-127">E_NOINTERFACE</span></span>|<span data-ttu-id="d505c-128">Die angeforderte Schnittstelle wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d505c-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d505c-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d505c-129">Remarks</span></span>  
 <span data-ttu-id="d505c-130">Die CLR fragt den Host ab, um zu bestimmen, ob eine oder mehrere der folgenden Schnittstellen unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="d505c-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="d505c-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="d505c-131">IHostMemoryManager</span></span>](ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="d505c-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d505c-132">IHostTaskManager</span></span>](ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="d505c-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="d505c-133">IHostThreadPoolManager</span></span>](ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="d505c-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="d505c-134">IHostIoCompletionManager</span></span>](ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="d505c-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d505c-135">IHostSyncManager</span></span>](ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="d505c-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="d505c-136">IHostAssemblyManager</span></span>](ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="d505c-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="d505c-137">IHostGCManager</span></span>](ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="d505c-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="d505c-138">IHostPolicyManager</span></span>](ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="d505c-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="d505c-139">IHostSecurityManager</span></span>](ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="d505c-140">Wenn der Host die angegebene Schnittstelle unterstützt, legt er die `ppObject` Implementierung dieser Schnittstelle fest.</span><span class="sxs-lookup"><span data-stu-id="d505c-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="d505c-141">Andernfalls wird `ppObject` auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d505c-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="d505c-142">Die CLR ruft `Release` auf Host-Managern nicht auf, auch wenn Sie Sie Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="d505c-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d505c-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d505c-143">Requirements</span></span>  
 <span data-ttu-id="d505c-144">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d505c-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d505c-145">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d505c-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d505c-146">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d505c-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d505c-147">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d505c-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d505c-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d505c-148">See also</span></span>

- [<span data-ttu-id="d505c-149">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d505c-149">IHostControl Interface</span></span>](ihostcontrol-interface.md)
