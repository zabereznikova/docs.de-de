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
ms.openlocfilehash: 9df9263a0356b0c3c1a6d1da950c670f5a020d1e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966230"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="a4bb9-102">ICLRGCManager::GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="a4bb9-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="a4bb9-103">Ruft einen Satz aktueller Statistiken zum Garbage Collection System des Common Language Runtime ab.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4bb9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4bb9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4bb9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a4bb9-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="a4bb9-106">[in, out] Eine [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) -Instanz, die die angeforderte Statistik enthält.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4bb9-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a4bb9-107">Return Value</span></span>  
  
|<span data-ttu-id="a4bb9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4bb9-108">HRESULT</span></span>|<span data-ttu-id="a4bb9-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4bb9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4bb9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4bb9-110">S_OK</span></span>|<span data-ttu-id="a4bb9-111">`GetStats`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="a4bb9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4bb9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4bb9-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4bb9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4bb9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4bb9-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-115">The call timed out.</span></span>|  
|<span data-ttu-id="a4bb9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4bb9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4bb9-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4bb9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4bb9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4bb9-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4bb9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4bb9-120">E_FAIL</span></span>|<span data-ttu-id="a4bb9-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4bb9-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4bb9-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4bb9-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4bb9-124">Remarks</span></span>  
 <span data-ttu-id="a4bb9-125">Die CLR berechnet nur die Statistiken, die durch das `Flags` -Feld von `pStats`angegeben werden, und gibt diese zurück.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="a4bb9-126">Legen Sie `Flags` das-Feld auf einen oder mehrere Werte der [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) -Enumeration fest, um anzugeben, welche Statistiken in der [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) -Struktur festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="a4bb9-127">Es folgt ein Beispiel für die Verwendung:</span><span class="sxs-lookup"><span data-stu-id="a4bb9-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a4bb9-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4bb9-128">Requirements</span></span>  
 <span data-ttu-id="a4bb9-129">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4bb9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4bb9-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a4bb9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4bb9-131">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a4bb9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4bb9-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4bb9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4bb9-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4bb9-133">See also</span></span>

- [<span data-ttu-id="a4bb9-134">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="a4bb9-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="a4bb9-135">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="a4bb9-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="a4bb9-136">COR_GC_STAT_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a4bb9-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="a4bb9-137">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="a4bb9-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="a4bb9-138">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4bb9-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a4bb9-139">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4bb9-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="a4bb9-140">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a4bb9-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="a4bb9-141">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a4bb9-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="a4bb9-142">Hosting</span><span class="sxs-lookup"><span data-stu-id="a4bb9-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
