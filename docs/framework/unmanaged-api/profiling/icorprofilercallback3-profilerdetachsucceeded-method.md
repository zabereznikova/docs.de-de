---
title: ICorProfilerCallback3::ProfilerDetachSucceeded-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d4413e5c475bce6d6f2eea1f7a968c946237f47a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a>ICorProfilerCallback3::ProfilerDetachSucceeded-Methode
Benachrichtigt den Profiler, dass die CLR (Common Language Runtime) die Profiler-DLL entladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert von diesem Rückruf wird ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Der `ProfilerDetachSucceeded`-Rückruf wird ausgegeben, nachdem alle Threads den Code des Profilers beendet haben. Wenn diese Methode aufgerufen wird, sollte der Profiler alle abschließenden Aufgaben ausführen, die nicht für seinen Destruktor geeignet sind, z. B. das Benachrichtigen seiner Benutzeroberfläche oder Protokollierungskomponente. Allerdings der Profiler muss keine Funktionen für Schnittstellen aufrufen, die von der CLR während dieses Rückrufs bereitgestellt werden (z. B. die [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) oder `IMetaData*` Schnittstellen).  
  
 Die CLR erstellt einen Eintrag im Windows-Anwendungsereignisprotokoll, um anzugeben, dass der Trennvorgang erfolgreich war.  
  
 Nachdem der Profiler von diesem Rückruf zurückkehrt, gibt die CLR das Profilerobjekt frei und entlädt die Profiler-DLL. Daher darf der Profiler keine Aktionen ausführen, die bewirken, dass die Ausführung in der Profiler-DLL erfolgt, nachdem er von diesem Rückruf zurückkehrt. Es darf z. B. keine Threads erstellen oder Timerrückrufe registrieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
