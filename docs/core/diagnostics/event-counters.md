---
title: EventCounters in .NET Core
description: In diesem Artikel erfahren Sie, was EventCounters sind, wie Sie diese implementieren und wie Sie sie nutzen können.
ms.date: 08/07/2020
ms.openlocfilehash: 68868ff8b4e1393fc3b23af2bc8eef239ac56975
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024963"
---
# <a name="eventcounters-in-net-core"></a>EventCounters in .NET Core

**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen

EventCounters sind .NET Core-APIs, die für eine schlanke und plattformübergreifende Leistungsmetriksammlung nahezu in Echtzeit verwendet werden. EventCounters wurden als plattformübergreifende Alternative zu den „Leistungsindikatoren“ von .NET Framework unter Windows hinzugefügt. In diesem Artikel erfahren Sie, was EventCounters sind, wie Sie diese implementieren und wie Sie sie nutzen können.

Die .NET Core-Laufzeit und einige .NET-Bibliotheken veröffentlichen grundlegende Diagnoseinformationen mithilfe von EventCounters ab .NET Core 3.0. Abgesehen von den EventCounters, die von der .NET-Laufzeit bereitgestellt werden, können Sie auch Ihre eigenen EventCounters implementieren. EventCounters kann zum Nachverfolgen verschiedener Metriken verwendet werden.

EventCounters sind Teil einer <xref:System.Diagnostics.Tracing.EventSource> und werden in regelmäßigen Abständen automatisch an Listenertools übermittelt. Wie alle anderen Ereignisse für eine <xref:System.Diagnostics.Tracing.EventSource> können Sie sowohl in-process als auch out-of-process über <xref:System.Diagnostics.Tracing.EventListener> und EventPipe genutzt werden. Dieser Artikel konzentriert sich auf die plattformübergreifenden Funktionen von EventCounters und schließt PerfView und ETW (Event Tracing for Windows, Ereignisablaufverfolgung für Windows) bewusst aus, obwohl beides mit EventCounters verwendet werden kann.

![Abbildung zu EventCounters in-process und out-of-process](media/event-counters.svg)

[!INCLUDE [available-counters](includes/available-counters.md)]

## <a name="eventcounter-api-overview"></a>Übersicht über die EventCounter-API

Es gibt zwei Hauptkategorien von Leistungsindikatoren. Einige Leistungsindikatoren beziehen sich auf „Ratenwerte“, etwa auf die Gesamtzahl der Ausnahmen, die Gesamtzahl der GCs und die Gesamtzahl der Anforderungen. Andere Leistungsindikatoren sind „Momentaufnahmewerte“, z. B. Heapverwendung, CPU-Auslastung und Arbeitssatzgröße. Innerhalb jeder dieser Kategorien von Indikatoren gibt es zwei Arten von Indikatoren, die sich dadurch unterscheiden, wie sie ihren Wert ermitteln. Abrufindikatoren erhalten ihren Wert über einen Rückruf, und bei nicht abrufenden Indikatoren wird der Wert direkt für die Instanz des Indikators festgelegt.

Die Indikatoren werden durch die folgenden Implementierungen dargestellt:

* <xref:System.Diagnostics.Tracing.EventCounter>
* <xref:System.Diagnostics.Tracing.IncrementingEventCounter>
* <xref:System.Diagnostics.Tracing.IncrementingPollingCounter>
* <xref:System.Diagnostics.Tracing.PollingCounter>

Ein Ereignislistener gibt an, wie lang Messintervalle sind. Am Ende jedes Intervalls wird ein Wert an den Listener für jeden Indikator übermittelt. Die Implementierungen eines Indikators bestimmen, welche APIs und Berechnungen verwendet werden, um den Wert für jedes Intervall zu generieren.

1. <xref:System.Diagnostics.Tracing.EventCounter> zeichnet einen Satz von Werten auf. Die <xref:System.Diagnostics.Tracing.EventCounter.WriteMetric%2A?displayProperty=nameWithType>-Methode fügt dem Satz einen neuen Wert hinzu. Mit jedem Intervall wird eine statistische Zusammenfassung für den Satz berechnet, z. B. Mindestwert, Maximalwert und Mittelwert. Das Tool [dotnet-counters](dotnet-counters.md) zeigt immer den Mittelwert an. <xref:System.Diagnostics.Tracing.EventCounter> ist nützlich, um einen diskreten Satz von Vorgängen zu beschreiben. Zu den üblichen Verwendungszwecken kann die Überwachung der durchschnittlichen Größe der jüngsten E/A-Vorgänge in Bytes oder des durchschnittlichen Geldwerts einer Reihe von Finanztransaktionen gehören.

