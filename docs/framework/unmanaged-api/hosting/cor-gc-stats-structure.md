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
ms.openlocfilehash: 3fc212321b28545f62f0a1c2965281d02ac73e40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638105"
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
|`ExplicitGCCount`|Gibt die Anzahl von Garbage Collections, die durch externe Anforderung erzwungen wurden.|  
|`GenCollectionsTaken`|Gibt die Anzahl von Garbage Collections für jede Generierung durchgeführt.|  
|`CommittedKBytes`|Die Gesamtanzahl der Kilobytes, die ein Commit in allen Heaps.|  
|`ReservedKBytes`|Die Gesamtanzahl der Kilobytes, die in allen Heaps reserviert.|  
|`Gen0HeapSizeKBytes`|Die Größe des Heap für Generation 0 in Kilobytes.|  
|`Gen1HeapSizeKBytes`|Die Größe der Generation 1-Heap in Kilobytes.|  
|`Gen2HeapSizeKBytes`|Die Größe des Heap für Generation 2 in Kilobytes.|  
|`LargeObjectHeapSizeKBytes`|Die Größe des Heap für große Objekte in Kilobytes.|  
|`KBytesPromotedFromGen0`|Die Größe in Kilobyte, die Objekte, die von Generation 0 (null) zu Generation hochgestuft.|  
|`KBytesPromotedFromGen1`|Die Größe in Kilobyte, der die Objekte, die Generation zu Generation 2 hochgestuft.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) Methode erfordert die `Flags` Feld der `COR_GC_STATS` Struktur auf ein oder mehrere Werte festgelegt werden die [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) Enumeration angeben, welche Statistiken sind festgelegt werden.  
  
 In der folgende Tabelle sind die Statistiken, die von dieser Struktur den beiden bereitgestellten [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) -Enumerationswerte fest, `COR_GC_COUNTS` und `COR_GC_MEMORYUSAGE`.  
  
|Durch COR_GC_COUNTS angegeben|Durch COR_GC_MEMORYUSAGE angegeben|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Ein Beispiel für die Nutzung lautet wie folgt aus:  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** GCHost.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Automatische Speicherverwaltung](../../../../docs/standard/automatic-memory-management.md)
- [Garbage Collection](../../../../docs/standard/garbage-collection/index.md)
