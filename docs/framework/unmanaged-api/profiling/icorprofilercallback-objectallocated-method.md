---
title: ICorProfilerCallback::ObjectAllocated-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: 38d9e83e9fa0e9cd0586fb10a6fd79c29bead4a6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866103"
---
# <a name="icorprofilercallbackobjectallocated-method"></a>ICorProfilerCallback::ObjectAllocated-Methode
Benachrichtigt den Profiler, dass der Arbeitsspeicher im Heap für ein Objekt zugeordnet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>Parameters  
 `objectId`  
 in Die ID des Objekts, für das Speicher zugewiesen wurde.  
  
 `classId`  
 in Die ID der Klasse, für die das Objekt eine Instanz ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `ObjectedAllocated`-Methode wird nicht für Zuordnungen aus dem Stapel oder dem nicht verwalteten Speicher aufgerufen. Der `classId`-Parameter kann auf eine Klasse in verwaltetem Code verweisen, die noch nicht geladen wurde. Der Profiler empfängt direkt nach dem `ObjectAllocated` Rückruf einen Klassen Lade Rückruf für diese Klasse.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ClassLoadStarted-Methode](icorprofilercallback-classloadstarted-method.md)
- [ClassLoadFinished-Methode](icorprofilercallback-classloadfinished-method.md)
