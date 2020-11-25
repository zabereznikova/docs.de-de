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
ms.openlocfilehash: cef69ac7e3572b67dd676ce8408e4210d93accf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717577"
---
# <a name="icordebugprocess5-interface"></a>ICorDebugProcess5-Schnittstelle

Erweitert die ICorDebugProcess-Schnittstelle, um den Zugriff auf den verwalteten Heap zu unterstützen, um Informationen über Garbage Collection verwalteter Objekte bereitzustellen und um zu bestimmen, ob ein Debugger Bilder aus dem lokalen Anwendungssystem eigenen Image Cache lädt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnableNGENPolicy-Methode](icordebugprocess5-enablengenpolicy-method.md)|Legt einen Wert fest, der bestimmt, wie eine Anwendung systemeigene Images lädt, während Sie unter einem verwalteten Debugger ausgeführt wird.|  
|[EnumerateGCReferences-Methode](icordebugprocess5-enumerategcreferences-method.md)|Ruft einen Enumerator für alle Objekte ab, die in einem Prozess in eine Garbage Collection aufgenommen werden sollen.|  
|[EnumerateHandles-Methode](icordebugprocess5-enumeratehandles-method.md)|Ruft einen Enumerator für Objekt Handles in einem Prozess ab.|  
|[EnumerateHeap-Methode](icordebugprocess5-enumerateheap-method.md)|Ruft einen Enumerator für Objekte im verwalteten Heap ab.|  
|[EnumerateHeapRegions-Methode](icordebugprocess5-enumerateheapregions-method.md)|Ruft einen Enumerator für Bereiche des verwalteten Heaps ab.|  
|[GetArrayLayout-Methode](icordebugprocess5-getarraylayout-method.md)|Ruft Informationen über das Layout eines Arrays im Arbeitsspeicher ab.|  
|[GetGCHeapInformation-Methode](icordebugprocess5-getgcheapinformation-method.md)|Ruft einen Zeiger auf eine [COR_HEAPINFO](cor-heapinfo-structure.md) -Struktur ab, die Informationen zu Objekten enthält, die auf dem verwalteten Heap Garbage Collection ausgeführt werden sollen.|  
|[GetObject-Methode](icordebugprocess5-getobject-method.md)|Ruft einen Zeiger auf ein Objekt auf dem verwalteten Heap ab.|  
|[GetTypeFields-Methode](icordebugprocess5-gettypefields-method.md)|Ruft einen Zeiger auf ein Array ab, das Feldinformationen für einen Typ auf Grundlage des Typbezeichners enthält.|  
|[GetTypeForTypeID-Methode](icordebugprocess5-gettypefortypeid-method.md)|Ruft ein Type-Objekt ab, das Informationen zu einem-Objekt auf der Grundlage seiner Typbezeichner bereitstellt.|  
|[GetTypeID-Methode](icordebugprocess5-gettypeid-method.md)|Ruft den Typbezeichner für das-Objekt an einer angegebenen Adresse ab.|  
|[GetTypeLayout-Methode](icordebugprocess5-gettypelayout-method.md)|Ruft Informationen über das Layout eines Objekts im Arbeitsspeicher auf Grundlage des Typbezeichners ab.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Schnittstelle erweitert logisch die ICorDebugProcess-, ICorDebugProcess2-und [ICorDebugProcess3](icordebugprocess3-interface.md) -Schnittstellen.  
  
> [!NOTE]
> Diese Schnittstelle bietet keine Unterstützung für das Remote Aufrufen von einem anderen Computer oder von einem anderen Prozess.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
