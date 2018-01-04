---
title: COR_GC_STATS-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_STATS
helpviewer_keywords: COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02a775be4976760b354a492e7252a67ef04eace9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corgcstats-structure"></a><span data-ttu-id="111c4-102">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="111c4-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="111c4-103">Stellt Statistiken über Garbage Collection-Mechanismus der common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="111c4-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="111c4-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;   
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;   
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="111c4-105">Member</span><span class="sxs-lookup"><span data-stu-id="111c4-105">Members</span></span>  
  
|<span data-ttu-id="111c4-106">Member</span><span class="sxs-lookup"><span data-stu-id="111c4-106">Member</span></span>|<span data-ttu-id="111c4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="111c4-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="111c4-108">Gibt an, welche Feldwerte berechnet und zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="111c4-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="111c4-109">Gibt die Anzahl der Garbage Collections, die durch externe Anforderung erzwungen wurden.</span><span class="sxs-lookup"><span data-stu-id="111c4-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="111c4-110">Gibt die Anzahl der Garbage Collections für jede Generierung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="111c4-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="111c4-111">Die Gesamtanzahl der Kilobytes, die in allen Heaps ein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="111c4-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="111c4-112">Die Gesamtanzahl der Kilobytes, die in allen Heaps reserviert.</span><span class="sxs-lookup"><span data-stu-id="111c4-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="111c4-113">Die Größe in Kilobyte, der die Generation 0-Heap.</span><span class="sxs-lookup"><span data-stu-id="111c4-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="111c4-114">Die Größe in Kilobyte, die Generation 1-Heapgröße.</span><span class="sxs-lookup"><span data-stu-id="111c4-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="111c4-115">Die Größe in Kilobyte, die Generation 2-Heapgröße.</span><span class="sxs-lookup"><span data-stu-id="111c4-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="111c4-116">Die Größe des Heap für große Objekte in Kilobytes.</span><span class="sxs-lookup"><span data-stu-id="111c4-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="111c4-117">Die Größe in Kilobyte, der die Objekte, die von Generation 0 (null), die auf Generation höher gestuft.</span><span class="sxs-lookup"><span data-stu-id="111c4-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="111c4-118">Die Größe in Kilobyte, der die Objekte Generation auf Generation 2 hochgestuft.</span><span class="sxs-lookup"><span data-stu-id="111c4-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="111c4-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="111c4-119">Remarks</span></span>  
 <span data-ttu-id="111c4-120">Die [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) Methode erfordert die `Flags` Feld der `COR_GC_STATS` Struktur auf ein oder mehrere Werte festgelegt werden die [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) Enumeration angeben, welche Statistiken sind festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="111c4-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="111c4-121">Die folgende Tabelle ordnet die Statistiken über diese Struktur auf die beiden [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) Aufzählungswerte `COR_GC_COUNTS` und `COR_GC_MEMORYUSAGE`.</span><span class="sxs-lookup"><span data-stu-id="111c4-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="111c4-122">Durch COR_GC_COUNTS angegeben</span><span class="sxs-lookup"><span data-stu-id="111c4-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="111c4-123">Durch COR_GC_MEMORYUSAGE angegeben</span><span class="sxs-lookup"><span data-stu-id="111c4-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="111c4-124">Ein Beispiel für die Verwendung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="111c4-124">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="111c4-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="111c4-125">Requirements</span></span>  
 <span data-ttu-id="111c4-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="111c4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="111c4-127">**Header:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="111c4-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="111c4-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="111c4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="111c4-129">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="111c4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111c4-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="111c4-130">See Also</span></span>  
 [<span data-ttu-id="111c4-131">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="111c4-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="111c4-132">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="111c4-132">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="111c4-133">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="111c4-133">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
