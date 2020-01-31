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
ms.openlocfilehash: 6e6cc44c2f9028c0e26c4f933242cad93e3a98c3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866090"
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
  
## <a name="parameters"></a>Parameters  
 `objectId`  
 in Die ID des Objekts, das auf Objekte verweist.  
  
 `classId`  
 in Die ID der Klasse, von der das angegebene Objekt eine Instanz von ist.  
  
 `cObjectRefs`  
 in Die Anzahl der Objekte, auf die durch das angegebene Objekt verwiesen wird (d. h. die Anzahl der Elemente im `objectRefIds` Array).  
  
 `objectRefIds`  
 in Ein Array von IDs von Objekten, auf die von `objectId`verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `ObjectReferences`-Methode wird für jedes Objekt aufgerufen, das im Heap verbleiben, nachdem ein Garbage Collection abgeschlossen wurde. Wenn der Profiler einen Fehler von diesem Rückruf zurückgibt, brechen die Profil Erstellungs Dienste den Aufruf dieses Rückrufs bis zum nächsten Garbage Collection ab.  
  
 Der `ObjectReferences` Rückruf kann in Verbindung mit dem [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) -Rückruf verwendet werden, um ein umfassendes Objekt Verweis Diagramm für die Laufzeit zu erstellen. Der Common Language Runtime (CLR) stellt sicher, dass jeder Objekt Verweis nur einmal von der `ObjectReferences`-Methode gemeldet wird.  
  
 Die Objekt-IDs, die von `ObjectReferences` zurückgegeben werden, sind während des Rückrufs selbst nicht gültig, da die Garbage Collection in der Mitte des Verschiebens von Objekten liegen kann. Daher dürfen Profiler nicht versuchen, Objekte während eines `ObjectReferences` Aufrufens zu überprüfen. Wenn [ICorProfilerCallback2:: garbagecollectioncomplete](icorprofilercallback2-garbagecollectionfinished-method.md) aufgerufen wird, ist der Garbage Collection vollständig, und die Überprüfung kann sicher durchgeführt werden.  
  
 Ein NULL-`ClassId` gibt an, dass `objectId` einen Typ aufweist, der entladen wird.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
