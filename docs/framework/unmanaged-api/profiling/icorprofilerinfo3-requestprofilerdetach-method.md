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
ms.openlocfilehash: 3256f6f64e2ee4678b2627eea81e12cb4a02fd1e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449623"
---
# <a name="icorprofilerinfo3requestprofilerdetach-method"></a>ICorProfilerInfo3::RequestProfilerDetach-Methode
Weist das Laufzeitmodul an, den Profiler zu trennen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RequestProfilerDetach(  
   [in] DWORD    dwExpectedCompletionMilliseconds);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwExpectedCompletionMilliseconds`  
 [in] Die Zeitspanne in Millisekunden, die die Common Language Runtime (CLR) warten soll, bevor geprüft wird, ob es sicher ist, den Profiler zu entladen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Trennungsanforderung ist gültig, und die Trennprozedur wird jetzt für einen anderen Thread fortgesetzt. Wenn die Trennung vollständig abgeschlossen ist, wird ein `ProfilerDetachSucceeded`-Ereignis ausgegeben.|  
|E_ CORPROF_E_CALLBACK3_REQUIRED|The profiler failed an [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) attempt for the [ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md) interface, which it must implement to support the detach operation. Die Trennung wurde nicht ausgeführt.|  
|CORPROF_E_IMMUTABLE_FLAGS_SET|Die Trennung ist nicht möglich, da vom Profiler beim Start unveränderliche Flags festgelegt wurden. Die Trennung wurde nicht ausgeführt. Der Profiler ist noch vollständig angefügt.|  
|CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT|Detachment is impossible because the profiler used instrumented Microsoft intermediate language (MSIL) code, or inserted `enter`/`leave` hooks. Die Trennung wurde nicht ausgeführt. Der Profiler ist noch vollständig angefügt.<br /><br /> **Note** Instrumented MSIL is code is code that is provided by the profiler using the [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method.|  
|CORPROF_E_RUNTIME_UNINITIALIZED|Die Common Language Runtime wurde in der verwalteten Anwendung noch nicht initialisiert. (That is, the runtime has not been fully loaded.) This error code may be returned when detachment is requested inside the profiler callback's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) method.|  
|CORPROF_E_UNSUPPORTED_CALL_SEQUENCE|`RequestProfilerDetach` wurde zu einem nicht unterstützten Zeitpunkt aufgerufen. This occurs if the method is called on a managed thread but not from within an [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) method or from within an [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) method that cannot tolerate a garbage collection. For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).|  
  
## <a name="remarks"></a>Hinweise  
 Während der Trennprozedur prüft der Trennthread (der speziell zum Trennen des Profilers erstellte Thread) gelegentlich, ob alle Threads den Code des Profilers verlassen haben. Der Profiler sollte über den `dwExpectedCompletionMilliseconds`-Parameter eine Schätzung zur Dauer dieses Vorgangs bereitstellen. Ein geeigneter Wert ist die typische Zeitspanne, die der Profiler innerhalb einer angegebenen `ICorProfilerCallback*`-Methode benötigt. Dieser Wert sollte nicht kleiner als die Hälfte der maximalen Zeitspanne sein, die der Profiler für die Durchführung erwartet.  
  
 Der Trennthread verwendet `dwExpectedCompletionMilliseconds`, um zu entscheiden, wie lange er deaktiviert bleibt, bevor die Prüfung erfolgt, ob der Rückrufcode des Profilers von allen Stapeln geholt wurde. Obwohl die Details des folgenden Algorithmus in zukünftigen Releases der Common Language Runtime (CLR) möglicherweise geändert werden, veranschaulichen sie eine Möglichkeit, wie `dwExpectedCompletionMilliseconds` zur Ermittlung des sicheren Zeitpunkts für das Entladen des Profilers verwendet werden kann. Der Trennthread ist zunächst für `dwExpectedCompletionMilliseconds`-Millisekunden deaktiviert. If, after awakening from the sleep, the CLR finds that profiler callback code is still present, the detach thread sleeps again, this time for two times `dwExpectedCompletionMilliseconds` milliseconds. Wenn der Trennthread nach der Aktivierung aus dem zweiten Ruhezustand ermittelt, dass der Profilerrückrufcode weiterhin vorhanden ist, wird der Trennthread für 10 Minuten deaktiviert, bevor eine erneute Prüfung erfolgt. Der Trennthread für die Prüfung alle 10 Minuten erneut aus.  
  
 Wenn der Profiler für `dwExpectedCompletionMilliseconds` den Wert 0 (null) angibt, verwendet die CLR den Standardwert 5000, d. h. sie führt eine Prüfung nach fünf Sekunden aus, während eine erneute Prüfung nach weiteren 10 Sekunden und anschließend alle 10 Minuten ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
