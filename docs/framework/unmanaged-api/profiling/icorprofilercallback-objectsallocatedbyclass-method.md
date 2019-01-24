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
ms.openlocfilehash: 1200ca14b91c101a8145a3aed8023002ddb9298b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746634"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>ICorProfilerCallback::ObjectsAllocatedByClass-Methode
Benachrichtigt den Profiler über die Anzahl der Instanzen der einzelnen angegebenen Klassen, die seit der letzten Garbagecollection erstellt wurden.  
  
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
 [in] Ein Array von Klassen-IDs, die, in dem jede ID eine Klasse mit einer oder mehreren Instanzen angibt.  
  
 `cObjects`  
 [in] Ein Array von ganzen Zahlen, wobei jede ganze Zahl die Anzahl der Instanzen für die entsprechende Klasse im angibt der `classIds` Array.  
  
## <a name="remarks"></a>Hinweise  
 Die `classIds` und `cObjects` Arrays sind parallele Arrays. Z. B. `classIds[i]` und `cObjects[i]` verweisen auf die gleiche Klasse. Wenn keine Instanz einer Klasse seit der letzten Garbagecollection erstellt wurde, wird die Klasse weggelassen. Die `ObjectsAllocatedByClass` Rückruf meldet nicht in den großen Objektheap reservierten Objekte.  
  
 Die Anzahl von gemeldeten `ObjectsAllocatedByClass` nur Schätzungen. Verwenden Sie für die genaue Anzahl, [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 Die `classIds` Array kann eine oder mehrere null-Einträge enthalten, wenn die entsprechende `cObjects` Array verfügt über die Typen, die entladen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
