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
ms.openlocfilehash: bb4a8f7ff3ee54474804e3e5620dcce7c9f79fb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726612"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`domain`|Ein Zeiger auf die Anwendungsdomäne, zu der das Handle oder das Objekt gehört. Der Wert kann sein `null` .|  
|`location`|Eine ICorDebugValue-oder ICorDebugReferenceValue-Schnittstelle, die dem Objekt entspricht, das in die Garbage Collection aufgenommen werden soll.|  
|`type`|Ein [corgkreferencetype](corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, woher der Stamm stammt. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
|`extraData`|Zusätzliche Daten zu dem Objekt, für das die Garbage Collection durchgeführt werden soll. Diese Informationen hängen von der Quelle des Objekts ab, wie im Feld angegeben `type` . Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
  
## <a name="remarks"></a>Hinweise  

 Das `type` Feld ist ein [corgkreferencetype](corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, woher der Verweis stammt. Ein bestimmter `COR_GC_REFERENCE` Wert kann eine der folgenden Arten von verwalteten Objekten widerspiegeln:  
  
- Objekte aus allen verwalteten Stapeln ( `CorGCReferenceType.CorReferenceStack` ). Dies schließt sowohl Live Verweise in verwaltetem Code als auch Objekte ein, die vom Common Language Runtime erstellt wurden.  
  
- Objekte aus der Handle-Tabelle ( `CorGCReferenceType.CorHandle*` ). Dies schließt starke Verweise ( `HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT` ) sowie statische Variablen in einem Modul ein.  
  
- Objekte aus der Finalizerwarteschlange ( `CorGCReferenceType.CorReferenceFinalizer` ). Die Finalizer-Warteschlange wurzelt Objekte, bis der Finalizer ausgeführt wurde.  
  
 Das `extraData` Feld enthält zusätzliche Daten, abhängig von der Quelle (oder dem Typ) des Verweises. Mögliche Werte:  
  
- `DependentSource`. Wenn den `type` Wert `CorGCREferenceType.CorHandleStrongDependent` hat, ist dieses Feld das Objekt, das, wenn es aktiv ist, das Objekt, für das die Garbage Collection durchgeführt werden soll `COR_GC_REFERENCE.Location` .  
  
- `RefCount`. Wenn den `type` Wert `CorGCREferenceType.CorHandleStrongRefCount` hat, ist dieses Feld der Verweis Zähler des Handles.  
  
- `Size`. Wenn den `type` Wert `CorGCREferenceType.CorHandleStrongSizedByref` hat, ist dieses Feld die letzte Größe der Objektstruktur, für die der Garbage Collector die Objekt Stämme berechnet hat. Beachten Sie, dass diese Berechnung nicht unbedingt auf dem neuesten Stand ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
