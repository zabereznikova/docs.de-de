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
ms.openlocfilehash: e8d1948a7d0ff23410ba8670628424a4067fb47d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138489"
---
# <a name="icordebugheapenum-interface"></a>ICorDebugHeapEnum-Schnittstelle
Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit. Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|Ruft die angegebene Anzahl von [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanzen ab, die Informationen zu Objekten im verwalteten Heap enthalten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugHeapEnum`-Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.  
  
 Eine `ICorDebugHeapEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) -Methode mit [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanzen aufgefüllt. Jede [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanz in der Auflistung stellt entweder ein Live-Objekt auf dem Heap oder ein Objekt dar, das nicht von einem Objekt betroffen ist, aber noch nicht von der Garbage Collector erfasst wurde. Die [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Objekte in der Auflistung können durch Aufrufen der [icordebugheapenumum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) -Methode aufgelistet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
