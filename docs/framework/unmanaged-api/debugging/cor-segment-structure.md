---
title: COR_SEGMENT-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_SEGMENT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_SEGMENT
helpviewer_keywords: COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9414aa1c36ba059d9ee1101f6183dc8a669f9e6f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corsegment-structure"></a>COR_SEGMENT-Struktur
Enthält Informationen zu einem Bereich des Arbeitsspeichers im verwalteten Heap.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`start`|Die Startadresse des Arbeitsspeicherbereichs.|  
|`end`|Die Endadresse für den Speicherbereich.|  
|`gen`|Ein [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) Enumerationsmember, der die Generierung von den Speicherbereich angibt.|  
|`heap`|Die Heap-Anzahl in der der Speicherbereich befindet. Weitere Informationen finden Sie im Abschnitt Hinweise.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COR_SEGMENTS` -Struktur stellt einen Bereich des Arbeitsspeichers im verwalteten Heap dar.  `COR_SEGMENTS`Objekte sind Mitglieder der [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) Auflistungsobjekt, das durch Aufrufen von Werten aufgefüllt ist die[icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) Methode.  
  
 Die `heap` Feld wird die Prozessor-Zahl, die dem Heap gemeldet wird entspricht. Für die Arbeitsstation Garbage Collectors ist der Wert immer 0 (null), Schreibberechtigung Arbeitsstationen nur eine Garbage Collection-Heap an. Für Server-Garbage Collectors entspricht der Wert der Prozessor, dem der Heap zugeordnet ist. Beachten Sie, dass möglicherweise mehr oder weniger Garbagecollection heaps als tatsächliche Prozessoren aufgrund von den Implementierungsdetails der Garbage Collector vorhanden sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
