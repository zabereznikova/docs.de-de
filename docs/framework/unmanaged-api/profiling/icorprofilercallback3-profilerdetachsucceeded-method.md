---
title: ICorProfilerCallback3::ProfilerDetachSucceeded-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type:
- apiref
ms.openlocfilehash: b96a8930c24275546b0aac9fa650cf5447ef4ef2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865414"
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a>ICorProfilerCallback3::ProfilerDetachSucceeded-Methode
Benachrichtigt den Profiler, dass die CLR (Common Language Runtime) die Profiler-DLL entladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert von diesem Rückruf wird ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Der `ProfilerDetachSucceeded`-Rückruf wird ausgegeben, nachdem alle Threads den Code des Profilers beendet haben. Wenn diese Methode aufgerufen wird, sollte der Profiler alle abschließenden Aufgaben ausführen, die nicht für seinen Destruktor geeignet sind, z. B. das Benachrichtigen seiner Benutzeroberfläche oder Protokollierungskomponente. Der Profiler darf jedoch keine Funktionen für Schnittstellen aufzurufen, die von der CLR während dieses Rückrufs bereitgestellt werden (z. b. die [ICorProfilerInfo](icorprofilerinfo-interface.md) -Schnittstelle oder `IMetaData*`-Schnittstelle).  
  
 Die CLR erstellt einen Eintrag im Windows-Anwendungsereignisprotokoll, um anzugeben, dass der Trennvorgang erfolgreich war.  
  
 Nachdem der Profiler von diesem Rückruf zurückkehrt, gibt die CLR das Profilerobjekt frei und entlädt die Profiler-DLL. Daher darf der Profiler keine Aktionen ausführen, die bewirken, dass die Ausführung in der Profiler-DLL erfolgt, nachdem er von diesem Rückruf zurückkehrt. Es darf z. B. keine Threads erstellen oder Timerrückrufe registrieren.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
