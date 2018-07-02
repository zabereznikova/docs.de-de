---
title: COR_SEGMENT-Struktur
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: deea4e6128eace0ffa539d77bb63f7629eb72354
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207403"
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
  
|Member|description|  
|------------|-----------------|  
|`start`|Die Startadresse des Arbeitsspeicherbereichs|  
|`end`|Die Endadresse des Arbeitsspeicherbereichs|  
|`gen`|Ein [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)-Enumerationsmember, der die Generierung des Arbeitsspeicherbereichs angibt.|  
|`heap`|Die Nummer des Heaps, in dem sich der Arbeitsspeicherbereich befindet. Weitere Informationen finden Sie im Abschnitt Hinweise.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COR_SEGMENTS`-Struktur stellt einen Bereich des Arbeitsspeichers im verwalteten Heap dar.  `COR_SEGMENTS`-Objekte sind Member des Auflistungsobjekts [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md), das durch einen Aufruf der Methode [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) aufgefüllt wird.  
  
 Das `heap`-Feld ist die Nummer des Prozessors, der dem gemeldeten Heap entspricht. Für Arbeitsstation-Garbage Collectors ist der Wert immer 0 (null), da Arbeitsstationen nur über einen Garbage Collection-Heap verfügen. Für Server-Garbage Collector entspricht der Wert dem Prozessor, dem der Heap angefügt ist. Beachten Sie, dass es aufgrund der Implementierungsdetails des Garbage Collectors mehr oder weniger Garbage Collection-Heaps als tatsächliche Prozessoren geben kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
