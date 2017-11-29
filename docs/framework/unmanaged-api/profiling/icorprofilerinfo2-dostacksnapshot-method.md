---
title: ICorProfilerInfo2::DoStackSnapshot-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.DoStackSnapshot
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type: apiref
caps.latest.revision: "25"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6a210fc0c1984ee9bc77114ba30c3287ae43b169
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>ICorProfilerInfo2::DoStackSnapshot-Methode
Durchläuft die verwalteten Frames auf dem Stapel für den angegebenen Thread und sendet die Informationen an den Profiler in einem Rückruf.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `thread`  
 [in] Die ID des Zielthreads.  
  
 Übergeben von null in `thread` ergibt sich eine Momentaufnahme des aktuellen Threads. Wenn eine `ThreadID` von ein anderen Thread übergeben wird, hält dieser Thread, führt die Momentaufnahme und setzt die common Language Runtime (CLR).  
  
 `callback`  
 [in] Ein Zeiger auf die Implementierung der [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) Methode, die von der CLR, um den Profiler Informationen über jeden verwalteten Frame und die Ausführung von nicht verwalteten Frames bereitzustellen aufgerufen wird.  
  
 Die `StackSnapshotCallback` Methode wird vom Profilerwriter implementiert.  
  
 `infoFlags`  
 [in] Der Wert der [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) -Enumeration, die gibt die Menge der Daten für jeden Frame von zu übergebenden `StackSnapshotCallback`.  
  
 `clientData`  
 [in] Ein Zeiger auf die Clientdaten, die direkt über, um übergeben wird die `StackSnapshotCallback` Rückruffunktion.  
  
 `context`  
 [in] Ein Zeiger auf eine Win32- `CONTEXT` -Struktur, die verwendet wird, um den Stackwalk zu starten. Die Win32 `CONTEXT` Struktur enthält die Werte der CPU-Register und den Zustand der CPU zu einem bestimmten Zeitpunkt darstellt.  
  
 Bestimmen des Installationsorts für den Stackwalk zu beginnen, wenn der Anfang des Stapels nicht verwalteten Hilfscode ist CLR Startwerts; Andernfalls ist der Ausgangswert ignoriert. Für einen asynchronen Durchlauf muss kein Ausgangswert angegeben werden. Wenn Sie einen synchronen Durchlauf durchführen, ist kein Ausgangswert erforderlich.  
  
 Die `context` Parameter ist nur gültig, wenn das COR_PRF_SNAPSHOT_CONTEXT-Flag, in übergeben wurde der `infoFlags` Parameter.  
  
 `contextSize`  
 [in] Die Größe des der `CONTEXT` -Struktur, die verweist die `context` Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Übergeben von null `thread` ergibt sich eine Momentaufnahme des aktuellen Threads. Momentaufnahmen können von anderen Threads erstellt werden, nur, wenn der Zielthread zu dem Zeitpunkt unterbrochen wurde.  
  
 Wenn der Profiler den Stapel zu durchlaufen möchte, ruft er `DoStackSnapshot`. Bevor die CLR über diesen Aufruf zurückgegeben wird, ruft der `StackSnapshotCallback` mehrere Male einmal für jeden verwalteten Frame (oder die Ausführung von nicht verwalteten Frames) auf dem Stapel. Wenn bei der nicht verwalteten Frames auftreten, müssen Sie sie selbst durchlaufen.  
  
 Die Reihenfolge, in dem der Stapel durchlaufen wird, ist in umgekehrter Reihenfolge wie die Frames auf dem Stapel abgelegt wurden: Frame (zuletzt verschoben) zuerst, Hauptframe (zuerst verschoben) von anderen zuletzt Blattelemente.  
  
 Weitere Informationen dazu, wie Sie den Profiler zum Durchlaufen verwalteter Stapel programmieren, finden Sie unter [Stackwalk in .NET Framework 2.0 Profiler: Grundlagen und mehr](http://go.microsoft.com/fwlink/?LinkId=73638).  
  
 Ein Stackwalk kann synchron oder asynchron sein, wie in den folgenden Abschnitten erläutert.  
  
## <a name="synchronous-stack-walk"></a>Synchroner Stackwalk  
 Ein synchroner Stackwalk umfasst das Durchlaufen des Stapels für den aktuellen Thread als Antwort auf einen Rückruf. Das seeding oder anhalten, ist nicht erforderlich.  
  
 Stellen Sie einen synchronen Aufruf durch, wenn als Antwort auf die CLR einen Aufruf der des Profilers [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (oder [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) Methoden, rufen Sie `DoStackSnapshot` Durchlaufen des Stapels für die aktuellen Thread. Dies ist nützlich, wenn Sie der Stapel bei einer Benachrichtigung wie z. B. illustriert anzeigen möchten [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md). Rufen Sie einfach `DoStackSnapshot` innerhalb Ihrer `ICorProfilerCallback` Methode, und übergeben null in der `context` und `thread` Parameter.  
  
## <a name="asynchronous-stack-walk"></a>Asynchrone Stackwalk  
 Ein asynchroner Stackwalk umfasst das Durchlaufen des Stapels von einem anderen Thread oder das Durchlaufen des aktuellen Threads nicht als Reaktion auf einen Rückruf, sondern durch den aktuellen Thread Anweisungszeiger hijacking. Ein asynchrone Walk erfordert einen Ausgangswert ist der Anfang des Stapels nicht verwaltetem Code, der nicht Teil einer Plattform ist aufrufen (PInvoke) oder COM-Aufruf jedoch Hilfscode in die CLR selbst. Beispielsweise ist Code, Just-in-Time (JIT) kompilieren oder Garbage Collection ausführt, Hilfscode.  
  
 Sie erhalten einen Ausgangswert an, indem Sie direkt durch das Anhalten des Zielthreads, und durchlaufen einen Stapel selbst, bis Sie den obersten gefunden Frame verwaltet. Nachdem der Zielthread angehalten wird, erhalten Sie aktuelle Registerkontext der Zielthread. Als Nächstes zu bestimmen, ob der Registerkontext durch Aufrufen von nicht verwaltetem Code zeigt [ICorProfilerInfo:: GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) – Wenn zurückgegeben wird ein `FunctionID` gleich 0 (null), wird der Frame nicht verwaltetem Code. Durchlaufen Sie jetzt den Stapel, bis Sie den ersten verwalteten Frame zu erreichen, und berechnen Sie den Ausgangswert Kontext auf Grundlage des Registerkontexts für diesen Rahmen.  
  
 Rufen Sie `DoStackSnapshot` mit den Ausgangswert Kontext auf den asynchronen Stackwalk zu beginnen. Wenn Sie keinen Ausgangswert angeben `DoStackSnapshot` verwalteten Frames am oberen Ende des Stapels überspringen und folglich erhalten Sie einen unvollständige Stackwalk. Wenn Sie einen Ausgangswert angeben, muss er auf JIT-kompilierten oder Native Image Generator (Ngen.exe) zeigen-generierter Code; andernfalls `DoStackSnapshot` gibt den Fehlercode CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX zurück.  
  
 Asynchrone Stackwalks können Sie bequem Deadlocks verursachen oder zugriffsverletzungen, es sei denn, Sie die folgenden Richtlinien beachten:  
  
-   Wenn Sie direkt über Threads anhalten, denken Sie daran, dass nur ein Thread, der nicht verwalteten Code ausgeführt hat ein anderer Thread angehalten werden kann.  
  
-   Immer-block in Ihre [ICorProfilerCallback:: ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) Rückruf bis Stackwalk des betreffenden Threads abgeschlossen ist.  
  
-   Aufrechterhalten Sie eine Sperre kann nicht werden, während der Profiler in eine CLR-Funktion aufruft, die eine Garbagecollection auslösen können. Halten Sie also keine Sperre der Besitzerthread ein Aufrufs vorgenommen werden kann, das eine Garbagecollection auslöst.  
  
 Zudem besteht ein Risiko von Deadlocks beim Aufrufen `DoStackSnapshot` von einem anderen Thread, die der Profiler erstellt hat, damit Sie den Stapel eines separaten Zielthreads durchlaufen können. Beim ersten erstellten Thread wechselt bestimmte `ICorProfilerInfo*` Methoden (einschließlich `DoStackSnapshot`), die CLR wird pro Thread, CLR-spezifische Initialisierung auf diesem Thread ausgeführt. Wenn der Profiler den Zielthread angehalten wurde, dessen Stapel zu durchlaufen werden soll, und Zielthread aufgetreten ist, eine Sperre für die Durchführung dieser threadspezifischen Initialisierung erforderlich verfügen, wird ein Deadlock auftreten. Um diese Deadlocks zu vermeiden, stellen Sie in einen ersten Aufruf `DoStackSnapshot` aus dem Thread erstellt mit dem Profiler zum Durchlaufen ein separaten Zielthread, aber den Zielthread nicht zunächst anhalten. Diese ersten Aufruf wird sichergestellt, dass die threadspezifische Initialisierung ohne Deadlock abgeschlossen werden kann. Wenn `DoStackSnapshot` erfolgreich ist, und gibt mindestens einen Frame nach diesem Punkt werden sie alle Zielthread und Aufruf anzuhalten, Profiler erstellte Thread sicher `DoStackSnapshot` , den Stapel der Zielthread zu durchlaufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
