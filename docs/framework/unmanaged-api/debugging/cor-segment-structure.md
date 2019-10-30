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
ms.openlocfilehash: 0370c74bde9ca5bdbd0fd03515f4b174ddd0a39a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132319"
---
# <a name="cor_segment-structure"></a>COR_SEGMENT-Struktur
Enthält Informationen zu einem Bereich des Arbeitsspeichers im verwalteten Heap.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`start`|Die Startadresse des Arbeitsspeicherbereichs|  
|`end`|Die Endadresse des Arbeitsspeicherbereichs|  
|`gen`|Ein [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md)-Enumerationsmember, der die Generierung des Arbeitsspeicherbereichs angibt.|  
|`heap`|Die Nummer des Heaps, in dem sich der Arbeitsspeicherbereich befindet. Weitere Informationen finden Sie im Abschnitt Hinweise.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COR_SEGMENTS`-Struktur stellt einen Bereich des Arbeitsspeichers im verwalteten Heap dar.  `COR_SEGMENTS`-Objekte sind Member des Auflistungsobjekts [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md), das durch einen Aufruf der Methode [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) aufgefüllt wird.  
  
 Das `heap`-Feld ist die Nummer des Prozessors, der dem gemeldeten Heap entspricht. Für Arbeitsstations-Garbage Collectors ist der Wert immer 0 (null), da Arbeitsstationen über nur einen Garbage Collection-Heap verfügen. Für Server-Garbage Collectors entspricht der Wert dem Prozessor, an den der Heap angefügt ist. Beachten Sie, dass es aufgrund der Implementierungsdetails des Garbage Collectors mehr oder weniger Garbage Collection-Heaps als tatsächliche Prozessoren geben kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
