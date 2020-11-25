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
ms.openlocfilehash: 54af02b48dabdf2042763954805f0d454323ac89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726365"
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
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`address`|Die Adresse des Objekts im Arbeitsspeicher.|  
|`size`|Die Gesamtgröße des-Objekts in Bytes.|  
|`type`|Ein [COR_TYPEID](cor-typeid-structure.md) Token, das den Typ des Objekts darstellt.|  
  
## <a name="remarks"></a>Hinweise  

 `COR_HEAPOBJECT` Instanzen können abgerufen werden, indem ein [icordebugheapenum](icordebugheapenum-interface.md) -Schnittstellen Objekt aufgezählt wird, das durch Aufrufen der [ICorDebugProcess5:: enumerateheap](icordebugprocess5-enumerateheap-method.md) -Methode ausgefüllt wird.  
  
 Eine- `COR_HEAPOBJECT` Instanz stellt Informationen entweder über ein Live Objekt im verwalteten Heap oder über ein Objekt bereit, das nicht von einem Objekt betroffen ist, aber noch nicht von der Garbage Collector erfasst wurde.  
  
 Um eine bessere Leistung zu erzielen, `COR_HEAPOBJECT.address` ist das Feld ein `CORDB_ADDRESS` Wert und nicht der ICorDebugValue-Schnittstellen Wert, der in einem Großteil der Debug-API verwendet wird. Zum Abrufen eines ICorDebugValue-Objekts für eine angegebene Objekt Adresse können Sie den `CORDB_ADDRESS` Wert an die [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) -Methode übergeben.  
  
 Um eine bessere Leistung zu erzielen, `COR_HEAPOBJECT.type` ist das Feld ein `COR_TYPEID` Wert und nicht der ICorDebugType-Schnittstellen Wert, der in einem Großteil der Debug-API verwendet wird. Zum Abrufen eines ICorDebugType-Objekts für eine bestimmte Typ-ID können Sie den `COR_TYPEID` Wert an die [ICorDebugProcess5:: gettyps](icordebugprocess5-gettypefortypeid-method.md) -Methode übergeben.  
  
 Die `COR_HEAPOBJECT` -Struktur enthält eine COM-Schnittstelle mit Verweis Zählung. Wenn Sie eine- `COR_HEAPOBJECT` Instanz aus dem Enumerator abrufen, indem Sie die [icordebugheapenum:: Next](icordebugheapenum-next-method.md) -Methode aufrufen, müssen Sie anschließend den-Verweis freigeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
