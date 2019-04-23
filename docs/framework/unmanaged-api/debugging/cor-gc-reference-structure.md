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
ms.openlocfilehash: e1e31e95473136bf7e7c196eacc278fa8a1caab2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093656"
---
# <a name="corgcreference-structure"></a>COR_GC_REFERENCE-Struktur
Enthält Informationen zu einem Objekt, das speicherbereinigt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`domain`|Ein Zeiger auf die Anwendungsdomäne, zu der das Handle oder das Objekt gehört. Der Wert möglicherweise `null`.|  
|`location`|ICorDebugValue- oder eine ICorDebugReferenceValue-Schnittstelle, die das Objekt, das speicherbereinigt werden soll entspricht.|  
|`type`|Ein [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, woher das Stammverzeichnis stammen. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
|`extraData`|Zusätzliche Daten über das Objekt, das speicherbereinigt werden soll. Diese Informationen hängen von der Quelle des Objekts, die durch die `type` Feld. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
  
## <a name="remarks"></a>Hinweise  
 Die `type` Feld ist ein [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, in dem der Verweis stammt. Eine bestimmte `COR_GC_REFERENCE` Wert kann eine der folgenden Arten von verwalteten Objekten widerspiegeln:  
  
-   Objekte aus allen verwalteten Stapel (`CorGCReferenceType.CorReferenceStack`). Dies schließt die aktiven Verweise in verwaltetem Code als auch Objekte, die von der common Language Runtime erstellt.  
  
-   Objekte aus der Handletabelle (`CorGCReferenceType.CorHandle*`). Dies schließt starken Verweise (`HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT`) und statische Variablen in einem Modul.  
  
-   Objekte aus der Finalizerwarteschlange (`CorGCReferenceType.CorReferenceFinalizer`). Die Finalizer-Warteschlange Stämme Objekte an, bis der Finalizer ausgeführt wurde.  
  
 Die `extraData` Feld enthält die zusätzliche Daten abhängig von der Quelle (oder Typ) des Verweises. Dabei sind folgende Werte möglich:  
  
-   `DependentSource`. Wenn die `type` ist `CorGCREferenceType.CorHandleStrongDependent`, dieses Feld ist das Objekt, das, wenn aktiv ist, wird das Objekt, um die Garbage Collection auf Stammelemente `COR_GC_REFERENCE.Location`.  
  
-   `RefCount`. Wenn die `type` ist `CorGCREferenceType.CorHandleStrongRefCount`, dieses Feld wird der Verweiszähler des Handles.  
  
-   `Size`. Wenn die `type` ist `CorGCREferenceType.CorHandleStrongSizedByref`, dieses Feld ist die letzte Größe der Objektstruktur, die für den Garbage Collector die Stämme Objekt berechnet. Beachten Sie, dass diese Berechnung nicht unbedingt auf dem neuesten Stand ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
