---
title: ICLRGCManager::SetGCStartupLimits-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.SetGCStartupLimits
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1fd0c31fd6f988d4ee36bfe140b95ec258d4214e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="c7449-102">ICLRGCManager::SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="c7449-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="c7449-103">Legt die Größe der Garbage Collection-Segment und die maximale Größe der der Garbage Collection-System Generation 0.</span><span class="sxs-lookup"><span data-stu-id="c7449-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c7449-104">Beginnend mit der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], Sie können die Größe des Segments festlegen und die Größe von maximal Generation 0 zu Werte größer als `DWORD` mithilfe der [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="c7449-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7449-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7449-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7449-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7449-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="c7449-107">[in] Die angegebene Größe der Garbage Collection-Segment.</span><span class="sxs-lookup"><span data-stu-id="c7449-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="c7449-108">Die minimale Segmentgröße beträgt 4 MB.</span><span class="sxs-lookup"><span data-stu-id="c7449-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="c7449-109">Segmente können in Inkrementen von 1 MB oder größer sein.</span><span class="sxs-lookup"><span data-stu-id="c7449-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="c7449-110">[in] Die angegebene maximale Größe für Generation 0.</span><span class="sxs-lookup"><span data-stu-id="c7449-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="c7449-111">Die minimale Bereich der Generation 0-Größe beträgt 64 KB.</span><span class="sxs-lookup"><span data-stu-id="c7449-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7449-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c7449-112">Return Value</span></span>  
  
|<span data-ttu-id="c7449-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7449-113">HRESULT</span></span>|<span data-ttu-id="c7449-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7449-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7449-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7449-115">S_OK</span></span>|<span data-ttu-id="c7449-116">`SetGCStartupLimits`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c7449-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="c7449-117">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="c7449-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c7449-118">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c7449-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c7449-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c7449-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c7449-120">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c7449-120">The call timed out.</span></span>|  
|<span data-ttu-id="c7449-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c7449-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c7449-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c7449-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c7449-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c7449-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c7449-124">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c7449-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c7449-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7449-125">E_FAIL</span></span>|<span data-ttu-id="c7449-126">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c7449-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7449-127">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="c7449-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c7449-128">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c7449-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7449-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7449-129">Remarks</span></span>  
 <span data-ttu-id="c7449-130">Die Werte, die `SetGCStartupLimits` Mengen können nur einmal angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c7449-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="c7449-131">Spätere Aufrufe von `SetGCStartupLimits` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c7449-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7449-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7449-132">Requirements</span></span>  
 <span data-ttu-id="c7449-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7449-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7449-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7449-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7449-135">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c7449-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7449-136">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7449-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7449-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7449-137">See Also</span></span>  
 [<span data-ttu-id="c7449-138">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="c7449-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="c7449-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="c7449-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="c7449-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7449-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="c7449-141">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7449-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
