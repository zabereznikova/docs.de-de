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
ms.openlocfilehash: efb3d913e1d8ef0c486d7e5e1d9777ae7d88bc71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179334"
---
# <a name="cor_heapobject-structure"></a>COR_HEAPOBJECT-Struktur
Stellt Informationen zu einem Objekt auf dem verwalteten Heap bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`address`|Die Adresse des Objekts im Speicher.|  
|`size`|Die Gesamtgröße des Objekts in Bytes.|  
|`type`|Ein [COR_TYPEID](cor-typeid-structure.md) Token, das den Typ des Objekts darstellt.|  
  
## <a name="remarks"></a>Bemerkungen  
 `COR_HEAPOBJECT`Instanzen können abgerufen werden, indem ein [ICorDebugHeapEnum-Schnittstellenobjekt](icordebugheapenum-interface.md) aufgezählt wird, das durch Aufrufen der [ICorDebugProcess5::EnumerateHeap-Methode](icordebugprocess5-enumerateheap-method.md) aufgefüllt wird.  
  
 Eine `COR_HEAPOBJECT` Instanz stellt Informationen entweder zu einem Liveobjekt auf dem verwalteten Heap oder zu einem Objekt bereit, das nicht von einem Objekt gerootet ist, aber noch nicht vom Garbage Collector gesammelt wurde.  
  
 Für eine bessere `COR_HEAPOBJECT.address` Leistung `CORDB_ADDRESS` ist das Feld ein Wert und kein ICorDebugValue-Schnittstellenwert, der in einem Großteil der Debug-API verwendet wird. Um ein ICorDebugValue-Objekt für eine bestimmte Objektadresse zu erhalten, können Sie den `CORDB_ADDRESS` Wert an die [ICorDebugProcess5::GetObject-Methode](icordebugprocess5-getobject-method.md) übergeben.  
  
 Für eine bessere `COR_HEAPOBJECT.type` Leistung `COR_TYPEID` ist das Feld ein Wert und kein ICorDebugType-Schnittstellenwert, der in einem Großteil der Debug-API verwendet wird. Um ein ICorDebugType-Objekt für eine bestimmte Typ-ID zu erhalten, können Sie den `COR_TYPEID` Wert an die [ICorDebugProcess5::GetTypeForTypeID-Methode](icordebugprocess5-gettypefortypeid-method.md) übergeben.  
  
 Die `COR_HEAPOBJECT` Struktur enthält eine COM-Schnittstelle mit Referenzzählung. Wenn Sie `COR_HEAPOBJECT` eine Instanz aus dem Enumerator abrufen, indem Sie die [ICorDebugHeapEnum::Next-Methode](icordebugheapenum-next-method.md) aufrufen, müssen Sie den Verweis anschließend freigeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
