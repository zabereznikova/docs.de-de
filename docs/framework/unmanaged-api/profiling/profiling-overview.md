---
title: Übersicht über die Profilerstellung
ms.date: 03/30/2017
helpviewer_keywords:
- managed code, profiling API support
- unmanaged code, combining with managed code in profiling
- notification threads [.NET Framework profiling]
- unmanaged code, profiling
- profiling API [.NET Framework], and COM
- profiling API [.NET Framework], unmanaged code profiling
- profilers, writing
- profiling API [.NET Framework], call stacks
- code profilers, writing
- profiling API [.NET Framework], security considerations
- profiling API [.NET Framework], managed code support
- common language runtime, profiling
- profiling API [.NET Framework], notification threads
- call stacks [.NET Framework profiling]
- profiling API [.NET Framework], stack depth
- common language runtime, writing a profiler
- profiling API [.NET Framework], information retrieval interfaces
- shadow stacks [.NET Framework profiling]
- COM, using in the profiling API
- stack snapshots [.NET Framework profiling]
- profiling API [.NET Framework], supported features
- profiling API [.NET Framework], overview
- security, profiling API considerations
- stack depth [.NET Framework profiling]
ms.assetid: 864c2344-71dc-46f9-96b2-ed59fb6427a8
ms.openlocfilehash: cf29260c36437aaf679498f648d0fcac5d65f321
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558328"
---
# <a name="profiling-overview"></a>Übersicht über die Profilerstellung

Ein Profiler ist ein Tool, das die Ausführung einer anderen Anwendung überwacht. Ein Common Language Runtime (CLR)-Profiler ist eine Dynamic Link Library (DLL), die aus Funktionen besteht, die mithilfe der Profilerstellungs-API Meldungen von der CLR empfangen und an diese senden. Die Profiler-DLL wird zur Laufzeit von der CLR geladen.

Herkömmliche Profilerstellungstools dienen vorwiegend dazu, die Ausführung der Anwendung zu messen. Das bedeutet, dass sie die für jede Funktion aufgebrachte Zeit und die Speicherauslastung der Anwendung über einen bestimmten Zeitraum messen. Die Profilerstellungs-API zielt auf eine breitere Klasse von Diagnosetools ab, z. B. Dienstprogramme zur Codeabdeckung und sogar erweiterte Debughilfen. Diese Verwendungsmöglichkeiten sind ausnahmslos von diagnostischer Natur. Die Profilerstellungs-API misst nicht nur die Ausführung einer Anwendung, sondern überwacht sie auch. Aus diesem Grund sollte die Profilerstellungs-API nie von der Anwendung selbst verwendet werden, und die Ausführung der Anwendung sollte nicht vom Profiler abhängen (oder davon beeinflusst werden).

Die Profilerstellung für eine CLR-Anwendung erfordert eine weiter reichende Unterstützung als die Profilerstellung für Computercode, der auf herkömmliche Weise kompiliert wurde. Dies liegt darin begründet, dass von der CLR Konzepte wie Anwendungsdomänen, Garbage Collection, verwaltete Ausnahmenbehandlung, Just-In-Time (JIT)-Kompilierung von Code (die Konvertierung von Microsoft Intermediate Language- bzw. MSIL-Code in nativen Computercode) und ähnliche Funktionen eingeführt werden. Herkömmliche Profilerstellungsmechanismen können keine nützlichen Informationen über diese Funktionen identifizieren oder bereitstellen. Die Profilerstellungs-API liefert diese fehlenden Informationen hingegen in effizienter Weise und mit minimalen Auswirkungen auf die Leistung der CLR und die Anwendung, für die das Profil erstellt wird.

