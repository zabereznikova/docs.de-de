---
title: ICorProfilerInfo3::RequestProfilerDetach-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.RequestProfilerDetach Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::RequestProfilerDetach
helpviewer_keywords:
- RequestProfilerDetach method [.NET Framework profiling]
- ICorProfilerInfo3::RequestProfilerDetach method [.NET Framework profiling]
ms.assetid: ea102e62-0454-4477-bcf3-126773acd184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5171022d35c6f9e194ddcf615d29610ea2e0d4fb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465537"
---
# <a name="icorprofilerinfo3requestprofilerdetach-method"></a>ICorProfilerInfo3::RequestProfilerDetach-Methode
Weist das Laufzeitmodul an, den Profiler zu trennen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RequestProfilerDetach(  
   [in] DWORD    dwExpectedCompletionMilliseconds);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwExpectedCompletionMilliseconds`  
 [in] Die Zeitspanne in Millisekunden, die die Common Language Runtime (CLR) warten soll, bevor geprüft wird, ob es sicher ist, den Profiler zu entladen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Trennungsanforderung ist gültig, und die Trennprozedur wird jetzt für einen anderen Thread fortgesetzt. Wenn die Trennung vollständig abgeschlossen ist, wird ein `ProfilerDetachSucceeded`-Ereignis ausgegeben.|  
|E_ CORPROF_E_CALLBACK3_REQUIRED|Der Profiler konnte kein [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) versuchen für die [ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md) -Schnittstelle, die er implementieren muss, um den Trennvorgang zu unterstützen. Die Trennung wurde nicht ausgeführt.|  
|CORPROF_E_IMMUTABLE_FLAGS_SET|Die Trennung ist nicht möglich, da vom Profiler beim Start unveränderliche Flags festgelegt wurden. Die Trennung wurde nicht ausgeführt. Der Profiler ist noch vollständig angefügt.|  
|CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT|Trennung ist nicht möglich, da der Profiler verwendet Microsoft intermediate Language (MSIL)-Code instrumentiert oder eingefügte `enter` / `leave` Hooks. Die Trennung wurde nicht ausgeführt. Der Profiler ist noch vollständig angefügt.<br /><br /> **Beachten Sie** instrumentierter MSIL ist Code wird Code bezeichnet, die vom Profiler bereitgestellt wird die [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) Methode.|  
|CORPROF_E_RUNTIME_UNINITIALIZED|Die Common Language Runtime wurde in der verwalteten Anwendung noch nicht initialisiert. (Das bedeutet, die Common Language Runtime wurde nicht vollständig geladen.) Mit diesem Fehlercode kann zurückgegeben werden, wenn die Trennung innerhalb des Profilerrückrufs angefordert wird [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Methode.|  
|CORPROF_E_UNSUPPORTED_CALL_SEQUENCE|`RequestProfilerDetach` wurde zu einem nicht unterstützten Zeitpunkt aufgerufen. Dies geschieht, wenn die Methode, für einen verwalteten Thread jedoch nicht innerhalb aufgerufen wird einer [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Methode oder in einem [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) -Methode, die eine Garbagecollection nicht tolerieren kann. Weitere Informationen finden Sie unter [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).|  
  
## <a name="remarks"></a>Hinweise  
 Während der Trennprozedur prüft der Trennthread (der speziell zum Trennen des Profilers erstellte Thread) gelegentlich, ob alle Threads den Code des Profilers verlassen haben. Der Profiler sollte über den `dwExpectedCompletionMilliseconds`-Parameter eine Schätzung zur Dauer dieses Vorgangs bereitstellen. Ein geeigneter Wert ist die typische Zeitspanne, die der Profiler innerhalb einer angegebenen `ICorProfilerCallback*`-Methode benötigt. Dieser Wert sollte nicht kleiner als die Hälfte der maximalen Zeitspanne sein, die der Profiler für die Durchführung erwartet.  
  
 Der Trennthread verwendet `dwExpectedCompletionMilliseconds`, um zu entscheiden, wie lange er deaktiviert bleibt, bevor die Prüfung erfolgt, ob der Rückrufcode des Profilers von allen Stapeln geholt wurde. Obwohl die Details des folgenden Algorithmus in zukünftigen Versionen der Common Language Runtime (CLR) möglicherweise geändert werden, veranschaulichen sie eine Möglichkeit, wie `dwExpectedCompletionMilliseconds` zur Ermittlung des sicheren Zeitpunkts für das Entladen des Profilers verwendet werden kann. Der Trennthread ist zunächst für `dwExpectedCompletionMilliseconds`-Millisekunden deaktiviert. Wenn Sie die CLR nach der Profilerrückrufcode aus dem Ruhezustand, feststellt, dass der Profilerrückrufcode weiterhin vorhanden ist, der Trennthread erneut, diesmal für zweimal `dwExpectedCompletionMilliseconds` Millisekunden. Wenn der Trennthread nach der Aktivierung aus dem zweiten Ruhezustand ermittelt, dass der Profilerrückrufcode weiterhin vorhanden ist, wird der Trennthread für 10 Minuten deaktiviert, bevor eine erneute Prüfung erfolgt. Der Trennthread für die Prüfung alle 10 Minuten erneut aus.  
  
 Wenn der Profiler für `dwExpectedCompletionMilliseconds` den Wert 0 (null) angibt, verwendet die CLR den Standardwert 5000, d. h. sie führt eine Prüfung nach fünf Sekunden aus, während eine erneute Prüfung nach weiteren 10 Sekunden und anschließend alle 10 Minuten ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
