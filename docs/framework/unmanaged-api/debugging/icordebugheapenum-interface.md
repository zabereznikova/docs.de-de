---
title: ICorDebugHeapEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
ms.openlocfilehash: bed2871c46712490bc4b0520fa1ab8023dbab5cf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794425"
---
# <a name="icordebugheapenum-interface"></a>ICorDebugHeapEnum-Schnittstelle
Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit. Diese Schnittstelle ist eine Unterklasse von der ICorDebugEnum-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](icordebugheapenum-next-method.md)|Ruft die angegebene Anzahl von [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanzen ab, die Informationen zu Objekten im verwalteten Heap enthalten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugHeapEnum`-Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.  
  
 Eine `ICorDebugHeapEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerateheap](icordebugprocess5-enumerateheap-method.md) -Methode mit [COR_HEAPOBJECT](cor-heapobject-structure.md) -Instanzen aufgefüllt. Jede [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanz in der Auflistung stellt entweder ein Live Objekt auf dem Heap oder ein Objekt dar, das nicht von einem Objekt betroffen ist, aber noch nicht vom Garbage Collector erfasst wurde. Die [COR_HEAPOBJECT](cor-heapobject-structure.md) Objekte in der Auflistung können durch Aufrufen der [icordebugheapenumum:: Next](icordebugheapenum-next-method.md) -Methode aufgelistet werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
