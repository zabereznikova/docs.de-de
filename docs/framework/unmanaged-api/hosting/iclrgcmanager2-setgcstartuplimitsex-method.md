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
ms.openlocfilehash: 9885149a71147db6eef13958b8ef825caa1d6ec6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176382"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="f2250-102">ICLRGCManager2::SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="f2250-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="f2250-103">Legt die Größe eines Garbage Collection-Segments und die maximale Größe der Generation 0 des Garbage Collection-Systems fest.</span><span class="sxs-lookup"><span data-stu-id="f2250-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2250-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2250-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2250-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2250-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="f2250-106">[in] Die angegebene Größe eines Garbage Collection-Segments.</span><span class="sxs-lookup"><span data-stu-id="f2250-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="f2250-107">Die minimale Segmentgröße beträgt 4 MB.</span><span class="sxs-lookup"><span data-stu-id="f2250-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="f2250-108">Segmente können in Schritten von 1 MB oder größer vergrößert werden.</span><span class="sxs-lookup"><span data-stu-id="f2250-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="f2250-109">[in] Die angegebene maximale Größe für Generation 0.</span><span class="sxs-lookup"><span data-stu-id="f2250-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="f2250-110">Die Minimale Größe der Generation 0 beträgt 64 KB.</span><span class="sxs-lookup"><span data-stu-id="f2250-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2250-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f2250-111">Return Value</span></span>  
  
|<span data-ttu-id="f2250-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2250-112">HRESULT</span></span>|<span data-ttu-id="f2250-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2250-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2250-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2250-114">S_OK</span></span>|<span data-ttu-id="f2250-115">`SetGCStartupLimitsEx`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2250-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="f2250-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2250-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2250-117">Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f2250-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f2250-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2250-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2250-119">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="f2250-119">The call timed out.</span></span>|  
|<span data-ttu-id="f2250-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2250-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2250-121">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="f2250-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2250-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2250-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2250-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="f2250-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2250-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2250-124">E_FAIL</span></span>|<span data-ttu-id="f2250-125">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f2250-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2250-126">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2250-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2250-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f2250-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2250-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f2250-128">Remarks</span></span>  
 <span data-ttu-id="f2250-129">Die Werte, die festgelegt werden, können nur angegeben werden, `SetGCStartupLimitsEx` bevor der Host gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f2250-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="f2250-130">Spätere `SetGCStartupLimitsEx` Aufrufe werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f2250-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="f2250-131">Um einen der beiden Parameter festzulegen, ohne den anderen zu beeinflussen, geben Sie 0 (Null) für den Parameter an, den Sie nicht ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f2250-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2250-132">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f2250-132">Requirements</span></span>  
 <span data-ttu-id="f2250-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2250-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2250-134">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2250-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2250-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f2250-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2250-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2250-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2250-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2250-137">See also</span></span>

- [<span data-ttu-id="f2250-138">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="f2250-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="f2250-139">Automatische Speicherbereinigung</span><span class="sxs-lookup"><span data-stu-id="f2250-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="f2250-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2250-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="f2250-141">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2250-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
