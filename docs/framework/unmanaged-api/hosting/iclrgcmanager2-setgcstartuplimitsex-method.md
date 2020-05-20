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
ms.openlocfilehash: f71c3b738d8e1f1670ac870d5e8c23ea9182d924
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703969"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="6b84e-102">ICLRGCManager2::SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="6b84e-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="6b84e-103">Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest.</span><span class="sxs-lookup"><span data-stu-id="6b84e-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b84e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b84e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b84e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b84e-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="6b84e-106">in Die angegebene Größe eines Garbage Collection Segments.</span><span class="sxs-lookup"><span data-stu-id="6b84e-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="6b84e-107">Die minimale Segmentgröße beträgt 4 MB.</span><span class="sxs-lookup"><span data-stu-id="6b84e-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="6b84e-108">Segmente können in Inkrementen von mindestens 1 MB erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="6b84e-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="6b84e-109">in Die angegebene maximale Größe für die Generation 0.</span><span class="sxs-lookup"><span data-stu-id="6b84e-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="6b84e-110">Die Mindestgröße der Generation 0 beträgt 64 KB.</span><span class="sxs-lookup"><span data-stu-id="6b84e-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b84e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6b84e-111">Return Value</span></span>  
  
|<span data-ttu-id="6b84e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b84e-112">HRESULT</span></span>|<span data-ttu-id="6b84e-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6b84e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b84e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b84e-114">S_OK</span></span>|<span data-ttu-id="6b84e-115">`SetGCStartupLimitsEx`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6b84e-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="6b84e-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6b84e-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6b84e-117">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="6b84e-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6b84e-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6b84e-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6b84e-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="6b84e-119">The call timed out.</span></span>|  
|<span data-ttu-id="6b84e-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b84e-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6b84e-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="6b84e-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6b84e-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6b84e-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6b84e-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="6b84e-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6b84e-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6b84e-124">E_FAIL</span></span>|<span data-ttu-id="6b84e-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6b84e-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6b84e-126">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b84e-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6b84e-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="6b84e-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b84e-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b84e-128">Remarks</span></span>  
 <span data-ttu-id="6b84e-129">Die Werte, die von `SetGCStartupLimitsEx` festgelegt werden, können nur angegeben werden, bevor der Host gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="6b84e-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="6b84e-130">Spätere Aufrufe von `SetGCStartupLimitsEx` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6b84e-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="6b84e-131">Wenn Sie einen Parameter ohne Auswirkung auf den anderen Parameter festlegen möchten, geben Sie 0 (null) für den Parameter an, den Sie nicht ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="6b84e-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b84e-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b84e-132">Requirements</span></span>  
 <span data-ttu-id="6b84e-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b84e-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b84e-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="6b84e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b84e-135">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6b84e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b84e-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b84e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b84e-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b84e-137">See also</span></span>

- [<span data-ttu-id="6b84e-138">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="6b84e-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="6b84e-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="6b84e-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="6b84e-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b84e-140">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="6b84e-141">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b84e-141">ICLRGCManager2 Interface</span></span>](iclrgcmanager2-interface.md)
