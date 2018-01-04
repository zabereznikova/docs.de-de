---
title: ICorProfilerCallback::ObjectAllocated-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectAllocated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37f4701271f299698d7cd323b7d701f4cb7adb25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackobjectallocated-method"></a>ICorProfilerCallback::ObjectAllocated-Methode
Benachrichtigt den Profiler, der Speicher im Heap für ein Objekt zugewiesen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a>Parameter  
 `objectId`  
 [in] Die ID des Objekts für den Speicher belegt wurde.  
  
 `classId`  
 [in] Die ID der Klasse, von der das Objekt eine Instanz ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `ObjectedAllocated` Methode wird nicht für Zuordnungen aus dem Stapel oder nicht verwalteten Speicher aufgerufen. Die `classId` Parameter kann verweisen auf eine Klasse in verwaltetem Code, die noch nicht geladen wurde. Empfängt der Profiler einen Klasse laden Rückruf für diese Klasse direkt nach der `ObjectAllocated` Rückruf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ClassLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)  
 [ClassLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
