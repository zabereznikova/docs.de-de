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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3a558ad6f87995d6c0a0d164cf96376fba12da4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485264"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>ICorProfilerInfo2::DoStackSnapshot-Methode
Durchläuft die verwalteten Frames im Stapel für den angegebenen Thread und sendet die Informationen an den Profiler in einem Rückruf.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Die ID des Zielthreads.  
  
 Übergeben von null in `thread` ergibt sich eine Momentaufnahme des aktuellen Threads. Wenn eine `ThreadID` von ein anderen Thread übergeben, die common Language Runtime (CLR) hält dieser Thread erstellt eine Momentaufnahme und fortgesetzt wird.  
  
 `callback`  
 [in] Ein Zeiger auf die Implementierung der [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) -Methode, die von der CLR, geben Sie den Profiler mit Informationen über jeden verwalteten Frame und die Ausführung von nicht verwalteten Frames aufgerufen wird.  
  
 Die `StackSnapshotCallback` Methode wird vom Profilerwriter implementiert.  
  
 `infoFlags`  
 [in] Der Wert der [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) -Enumeration, die gibt an, die Menge der Daten für jeden Frame von zu übergebenden `StackSnapshotCallback`.  
  
 `clientData`  
 [in] Ein Zeiger auf die Clientdaten, die direkt, um übergeben wird die `StackSnapshotCallback` Callback-Funktion.  
  
 `context`  
 [in] Ein Zeiger auf eine Win32- `CONTEXT` -Struktur, die verwendet wird, um den Stackwalk zu starten. Die Win32 `CONTEXT` Struktur enthält Werte, der die CPU-Register und stellt den Zustand der CPU zu einem bestimmten Zeitpunkt dar.  
  
 Die CLR Bestimmen des Installationsorts für den Stackwalk zu beginnen, ist der Anfang des Stapels nicht verwalteter Hilfscode Startwerts; Andernfalls wird der Ausgangswert ignoriert. Ein Ausgangswert muss für einen asynchronen Durchlauf angegeben werden. Wenn Sie einen synchronen Durchlauf durchführen, ist kein Ausgangswert erforderlich.  
  
 Die `context` Parameter ist nur gültig, wenn das Flag COR_PRF_SNAPSHOT_CONTEXT übergebene der `infoFlags` Parameter.  
  
 `contextSize`  
 [in] Die Größe des der `CONTEXT` -Struktur, die verweist die `context` Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Übergeben von null `thread` ergibt sich eine Momentaufnahme des aktuellen Threads. Momentaufnahmen können von anderen Threads erstellt werden, nur dann, wenn der Zielthread zur Zeit angehalten wird.  
  
 Wenn Sie möchte, dass der Profiler den Stapel zu durchlaufen, ruft er `DoStackSnapshot`. Bevor die CLR von diesem Aufruf zurückkehrt, ruft Ihre `StackSnapshotCallback` mehrfach, einmal für jeden verwalteten Frame (oder die Ausführung von nicht verwalteten Frames) auf dem Stapel. Wenn nicht verwalteter Frames gefunden werden, müssen Sie sie selbst durchlaufen.  
  
 Die Reihenfolge, in dem der Stapel durchgelaufen wird, ist die Umkehrung des wie die Frames auf dem Stapel abgelegt wurden: zuletzt Blattelemente der Frame (letzte verschoben) ersten, main (zuerst verschoben).  
  
 Weitere Informationen dazu, wie Sie den Profiler zum Durchlaufen verwalteter Stapel programmieren, finden Sie unter [Profiler Durchlaufen von Stapeln im .NET Framework 2.0: Grundlagen und mehr](https://go.microsoft.com/fwlink/?LinkId=73638).  
  
 Ein Stackwalk kann synchron oder asynchron sein, wie in den folgenden Abschnitten erläutert.  
  
## <a name="synchronous-stack-walk"></a>Synchroner Stackwalk  
 Ein synchroner Stackwalk umfasst den Stapel des aktuellen Threads in Reaktion auf einen Rückruf zu durchlaufen. Das seeding oder angehalten ist nicht erforderlich.  
  
 Sie stellen einen synchronen Aufruf durch, wenn als Reaktion auf die CLR einen Aufruf der Ihres Profilers [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (oder [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md))-Methoden aufrufen, Sie `DoStackSnapshot` Durchlaufen des Stapels für die aktuellen Thread. Dies ist nützlich, wenn Sie möchten, finden Sie unter der Stapel bei einer Benachrichtigung wie sieht [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md). Rufen Sie einfach `DoStackSnapshot` innerhalb Ihrer `ICorProfilerCallback` -Methode und übergeben null in der `context` und `thread` Parameter.  
  
## <a name="asynchronous-stack-walk"></a>Asynchroner Stapeldurchlauf  
 Ein asynchroner Stapeldurchlauf umfasst den Stapel eines anderen Threads zu durchlaufen oder das Durchlaufen des Stapels für den aktuellen Thread nicht in der Antwort auf einen Rückruf, jedoch über den Anweisungszeiger des aktuellen Threads hijacking. Asynchroner Durchlauf erfordert einen Ausgangswert ist der Anfang des Stapels nicht verwalteter Code, der nicht Teil einer Plattform ist Plattformaufruf (PInvoke) oder COM-Aufruf, aber Hilfscode in der CLR selbst. Code, der just-in-Time (JIT) Kompilierung oder Garbage Collection ist z. B. Hilfscode.  
  
 Sie erhalten einen Ausgangswert an, indem Sie den Zielthread direkt anhalten von und seinen Stapel durchlaufen selbst bis Sie den obersten finden verwalteten Frame. Nachdem der Zielthread angehalten wird, erhalten Sie aktuellen Registerkontext in den Zielthread an. Als Nächstes zu bestimmen, ob der Registerkontext auf nicht verwalteten Code durch den Aufruf zeigt [ICorProfilerInfo:: GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) – Wenn zurückgegeben wird ein `FunctionID` gleich 0 (null) ist, wird der Frame nicht verwaltetem Code. Führen Sie nun den Stapel, bis Sie den ersten verwalteten Frame erreichen, und klicken Sie dann die Seed-Kontext, der basierend auf der Registerkontext für diesen Frame zu berechnen.  
  
 Rufen Sie `DoStackSnapshot` mit den Kontext Ihres Ausgangswerts, um den asynchronen Stackwalk zu beginnen. Wenn Sie keinen Ausgangswert angeben `DoStackSnapshot` verwalteten Frames an der Spitze des Stapels überspringen und, folglich erhalten Sie einen unvollständiger Stackwalk. Wenn Sie einen Ausgangswert angeben, müssen sie zeigen Sie auf die JIT-Kompilierung oder Native Image Generator (Ngen.exe)-Code generiert andernfalls `DoStackSnapshot` gibt den Fehlercode CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX zurück.  
  
 Asynchroner Stapeldurchläufe können leicht dazu führen, dass Deadlocks oder zugriffsverletzungen, es sei denn, Sie die folgenden Richtlinien beachten:  
  
-   Wenn Sie direkt über Threads anhalten, denken Sie daran, dass nur ein Thread, der nie verwalteten Code ausgeführt hat einen anderen Thread anhalten kann.  
  
-   Immer-block in Ihre [ICorProfilerCallback:: ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) Rückruf bis zum Abschluss der Stapeldurchlauf dieses Threads.  
  
-   Führen Sie keine Sperre, während Ihr Profiler an eine CLR-Funktion aufruft, die eine Garbagecollection auslösen können. D. h. keine Sperre, wenn der belegende Thread einen Aufruf durchführen kann, der eine Garbagecollection auslöst.  
  
 Es gibt auch Risiko eines Deadlocks Aufrufen `DoStackSnapshot` von einem Thread, der Ihr Profiler erstellt wurde, damit Sie den Stapel des einen separaten Zielthread zu durchlaufen können. Beim ersten erstellten Thread gibt bestimmte `ICorProfilerInfo*` Methoden (einschließlich `DoStackSnapshot`), die CLR wird pro Thread, CLR-spezifische-Initialisierung auf diesem Thread ausgeführt. Wenn Ihr Profiler den Zielthread angehalten hat, dessen Stapel, die Sie durchlaufen möchten, und Zielthread aufgetreten ist, eine Sperre für diese Initialisierung pro Thread durchführen besitzen, wird ein Deadlock auftreten. Um diese Deadlocks zu vermeiden, stellen Sie einen anfänglichen Aufruf in `DoStackSnapshot` aus Ihrem Profiler erstellte Thread durchlaufen ein separaten Thread, als Zielplattform halten den Zielthread nicht zuerst. Diese ersten Aufruf wird sichergestellt, dass die Initialisierung pro Thread ohne Deadlock durchführen kann. Wenn `DoStackSnapshot` erfolgreich ist, und meldet Sie mindestens einen Frame nach diesem Punkt, sie werden alle Zielthread und der Aufruf angehalten, Profiler erstellte Thread sicher `DoStackSnapshot` auf den Stapel Zielthread zu durchlaufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
