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
ms.openlocfilehash: 12a0792e8fafc73b480de6bacc86f98470dfedf7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503288"
---
# <a name="icorprofilercallbackobjectreferences-method"></a>ICorProfilerCallback::ObjectReferences-Methode
Benachrichtigt den Profiler über Objekte im Speicher, auf die vom angegebenen-Objekt verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a>Parameter  
 `objectId`  
 in Die ID des Objekts, das auf Objekte verweist.  
  
 `classId`  
 in Die ID der Klasse, von der das angegebene Objekt eine Instanz von ist.  
  
 `cObjectRefs`  
 in Die Anzahl der Objekte, auf die durch das angegebene-Objekt verwiesen wird (d. h. die Anzahl der Elemente im- `objectRefIds` Array).  
  
 `objectRefIds`  
 in Ein Array von IDs von Objekten, auf die von verwiesen wird `objectId` .  
  
## <a name="remarks"></a>Bemerkungen  
 Die- `ObjectReferences` Methode wird für jedes Objekt aufgerufen, das nach Abschluss eines Garbage Collection im Heap verbleiben. Wenn der Profiler einen Fehler von diesem Rückruf zurückgibt, brechen die Profil Erstellungs Dienste den Aufruf dieses Rückrufs bis zum nächsten Garbage Collection ab.  
  
 Der `ObjectReferences` Rückruf kann in Verbindung mit dem [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) -Rückruf verwendet werden, um ein umfassendes Objekt Verweis Diagramm für die Laufzeit zu erstellen. Der Common Language Runtime (CLR) stellt sicher, dass jeder Objekt Verweis nur einmal von der-Methode gemeldet wird `ObjectReferences` .  
  
 Die Objekt-IDs, die von zurückgegeben werden `ObjectReferences` , sind während des Rückrufs selbst ungültig, da sich die Garbage Collection möglicherweise in der Mitte der Verschiebung von Objekten befinden. Daher dürfen Profiler nicht versuchen, Objekte während eines `ObjectReferences` Aufrufens zu überprüfen. Wenn [ICorProfilerCallback2:: garbagecollectioncomplete](icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, ist der Garbage Collection vollständig, und die Überprüfung kann sicher durchgeführt werden.  
  
 Ein NULL-Wert `ClassId` gibt an, dass `objectId` einen Typ aufweist, der entladen wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
