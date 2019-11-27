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
ms.openlocfilehash: d01b864be231e5b0a3fd72dc2f3636a87c8cae83
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448627"
---
# <a name="cor_prf_gc_generation-enumeration"></a>COR_PRF_GC_GENERATION-Enumeration
Identifiziert eine Garbage Collection-Generierung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|Das-Objekt wird als Generation 0 gespeichert.|  
|`COR_PRF_GC_GEN_1`|Das Objekt wird als Generation 1 gespeichert.|  
|`COR_PRF_GC_GEN_2`|Das-Objekt wird als Generation 2 gespeichert.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|Das Objekt wird im Heap für große Objekte gespeichert.|  
  
## <a name="remarks"></a>Hinweise  
 Der Garbage Collector verbessert die Leistung der Speicherverwaltung, indem Objekte basierend auf dem Alter in Generationen aufgeteilt werden. Der Garbage Collector verwendet derzeit drei Generationen mit den Nummerierungen 0, 1 und 2 sowie ein spezielles Heap Segment, das für große Objekte verwendet wird. Objekte, deren Größe größer ist als ein bestimmter Wert, werden im Heap für große Objekte gespeichert. Andere zugeordnete Objekte beginnen zu Generation 0. Alle Objekte, die nach Garbage Collection in Generation 0 vorhanden sind, werden auf Generation 1 herauf gestuft. Objekte, die nach dem Garbage Collection vorhanden sind, treten in Generation 1 in Generation 2 ein.  
  
 Die Verwendung von Generations bedeutet, dass die Garbage Collector nur mit einer Teilmenge der zugeordneten Objekte gleichzeitig funktionieren muss.  
  
 Die `COR_PRF_GC_GENERATION`-Enumeration wird von der [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) -Struktur verwendet.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
