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
ms.openlocfilehash: 627df3600b920e2fe2250f2fc3da51c852edc774
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496240"
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
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Trennungsanforderung ist gültig, und die Trennprozedur wird jetzt für einen anderen Thread fortgesetzt. Wenn die Trennung vollständig abgeschlossen ist, wird ein `ProfilerDetachSucceeded`-Ereignis ausgegeben.|  
|E_CORPROF_E_CALLBACK3_REQUIRED|Der Profiler konnte einen [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) -Versuch für die [ICorProfilerCallback3](icorprofilercallback3-interface.md) -Schnittstelle nicht ausführen, die er implementieren muss, um den Trennvorgang zu unterstützen. Die Trennung wurde nicht ausgeführt.|  
|CORPROF_E_IMMUTABLE_FLAGS_SET|Die Trennung ist nicht möglich, da vom Profiler beim Start unveränderliche Flags festgelegt wurden. Die Trennung wurde nicht ausgeführt. Der Profiler ist noch vollständig angefügt.|  
|CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT|Die Trennung ist nicht möglich, da der Profiler instrumentierten MSIL-Code (Microsoft Intermediate Language) oder eingefügte Hooks verwendet hat `enter` / `leave` . Die Trennung wurde nicht ausgeführt. Der Profiler ist noch vollständig angefügt.<br /><br /> **Hinweis** Instrumentiertes MSIL ist der Code, der vom Profiler mit der [SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) -Methode bereitgestellt wird.|  
|CORPROF_E_RUNTIME_UNINITIALIZED|Die Common Language Runtime wurde in der verwalteten Anwendung noch nicht initialisiert. (Das heißt, die Laufzeit wurde nicht vollständig geladen.) Dieser Fehlercode kann zurückgegeben werden, wenn die Trennung innerhalb der [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) -Methode des Profiler-Rückrufs angefordert wird.|  
|CORPROF_E_UNSUPPORTED_CALL_SEQUENCE|`RequestProfilerDetach` wurde zu einem nicht unterstützten Zeitpunkt aufgerufen. Dies tritt auf, wenn die Methode für einen verwalteten Thread aufgerufen wird, nicht jedoch innerhalb einer [ICorProfilerCallback](icorprofilercallback-interface.md) -Methode oder innerhalb einer [ICorProfilerCallback](icorprofilercallback-interface.md) -Methode, die eine Garbage Collection nicht tolerieren kann. Weitere Informationen finden Sie unter [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).|  
  
## <a name="remarks"></a>Bemerkungen  
 Während der Trennprozedur prüft der Trennthread (der speziell zum Trennen des Profilers erstellte Thread) gelegentlich, ob alle Threads den Code des Profilers verlassen haben. Der Profiler sollte über den `dwExpectedCompletionMilliseconds`-Parameter eine Schätzung zur Dauer dieses Vorgangs bereitstellen. Ein geeigneter Wert ist die typische Zeitspanne, die der Profiler innerhalb einer angegebenen `ICorProfilerCallback*`-Methode benötigt. Dieser Wert sollte nicht kleiner als die Hälfte der maximalen Zeitspanne sein, die der Profiler für die Durchführung erwartet.  
  
 Der Trennthread verwendet `dwExpectedCompletionMilliseconds`, um zu entscheiden, wie lange er deaktiviert bleibt, bevor die Prüfung erfolgt, ob der Rückrufcode des Profilers von allen Stapeln geholt wurde. Obwohl die Details des folgenden Algorithmus in zukünftigen Releases der Common Language Runtime (CLR) möglicherweise geändert werden, veranschaulichen sie eine Möglichkeit, wie `dwExpectedCompletionMilliseconds` zur Ermittlung des sicheren Zeitpunkts für das Entladen des Profilers verwendet werden kann. Der Trennthread ist zunächst für `dwExpectedCompletionMilliseconds`-Millisekunden deaktiviert. Wenn die CLR nach dem wiederholen im Standbymodus feststellt, dass der Profiler-Rückruf Code weiterhin vorhanden ist, wird der Trenn Thread wieder in den Ruhezustand versetzt, dieses Mal für zweifache `dwExpectedCompletionMilliseconds` Millisekunden. Wenn der Trennthread nach der Aktivierung aus dem zweiten Ruhezustand ermittelt, dass der Profilerrückrufcode weiterhin vorhanden ist, wird der Trennthread für 10 Minuten deaktiviert, bevor eine erneute Prüfung erfolgt. Der Trennthread für die Prüfung alle 10 Minuten erneut aus.  
  
 Wenn der Profiler für `dwExpectedCompletionMilliseconds` den Wert 0 (null) angibt, verwendet die CLR den Standardwert 5000, d. h. sie führt eine Prüfung nach fünf Sekunden aus, während eine erneute Prüfung nach weiteren 10 Sekunden und anschließend alle 10 Minuten ausgeführt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