1. <xref:System.Diagnostics.Tracing.IncrementingEventCounter> zeichnet eine laufende Summe für jedes Zeitintervall auf. Die <xref:System.Diagnostics.Tracing.IncrementingEventCounter.Increment%2A?displayProperty=nameWithType>-Methode fügt der Summe Werte hinzu. Wenn `Increment()` z. B. drei Mal während eines Intervalls mit den Werten `1`, `2` und `5` aufgerufen wird, wird die laufende Summe von `8` als Indikatorwert für dieses Intervall gemeldet. Mit dem Tool [dotnet-counters](dotnet-counters.md) wird die Rate als die aufgezeichnete Summe/Zeit angezeigt. <xref:System.Diagnostics.Tracing.IncrementingEventCounter> ist hilfreich, um zu messen, wie häufig eine Aktion ausgeführt wird, z. B. die Anzahl der pro Sekunde verarbeiteten Anforderungen.

1. <xref:System.Diagnostics.Tracing.PollingCounter> verwendet einen Rückruf, um den Wert zu bestimmen, der gemeldet wird. Bei jedem Zeitintervall wird die vom Benutzer bereitgestellte Rückruffunktion aufgerufen, und der Rückgabewert wird als Indikatorwert verwendet. <xref:System.Diagnostics.Tracing.PollingCounter> kann verwendet werden, um eine Metrik aus einer externen Quelle abzufragen, z. B. zum Abrufen der aktuellen freien Bytes auf einem Datenträger. Der Indikator kann auch verwendet werden, um benutzerdefinierte Statistiken aufzuzeichnen, die bei Bedarf von einer Anwendung berechnet werden können. Beispiele hierfür sind Angaben zum 95. Perzentil der aktuellen Anforderungslatenz oder die aktuelle Treffer- oder Fehlquote eines Caches.

1. <xref:System.Diagnostics.Tracing.IncrementingPollingCounter> verwendet einen Rückruf, um den gemeldeten Inkrementwert zu ermitteln. In jedem Zeitintervall wird der Rückruf aufgerufen, dann wird die Differenz zwischen dem aktuellen Aufruf und dem letzten Aufruf als gemeldeter Wert verwendet. Das Tool [dotnet-counters](dotnet-counters.md) zeigt die Differenz immer als Rate an, als aufgezeichneten Wert bzw. als Zeit. Dieser Indikator ist nützlich, wenn es nicht praktikabel ist, eine API für jedes Vorkommen aufzurufen, aber die Möglichkeit besteht, die Gesamtzahl der Vorkommen abzufragen. Sie könnten z. B. die Anzahl der pro Sekunde in eine Datei geschriebenen Bytes aufzeichnen, auch ohne Benachrichtigung bei jedem Schreiben eines Bytes.

## <a name="implement-an-eventsource"></a>Implementieren einer EventSource

Der folgende Code implementiert eine Beispiel-<xref:System.Diagnostics.Tracing.EventSource>, die als benannter `"Sample.EventCounter.Minimal"`-Anbieter zur Verfügung gestellt wird. Diese Quelle enthält ein <xref:System.Diagnostics.Tracing.EventCounter>-Element,das die Anforderungsverarbeitungszeit darstellt. Ein solcher Indikator besitzt einen Namen (d. h. seine eindeutige ID in der Quelle) und einen Anzeigenamen. Beides wird von Listenertools wie [dotnet-counter](dotnet-counters.md) verwendet.

:::code language="csharp" source="snippets/EventCounters/MinimalEventCounterSource.cs":::

Sie verwenden `dotnet-counters ps`, um eine Liste der .NET-Prozesse anzuzeigen, die überwacht werden können:

```console
dotnet-counters ps
   1398652 dotnet     C:\Program Files\dotnet\dotnet.exe
   1399072 dotnet     C:\Program Files\dotnet\dotnet.exe
   1399112 dotnet     C:\Program Files\dotnet\dotnet.exe
   1401880 dotnet     C:\Program Files\dotnet\dotnet.exe
   1400180 sample-counters C:\sample-counters\bin\Debug\netcoreapp3.1\sample-counters.exe
```

Übergeben Sie den <xref:System.Diagnostics.Tracing.EventSource>-Namen an den `counter_list`-Schalter, um die Überwachung des Indikators zu starten:

