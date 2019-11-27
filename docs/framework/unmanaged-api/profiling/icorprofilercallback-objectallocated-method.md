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
ms.openlocfilehash: 66643bbb8dbc914b2e0e48a7f0c87630fe95e5d3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445854"
---
# <a name="icorprofilercallbackobjectallocated-method"></a>ICorProfilerCallback::ObjectAllocated-Methode
Benachrichtigt den Profiler, dass der Arbeitsspeicher im Heap für ein Objekt zugeordnet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>Parameter  
 `objectId`  
 in Die ID des Objekts, für das Speicher zugewiesen wurde.  
  
 `classId`  
 in Die ID der Klasse, für die das Objekt eine Instanz ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `ObjectedAllocated`-Methode wird nicht für Zuordnungen aus dem Stapel oder dem nicht verwalteten Speicher aufgerufen. Der `classId`-Parameter kann auf eine Klasse in verwaltetem Code verweisen, die noch nicht geladen wurde. Der Profiler empfängt direkt nach dem `ObjectAllocated` Rückruf einen Klassen Lade Rückruf für diese Klasse.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ClassLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [ClassLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
