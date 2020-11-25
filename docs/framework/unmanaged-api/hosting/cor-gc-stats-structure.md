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
ms.openlocfilehash: 53a70c53a06ac55a2dab7c646018d63189ee0b36
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726222"
---
# <a name="cor_gc_stats-structure"></a>COR_GC_STATS-Struktur

Stellt Statistiken zum Garbage Collection Mechanismus des Common Language Runtime (CLR) bereit.  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`Flags`|Gibt an, welche Feldwerte berechnet und zurückgegeben werden sollen.|  
|`ExplicitGCCount`|Gibt die Anzahl der Garbage Collections an, die von einer externen Anforderung erzwungen wurden.|  
|`GenCollectionsTaken`|Gibt die Anzahl der Garbage Collections an, die für jede Generation ausgeführt werden.|  
|`CommittedKBytes`|Die Gesamtanzahl von Kilobyte, die in allen Heaps committet wurden.|  
|`ReservedKBytes`|Die Gesamtanzahl der in allen Heaps reservierten Kilobyte.|  
|`Gen0HeapSizeKBytes`|Die Größe des Heaps der Generation 0 in Kilobyte.|  
|`Gen1HeapSizeKBytes`|Die Größe (in Kilobyte) des "Generation 1"-Heaps.|  
|`Gen2HeapSizeKBytes`|Die Größe des Heap der Generation 2 in Kilobyte.|  
|`LargeObjectHeapSizeKBytes`|Die Größe des großen Objekt Heaps in Kilobyte.|  
|`KBytesPromotedFromGen0`|Die Größe der Objekte, die von Generation 0 zu Generation 1 herauf gestuft werden, in Kilobyte.|  
|`KBytesPromotedFromGen1`|Die Größe der Objekte, die von Generation 1 zu Generation Two herauf gestuft wurden, in Kilobyte.|  
  
## <a name="remarks"></a>Hinweise  

 Die [ICLRGCManager:: GetStats](iclrgcmanager-getstats-method.md) -Methode erfordert, dass das- `Flags` Feld der- `COR_GC_STATS` Struktur auf einen oder mehrere Werte der [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) -Enumeration festgelegt wird, um anzugeben, welche Statistiken festgelegt werden sollen.  
  
 In der folgenden Tabelle sind die Statistiken, die von dieser Struktur bereitgestellt werden, den beiden [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) Enumerationswerten `COR_GC_COUNTS` und zugeordnet `COR_GC_MEMORYUSAGE` .  
  
|Angegeben durch COR_GC_COUNTS|Angegeben durch COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Es folgt ein Beispiel für die Verwendung:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Gchost. idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Strukturen](hosting-structures.md)
- [Automatische Speicherverwaltung](../../../standard/automatic-memory-management.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
