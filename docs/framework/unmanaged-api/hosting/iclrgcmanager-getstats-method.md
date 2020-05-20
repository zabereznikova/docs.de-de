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
ms.openlocfilehash: 1e881b4a55a99bac3f9ca0e8db1556807b888f13
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616963"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="b966b-102">ICLRGCManager::GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="b966b-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="b966b-103">Ruft einen Satz aktueller Statistiken zum Garbage Collection System des Common Language Runtime ab.</span><span class="sxs-lookup"><span data-stu-id="b966b-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b966b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b966b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b966b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b966b-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="b966b-106">[in, out] Eine [COR_GC_STATS](cor-gc-stats-structure.md) -Instanz, die die angeforderte Statistik enthält.</span><span class="sxs-lookup"><span data-stu-id="b966b-106">[in, out] A [COR_GC_STATS](cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b966b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b966b-107">Return Value</span></span>  
  
|<span data-ttu-id="b966b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b966b-108">HRESULT</span></span>|<span data-ttu-id="b966b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b966b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b966b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b966b-110">S_OK</span></span>|<span data-ttu-id="b966b-111">`GetStats`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b966b-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="b966b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b966b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b966b-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b966b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b966b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b966b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b966b-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="b966b-115">The call timed out.</span></span>|  
|<span data-ttu-id="b966b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b966b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b966b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b966b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b966b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b966b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b966b-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="b966b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b966b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b966b-120">E_FAIL</span></span>|<span data-ttu-id="b966b-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b966b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b966b-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b966b-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b966b-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b966b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b966b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b966b-124">Remarks</span></span>  
 <span data-ttu-id="b966b-125">Die CLR berechnet nur die Statistiken, die durch das-Feld von angegeben werden, und gibt diese zurück `Flags` `pStats` .</span><span class="sxs-lookup"><span data-stu-id="b966b-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="b966b-126">Legen Sie das- `Flags` Feld auf einen oder mehrere Werte der [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) -Enumeration fest, um anzugeben, welche Statistiken in der [COR_GC_STATS](cor-gc-stats-structure.md) Struktur festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b966b-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="b966b-127">Es folgt ein Beispiel für die Verwendung:</span><span class="sxs-lookup"><span data-stu-id="b966b-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b966b-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b966b-128">Requirements</span></span>  
 <span data-ttu-id="b966b-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b966b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b966b-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b966b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b966b-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b966b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b966b-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b966b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b966b-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b966b-133">See also</span></span>

- [<span data-ttu-id="b966b-134">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="b966b-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="b966b-135">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="b966b-135">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="b966b-136">COR_GC_STAT_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b966b-136">COR_GC_STAT_TYPES Enumeration</span></span>](cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="b966b-137">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="b966b-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="b966b-138">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b966b-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="b966b-139">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b966b-139">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="b966b-140">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b966b-140">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="b966b-141">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b966b-141">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b966b-142">Hosting</span><span class="sxs-lookup"><span data-stu-id="b966b-142">Hosting</span></span>](index.md)