Die JIT-Kompilierung zur Laufzeit bietet hervorragende Möglichkeiten zur Profilerstellung. Die Profilerstellungs-API ermöglicht einem Profiler, den speicherinternen MSIL-Codestream für eine Routine zu ändern, bevor er JIT-kompiliert wird. Auf diese Weise kann der Profiler bestimmten Routinen, die genauer überprüft werden müssen, Instrumentierungscode dynamisch hinzufügen. Dieser Ansatz ist zwar auch in herkömmlichen Szenarios möglich, lässt sich aber für die CLR mit der Profilerstellungs-API wesentlich einfacher umsetzen.

## <a name="the-profiling-api"></a>Die Profilerstellungs-API

In der Regel wird die Profilerstellungs-API verwendet, um einen *Codeprofiler*zu schreiben. dabei handelt es sich um ein Programm, das die Ausführung einer verwalteten Anwendung überwacht.

Die Profilerstellungs-API wird von einer Profiler-DLL verwendet, die in den gleichen Prozess geladen wird wie die Anwendung, für die ein Profil erstellt wird. Die Profiler-DLL implementiert eine Rückruf Schnittstelle ([ICorProfilerCallback](icorprofilercallback-interface.md) in den .NET Framework Version 1,0 und 1,1, [ICorProfilerCallback2](icorprofilercallback2-interface.md) in Version 2,0 und höher). Die CLR ruft die Methoden in dieser Schnittstelle auf, um den Profiler über Ereignisse im profilierten Prozess zu benachrichtigen. Der Profiler kann mithilfe der Methoden in der [ICorProfilerInfo](icorprofilerinfo-interface.md) -Schnittstelle und der [ICorProfilerInfo2](icorprofilerinfo2-interface.md) -Schnittstelle einen Rückruf für die Laufzeit durchgeführt werden, um Informationen über den Status der profilierten Anwendung zu erhalten.

> [!NOTE]
> Lediglich der zur Datenerfassung verwendete Teil der Profilerlösung sollte im gleichen Prozess ausgeführt werden wie die Anwendung, für die ein Profil erstellt wird. Alle Benutzeroberflächen- und Datenanalysevorgänge sollten in einem separaten Prozess ausgeführt werden.

Die folgende Abbildung zeigt, wie die Profiler-DLL mit der Anwendung, für die ein Profil erstellt wird, und der CLR interagiert.

![Screenshot, der die Profil Erstellungs Architektur anzeigt](./media/profiling-overview/profiling-architecture.png)

### <a name="the-notification-interfaces"></a>Die Benachrichtigungsschnittstellen

[ICorProfilerCallback](icorprofilercallback-interface.md) und [ICorProfilerCallback2](icorprofilercallback2-interface.md) können als Benachrichtigungs Schnittstellen angesehen werden. Diese Schnittstellen bestehen aus Methoden wie [ClassLoadStarted](icorprofilercallback-classloadstarted-method.md), [ClassLoadStarted](icorprofilercallback-classloadfinished-method.md)und [JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md). Jedes Mal, wenn die CLR eine Klasse lädt oder entlädt, eine Funktion kompiliert usw., ruft sie die entsprechende Methode in der `ICorProfilerCallback`-Schnittstelle oder in der `ICorProfilerCallback2`-Schnittstelle des Profilers auf.

Ein Profiler könnte z. b. die Code Leistung über zwei Benachrichtigungsfunktionen Messen: [FunctionEnter2](functionenter2-function.md) und [FunctionLeave2](functionleave2-function.md). Dazu versieht er lediglich jede Benachrichtigung mit einem Zeitstempel, sammelt Ergebnisse und gibt eine Liste aus, aus der ersichtlich ist, welche Funktionen während der Anwendungsausführung die meiste CPU- oder Realzeit in Anspruch genommen haben.

### <a name="the-information-retrieval-interfaces"></a>Die Datenabrufschnittstellen

