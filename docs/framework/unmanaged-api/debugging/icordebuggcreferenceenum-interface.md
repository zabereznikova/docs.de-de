---
title: ICorDebugGCReferenceEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: 49f89f7d36e74b1fa5921230d7dc6d271d4c0883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134632"
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum-Schnittstelle
Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|Ruft die angegebene Anzahl von [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) -Instanzen ab, die Informationen über Objekte enthalten, für die eine Garbage Collection durchgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugGCReferenceEnum`-Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.  
  
 Eine `ICorDebugGCReferenceEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) -Methode mit [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) -Instanzen aufgefüllt. [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) -Objekte können durch Aufrufen der [icordebuggcreferen:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) -Methode aufgezählt werden.  
  
 Die [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) -Objekte in der Auflistung, die von dieser Methode aufgefüllt werden, stellen drei Arten von Objekten dar:  
  
- Objekte aus allen verwalteten stapeln. Dies schließt sowohl Live Verweise in verwaltetem Code als auch Objekte ein, die vom Common Language Runtime erstellt wurden.  
  
- Objekte aus der Handle-Tabelle. Dies schließt starke Verweise (`HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT`) und statische Variablen in einem Modul ein.  
  
- Objekte aus der Finalizerwarteschlange. Die Finalizer-Warteschlange wurzelt Objekte, bis der Finalizer ausgeführt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
