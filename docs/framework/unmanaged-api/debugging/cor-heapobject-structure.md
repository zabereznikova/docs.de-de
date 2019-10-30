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
ms.openlocfilehash: 270360a8950197eca14e02a60554659e5ac7b91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099078"
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`address`|Die Adresse des Objekts im Arbeitsspeicher.|  
|`size`|Die Gesamtgröße des-Objekts in Bytes.|  
|`type`|Ein [COR_TYPEID](cor-typeid-structure.md) -Token, das den Typ des Objekts darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 `COR_HEAPOBJECT` Instanzen können abgerufen werden, indem ein [icordebugheapenum](icordebugheapenum-interface.md) -Schnittstellen Objekt aufgezählt wird, das durch Aufrufen der [ICorDebugProcess5:: enumerateheap](icordebugprocess5-enumerateheap-method.md) -Methode aufgefüllt wird.  
  
 Eine `COR_HEAPOBJECT`-Instanz stellt Informationen entweder über ein Live Objekt im verwalteten Heap oder über ein Objekt bereit, das nicht von einem Objekt betroffen ist, aber noch nicht vom Garbage Collector erfasst wurde.  
  
 Um die Leistung zu verbessern, ist das `COR_HEAPOBJECT.address` Feld ein `CORDB_ADDRESS` Wert und nicht der ICorDebugValue-Schnittstellen Wert, der in einem Großteil der Debug-API verwendet wird. Zum Abrufen eines ICorDebugValue-Objekts für eine angegebene Objekt Adresse können Sie den `CORDB_ADDRESS` Wert an die [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) -Methode übergeben.  
  
 Um die Leistung zu verbessern, ist das `COR_HEAPOBJECT.type` Feld ein `COR_TYPEID` Wert und nicht der ICorDebugType-Schnittstellen Wert, der in einem Großteil der Debug-API verwendet wird. Zum Abrufen eines ICorDebugType-Objekts für eine bestimmte Typ-ID können Sie den `COR_TYPEID` Wert an die [ICorDebugProcess5:: gettypeer fortypeid](icordebugprocess5-gettypefortypeid-method.md) -Methode übergeben.  
  
 Die `COR_HEAPOBJECT`-Struktur enthält eine COM-Schnittstelle mit Verweis Zählung. Wenn Sie eine `COR_HEAPOBJECT` Instanz aus dem Enumerator abrufen, indem Sie die [icordebugheapenum:: Next](icordebugheapenum-next-method.md) -Methode aufrufen, müssen Sie anschließend den Verweis freigeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
