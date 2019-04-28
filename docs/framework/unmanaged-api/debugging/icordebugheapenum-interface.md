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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79ef77e52e14fede9949121e7ec4575d10b820c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775582"
---
# <a name="icordebugheapenum-interface"></a>ICorDebugHeapEnum-Schnittstelle
Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit. Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|Ruft die angegebene Anzahl von [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen zu Objekten im verwalteten Heap enthalten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugHeapEnum` -Schnittstelle implementiert, die ICorDebugEnum-Schnittstelle.  
  
 Ein `ICorDebugHeapEnum` Instanz wird mit aufgefüllt [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen durch Aufrufen der [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) Methode. Jede [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen in der Auflistung darstellt, entweder ein aktives Objekt auf dem Heap oder ein Objekt, das nicht wurden die nutzungsbeschränkungen entfernt jedes Objekt, aber noch nicht vom Garbage Collector übergeben wurde. Die [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte in der Auflistung aufgelistet werden können, durch den Aufruf der [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