Die anderen Haupt Schnittstellen, die an der Profilerstellung beteiligt sind, sind [ICorProfilerInfo](icorprofilerinfo-interface.md) und [ICorProfilerInfo2](icorprofilerinfo2-interface.md). Der Profiler ruft diese Schnittstellen nach Bedarf auf, um weitere Daten für seine Analysen abzurufen. Wenn die CLR z. b. die [FunctionEnter2](functionenter2-function.md) -Funktion aufruft, stellt Sie einen Funktions Bezeichner bereit. Der Profiler kann weitere Informationen zu dieser Funktion abrufen, indem die [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) -Methode aufgerufen wird, um die übergeordnete Klasse der Funktion, Ihren Namen usw. zu ermitteln.

## <a name="supported-features"></a>Unterstützte Funktionen

Die Profilerstellungs-API bietet Informationen über verschiedene Ereignisse und Aktionen in der Common Language Runtime. Sie können diese Informationen zum Überwachen der internen Funktionsweise von Prozessen und zum Analysieren der Leistung Ihrer .NET Framework-Anwendung verwenden.

Die Profilerstellungs-API ruft Informationen über die folgenden Aktionen und die Ereignisse ab, die in der CLR auftreten:

- CLR-Ereignisse beim Starten und Herunterfahren.

- Ereignisse bei der Anwendungsdomänenerstellung und beim Herunterfahren.

- Ereignisse beim Laden und Entladen von Assemblys.

- Ereignisse beim Laden und Entladen von Ereignissen.

- Ereignisse beim Erstellen und Löschen von COM-vtable.

- Ereignisse bei der JIT-Kompilierung (Just-In-Time) und beim Codepitching.

- Ereignisse beim Laden und Entladen von Klassen.

- Ereignisse beim Erstellen und Löschen von Threads.

- Ereignisse beim Funktionseinstieg und Funktionsende.

- Ausnahmen.

- Übergänge zwischen verwalteter und nicht verwalteter Codeausführung.

- Übergänge zwischen verschiedenen Laufzeitkontexten.

- Informationen über Laufzeitunterbrechungen.

- Informationen über den Laufzeitspeicherheap und die Garbage Collection-Aktivität.

Die Profilerstellungs-API kann von jeder (nicht verwalteten) COM-kompatiblen Sprache aufgerufen werden.

Die API ist im Hinblick auf die Prozessor- und Speicherauslastung effizient. Durch die Profilerstellung werden an der Anwendung mit Profil keine Änderungen durchgeführt, die so signifikant sind, dass es zu falschen Ergebnissen kommt.

Die Profilerstellungs-API ist sowohl für Samplingprofiler als auch für andere Profiler nützlich. Ein *Samplingprofiler* überprüft das Profil zu regulären Takt Einheiten, z. A. 5 Millisekunden voneinander entfernt. Ein *nicht-Sampling-Profiler* wird über ein Ereignis synchron mit dem Thread informiert, der das Ereignis auslöst.

### <a name="unsupported-functionality"></a>Nicht unterstützte Funktionalität

Die Profilerstellungs-API unterstützt die folgenden Funktionen nicht:

- Nicht verwalteter Code, der mit konventionellen Win32-Methoden profiliert werden muss. Der CLR-Profiler umfasst jedoch Übergangsereignisse, um die Grenzen zwischen verwaltetem und nicht verwaltetem Code zu ermitteln.

- Sich selbst ändernde Anwendungen, die ihren eigenen Code zu bestimmten Zwecken, beispielsweise bei der aspektorientierten Programmierung, selbsttätig ändern.

- Grenzüberprüfung, da die Profilerstellungs-API diese Informationen nicht bereitstellt. Die CLR bietet systeminterne Unterstützung für die Überprüfung von Grenzen des gesamten verwalteten Codes.

