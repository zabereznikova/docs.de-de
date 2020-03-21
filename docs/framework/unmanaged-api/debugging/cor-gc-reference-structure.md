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
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179320"
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`domain`|Ein Zeiger auf die Anwendungsdomäne, zu der das Handle oder Objekt gehört. Sein Wert `null`kann .|  
|`location`|Entweder eine ICorDebugValue- oder eine ICorDebugReferenceValue-Schnittstelle, die dem zu garbagecollected Objekt entspricht.|  
|`type`|Ein [CorGCReferenceType](corgcreferencetype-enumeration.md) CorGCReferenceType-Enumerationswert, der angibt, woher der Stamm stammt. Weitere Informationen finden Sie im Abschnitt mit Hinweisen.|  
|`extraData`|Zusätzliche Daten über das Objekt, das Garbage Collection sein soll. Diese Informationen hängen von der Quelle des `type` Objekts ab, wie im Feld angegeben. Weitere Informationen finden Sie im Abschnitt mit Hinweisen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `type` Feld ist ein CorGCReferenceType-Enumerationswert, der angibt, woher der Verweis stammt. [CorGCReferenceType](corgcreferencetype-enumeration.md) Ein `COR_GC_REFERENCE` bestimmter Wert kann eine der folgenden Arten von verwalteten Objekten widerspiegeln:  
  
- Objekte aus allen verwalteten Stacks (`CorGCReferenceType.CorReferenceStack`). Dazu gehören Live-Referenzen in verwaltetem Code sowie Objekte, die von der Common Language Runtime erstellt wurden.  
  
- Objekte aus der`CorGCReferenceType.CorHandle*`Handle-Tabelle ( ). Dazu gehören starke`HNDTYPE_STRONG` `HNDTYPE_REFCOUNT`Referenzen ( und ) und statische Variablen in einem Modul.  
  
- Objekte aus der Finalizerwarteschlange (`CorGCReferenceType.CorReferenceFinalizer`). Die Finalizer-Warteschlangen-Roots-Objekte, bis der Finalizer ausgeführt wurde.  
  
 Das `extraData` Feld enthält zusätzliche Daten, abhängig von der Quelle (oder dem Typ) des Verweises. Mögliche Werte:  
  
- `DependentSource`. Wenn `type` die `CorGCREferenceType.CorHandleStrongDependent`ist , ist dieses Feld das Objekt, das, wenn `COR_GC_REFERENCE.Location`es noch lebt, das Objekt entwurzelt, das garbage-collection bei sein soll.  
  
- `RefCount`. Wenn `type` der `CorGCREferenceType.CorHandleStrongRefCount`ist , ist dieses Feld die Referenzanzahl des Handles.  
  
- `Size`. Wenn `type` der `CorGCREferenceType.CorHandleStrongSizedByref`ist , ist dieses Feld die letzte Größe der Objektstruktur, für die der Garbage Collector die Objektwurzeln berechnet hat. Beachten Sie, dass diese Berechnung nicht unbedingt auf dem neuesten Stand ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