```console
dotnet-counters monitor --process-id 1400180 Sample.EventCounter.Minimal
```

Das folgende Beispiel zeigt die Überwachunsausgabe:

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[Samples-EventCounterDemos-Minimal]
    Request Processing Time (ms)                            0.445
```

Drücken Sie <kbd>q</kbd>, um den Überwachungsbefehl zu beenden.

#### <a name="conditional-counters"></a>Bedingte Indikatoren

Beim Implementieren einer <xref:System.Diagnostics.Tracing.EventSource>können die enthaltenen Leistungsindikatoren bedingt instanziiert werden, wenn die <xref:System.Diagnostics.Tracing.EventSource.OnEventCommand%2A?displayProperty=nameWithType>-Methode mit dem Wert <xref:System.Diagnostics.Tracing.EventCommandEventArgs.Command> für `EventCommand.Enable` aufgerufen wird. Um eine Indikatorinstanz nur dann sicher zu instanziieren, wenn sie `null` ist, verwenden Sie den [NULL-Sammeloperator](../../csharp/language-reference/operators/null-coalescing-operator.md). Darüber hinaus können benutzerdefinierte Methoden die <xref:System.Diagnostics.DiagnosticSource.IsEnabled%2A>-Methode auswerten, um zu bestimmen, ob die aktuelle Ereignisquelle aktiviert ist.

:::code language="csharp" source="snippets/EventCounters/ConditionalEventCounterSource.cs":::

> [!TIP]
> Bedingte Indikatoren sind Leistungsindikatoren, die bedingt instanziiert werden: eine Mikrooptimierung. Die Laufzeit übernimmt dieses Muster für Szenarien, in denen normalerweise keine Leistungsindikatoren verwendet werden, um den Bruchteil einer Millisekunde einzusparen.

### <a name="net-core-runtime-example-counters"></a>Beispielindikatoren für die .NET Core-Laufzeit

Es gibt viele hervorragende Beispielimplementierungen in der .NET Core-Laufzeit. Hier sehen Sie die Laufzeitimplementierung für den Leistungsindikator, der die Größe des Arbeitssatzes der Anwendung nachverfolgt.

```csharp
var workingSetCounter = new PollingCounter(
    "working-set",
    this,
    () => (double)(Environment.WorkingSet / 1_000_000))
{
    DisplayName = "Working Set",
    DisplayUnits = "MB"
};
```

<xref:System.Diagnostics.Tracing.PollingCounter> meldet die aktuelle Menge an physischem Arbeitsspeicher, der dem Prozess (Arbeitssatz) der App zugeordnet ist, da eine Metrik zu einem bestimmten Zeitpunkt erfasst wird. Der Rückruf zum Abrufen eines Werts ist der bereitgestellte Lambdaausdruck, bei dem es sich nur um einen Aufrufs der <xref:System.Environment.WorkingSet?displayProperty=fullName>-API handelt. <xref:System.Diagnostics.Tracing.DiagnosticCounter.DisplayName> und <xref:System.Diagnostics.Tracing.DiagnosticCounter.DisplayUnits> sind optionale Eigenschaften, die festgelegt werden können, um der Consumerseite des Indikators zu helfen, den Wert deutlicher anzuzeigen. Beispielsweise werden diese Eigenschaften von [dotnet-counters](dotnet-counters.md) zum Anzeigen der anzeigefreundlicheren Version der Indikatornamen verwendet.

> [!IMPORTANT]
> Die `DisplayName`-Eigenschaften sind nicht lokalisiert.

Für <xref:System.Diagnostics.Tracing.PollingCounter> und <xref:System.Diagnostics.Tracing.IncrementingPollingCounter> sind keine weiteren Aktionen erforderlich. Beide Indikatoren fragen die Werte selbst in einem vom Consumer angeforderten Intervall ab.

Im Folgenden finden Sie ein Beispiel für einen mit <xref:System.Diagnostics.Tracing.IncrementingPollingCounter> implementierten Laufzeitindikator.

```csharp
var monitorContentionCounter = new IncrementingPollingCounter(
    "monitor-lock-contention-count",
    this,
    () => Monitor.LockContentionCount
)
{
    DisplayName = "Monitor Lock Contention Count",
    DisplayRateTimeScale = TimeSpan.FromSeconds(1)
};
```

<xref:System.Diagnostics.Tracing.IncrementingPollingCounter> verwendet die <xref:System.Threading.Monitor.LockContentionCount?displayProperty=nameWithType>-API, um das Inkrement der Gesamtzahl der Sperrkonflikte zu melden. Die <xref:System.Diagnostics.Tracing.IncrementingPollingCounter.DisplayRateTimeScale>-Eigenschaft ist optional, aber wenn sie verwendet wird, kann Sie einen Hinweis darauf bereitstellen, in welchem Zeitintervall der Indikator am besten angezeigt wird. Beispielsweise wird die Anzahl der Sperrkonflikte am besten als _Anzahl pro Sekunde_angezeigt, sodass deren <xref:System.Diagnostics.Tracing.IncrementingPollingCounter.DisplayRateTimeScale> auf eine Sekunde festgelegt ist. Die Anzeigerate kann für verschiedene Typen von Ratenindikatoren angepasst werden.

> [!NOTE]
> <xref:System.Diagnostics.Tracing.IncrementingPollingCounter.DisplayRateTimeScale> wird _nicht_ von [dotnet-counters](dotnet-counters.md) verwendet, und Ereignislistener müssen den Indikator nicht verwenden.

Es gibt weitere Indikatorimplementierungen im [.NET-Runtime](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Private.CoreLib/src/System/Diagnostics/Tracing/RuntimeEventSource.cs)-Repository, die als Referenz verwendet werden können.

## <a name="concurrency"></a>Parallelität

> [!TIP]
> Die EventCounters-API garantiert keine Threadsicherheit. Wenn die an <xref:System.Diagnostics.Tracing.PollingCounter>- oder <xref:System.Diagnostics.Tracing.IncrementingPollingCounter>-Instanzen übergebenen Delegaten von mehreren Threads aufgerufen werden, liegt es in Ihrer Verantwortung, die Threadsicherheit der Delegaten zu gewährleisten.

Ziehen Sie z. B. die folgende <xref:System.Diagnostics.Tracing.EventSource> in Betracht, um Anforderungen nachzuverfolgen.

:::code language="csharp" source="snippets/EventCounters/RequestEventSource.cs":::

Die `AddRequest()`-Methode kann aus einem Anforderungshandler aufgerufen werden, und `RequestRateCounter` fragt den Wert in dem Intervall ab, das vom Consumer des Indikators angegeben wird. Allerdings kann die `AddRequest()`-Methode von mehreren Threads gleichzeitig aufgerufen werden, wobei eine Racebedingung für `_requestCount` festgelegt wird. Eine threadsichere alternative Möglichkeit, `_requestCount` zu inkrementieren, ist die Verwendung von <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.

```csharp
public void AddRequest() => Interlocked.Increment(ref _requestCount);
```

## <a name="consume-eventcounters"></a>Nutzen von EventCounters

Es gibt zwei Hauptmethoden, um EventCounters in-process oder out-of-process zu nutzen. Die Nutzung von EventCounters lässt sich in drei Ebenen von verschiedenen genutzten Technologien unterscheiden.

- Transportereignisse in einem Rohdatenstrom über ETW oder EventPipe:
  - ETW-APIs sind im Lieferumfang des Windows-Betriebssystems enthalten, und EventPipe ist als [.NET-API](https://github.com/dotnet/diagnostics/blob/master/documentation/design-docs/diagnostics-client-library.md#1-attaching-to-a-process-and-dumping-out-all-the-runtime-gc-events-in-real-time-to-the-console) oder als diagnostisches [IPC-Protokoll](https://github.com/dotnet/diagnostics/blob/master/documentation/design-docs/ipc-protocol.md) verfügbar.
- Decodieren des binären Ereignisdatenstroms in Ereignisse:
  - Die [TraceEvent-Bibliothek](https://www.nuget.org/packages/Microsoft.Diagnostics.Tracing.TraceEvent) verarbeitet sowohl das ETW- als auch das EventPipe-Streamformat.
- Befehlszeilen- und GUI-Tools:
  - Tools wie PerfView (ETW oder EventPipe), dotnet-counters (nur EventPipe) und dotnet-monitor (nur EventPipe).

### <a name="consume-out-of-proc"></a>Out-of-Process-Nutzung

Die Out-of-Process-Nutzung von EventCounters ist ein sehr gängiger Ansatz. Sie können [dotnet-counters](dotnet-counters.md) verwenden, um die Indikatoren in plattformübergreifender Weise über eine EventPipe zu nutzen. Das Tool `dotnet-counters` ist ein plattformübergreifendes globales CLI-Tool, das zum Überwachen der Indikatorwerte verwendet werden kann. Informationen dazu, wie Sie `dotnet-counters` zum Überwachen Ihrer Leistungsindikatoren verwenden, finden Sie unter [dotnet-counters](dotnet-counters.md) oder im Tutorial [Messen der Leistung mithilfe von EventCounters](event-counter-perf.md).

#### <a name="dotnet-trace"></a>dotnet-trace

Das Tool `dotnet-trace` kann verwendet werden, um die Indikatordaten über eine EventPipe zu nutzen. Im Folgenden finden Sie ein Beispiel für die Verwendung von `dotnet-trace` zum Erfassen von Indikatordaten.

```console
dotnet-trace collect --process-id <pid> Sample.EventCounter.Minimal:0:0:EventCounterIntervalSec=1
```

Weitere Informationen zum Erfassen von Indikatorwerten im Zeitverlauf finden Sie in der [dotnet-trace](dotnet-trace.md#use-dotnet-trace-to-collect-counter-values-over-time)-Dokumentation.

#### <a name="azure-application-insights"></a>Azure Application Insights

EventCounters können von Azure Monitor genutzt werden, insbesondere von Azure Application Insights. Leistungsindikatoren können hinzugefügt und entfernt werden, und Sie können benutzerdefinierte oder bekannte Leistungsindikatoren angeben. Weitere Informationen finden Sie unter [Anpassen der zu erfassenden Leistungsindikatoren](/azure/azure-monitor/app/eventcounters#customizing-counters-to-be-collected).

#### <a name="dotnet-monitor"></a>dotnet-monitor

`dotnet-monitor` ist ein experimentelles Tool, das den Zugriff auf Diagnoseinformationen in einem .NET-Prozess vereinfacht. Weitere Informationen finden Sie unter [Vorstellung von dotnet-monitor, einem experimentellen Tool](https://devblogs.microsoft.com/dotnet/introducing-dotnet-monitor).

### <a name="consume-in-proc"></a>In-Process-Nutzung

Sie können die Indikatorwerte über die <xref:System.Diagnostics.Tracing.EventListener>-API nutzen. Ein <xref:System.Diagnostics.Tracing.EventListener> ist eine In-Process-Möglichkeit, alle Ereignisse zu nutzen, die von allen Instanzen einer <xref:System.Diagnostics.Tracing.EventSource> in der Anwendung geschrieben werden. Weitere Informationen zur Verwendung der `EventListener`-API finden Sie unter <xref:System.Diagnostics.Tracing.EventListener>.

Zuerst muss die <xref:System.Diagnostics.Tracing.EventSource>, die den Indikatorwert generiert, aktiviert werden. Überschreiben Sie die <xref:System.Diagnostics.Tracing.EventListener.OnEventSourceCreated%2A?displayProperty=nameWithType>-Methode, um eine Benachrichtigung zu erhalten, wenn eine <xref:System.Diagnostics.Tracing.EventSource> erstellt wird. Wenn dies die richtige <xref:System.Diagnostics.Tracing.EventSource> für Ihre EventCounters ist, können Sie dafür <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%2A?displayProperty=nameWithType> aufrufen. Dies ist eine Beispielüberschreibung:

:::code language="csharp" source="snippets/EventCounters/SimpleEventListener.cs" range="16-27":::

#### <a name="sample-code"></a>Beispielcode

Im Folgenden sehen Sie eine Beispielklasse <xref:System.Diagnostics.Tracing.EventListener>, die alle Indikatornamen und -werte aus der <xref:System.Diagnostics.Tracing.EventSource> der .NET-Laufzeit ausgibt, um ihre internen Indikatoren (`System.Runtime`) in einem bestimmten Intervall zu veröffentlichen.

:::code language="csharp" source="snippets/EventCounters/SimpleEventListener.cs":::

Wie oben gezeigt, _müssen_ Sie sicherstellen, dass beim Aufruf von <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%2A> das `"EventCounterIntervalSec"`-Argument im Argument `filterPayload` festgelegt wird. Andernfalls können die Leistungsindikatoren keine Werte ausgeben, da sie nicht wissen, in welchem Intervall Werte ausgegeben werden sollen.

## <a name="see-also"></a>Siehe auch

- [dotnet-counters](dotnet-counters.md)
- [dotnet-trace](dotnet-trace.md)
- <xref:System.Diagnostics.Tracing.EventCounter>
- <xref:System.Diagnostics.Tracing.EventListener>
- <xref:System.Diagnostics.Tracing.EventSource>
