---
title: CorGCReferenceType-Enumeration
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
ms.openlocfilehash: e2903637faa11a3c0a62080cc6fafcf1fc668a56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704993"
---
# <a name="corgcreferencetype-enumeration"></a>CorGCReferenceType-Enumeration

Identifiziert die Quelle eines Objekts, das speicherbereinigt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a>Member  
  
|Membername|BESCHREIBUNG|  
|-----------------|-----------------|  
|`CorHandleStrong`|Ein Handle für einen starken Verweis von der Objekthandletabelle.|  
|`CorHandleStrongPinning`|Ein Handle für einen fixierten starken Verweis aus der Objekt Handle-Tabelle.|  
|`CorHandleWeakShort`|Ein Handle für einen schwachen Verweis aus der Objekt Handle-Tabelle.|  
|`CorHandleWeakRefCount`|Ein Handle für ein schwaches Verweis Gezähltes Objekt aus der Objekt Handle-Tabelle.|  
|`CorHandleStrongRefCount`|Ein Handle für ein Objekt mit Verweis Zählung aus der Objekt Handle-Tabelle.|  
|`CorHandleStrongDependent`|Ein Handle für ein abhängiges Objekt aus der Objekt Handle-Tabelle.|  
|`CorHandleStrongAsyncPinned`|Ein asynchrones angeheftetes Objekt von der Objekthandletabelle.|  
|`CorHandleStrongSizedByref`|Ein starkes Handle, das eine ungefähre Größe des kollektiven Abschlusses aller Objekte und Objektstämme zur Garbage Collection-Zeit enthält.|  
|`CorReferenceStack`|Ein Verweis aus dem verwalteten Stapel.|  
|`CorReferenceFinalizer`|Ein Verweis aus der Finalizerwarteschlange.|  
|Corlenker strongonly|Gibt nur starke Verweise aus der Handle-Tabelle zurück. Dieser Wert wird nur von der [ICorDebugProcess5:: enumeratehandles](icordebugprocess5-enumeratehandles-method.md) -Methode verwendet.|  
|`CorHandleWeakOnly`|Gibt nur schwache Verweise aus der Handle-Tabelle zurück. Dieser Wert wird nur von der [ICorDebugProcess5:: enumeratehandles](icordebugprocess5-enumeratehandles-method.md) -Methode verwendet.|  
|`CorHandleAll`|Gibt alle Verweise aus der Handle-Tabelle zurück. Dieser Wert wird nur von der [ICorDebugProcess5:: enumeratehandles](icordebugprocess5-enumeratehandles-method.md) -Methode verwendet.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `CorGCReferenceType` Enumeration wird wie folgt verwendet:  
  
- Als Wert des- `type` Felds der [COR_GC_REFERENCE](cor-gc-reference-structure.md) Struktur wird die Quelle eines Verweises oder eines Handles angegeben.  
  
- Als `types` Argument für die [ICorDebugProcess5:: enumeratehandles](icordebugprocess5-enumeratehandles-method.md) -Methode gibt es die Typen von Handles an, die in der-Enumeration enthalten sein sollen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
