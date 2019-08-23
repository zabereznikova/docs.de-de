---
title: ICLRGCManager::SetGCStartupLimits-Methode
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29311f00f5ac4b61380b57cdd9fda07ec7de1b23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966203"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="5a90d-102">ICLRGCManager::SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="5a90d-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="5a90d-103">Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest.</span><span class="sxs-lookup"><span data-stu-id="5a90d-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5a90d-104">Beginnend mit dem .NET Framework 4,5 können Sie die Segmentgröße und die maximale Generation 0-Größe auf Werte `DWORD` festlegen, die größer als sind, indem Sie die [ICLRGCManager2:: setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) -Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="5a90d-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a90d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a90d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a90d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a90d-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="5a90d-107">in Die angegebene Größe eines Garbage Collection Segments.</span><span class="sxs-lookup"><span data-stu-id="5a90d-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="5a90d-108">Die minimale Segmentgröße beträgt 4 MB.</span><span class="sxs-lookup"><span data-stu-id="5a90d-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="5a90d-109">Segmente können in Inkrementen von mindestens 1 MB erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="5a90d-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="5a90d-110">in Die angegebene maximale Größe für die Generation 0.</span><span class="sxs-lookup"><span data-stu-id="5a90d-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="5a90d-111">Die Mindestgröße der Generation 0 beträgt 64 KB.</span><span class="sxs-lookup"><span data-stu-id="5a90d-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a90d-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5a90d-112">Return Value</span></span>  
  
|<span data-ttu-id="5a90d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a90d-113">HRESULT</span></span>|<span data-ttu-id="5a90d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a90d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a90d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a90d-115">S_OK</span></span>|<span data-ttu-id="5a90d-116">`SetGCStartupLimits`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5a90d-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="5a90d-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a90d-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a90d-118">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5a90d-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a90d-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a90d-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a90d-120">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="5a90d-120">The call timed out.</span></span>|  
|<span data-ttu-id="5a90d-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a90d-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a90d-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="5a90d-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a90d-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a90d-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a90d-124">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="5a90d-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a90d-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a90d-125">E_FAIL</span></span>|<span data-ttu-id="5a90d-126">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5a90d-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a90d-127">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a90d-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a90d-128">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5a90d-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a90d-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a90d-129">Remarks</span></span>  
 <span data-ttu-id="5a90d-130">Die Werte, `SetGCStartupLimits` die von festgelegt werden, können nur einmal angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5a90d-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="5a90d-131">Spätere Aufrufe von `SetGCStartupLimits` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="5a90d-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a90d-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5a90d-132">Requirements</span></span>  
 <span data-ttu-id="5a90d-133">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a90d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a90d-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a90d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a90d-135">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5a90d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a90d-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a90d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a90d-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a90d-137">See also</span></span>

- [<span data-ttu-id="5a90d-138">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="5a90d-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="5a90d-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="5a90d-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="5a90d-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a90d-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5a90d-141">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a90d-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
