---
title: ICLRGCManager2::SetGCStartupLimitsEx-Methode
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d881c71d4725e1a73d743aa098aecc053182947
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918604"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="42603-102">ICLRGCManager2::SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="42603-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="42603-103">Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest.</span><span class="sxs-lookup"><span data-stu-id="42603-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42603-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42603-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42603-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="42603-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="42603-106">in Die angegebene Größe eines Garbage Collection Segments.</span><span class="sxs-lookup"><span data-stu-id="42603-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="42603-107">Die minimale Segmentgröße beträgt 4 MB.</span><span class="sxs-lookup"><span data-stu-id="42603-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="42603-108">Segmente können in Inkrementen von mindestens 1 MB erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="42603-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="42603-109">in Die angegebene maximale Größe für die Generation 0.</span><span class="sxs-lookup"><span data-stu-id="42603-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="42603-110">Die Mindestgröße der Generation 0 beträgt 64 KB.</span><span class="sxs-lookup"><span data-stu-id="42603-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42603-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="42603-111">Return Value</span></span>  
  
|<span data-ttu-id="42603-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42603-112">HRESULT</span></span>|<span data-ttu-id="42603-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42603-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42603-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="42603-114">S_OK</span></span>|<span data-ttu-id="42603-115">`SetGCStartupLimitsEx`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42603-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="42603-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42603-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42603-117">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="42603-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="42603-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="42603-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="42603-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="42603-119">The call timed out.</span></span>|  
|<span data-ttu-id="42603-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="42603-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="42603-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="42603-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="42603-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="42603-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="42603-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="42603-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="42603-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42603-124">E_FAIL</span></span>|<span data-ttu-id="42603-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="42603-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42603-126">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42603-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="42603-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="42603-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42603-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42603-128">Remarks</span></span>  
 <span data-ttu-id="42603-129">Die Werte, `SetGCStartupLimitsEx` die von festgelegt werden, können nur angegeben werden, bevor der Host gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="42603-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="42603-130">Spätere Aufrufe von `SetGCStartupLimitsEx` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="42603-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="42603-131">Wenn Sie einen Parameter ohne Auswirkung auf den anderen Parameter festlegen möchten, geben Sie 0 (null) für den Parameter an, den Sie nicht ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="42603-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42603-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42603-132">Requirements</span></span>  
 <span data-ttu-id="42603-133">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42603-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42603-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42603-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42603-135">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="42603-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42603-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42603-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42603-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42603-137">See also</span></span>

- [<span data-ttu-id="42603-138">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="42603-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="42603-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="42603-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="42603-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42603-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="42603-141">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42603-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
