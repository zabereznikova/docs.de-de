---
title: ICorProfilerCallback::ObjectsAllocatedByClass-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
ms.openlocfilehash: 9ba021ec223d00e57081567b76f70f59768e6b9a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445860"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>ICorProfilerCallback::ObjectsAllocatedByClass-Methode
Benachrichtigt den Profiler über die Anzahl von Instanzen der angegebenen Klasse, die seit dem letzten Garbage Collection erstellt wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a>Parameter  
 `cClassCount`  
 in Die Größe der `classIds` und `cObjects` Arrays.  
  
 `classIds`  
 in Ein Array von Klassen-IDs, wobei jede ID eine Klasse mit einer oder mehreren Instanzen angibt.  
  
 `cObjects`  
 in Ein Array von Ganzzahlen, wobei jede ganze Zahl die Anzahl der Instanzen für die entsprechende Klasse im `classIds` Array angibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `classIds`-und `cObjects` Arrays sind parallele Arrays. Beispielsweise verweisen `classIds[i]` und `cObjects[i]` auf die gleiche Klasse. Wenn seit dem vorherigen Garbage Collection keine Instanz einer Klasse erstellt wurde, wird die Klasse ausgelassen. Der `ObjectsAllocatedByClass` Rückruf meldet im großen Objekt Heap zugeordnete Objekte nicht.  
  
 Die von `ObjectsAllocatedByClass` gemeldeten Zahlen sind nur Schätzungen. Verwenden Sie für exakte Anzahlen [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 Das `classIds` Array kann mindestens einen NULL-Eintrag enthalten, wenn das entsprechende `cObjects` Array Typen aufweist, die entladen werden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
