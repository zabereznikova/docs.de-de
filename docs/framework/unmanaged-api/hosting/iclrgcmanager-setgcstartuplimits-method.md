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
ms.openlocfilehash: 6aff2c73eeb3360d4ed21c349e3b85194c73b6ec
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380268"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="8f8a3-102">ICLRGCManager::SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="8f8a3-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="8f8a3-103">Legt die Größe der eine Garbage Collection-Segment und die maximale Größe der Garbage Collection-Systems die Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8f8a3-104">Ab .NET Framework 4.5, Sie können festlegen Segmentgröße und Größe von maximal Generation 0 zu Werten größer als `DWORD` mithilfe der [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f8a3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f8a3-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f8a3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f8a3-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="8f8a3-107">[in] Die angegebene Größe der Garbage Collection-Segments.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="8f8a3-108">Die minimale Segmentgröße ist 4 MB.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="8f8a3-109">Segmente können in Inkrementen von 1 MB oder größer sein.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="8f8a3-110">[in] Die angegebene maximale Größe für Generation 0.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="8f8a3-111">Die minimale Generation 0 beträgt 64 KB.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f8a3-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8f8a3-112">Return Value</span></span>  
  
|<span data-ttu-id="8f8a3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f8a3-113">HRESULT</span></span>|<span data-ttu-id="8f8a3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f8a3-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f8a3-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f8a3-115">S_OK</span></span>|<span data-ttu-id="8f8a3-116">`SetGCStartupLimits` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="8f8a3-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8f8a3-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8f8a3-118">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8f8a3-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8f8a3-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8f8a3-120">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-120">The call timed out.</span></span>|  
|<span data-ttu-id="8f8a3-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8f8a3-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8f8a3-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8f8a3-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8f8a3-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8f8a3-124">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8f8a3-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8f8a3-125">E_FAIL</span></span>|<span data-ttu-id="8f8a3-126">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8f8a3-127">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8f8a3-128">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f8a3-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f8a3-129">Remarks</span></span>  
 <span data-ttu-id="8f8a3-130">Die Werte, die `SetGCStartupLimits` legt können nur einmal angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="8f8a3-131">Spätere Aufrufe von `SetGCStartupLimits` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f8a3-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f8a3-132">Requirements</span></span>  
 <span data-ttu-id="8f8a3-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f8a3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f8a3-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8f8a3-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f8a3-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8f8a3-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f8a3-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f8a3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f8a3-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f8a3-137">See also</span></span>

- [<span data-ttu-id="8f8a3-138">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="8f8a3-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="8f8a3-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="8f8a3-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="8f8a3-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f8a3-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="8f8a3-141">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f8a3-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
