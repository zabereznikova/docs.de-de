---
title: COR_GC_REFERENCE-Struktur
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc0b67621f77c0741e0b63b84ab1794530d6280b
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274226"
---
# <a name="cor_gc_reference-structure"></a>COR_GC_REFERENCE-Struktur
Enthält Informationen zu einem Objekt, das speicherbereinigt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`domain`|Ein Zeiger auf die Anwendungsdomäne, zu der das Handle oder das Objekt gehört. Der Wert kann sein `null`.|  
|`location`|Eine ICorDebugValue-oder ICorDebugReferenceValue-Schnittstelle, die dem Objekt entspricht, das in die Garbage Collection aufgenommen werden soll.|  
|`type`|Ein [corgkreferencetype](corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, woher der Stamm stammt. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
|`extraData`|Zusätzliche Daten zu dem Objekt, für das die Garbage Collection durchgeführt werden soll. Diese Informationen hängen von `type` der Quelle des Objekts ab, wie im Feld angegeben. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
  
## <a name="remarks"></a>Hinweise  
 Das `type` Feld ist ein [corgkreferencetype](corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, woher der Verweis stammt. Ein bestimmter `COR_GC_REFERENCE` Wert kann eine der folgenden Arten von verwalteten Objekten widerspiegeln:  
  
- Objekte aus allen verwalteten Stapeln (`CorGCReferenceType.CorReferenceStack`). Dies schließt sowohl Live Verweise in verwaltetem Code als auch Objekte ein, die vom Common Language Runtime erstellt wurden.  
  
- Objekte aus der Handle-Tabelle`CorGCReferenceType.CorHandle*`(). Dies schließt starke Verweise (`HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT`) sowie statische Variablen in einem Modul ein.  
  
- Objekte aus der Finalizerwarteschlange (`CorGCReferenceType.CorReferenceFinalizer`). Die Finalizer-Warteschlange wurzelt Objekte, bis der Finalizer ausgeführt wurde.  
  
 Das `extraData` Feld enthält zusätzliche Daten, abhängig von der Quelle (oder dem Typ) des Verweises. Dabei sind folgende Werte möglich:  
  
- `DependentSource`. Wenn den `type` `CorGCREferenceType.CorHandleStrongDependent`Wert hat, ist dieses Feld das Objekt, das, wenn es aktiv ist, das Objekt, für das `COR_GC_REFERENCE.Location`die Garbage Collection durchgeführt werden soll.  
  
- `RefCount`. Wenn den `type` `CorGCREferenceType.CorHandleStrongRefCount`Wert hat, ist dieses Feld der Verweis Zähler des Handles.  
  
- `Size`. Wenn den `type` `CorGCREferenceType.CorHandleStrongSizedByref`Wert hat, ist dieses Feld die letzte Größe der Objektstruktur, für die der Garbage Collector die Objekt Stämme berechnet hat. Beachten Sie, dass diese Berechnung nicht unbedingt auf dem neuesten Stand ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
