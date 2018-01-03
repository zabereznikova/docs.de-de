---
title: ICLRGCManager2::SetGCStartupLimitsEx-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2.SetGCStartupLimitsEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 371d6d32b3f9f5da0411234438972a8d2df4cc3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="0f6f1-102">ICLRGCManager2::SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="0f6f1-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="0f6f1-103">Legt die Größe der Garbage Collection-Segment und die maximale Größe der der Garbage Collection-System Generation 0.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f6f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f6f1-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f6f1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f6f1-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="0f6f1-106">[in] Die angegebene Größe der Garbage Collection-Segment.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="0f6f1-107">Die minimale Segmentgröße beträgt 4 MB.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="0f6f1-108">Segmente können in Inkrementen von 1 MB oder größer sein.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="0f6f1-109">[in] Die angegebene maximale Größe für Generation 0.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="0f6f1-110">Die minimale Bereich der Generation 0-Größe beträgt 64 KB.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f6f1-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0f6f1-111">Return Value</span></span>  
  
|<span data-ttu-id="0f6f1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f6f1-112">HRESULT</span></span>|<span data-ttu-id="0f6f1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f6f1-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f6f1-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f6f1-114">S_OK</span></span>|<span data-ttu-id="0f6f1-115">`SetGCStartupLimitsEx`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="0f6f1-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="0f6f1-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f6f1-117">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f6f1-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f6f1-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f6f1-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-119">The call timed out.</span></span>|  
|<span data-ttu-id="0f6f1-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f6f1-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f6f1-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f6f1-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f6f1-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f6f1-123">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f6f1-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f6f1-124">E_FAIL</span></span>|<span data-ttu-id="0f6f1-125">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f6f1-126">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f6f1-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f6f1-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f6f1-128">Remarks</span></span>  
 <span data-ttu-id="0f6f1-129">Die Werte, die `SetGCStartupLimitsEx` Mengen können nur vor dem Starten des Hosts angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="0f6f1-130">Spätere Aufrufe von `SetGCStartupLimitsEx` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="0f6f1-131">Beide Parameter festlegen, ohne die anderen zu beeinflussen möchten, geben Sie 0 (null) für den Parameter, die, den Sie nicht ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="0f6f1-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f6f1-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f6f1-132">Requirements</span></span>  
 <span data-ttu-id="0f6f1-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f6f1-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f6f1-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0f6f1-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f6f1-135">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0f6f1-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f6f1-136">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f6f1-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f6f1-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f6f1-137">See Also</span></span>  
 [<span data-ttu-id="0f6f1-138">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="0f6f1-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="0f6f1-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="0f6f1-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="0f6f1-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f6f1-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="0f6f1-141">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f6f1-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
