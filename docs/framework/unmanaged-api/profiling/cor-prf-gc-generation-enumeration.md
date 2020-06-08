---
title: COR_PRF_GC_GENERATION-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
ms.openlocfilehash: b7a068efcf20b2028e9c193567d15b59e582febf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500922"
---
# <a name="cor_prf_gc_generation-enumeration"></a>COR_PRF_GC_GENERATION-Enumeration
Identifiziert eine Garbage Collection-Generierung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3,
    COR_PRF_GC_PINNED_OBJECT_HEAP= 4
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|Das-Objekt wird als Generation 0 gespeichert.|  
|`COR_PRF_GC_GEN_1`|Das Objekt wird als Generation 1 gespeichert.|  
|`COR_PRF_GC_GEN_2`|Das-Objekt wird als Generation 2 gespeichert.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|Das Objekt wird im Heap für große Objekte gespeichert.|  
|`COR_PRF_GC_PINNED_OBJECT_HEAP`|Das Objekt wird im Heap des fixierten Objekts gespeichert.|  
  
## <a name="remarks"></a>Bemerkungen  
 Der Garbage Collector verbessert die Leistung der Speicherverwaltung, indem Objekte basierend auf dem Alter in Generationen aufgeteilt werden. Der Garbage Collector verwendet derzeit drei Generationen, nummerierte 0, 1 und 2, und zwei spezielle Heap Segmente, eine für große Objekte und eine für fixierte Objekte.
  
 Objekte, deren Größe größer ist als ein Schwellenwert, werden im Heap für große Objekte gespeichert. Fixierte Objekte können dem fixierten Objekt Heap zugeordnet werden, um die Leistungseinbußen bei der Zuordnung auf die normalen Heaps zu vermeiden. Andere zugeordnete Objekte beginnen zu Generation 0. Alle Objekte, die nach Garbage Collection in Generation 0 vorhanden sind, werden auf Generation 1 herauf gestuft. Objekte, die nach dem Garbage Collection vorhanden sind, treten in Generation 1 in Generation 2 ein.  
  
 Die Verwendung von Generations bedeutet, dass die Garbage Collector nur mit einer Teilmenge der zugeordneten Objekte gleichzeitig funktionieren muss.  
  
 Die- `COR_PRF_GC_GENERATION` Enumeration wird von der [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) -Struktur verwendet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Profilerstellungsenumerationen](profiling-enumerations.md)