- Remoteprofilerstellung, die aus den folgenden Gründen nicht unterstützt wird:

  - Durch die Remoteprofilerstellung verlängert sich die Ausführungszeit. Bei der Verwendung der Profilerstellungsschnittstellen müssen Sie die Ausführungszeit minimieren, damit die Auswirkungen auf die Profilerstellungsergebnisse möglichst gering bleiben. Dies trifft insbesondere dann zu, wenn die Ausführungsleistung überwacht wird. Dabei stellt die Remoteprofilerstellung jedoch keine Einschränkung dar, wenn Profilerstellungsschnittstellen zum Überwachen der Speicherauslastung oder zum Abrufen von Laufzeitinformationen über Stapelrahmen, Objekte usw. verwendet werden.

  - Der CLR-Codeprofiler muss mindestens eine Rückrufschnittstelle bei der Laufzeit des lokalen Computers registrieren, auf dem die Anwendung mit Profil ausgeführt wird. Hierdurch wird die Möglichkeit eingeschränkt, einen Remotecodeprofiler zu erstellen.

## <a name="notification-threads"></a>Benachrichtigungsthreads

In den meisten Fällen führt der Thread, der ein Ereignis generiert, auch Benachrichtigungen aus. Solche Benachrichtigungen (z. b. [FunctionEnter](functionenter-function.md) und [FunctionLeave](functionleave-function.md)) müssen nicht explizit bereitgestellt werden `ThreadID` . Zudem kann der Profiler basierend auf der `ThreadID` des jeweiligen Threads entscheiden, seine Analyseblöcke im lokalen Threadspeicher zu speichern und zu aktualisieren, anstatt die Analyseblöcke im globalen Speicher zu indizieren.

Beachten Sie, dass diese Rückrufe nicht serialisiert werden. Benutzer müssen ihren Code schützen, indem sie threadsichere Datenstrukturen erstellen und den Profilercode ggf. sperren, um zu verhindern, dass mehrere Threads parallel darauf zugreifen. Deshalb kann es in bestimmten Fällen passieren, dass Sie eine ungewöhnliche Sequenz von Rückrufen erhalten. Nehmen Sie z. B. an, dass eine verwaltete Anwendung zwei Threads erzeugt, die identischen Code ausführen. In diesem Fall ist es möglich, ein [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) -Ereignis für eine Funktion von einem Thread und einen `FunctionEnter` Rückruf vom anderen Thread zu empfangen, bevor der [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationfinished-method.md) -Rückruf empfangen wird. In diesem Fall erhält der Benutzer einen `FunctionEnter`-Rückruf für eine Funktion, für die möglicherweise noch keine vollständige JIT-Kompilierung (Just-In-Time) erfolgt ist.

## <a name="security"></a>Sicherheit

Eine Profilerstellungs-DLL ist eine nicht verwaltete DLL, die als Teil der Common Language Runtime-Ausführungs-Engine ausgeführt wird. Daher gelten die Einschränkungen für die Sicherheit des Zugriffs auf verwalteten Code nicht für den Code in der Profilerstellungs-DLL. Für die Profilerstellungs-DLL gelten nur die Einschränkungen, die das Betriebssystem für den Benutzer erzwingt, der die Anwendung mit Profil ausführt.

Entwickler von Profilern sollten entsprechende Vorkehrungen treffen, um sicherheitsrelevante Probleme zu vermeiden. So sollte beispielsweise eine Profilerstellungs-DLL während der Installation in eine Zugriffssteuerungsliste (ACL) aufgenommen werden, damit sie nicht durch böswillige Benutzer geändert werden kann.

## <a name="combining-managed-and-unmanaged-code-in-a-code-profiler"></a>Kombination von verwaltetem und nicht verwaltetem Code in einem Codeprofiler

Ein falsch geschriebener Profiler kann zirkuläre Verweise auf sich selbst verursachen und zu unvorhersehbarem Verhalten führen.

Bei näherer Betrachtung der Profilerstellungs-API kann der Eindruck entstehen, dass es möglich wäre, einen Profiler mit verwalteten und nicht verwalteten Komponenten zu schreiben, die sich gegenseitig über COM-Interop oder indirekte Aufrufe aufrufen.

