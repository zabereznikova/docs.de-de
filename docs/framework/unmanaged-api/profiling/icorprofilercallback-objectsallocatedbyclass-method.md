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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78dde5c50666333c02c8c1a9a167e17af3f40341
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>ICorProfilerCallback::ObjectsAllocatedByClass-Methode
Benachrichtigt den Profiler über die Anzahl der Instanzen jeder angegebenen Klasse, die seit der letzten Garbagecollection erstellt wurden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a>Parameter  
 `cClassCount`  
 [in] Die Größe der `classIds` und `cObjects` Arrays.  
  
 `classIds`  
 [in] Ein Array von Klassen-IDs, wobei jede ID eine Klasse mit einer oder mehrerer Instanzen angibt.  
  
 `cObjects`  
 [in] Ein Array von Ganzzahlen, in dem jede ganze Zahl gibt die Anzahl der Instanzen für die entsprechende Klasse im an die `classIds` Array.  
  
## <a name="remarks"></a>Hinweise  
 Die `classIds` und `cObjects` Arrays sind parallele Arrays. Beispielsweise `classIds[i]` und `cObjects[i]` verweisen auf die gleiche Klasse. Wenn keine Instanz einer Klasse seit der letzten Garbagecollection erstellt wurde, wird die Klasse ausgelassen. Die `ObjectsAllocatedByClass` Rückruf meldet sich nicht auf die im großen Objektheap reservierten Objekte.  
  
 Die Anzahl von gemeldeten `ObjectsAllocatedByClass` sind nur Schätzungen. Verwenden Sie für die genaue Anzahl [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 Die `classIds` Array kann eine oder mehrere null-Einträge enthalten, wenn das entsprechende `cObjects` Array verfügt über die Typen, die entladen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
