---
title: COR_HEAPOBJECT-Struktur
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f179b58ff8eb51e2843780d3212cf38ed7d13216
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168830"
---
# <a name="corheapobject-structure"></a>COR_HEAPOBJECT-Struktur
Stellt Informationen zu einem Objekt auf dem verwalteten Heap bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`address`|Die Adresse des Objekts im Arbeitsspeicher.|  
|`size`|Die Gesamtgröße des Objekts, in Bytes.|  
|`type`|Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Token, das den Typ des Objekts darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 `COR_HEAPOBJECT` Instanzen abgerufen werden können, durch das Auflisten einer [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) Schnittstellenobjekt, das durch den Aufruf enthält das [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) Methode.  
  
 Ein `COR_HEAPOBJECT` Instanz enthält Informationen, die entweder über ein aktives Objekt auf dem verwalteten Heap oder über ein Objekt, das nicht wurden die nutzungsbeschränkungen entfernt jedes Objekt, aber noch nicht vom Garbage Collector übergeben wurde.  
  
 Zur Verbesserung der Leistung der `COR_HEAPOBJECT.address` Feld ist ein `CORDB_ADDRESS` Wert anstelle der ICorDebugValue-Schnittstelle in einem Großteil der Debug-API verwendete Wert. Um ICorDebugValue-Objekts für eine Adresse für die angegebene Objekt zu erhalten, können Sie übergeben die `CORDB_ADDRESS` Wert der [icordebugprocess5:: GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) Methode.  
  
 Zur Verbesserung der Leistung der `COR_HEAPOBJECT.type` Feld ist ein `COR_TYPEID` Wert anstelle der ICorDebugType-Schnittstelle in einem Großteil der Debug-API verwendete Wert. Um ein ICorDebugType für einen angegebenen Typ-ID zu erhalten, können Sie übergeben die `COR_TYPEID` Wert der [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) Methode.  
  
 Die `COR_HEAPOBJECT` Struktur enthält eine COM-Schnittstelle mit referenzzählung. Wenn Sie abrufen eine `COR_HEAPOBJECT` Instanz aus dem Enumerator durch Aufrufen der [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) -Methode, Sie müssen anschließend den Verweis frei.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
