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
ms.openlocfilehash: fda234a6a280aeea1f497ad195d6d41efb6aa951
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674331"
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

 Die- `ObjectedAllocated` Methode wird nicht für Zuordnungen aus dem Stapel oder dem nicht verwalteten Speicher aufgerufen. Der- `classId` Parameter kann auf eine Klasse in verwaltetem Code verweisen, die noch nicht geladen wurde. Der Profiler empfängt direkt nach dem Rückruf einen Klassen Lade Rückruf für diese Klasse `ObjectAllocated` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ClassLoadStarted-Methode](icorprofilercallback-classloadstarted-method.md)
- [ClassLoadFinished-Methode](icorprofilercallback-classloadfinished-method.md)