Obwohl dies aus der Entwurfsperspektive möglich ist, unterstützt die Profilerstellungs-API keine verwalteten Komponenten. Ein CLR-Profiler darf keinerlei verwaltete Komponenten enthalten. Versuche, verwalteten und nicht verwalteten Code in einem CLR-Profiler zu kombinieren, können Regelverletzungen, Programmausfälle oder Deadlocks verursachen. Die verwalteten Komponenten des Profilers verweisen Ereignisse zurück an ihre nicht verwalteten Komponenten, die in der Folge erneut die verwalteten Komponenten aufrufen. Dies führt zu zirkulären Verweisen.

Der einzige Ort, an dem ein CLR-Profiler verwalteten Code sicher aufrufen kann, ist innerhalb des Texts einer Methode im MSIL-Code (Microsoft Intermediate Language). Die empfohlene Vorgehensweise zum Ändern des MSIL-Texts besteht darin, die Methoden der JIT-Neukompilierung in der [ICorProfilerCallback4](icorprofilercallback4-interface.md) -Schnittstelle zu verwenden.

Es können auch die älteren Instrumentationsmethoden zum Ändern von MSIL verwendet werden. Bevor die Just-in-time (JIT)-Kompilierung einer Funktion abgeschlossen ist, kann der Profiler verwaltete Aufrufe in den MSIL-Text einer Methode einfügen und ihn dann JIT-Kompilieren (siehe die [ICorProfilerInfo:: GetILFunctionBody](icorprofilerinfo-getilfunctionbody-method.md) -Methode). Diese Technik lässt sich erfolgreich für die selektive Instrumentierung von verwaltetem Code oder für die Erfassung von Statistik- und Leistungsdaten für JIT verwenden.

Alternativ dazu kann ein Codeprofiler native Hooks in den MSIL-Text jeder verwalteten Funktion einfügen, die nicht verwalteten Code aufruft. Diese Technik kann für Instrumentation und Abdeckung verwendet werden. So kann beispielsweise ein Codeprofiler Instrumentierungshooks nach jedem MSIL-Block einfügen, um sicherzustellen, dass der Block ausgeführt wurde. Bei der Modifikation des MSIL-Texts einer Methode muss sehr sorgfältig vorgegangen werden, und eine Vielzahl von Faktoren muss berücksichtigt werden.

## <a name="profiling-unmanaged-code"></a>Profilerstellung für nicht verwalteten Code

Die Profilerstellungs-API der Common Language Runtime (CLR) bietet minimale Unterstützung zur Profilerstellung für nicht verwalteten Code. Die folgende Funktionalität wird bereitgestellt:

- Enumeration von Stapelketten. Diese Funktion ermöglicht einem Codeprofiler, die Grenze zwischen verwaltetem und nicht verwaltetem Code zu bestimmen.

- Feststellung, ob eine Stapelkette verwaltetem oder nativem Code entspricht.

In .NET Framework, Version 1.0 und 1.1, sind diese Methoden über den prozessinternen Teil der Debug-API der CLR verfügbar. Sie sind in der Datei "CorDebug.idl" definiert.

