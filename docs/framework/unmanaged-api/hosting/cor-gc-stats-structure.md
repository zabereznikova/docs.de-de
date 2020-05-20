---
title: COR_GC_STATS-Struktur
ms.date: 03/30/2017
api_name:
- COR_GC_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STATS
helpviewer_keywords:
- COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type:
- apiref
ms.openlocfilehash: 8446960d0746a864c44febbbe4a4d0313d6dcd4d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616711"
---
# <a name="cor_gc_stats-structure"></a><span data-ttu-id="68049-102">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="68049-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="68049-103">Stellt Statistiken zum Garbage Collection Mechanismus des Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="68049-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68049-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68049-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="68049-105">Member</span><span class="sxs-lookup"><span data-stu-id="68049-105">Members</span></span>  
  
|<span data-ttu-id="68049-106">Member</span><span class="sxs-lookup"><span data-stu-id="68049-106">Member</span></span>|<span data-ttu-id="68049-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68049-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="68049-108">Gibt an, welche Feldwerte berechnet und zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="68049-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="68049-109">Gibt die Anzahl der Garbage Collections an, die von einer externen Anforderung erzwungen wurden.</span><span class="sxs-lookup"><span data-stu-id="68049-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="68049-110">Gibt die Anzahl der Garbage Collections an, die für jede Generation ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="68049-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="68049-111">Die Gesamtanzahl von Kilobyte, die in allen Heaps committet wurden.</span><span class="sxs-lookup"><span data-stu-id="68049-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="68049-112">Die Gesamtanzahl der in allen Heaps reservierten Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="68049-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="68049-113">Die Größe des Heaps der Generation 0 in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="68049-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="68049-114">Die Größe (in Kilobyte) des "Generation 1"-Heaps.</span><span class="sxs-lookup"><span data-stu-id="68049-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="68049-115">Die Größe des Heap der Generation 2 in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="68049-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="68049-116">Die Größe des großen Objekt Heaps in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="68049-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="68049-117">Die Größe der Objekte, die von Generation 0 zu Generation 1 herauf gestuft werden, in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="68049-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="68049-118">Die Größe der Objekte, die von Generation 1 zu Generation Two herauf gestuft wurden, in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="68049-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68049-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68049-119">Remarks</span></span>  
 <span data-ttu-id="68049-120">Die [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) -Methode erfordert, dass das- `Flags` Feld der- `COR_GC_STATS` Struktur auf einen oder mehrere Werte der [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) -Enumeration festgelegt wird, um anzugeben, welche Statistiken festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="68049-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="68049-121">In der folgenden Tabelle sind die Statistiken, die von dieser Struktur bereitgestellt werden, den beiden [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) Enumerationswerten `COR_GC_COUNTS` und zugeordnet `COR_GC_MEMORYUSAGE` .</span><span class="sxs-lookup"><span data-stu-id="68049-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="68049-122">Angegeben durch COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="68049-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="68049-123">Angegeben durch COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="68049-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="68049-124">Es folgt ein Beispiel für die Verwendung:</span><span class="sxs-lookup"><span data-stu-id="68049-124">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="68049-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68049-125">Requirements</span></span>  
 <span data-ttu-id="68049-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68049-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68049-127">**Header:** Gchost. idl</span><span class="sxs-lookup"><span data-stu-id="68049-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="68049-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="68049-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68049-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68049-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68049-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68049-130">See also</span></span>

- [<span data-ttu-id="68049-131">Hostingstrukturen</span><span class="sxs-lookup"><span data-stu-id="68049-131">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="68049-132">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="68049-132">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="68049-133">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="68049-133">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
