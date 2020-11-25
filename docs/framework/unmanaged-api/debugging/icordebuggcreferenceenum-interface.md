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
ms.openlocfilehash: 12ce800cb83ef4f79710aa441b50be860526023c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728120"
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum-Schnittstelle

Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Next-Methode](icordebuggcreferenceenum-next-method.md)|Ruft die angegebene Anzahl von [COR_GC_REFERENCE](cor-gc-reference-structure.md) Instanzen ab, die Informationen über Objekte enthalten, für die eine Garbage Collection durchgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  

 Die `ICorDebugGCReferenceEnum` Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.  
  
 Eine `ICorDebugGCReferenceEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerategcreferences](icordebugprocess5-enumerategcreferences-method.md) -Methode mit [COR_GC_REFERENCE](cor-gc-reference-structure.md) Instanzen aufgefüllt. [COR_GC_REFERENCE](cor-gc-reference-structure.md) Objekte können durch Aufrufen der [icordebuggcreferen:: Next](icordebuggcreferenceenum-next-method.md) -Methode aufgezählt werden.  
  
 Die [COR_GC_REFERENCE](cor-gc-reference-structure.md) Objekte in der Auflistung, die von dieser Methode aufgefüllt werden, stellen drei Arten von Objekten dar:  
  
- Objekte aus allen verwalteten stapeln. Dies schließt sowohl Live Verweise in verwaltetem Code als auch Objekte ein, die vom Common Language Runtime erstellt wurden.  
  
- Objekte aus der Handle-Tabelle. Dies schließt starke Verweise ( `HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT` ) sowie statische Variablen in einem Modul ein.  
  
- Objekte aus der Finalizerwarteschlange. Die Finalizer-Warteschlange wurzelt Objekte, bis der Finalizer ausgeführt wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
