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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 009f1482de6e1daea21766300b4fb6a3ab0ffc8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432287"
---
# <a name="corgcstats-structure"></a>COR_GC_STATS-Struktur
Stellt Statistiken über Garbage Collection-Mechanismus der common Language Runtime (CLR) bereit.  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`Flags`|Gibt an, welche Feldwerte berechnet und zurückgegeben werden soll.|  
|`ExplicitGCCount`|Gibt die Anzahl der Garbage Collections, die durch externe Anforderung erzwungen wurden.|  
|`GenCollectionsTaken`|Gibt die Anzahl der Garbage Collections für jede Generierung ausgeführt.|  
|`CommittedKBytes`|Die Gesamtanzahl der Kilobytes, die in allen Heaps ein Commit ausgeführt.|  
|`ReservedKBytes`|Die Gesamtanzahl der Kilobytes, die in allen Heaps reserviert.|  
|`Gen0HeapSizeKBytes`|Die Größe in Kilobyte, der die Generation 0-Heap.|  
|`Gen1HeapSizeKBytes`|Die Größe in Kilobyte, die Generation 1-Heapgröße.|  
|`Gen2HeapSizeKBytes`|Die Größe in Kilobyte, die Generation 2-Heapgröße.|  
|`LargeObjectHeapSizeKBytes`|Die Größe des Heap für große Objekte in Kilobytes.|  
|`KBytesPromotedFromGen0`|Die Größe in Kilobyte, der die Objekte, die von Generation 0 (null), die auf Generation höher gestuft.|  
|`KBytesPromotedFromGen1`|Die Größe in Kilobyte, der die Objekte Generation auf Generation 2 hochgestuft.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) Methode erfordert die `Flags` Feld der `COR_GC_STATS` Struktur auf ein oder mehrere Werte festgelegt werden die [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) Enumeration angeben, welche Statistiken sind festgelegt werden.  
  
 Die folgende Tabelle ordnet die Statistiken über diese Struktur auf die beiden [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) Aufzählungswerte `COR_GC_COUNTS` und `COR_GC_MEMORYUSAGE`.  
  
|Durch COR_GC_COUNTS angegeben|Durch COR_GC_MEMORYUSAGE angegeben|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Ein Beispiel für die Verwendung lautet wie folgt:  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** GCHost.idl  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [Automatische Speicherverwaltung](../../../../docs/standard/automatic-memory-management.md)  
 [Garbage Collection](../../../../docs/standard/garbage-collection/index.md)
