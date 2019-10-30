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
ms.openlocfilehash: e9679029cd54ac44832add9bc4f47f8c8e9a26a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138450"
---
# <a name="icordebugheapsegmentenum-interface"></a>ICorDebugHeapSegmentEnum-Schnittstelle
Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit. Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|Ruft die angegebene Anzahl von [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanzen ab, die Informationen zu Regionen des verwalteten Heaps enthalten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugHeapSegmentEnum`-Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.  
  
 Eine `ICorDebugHeapSegmentEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) -Methode mit [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanzen aufgefüllt. Die [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Objekte in der Auflistung können durch Aufrufen der [icordebugheapsegmenterum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) -Methode aufgelistet werden.  
  
 Ein `ICorDebugHeapSegmentEnum` Auflistungs Objekt listet alle Speicherbereiche auf, die verwaltete Objekte enthalten können, garantiert jedoch nicht, dass sich verwaltete Objekte tatsächlich in diesen Regionen befinden. Sie kann Informationen über leere oder reservierte Speicherbereiche enthalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
