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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 822425b958422ba364a1f10903c7c312ba43fab9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="corgcreferencetype-enumeration"></a>CorGCReferenceType-Enumeration
Identifiziert die Quelle eines Objekts, das speicherbereinigt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
|Membername|Beschreibung|  
|-----------------|-----------------|  
|`CorHandleStrong`|Ein Handle für einen starken Verweis von der Objekthandletabelle.|  
|`CorHandleStrongPinning`|Ein Handle auf ein angehefteter starker Verweis von der objekthandletabelle.|  
|`CorHandleWeakShort`|Ein Handle auf einen schwachen Verweis von der objekthandletabelle.|  
|`CorHandleWeakRefCount`|Ein Handle zu einem schwachen Verweis gezähltes Objekt von der objekthandletabelle.|  
|`CorHandleStrongRefCount`|Ein Handle auf ein Objekt mit verweiszählung von der objekthandletabelle.|  
|`CorHandleStrongDependent`|Ein Handle für ein abhängiges Objekt von der objekthandletabelle werden soll.|  
|`CorHandleStrongAsyncPinned`|Ein asynchrones angeheftetes Objekt von der Objekthandletabelle.|  
|`CorHandleStrongSizedByref`|Ein starkes Handle, das eine ungefähre Größe des kollektiven Abschlusses aller Objekte und Objektstämme zur Garbage Collection-Zeit enthält.|  
|`CorReferenceStack`|Ein Verweis vom verwalteten Stapel.|  
|`CorReferenceFinalizer`|Ein Verweis von der Finalizerwarteschlange.|  
|CorHandleStrongOnly|Geben Sie nur starke Verweise aus der Handletabelle zurück. Dieser Wert wird verwendet, durch die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) nur Methode.|  
|`CorHandleWeakOnly`|Geben Sie nur schwache Verweise aus der Handletabelle zurück. Dieser Wert wird verwendet, durch die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) nur Methode.|  
|`CorHandleAll`|Geben Sie alle Verweise aus der Handletabelle zurück. Dieser Wert wird verwendet, durch die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) nur Methode.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CorGCReferenceType` Enumeration wird wie folgt verwendet:  
  
-   Als Wert des der `type` Feld der [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) -Struktur, es gibt die Datenquelle ein Verweis oder ein Handle.  
  
-   Als die `types` Argument an die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) -Methode, gibt die Arten von Handles in der Enumeration einschließen an.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
