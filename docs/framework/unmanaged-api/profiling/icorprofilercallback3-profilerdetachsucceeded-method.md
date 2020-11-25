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
ms.openlocfilehash: b9b284de102dc75a637803ca5be0f2769da452ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730317"
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

 Der `ProfilerDetachSucceeded`-Rückruf wird ausgegeben, nachdem alle Threads den Code des Profilers beendet haben. Wenn diese Methode aufgerufen wird, sollte der Profiler alle abschließenden Aufgaben ausführen, die nicht für seinen Destruktor geeignet sind, z. B. das Benachrichtigen seiner Benutzeroberfläche oder Protokollierungskomponente. Allerdings darf der Profiler keine Funktionen für Schnittstellen aufzurufen, die von der CLR während dieses Rückrufs bereitgestellt werden (z. b. [ICorProfilerInfo](icorprofilerinfo-interface.md) oder `IMetaData*` Schnittstellen).  
  
 Die CLR erstellt einen Eintrag im Windows-Anwendungsereignisprotokoll, um anzugeben, dass der Trennvorgang erfolgreich war.  
  
 Nachdem der Profiler von diesem Rückruf zurückkehrt, gibt die CLR das Profilerobjekt frei und entlädt die Profiler-DLL. Daher darf der Profiler keine Aktionen ausführen, die bewirken, dass die Ausführung in der Profiler-DLL erfolgt, nachdem er von diesem Rückruf zurückkehrt. Es darf z. B. keine Threads erstellen oder Timerrückrufe registrieren.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenschnittstellen](../metadata/metadata-interfaces.md)
- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
