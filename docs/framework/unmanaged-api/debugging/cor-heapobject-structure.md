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
ms.openlocfilehash: 91e64bb2e1c8a7b11fe70024eb4a4fa1717c06e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407348"
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
 `COR_HEAPOBJECT` Instanzen können durch aufzählen abgerufen werden ein [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) Schnittstellenobjekt, das durch den Aufruf enthält die [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) Methode.  
  
 Ein `COR_HEAPOBJECT` Instanz enthält Informationen über ein aktives Objekt auf dem verwalteten Heap oder über ein Objekt, das ist keines Objekt als Stamm, aber noch nicht vom Garbage Collector erfasst.  
  
 Aus Leistungsgründen die `COR_HEAPOBJECT.address` Feld ist ein `CORDB_ADDRESS` Wert statt ICorDebugValue-Schnittstelle im Großteil der Debug-API verwendete Wert. Um ICorDebugValue-Objekts für eine Adresse für die angegebene Objekt zu erhalten, übergeben Sie die `CORDB_ADDRESS` -Wert an die [icordebugprocess5:: GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) Methode.  
  
 Aus Leistungsgründen die `COR_HEAPOBJECT.type` Feld ist ein `COR_TYPEID` Wert anstelle der ICorDebugType-Schnittstelle im Großteil der Debug-API verwendete Wert. Um ein ICorDebugType für einen angegebenen Typ-ID zu erhalten, übergeben Sie die `COR_TYPEID` -Wert an die [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) Methode.  
  
 Die `COR_HEAPOBJECT` Struktur umfasst eine COM-Schnittstelle mit referenzzählung. Wenn Sie Abrufen einer `COR_HEAPOBJECT` Instanz aus dem Enumerator durch Aufrufen der [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) -Methode, Sie müssen den Verweis anschließend freigeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
