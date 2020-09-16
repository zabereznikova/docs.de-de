---
title: ICorProfilerInfo2::DoStackSnapshot-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
ms.openlocfilehash: ff0ff35f42e20725cab49afd971523aabda866c3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547804"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>ICorProfilerInfo2::DoStackSnapshot-Methode
Führt die verwalteten Frames auf dem Stapel für den angegebenen Thread durch und sendet Informationen über einen Rückruf an den Profiler.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
## <a name="parameters"></a>Parameter  
 `thread`  
 in Die ID des Ziel Threads.  
  
 Wenn NULL in übergeben wird, wird `thread` eine Momentaufnahme des aktuellen Threads erstellt. Wenn eine `ThreadID` von einem anderen Thread übermittelt wird, hält der Common Language Runtime (CLR) diesen Thread an, führt die Momentaufnahme aus und nimmt den Wert wieder auf.  
  
 `callback`  
 in Ein Zeiger auf die Implementierung der [StackSnapshotCallback](stacksnapshotcallback-function.md) -Methode, die von der CLR aufgerufen wird, um dem Profiler Informationen über jeden verwalteten Frame und jede Ausführung nicht verwalteter Frames bereitzustellen.  
  
 Die- `StackSnapshotCallback` Methode wird vom Profiler-Writer implementiert.  
  
 `infoFlags`  
 in Ein Wert der [COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md) -Enumeration, die die Menge der Daten angibt, die für jeden Frame von zurückgegeben werden sollen `StackSnapshotCallback` .  
  
 `clientData`  
 in Ein Zeiger auf die Client Daten, die direkt an die Rückruffunktion übermittelt werden `StackSnapshotCallback` .  
  
 `context`  
 in Ein Zeiger auf eine Win32-- `CONTEXT` Struktur, die verwendet wird, um den Stapel Durchlauf zu durchlaufen. Die Win32 `CONTEXT` -Struktur enthält Werte der CPU-Register und stellt den Status der CPU zu einem bestimmten Zeitpunkt dar.  
  
 Der Seed unterstützt die CLR dabei, zu bestimmen, wo der Stapel Durchlauf begonnen werden soll, wenn der obere Rand des Stapels nicht verwalteten Hilfscode ist. Andernfalls wird der Seed ignoriert. Für einen asynchronen Durchlauf muss ein Ausgangswerten angegeben werden. Wenn Sie eine synchrone Exemplarische Vorgehensweise durchführen, ist kein Ausgangswert erforderlich.  
  
 Der- `context` Parameter ist nur gültig, wenn das COR_PRF_SNAPSHOT_CONTEXT-Flag im-Parameter übergeben wurde `infoFlags` .  
  
 `contextSize`  
 in Die Größe der- `CONTEXT` Struktur, auf die vom-Parameter verwiesen wird `context` .  
  
## <a name="remarks"></a>Hinweise  
 Durch die Übergabe von NULL für wird `thread` eine Momentaufnahme des aktuellen Threads erstellt. Momentaufnahmen können nur von anderen Threads übernommen werden, wenn der Zielthread zu diesem Zeitpunkt angehalten wird.  
  
 Wenn der Profiler den Stapel durchlaufen möchte, wird aufgerufen `DoStackSnapshot` . Bevor die CLR von diesem Aufruf zurückkehrt, ruft Sie `StackSnapshotCallback` mehrmals auf, und zwar für jeden verwalteten Frame (bzw. durch Ausführen von nicht verwalteten Frames) auf dem Stapel. Wenn nicht verwaltete Frames gefunden werden, müssen Sie Sie selbst durchgehen.  
  
 Die Reihenfolge, in der der Stapel durchlaufen wird, ist das Gegenteil, wie die Frames auf den Stapel verschoben werden: Blatt (zuletzt per pushübertragung), erster Hauptrahmen (First-pushübertragung).  
  
 Weitere Informationen zum Programmieren des Profilers zum Durchlaufen verwalteter Stapel finden Sie unter [Profiler Stack Walking in the .NET Framework 2,0: Basics and Beyond](/previous-versions/dotnet/articles/bb264782(v=msdn.10)).  
  
 Ein Stackwalk kann synchron oder asynchron sein, wie in den folgenden Abschnitten erläutert.  
  
## <a name="synchronous-stack-walk"></a>Synchroner Stackwalk  
 Ein synchroner Stackwalk umfasst das Durchlaufen des Stapels des aktuellen Threads als Reaktion auf einen Rückruf. Das Seeding oder das Anhalten ist nicht erforderlich.  
  
 Sie führen einen synchronen Aufruf aus, wenn Sie als Antwort auf die CLR, die eine der [ICorProfilerCallback](icorprofilercallback-interface.md) (oder [ICorProfilerCallback2](icorprofilercallback2-interface.md))-Methoden Ihres Profilers aufruft, aufrufen, `DoStackSnapshot` um den Stapel des aktuellen Threads zu durchlaufen. Dies ist hilfreich, wenn Sie sehen möchten, wie der Stapel in einer Benachrichtigung wie z. b. [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md)aussieht. Sie können nur in `DoStackSnapshot` `ICorProfilerCallback` der-Methode aufzurufen und dabei NULL im `context` -Parameter und im- `thread` Parameter übergeben.  
  
