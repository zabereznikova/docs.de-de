---
title: ICLRGCManager::GetStats-Methode
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 784a879b262008e1d999498fcbf4b43bb1137e24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674244"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="52cce-102">ICLRGCManager::GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="52cce-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="52cce-103">Ruft einen Satz von aktuellen Statistiken über die common Language Runtime die Garbage Collection-System ab.</span><span class="sxs-lookup"><span data-stu-id="52cce-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52cce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52cce-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52cce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="52cce-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="52cce-106">[in, out] Ein [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) -Instanz, die die angeforderte Statistik enthält.</span><span class="sxs-lookup"><span data-stu-id="52cce-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52cce-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="52cce-107">Return Value</span></span>  
  
|<span data-ttu-id="52cce-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52cce-108">HRESULT</span></span>|<span data-ttu-id="52cce-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52cce-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52cce-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="52cce-110">S_OK</span></span>|<span data-ttu-id="52cce-111">`GetStats` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="52cce-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="52cce-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52cce-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52cce-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="52cce-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52cce-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52cce-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52cce-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="52cce-115">The call timed out.</span></span>|  
|<span data-ttu-id="52cce-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52cce-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52cce-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="52cce-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52cce-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52cce-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52cce-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="52cce-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52cce-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52cce-120">E_FAIL</span></span>|<span data-ttu-id="52cce-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="52cce-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52cce-122">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52cce-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52cce-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="52cce-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52cce-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52cce-124">Remarks</span></span>  
 <span data-ttu-id="52cce-125">Die CLR wird berechnet, und gibt nur die Statistiken mit den vom angegebenen die `Flags` Feld `pStats`.</span><span class="sxs-lookup"><span data-stu-id="52cce-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="52cce-126">Festlegen der `Flags` Feld auf eine oder mehrere Werte der [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) Enumeration, welche Statistiken in der [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) -Struktur sind festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="52cce-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="52cce-127">Ein Beispiel für die Nutzung lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="52cce-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="52cce-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52cce-128">Requirements</span></span>  
 <span data-ttu-id="52cce-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52cce-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52cce-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="52cce-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52cce-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="52cce-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52cce-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52cce-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52cce-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52cce-133">See also</span></span>
- [<span data-ttu-id="52cce-134">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="52cce-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="52cce-135">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="52cce-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="52cce-136">COR_GC_STAT_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="52cce-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="52cce-137">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="52cce-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="52cce-138">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52cce-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="52cce-139">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52cce-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="52cce-140">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="52cce-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="52cce-141">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="52cce-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="52cce-142">Hosting</span><span class="sxs-lookup"><span data-stu-id="52cce-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
