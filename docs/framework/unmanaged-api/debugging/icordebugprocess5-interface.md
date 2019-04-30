---
title: ICorDebugProcess5-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5904083be66d4bd6dc69729bebc28db8a800e77
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948680"
---
# <a name="icordebugprocess5-interface"></a>ICorDebugProcess5-Schnittstelle
Erweitert die ICorDebugProcess-Schnittstelle, um Zugriff auf dem verwalteten Heap, Informationen zur Garbagecollection von verwalteten Objekten zu unterstützen, und lädt bestimmen, ob ein Debugger Bilder aus dem lokalen systemeigene Images.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnableNGENPolicy-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|Legt einen Wert, der bestimmt, wie eine Anwendung für systemeigene Images während der Ausführung unter einem verwalteten Debugger geladen.|  
|[EnumerateGCReferences-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|Ruft einen Enumerator für alle Objekte, die in einem Prozess speicherbereinigt werden soll.|  
|[EnumerateHandles-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|Ruft einen Enumerator für die Objekt-Handles in einem Prozess ab.|  
|[EnumerateHeap-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|Ruft einen Enumerator für Objekte im verwalteten Heap.|  
|[EnumerateHeapRegions-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|Ruft einen Enumerator für die Regionen des verwalteten Heaps ab.|  
|[GetArrayLayout-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|Ruft Informationen zum Layout eines Arrays im Arbeitsspeicher ab.|  
|[GetGCHeapInformation-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|Ruft einen Zeiger auf eine [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) -Struktur, die Informationen zu Objekten enthält, die Garbage Collection auf dem verwalteten Heap werden sollen.|  
|[GetObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|Ruft einen Zeiger auf ein Objekt, auf dem verwalteten Heap.|  
|[GetTypeFields-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|Ruft einen Zeiger auf ein Array, das Feldinformationen für einen Typ auf Grundlage seines Bezeichners Typ enthält.|  
|[GetTypeForTypeID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|Ruft ein Typobjekt, das Informationen über ein Objekt, das basierend auf seiner Typ-IDs ab.|  
|[GetTypeID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|Ruft die Typ-ID für das Objekt an einer angegebenen Adresse an.|  
|[GetTypeLayout-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|Ruft Informationen zum Layout eines Objekts im Arbeitsspeicher auf Grundlage seines Bezeichners Typ ab.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle erweitert logisch die ICorDebugProcess, ICorDebugProcess2, und [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) Schnittstellen.  
  
> [!NOTE]
>  Diese Schnittstelle unterstützt nicht remote aufgerufen werden, entweder von einem anderen Computer oder einem anderen Prozess.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