## <a name="asynchronous-stack-walk"></a>Asynchroner Stackwalk  
 Ein asynchroner Stapel Durchlauf umfasst das Durchlaufen des Stapels eines anderen Threads oder das Durchlaufen des Stapels des aktuellen Threads, nicht als Reaktion auf einen Rückruf, sondern durch das Hijacking des Anweisungs Zeigers des aktuellen Threads. Ein asynchroner Durchlauf erfordert einen Ausgangswert, wenn der obere Rand des Stapels nicht verwalteter Code ist, der nicht Teil eines Platt Form Aufrufs (PInvoke) oder com-Aufrufs ist, sondern Hilfscode in der CLR selbst ist. Beispielsweise ist Code, der Just-in-time (JIT)-Kompilierung oder-Garbage Collection durchführt, Hilfscode.  
  
 Sie erhalten einen Ausgangswert, indem Sie den Zielthread direkt anhalten und den Stapel selbst durchlaufen, bis Sie den obersten verwalteten Frame gefunden haben. Nachdem der Zielthread angehalten wurde, wird der aktuelle Registrierungs Kontext des Zielthreads angezeigt. Legen Sie als nächstes fest, ob der Registrierungs Kontext auf nicht verwalteten Code zeigt, indem Sie [ICorProfilerInfo:: GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md) – aufrufen, wenn ein `FunctionID` gleich NULL zurückgegeben wird, der Frame nicht verwalteter Code ist. Durchlaufen Sie nun den Stapel, bis Sie den ersten verwalteten Frame erreichen, und berechnen Sie dann den Seed-Kontext basierend auf dem Registrierungs Kontext für diesen Frame.  
  
 Greifen `DoStackSnapshot` Sie mit Ihrem Seed-Kontext zu, um den asynchronen Stapel Durchlauf zu starten. Wenn Sie keinen Ausgangs Ausgangsbereich angeben, `DoStackSnapshot` überspringt möglicherweise verwaltete Frames am oberen Rand des Stapels und gibt somit einen unvollständigen Stapel Durchlauf aus. Wenn Sie einen Ausgangswert angeben, muss er auf JIT-kompilierten oder von System eigenem Image Generator (Ngen.exe) generierten Code verweisen. Andernfalls wird `DoStackSnapshot` der Fehlercode zurückgegeben, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.  
  
 Asynchrone Stapel Durchgänge können auf einfache Weise Deadlocks oder Zugriffs Verletzungen verursachen, es sei denn, Sie befolgen die folgenden Richtlinien:  
  
- Wenn Sie Threads direkt aussetzen, denken Sie daran, dass nur ein Thread, der verwalteten Code nie ausgeführt hat, einen anderen Thread unterbrechen kann.  
  
- Blockieren Sie in Ihrem [ICorProfilerCallback:: Thread}](icorprofilercallback-threaddestroyed-method.md) -Rückruf immer, bis der Stapel Durchlauf dieses Threads beendet ist.  
  
- Behalten Sie keine Sperre bei, während der Profiler eine CLR-Funktion aufruft, die eine Garbage Collection auslöst. Das heißt, keine Sperre aufrechterhalten, wenn der besitzende Thread einen-Garbage Collection auslösen kann, der einen auslöst.  
  
 Außerdem besteht das Risiko eines Deadlocks, wenn Sie `DoStackSnapshot` von einem Thread aufgerufen werden, den Ihr Profiler erstellt hat, sodass Sie den Stapel eines separaten Zielthreads durchlaufen können. Beim ersten Mal, wenn der von Ihnen erstellte Thread bestimmte `ICorProfilerInfo*` Methoden (einschließlich) eingibt `DoStackSnapshot` , führt die CLR die Thread spezifische Initialisierung pro Thread in diesem Thread aus. Wenn Ihr Profiler den Zielthread angehalten hat, dessen Stapel Sie durchlaufen möchten, und wenn der Zielthread eine Sperre besitzt, die für die Durchführung dieser Thread spezifischen Initialisierung erforderlich ist, tritt ein Deadlock auf. Um diesen Deadlock zu vermeiden, führen Sie einen ersten Rückruf `DoStackSnapshot` von aus dem vom Profiler erstellten Thread aus, um einen separaten Zielthread zu durchlaufen, aber halten Sie den Zielthread nicht an erster Stelle. Dieser anfängliche-Befehl stellt sicher, dass die Initialisierung pro Thread ohne deadlockvorgang durchgeführt werden kann. Wenn `DoStackSnapshot` erfolgreich ist und mindestens einen Frame meldet, ist es nach diesem Punkt sicher, dass der vom Profiler erstellte Thread sicher ist, dass ein beliebiger Zielthread angehalten und aufgerufen wird, `DoStackSnapshot` um den Stapel dieses Zielthreads zu durchlaufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
