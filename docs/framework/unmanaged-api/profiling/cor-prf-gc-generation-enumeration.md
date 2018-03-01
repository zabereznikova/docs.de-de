---
title: COR_PRF_GC_GENERATION-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69eec0c2dfccacee4c54c9f2493da523812259aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcgeneration-enumeration"></a>COR_PRF_GC_GENERATION-Enumeration
Identifiziert eine Garbage Collection-Generierung.  
  
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
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|Das Objekt wird in den großen Objektheap gespeichert.|  
  
## <a name="remarks"></a>Hinweise  
 Der Garbage Collector verbessert die Leistung der Speicher-Management von Division Objekten in Generationen basierend auf dem Alter. Der Garbage Collector verwendet derzeit drei Generationen: 0, 1 und 2 sowie einem besonderen Heap-Segment, das für große Objekte verwendet wird. Objekte, deren Größe einen bestimmten Wert übersteigt, werden in den großen Objektheap gespeichert. Andere zugeordnete Objekte Anfangs gehören zu Generation 0. Alle Objekte, die nach Garbagecollection in Generation 0 tritt vorhanden sind, werden auf Generation 1 höher gestuft. Objekte, die nach dem Auftreten einer Garbagecollection in Generation 1 vorhanden, die in Generation 2 verschoben werden.  
  
 Die Verwendung von Generationen bedeutet, dass der Garbage Collector hat jeweils nur eine Teilmenge von zugeordneten Objekten arbeiten.  
  
 Die `COR_PRF_GC_GENERATION` Enumeration wird verwendet, durch die [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
