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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0178e2a7877803644bb25e6700306d7ac2ef2d4f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215890"
---
# <a name="corprfgcgeneration-enumeration"></a>COR_PRF_GC_GENERATION-Enumeration
Identifiziert eine Garbage Collection-Generation.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`COR_PRF_GC_GEN_0`|Das Objekt wird als Generation 0 gespeichert.|  
|`COR_PRF_GC_GEN_1`|Das Objekt wird als Generation 1 gespeichert.|  
|`COR_PRF_GC_GEN_2`|Das Objekt wird als Generation 2 gespeichert.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|Das Objekt befindet sich im Heap für große Objekte.|  
  
## <a name="remarks"></a>Hinweise  
 Der Garbage Collector verbessert die speicherleistung für die Verwaltung durch Division Objekte in Generationen, die basierend auf dem Alter. Der Garbage Collector verwendet derzeit drei Generationen: 0, 1 und 2 sowie einem besonderen Heap-Segment, das für große Objekte verwendet wird. Objekte, deren Größe einen bestimmten Wert übersteigt, werden in den großen Objektheap gespeichert. Andere zugeordneten Objekte beginnen, die Sie die Generation 0 gehören. Alle Objekte, die vorhanden sind, nachdem die Garbagecollection in Generation 0 tritt werden auf Generation 1 höher gestuft. Objekte, die vorhanden sind, nachdem die Garbagecollection in Generation 1 tritt, in Generation 2 verschieben.  
  
 Die Verwendung von Generationen bedeutet, dass der Garbage Collector zu jedem Zeitpunkt nur eine Teilmenge der zugeordneten Objekte zusammenarbeiten.  
  
 Die `COR_PRF_GC_GENERATION` Enumeration wird verwendet, durch die [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
