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
ms.openlocfilehash: 2ab0c38645a8e5fbd9e71b3c1787e88bfe2c0604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176525"
---
# <a name="cor_gc_stats-structure"></a>COR_GC_STATS-Struktur
Stellt Statistiken über den Garbage Collection-Mechanismus der Common Language Runtime (CLR) bereit.  
  
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`Flags`|Gibt an, welche Feldwerte berechnet und zurückgegeben werden sollen.|  
|`ExplicitGCCount`|Gibt die Anzahl der Garbage Collections an, die durch externe Anforderung erzwungen wurden.|  
|`GenCollectionsTaken`|Gibt die Anzahl der Garbage Collections an, die für jede Generation ausgeführt werden.|  
|`CommittedKBytes`|Die Gesamtanzahl der Kilobytes, die in allen Heaps festgeschrieben wurden.|  
|`ReservedKBytes`|Die Gesamtanzahl der in allen Heaps reservierten Kilobytes.|  
|`Gen0HeapSizeKBytes`|Die Größe des Heaps "Generation-Null" in Kilobyte.|  
|`Gen1HeapSizeKBytes`|Die Größe des Heaps generation-one in Kilobyte.|  
|`Gen2HeapSizeKBytes`|Die Größe des Heaps der Generation 2 in Kilobyte.|  
|`LargeObjectHeapSizeKBytes`|Die Größe des heaps für große Objekte in Kilobyte.|  
|`KBytesPromotedFromGen0`|Die Größe der Objekte, die von Generation Null auf Generation 1 heraufgestuft werden, in Kilobyte.|  
|`KBytesPromotedFromGen1`|Die Größe der Objekte, die von Generation eins auf Generation zwei heraufgestuft werden, in Kilobyte.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die [ICLRGCManager::GetStats-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) erfordert, dass das `Flags` Feld der `COR_GC_STATS` Struktur auf einen oder mehrere Werte der [COR_GC_STAT_TYPES-Enumeration](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) festgelegt wird, um anzugeben, welche Statistiken festgelegt werden sollen.  
  
 In der folgenden Tabelle werden die von dieser Struktur bereitgestellten `COR_GC_COUNTS` `COR_GC_MEMORYUSAGE`Statistiken den beiden COR_GC_STAT_TYPES-Enumerationswerten und zugeordnet. [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
  
|Angegeben durch COR_GC_COUNTS|Angegeben durch COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Ein Beispiel für die Verwendung ist wie folgt:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** GCHost.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Automatische Speicherverwaltung](../../../standard/automatic-memory-management.md)
- [Automatische Speicherbereinigung](../../../standard/garbage-collection/index.md)