In den .NET Framework 2,0 und höher können Sie die [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode für diese Funktionalität verwenden.

## <a name="using-com"></a>Verwenden von COM

Obwohl die Profilerstellungsschnittstellen als COM-Schnittstellen definiert sind, initialisiert die Common Language Runtime (CLR) COM tatsächlich nicht zur Verwendung dieser Schnittstellen. Der Grund hierfür ist, dass Sie das Thread Modell nicht mithilfe der [CoInitialize](/windows/desktop/api/objbase/nf-objbase-coinitialize) -Funktion festlegen müssen, bevor die verwaltete Anwendung die Möglichkeit hatte, das gewünschte Threading Modell anzugeben. Ähnlich sollte auch der Profiler selbst `CoInitialize`, nicht aufrufen, da sonst ein Threadingmodell ausgewählt werden könnte, das mit der Anwendung, für die ein Profil erstellt wird, nicht kompatibel ist und es daher zu einem Anwendungsfehler kommen kann.

## <a name="call-stacks"></a>Aufruflisten

Die Profilerstellungs-API bietet zwei Methoden zum Abrufen von Aufruflisten: eine Stapelmomentaufnahmemethode, mit der Anruflisten sporadisch überwacht werden können, und eine Schattenstapelmethode, mit der Anruflisten laufend überwacht werden können.

### <a name="stack-snapshot"></a>Stapelmomentaufnahme

Unter einer Stapelmomentaufnahme versteht man die Überwachung eines Threadstapels zu einem bestimmten Zeitpunkt. Die Profilerstellungs-API unterstützt die Überwachung von verwalteten Funktionen im Stapel, überlässt jedoch die Überwachung nicht verwalteter Funktionen dem Stackwalker des Profilers.

Weitere Informationen zum Programmieren des Profilers zum Durchlaufen verwalteter Stapel finden Sie in der [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode in dieser Dokumentation und [im Abschnitt "Profiler Stack Walking" in der .NET Framework 2,0: Basics und darüber hinaus](/previous-versions/dotnet/articles/bb264782(v=msdn.10)).

### <a name="shadow-stack"></a>Schattenstapel

Die allzu häufige Verwendung der Momentaufnahmemethode kann schnell zu Leistungseinbußen führen. Wenn Sie Stapel Überwachungen häufig erstellen möchten, sollte der Profiler stattdessen einen Schatten Stapel erstellen, indem er die Ausnahme Rückrufe [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), [FunctionTailcall2](functiontailcall2-function.md)und [ICorProfilerCallback2](icorprofilercallback2-interface.md) verwendet. Der Schattenstapel ist immer aktuell und kann schnell in den Speicher kopiert werden, wenn eine Stapelmomentaufnahme benötigt wird.

Mit einem Schattenstapel können Funktionsargumente, Rückgabewerte und Informationen über generische Instanziierungen abgerufen werden. Diese Informationen sind nur über den Schattenstapel verfügbar und können abgerufen werden, wenn die Steuerung an eine Funktion übergeben wird. Sobald die Funktion ausgeführt wird, sind diese Informationen u. U. jedoch nicht mehr verfügbar.

## <a name="callbacks-and-stack-depth"></a>Rückrufe und Stapeltiefe

Profilerrückrufe können ausgegeben werden, wenn der Stapel stark eingeschränkt ist, und ein Stapelüberlauf in einem Profilerrückruf führt zum sofortigen Prozessende. Ein Profiler sollte bei der Reaktion auf Rückrufe möglichst wenige Stapel verwenden. Wenn der Profiler für Prozesse verwendet werden soll, die vor Stapelüberlauf geschützt sind, sollte der Profiler selbst möglichst auch keinen Stapelüberlauf auslösen.

## <a name="related-topics"></a>Verwandte Themen

|Titel|BESCHREIBUNG|
|-----------|-----------------|
|[Einrichten einer Profilerstellungsumgebung](setting-up-a-profiling-environment.md)|Erklärt, wie ein Profiler initialisiert, Ereignisbenachrichtigungen festgelegt und ein Profil für einen Windows-Dienst erstellt werden.|
|[Profilerstellungsschnittstellen](profiling-interfaces.md)|Beschreibt die nicht verwalteten Schnittstellen, die die Profilerstellungs-API verwendet.|
|[Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)|Beschreibt die nicht verwalteten globalen statischen Funktionen, die die Profilerstellungs-API verwendet.|
|[Profilerstellungsenumerationen](profiling-enumerations.md)|Beschreibt die nicht verwalteten Enumerationen, die die Profilerstellungs-API verwendet.|
|[Profilerstellungsstrukturen](profiling-structures.md)|Beschreibt die nicht verwalteten Strukturen, die die Profilerstellungs-API verwendet.|
