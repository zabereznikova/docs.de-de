---
title: ICorDebugHeapSegmentEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: 42126d15c64175f35bba89a1ab6abacc64128012
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704629"
---
# <a name="icordebugheapsegmentenum-interface"></a>ICorDebugHeapSegmentEnum-Schnittstelle

Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit. Diese Schnittstelle ist eine Unterklasse von der ICorDebugEnum-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Next-Methode](icordebugheapsegmentenum-next-method.md)|Ruft die angegebene Anzahl von [COR_SEGMENT](cor-segment-structure.md) Instanzen ab, die Informationen zu Regionen des verwalteten Heaps enthalten.|  
  
## <a name="remarks"></a>Hinweise  

 Die `ICorDebugHeapSegmentEnum` Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.  
  
 Eine `ICorDebugHeapSegmentEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerateheapregions](icordebugprocess5-enumerateheapregions-method.md) -Methode mit [COR_SEGMENT](cor-segment-structure.md) Instanzen aufgefüllt. Die [COR_SEGMENT](cor-segment-structure.md) -Objekte in der-Auflistung können durch Aufrufen der [icordebugheapsegmenterum:: Next](icordebugheapsegmentenum-next-method.md) -Methode aufgelistet werden.  
  
 Ein `ICorDebugHeapSegmentEnum` Auflistungs Objekt listet alle Speicherbereiche auf, die verwaltete Objekte enthalten können, garantiert jedoch nicht, dass sich verwaltete Objekte tatsächlich in diesen Regionen befinden. Sie kann Informationen über leere oder reservierte Speicherbereiche enthalten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
