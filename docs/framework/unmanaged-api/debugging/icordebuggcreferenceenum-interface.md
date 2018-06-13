---
title: ICorDebugGCReferenceEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa8c3160dc779b2475dec63be896af5283cf5346
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418164"
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum-Schnittstelle
Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|Ruft die angegebene Anzahl von [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Instanzen, die Informationen zu Objekten enthalten, die Garbage Collection übergeben werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugGCReferenceEnum` Schnittstelle implementiert, die "ICorDebugEnum"-Schnittstelle.  
  
 Ein `ICorDebugGCReferenceEnum` Instanz wird mit aufgefüllt [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Instanzen durch Aufrufen der [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) Methode. [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Objekte aufgelistet werden können, durch Aufrufen der [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) Methode.  
  
 Die [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Objekte in der Auflistung, die von dieser Methode aufgefüllt darstellen drei Arten von Objekten:  
  
-   Objekte aus allen verwalteten Stapel. Dies schließt die aktive Verweise in verwaltetem Code als auch Objekte, die von der common Language Runtime erstellt.  
  
-   Objekte aus der Handletabelle. Dies schließt starken Verweise (`HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT`) und statische Variablen in einem Modul.  
  
-   Objekte aus der Finalizerwarteschlange. Die Finalizer-Warteschlange Stämme Objekte auf, bis der Finalizer ausgeführt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
