---
title: ICorProfilerCallback::ObjectReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fc10344757d4dd9f9df7d4931eb339b652303f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683728"
---
# <a name="icorprofilercallbackobjectreferences-method"></a>ICorProfilerCallback::ObjectReferences-Methode
Benachrichtigt den Profiler zu Objekten im Arbeitsspeicher, die vom angegebenen Objekt verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a>Parameter  
 `objectId`  
 [in] Die ID des Objekts, die auf Objekte verweisen.  
  
 `classId`  
 [in] Die ID der Klasse, der das angegebene Objekt eine Instanz des ist.  
  
 `cObjectRefs`  
 [in] Die Anzahl der Objekte, die vom angegebenen Objekt verwiesen wird (d. h. die Anzahl der Elemente in der `objectRefIds` Array).  
  
 `objectRefIds`  
 [in] Ein Array von IDs von Objekten, die von verwiesen wird, wird `objectId`.  
  
## <a name="remarks"></a>Hinweise  
 Die `ObjectReferences` Methode wird aufgerufen, für die einzelnen Objekte im Heap verbleibt, nachdem eine Garbagecollection abgeschlossen wurde. Wenn der Profiler einen Fehler von diesem Rückruf zurückkehrt, stellt die Profilerstellungsdiensten dieser Rückruf aufgerufen, bis die nächste Garbagecollection.  
  
 Die `ObjectReferences` Rückruf kann verwendet werden, in Verbindung mit der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) Rückruf, der einen vollständigen objektverweisdiagramms für die Laufzeit zu erstellen. Die common Language Runtime (CLR) wird sichergestellt, dass jeder Objektverweis nur einmal, durch angegeben wird die `ObjectReferences` Methode.  
  
 Die Objekt-IDs von zurückgegebenen `ObjectReferences` sind nicht während des Rückrufs selbst gültig, da die Garbagecollection möglicherweise in der Mitte Verschieben von Objekten. Aus diesem Grund müssen Profiler nicht versuchen, Objekte, die beim Überprüfen einer `ObjectReferences` aufrufen. Wenn [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, wird die Garbage Auflistung abgeschlossen ist und die Überprüfung sicher durchgeführt werden kann.  
  
 Ein NULL-Wert `ClassId` gibt an, dass `objectId` verfügt über einen Typ, der entladen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
