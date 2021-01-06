---
title: Messen der Leistung mithilfe von EventCounters in .NET Core
description: In diesem Tutorial erfahren Sie, wie Sie die Leistung mithilfe von EventCounters messen.
ms.date: 08/07/2020
ms.topic: tutorial
ms.openlocfilehash: 2ed7f234b685dab91ab275105d26b474e3bd1a87
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700742"
---
# <a name="tutorial-measure-performance-using-eventcounters-in-net-core"></a>Tutorial: Messen der Leistung mithilfe von EventCounters in .NET Core

**Dieser Artikel gilt für: ✔️** .NET Core 3.0 SDK und neuere Versionen

In diesem Tutorial erfahren Sie, wie Sie mit <xref:System.Diagnostics.Tracing.EventCounter> die Leistung mit einer hohen Ereignishäufigkeit messen können. Sie können die [verfügbaren Leistungsindikatoren](available-counters.md) verwenden, die von verschiedenen offiziellen .NET Core-Paketen oder von Drittanbietern veröffentlicht werden, oder eigene Metriken für die Überwachung erstellen.

In diesem Lernprogramm lernen Sie Folgendes:

> [!div class="checklist"]
>
> - Implementieren einer <xref:System.Diagnostics.Tracing.EventSource>.
> - Überwachen von Leistungsindikatoren mit [dotnet-counters](dotnet-counters.md).

## <a name="prerequisites"></a>Voraussetzungen

Im Tutorial wird Folgendes verwendet:

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder höher
- [dotnet-counters](dotnet-counters.md) zum Überwachen von Ereignisleistungsindikatoren.
- Eine [Beispieldebugziel](/samples/dotnet/samples/diagnostic-scenarios)-App für die Diagnose.

## <a name="get-the-source"></a>Herunterladen des Quellcodes

Die Beispielanwendung wird als Grundlage für die Überwachung verwendet. Das [ASP.NET Core-Beispielrepository](/samples/dotnet/samples/diagnostic-scenarios) ist im Beispielbrowser verfügbar. Sie laden die ZIP-Datei herunter, extrahieren Sie nach dem Download und öffnen sie in Ihrer bevorzugten IDE. Erstellen Sie die Anwendung, und führen Sie sie aus, um sicherzustellen, dass sie ordnungsgemäß funktioniert.

## <a name="implement-an-eventsource"></a>Implementieren einer EventSource

Bei Ereignissen, die im Abstand von wenigen Millisekunden auftreten, sollte der Mehraufwand pro Ereignis gering sein (weniger als eine Millisekunde). Andernfalls sind die Auswirkungen auf die Leistung erheblich. Das Protokollieren eines Ereignisses bedeutet, dass Sie Daten auf einen Datenträger schreiben. Wenn der Datenträger nicht schnell genug ist, gehen die Ereignisse verloren. Sie benötigen eine andere Lösung als eine Protokollierung des Ereignisses selbst.

Bei einer großen Anzahl von Ereignissen ist es auch nicht sinnvoll, ein Measure pro Ereignis zu kennen. In den meisten Fällen benötigen Sie nur einige statistische Daten. Sie könnten also die Statistiken innerhalb des Prozesses selbst abrufen und dann ab und zu ein Ereignis schreiben, um die Statistiken zu melden. Auf diese Weise geht <xref:System.Diagnostics.Tracing.EventCounter> vor.

Im Folgenden finden Sie ein Beispiel für die Implementierung einer <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>. Erstellen Sie eine neue Datei mit dem Namen *MinimalEventCounterSource.cs*, und verwenden Sie den Codeausschnitt als Quelle:

:::code language="csharp" source="snippets/EventCounters/MinimalEventCounterSource.cs":::

Die Zeile <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=nameWithType> ist der <xref:System.Diagnostics.Tracing.EventSource>-Teil und nicht Teil von <xref:System.Diagnostics.Tracing.EventCounter>. Sie wurde geschrieben, um zu zeigen, dass Sie eine Meldung zusammen mit dem Ereignisindikator protokollieren können.

## <a name="add-an-action-filter"></a>Hinzufügen eines Aktionsfilters

Der Beispielquellcode ist ein ASP.NET Core-Projekt. Sie können einen [Aktionsfilter](/aspnet/core/mvc/controllers/filters#action-filters) global hinzufügen, der die gesamte Anforderungszeit protokolliert. Erstellen Sie eine neue Datei mit dem Namen *LogRequestTimeFilterAttribute.cs*, und verwenden Sie den folgenden Code:

```csharp
using System.Diagnostics;
using Microsoft.AspNetCore.Http.Extensions;
using Microsoft.AspNetCore.Mvc.Filters;

namespace DiagnosticScenarios
{
    public class LogRequestTimeFilterAttribute : ActionFilterAttribute
    {
        readonly Stopwatch _stopwatch = new Stopwatch();

        public override void OnActionExecuting(ActionExecutingContext context) => _stopwatch.Start();

        public override void OnActionExecuted(ActionExecutedContext context)
        {
            _stopwatch.Stop();

            MinimalEventCounterSource.Log.Request(
                context.HttpContext.Request.GetDisplayUrl(), _stopwatch.ElapsedMilliseconds);
        }
    }
}
```

Der Aktionsfilter startet ein <xref:System.Diagnostics.Stopwatch>-Element, wenn die Anforderung beginnt, und beendet es, wenn die Anforderung abgeschlossen ist, wobei die verstrichene Zeit erfasst wird. Die Gesamtzahl der Millisekunden wird in der `MinimalEventCounterSource`-Singleton-Instanz protokolliert. Damit dieser Filter angewendet werden kann, müssen Sie ihn der Filtersammlung hinzufügen. Aktualisieren Sie in der Datei *Startup.cs* die `ConfigureServices`-Methode so, dass dieser Filter einbezogen wird.

```csharp
public void ConfigureServices(IServiceCollection services) =>
    services.AddControllers(options => options.Filters.Add<LogRequestTimeFilterAttribute>())
            .AddNewtonsoftJson();
```

## <a name="monitor-event-counter"></a>Überwachen des Ereignisleistungsindikators

Erstellen und starten Sie die Anwendung mit der Implementierung für eine <xref:System.Diagnostics.Tracing.EventSource> und dem benutzerdefinierte Aktionsfilter.
Sie haben die Metrik in <xref:System.Diagnostics.Tracing.EventCounter> protokolliert, aber wenn Sie nicht auf die dort enthaltenen Statistiken zugreifen, ist sie nicht hilfreich. Um die Statistiken abzurufen, müssen Sie <xref:System.Diagnostics.Tracing.EventCounter> aktivieren, indem Sie einen Timer erstellen, der so häufig für die Ereignisse ausgelöst wird, wie Sie möchten, sowie einen Listener, der die Ereignisse erfasst. Hierzu können Sie [dotnet-counters](dotnet-counters.md) verwenden.

Verwenden Sie den Befehl [dotnet-counters ps](dotnet-counters.md#dotnet-counters-ps), um eine Liste der .NET-Prozesse anzuzeigen, die überwacht werden können.

```console
dotnet-counters ps
```

Mit dem Prozessbezeichner aus der Ausgabe des Befehls `dotnet-counters ps` können Sie die Überwachung des Ereignisleistungsindikators mit dem folgenden `dotnet-counters monitor`-Befehl starten:

```console
dotnet-counters monitor --process-id 2196 --counters Sample.EventCounter.Minimal,Microsoft.AspNetCore.Hosting[total-requests,requests-per-second],System.Runtime[cpu-usage]
```

Während der `dotnet-counters monitor`-Befehl ausgeführt wird, halten Sie <kbd>F5</kbd> im Browser gedrückt, um mit der Ausgabe fortlaufender Anforderungen an den `https://localhost:5001/api/values`-Endpunkt zu beginnen. Beenden Sie den Vorgang nach einigen Sekunden durch Drücken von <kbd>q</kbd>.

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[Microsoft.AspNetCore.Hosting]
    Request Rate / 1 sec                               9
    Total Requests                                   134
[System.Runtime]
    CPU Usage (%)                                     13
[Sample.EventCounter.Minimal]
    Request Processing Time (ms)                      34.5
```

Der `dotnet-counters monitor`-Befehl eignet sich hervorragend für aktive Überwachung. Möglicherweise möchten Sie diese Diagnosemetriken jedoch für die Nachverarbeitung und Analyse erfassen. Verwenden Sie dazu den Befehl `dotnet-counters collect`. Der `collect`-Schalterbefehl ähnelt dem `monitor`-Befehl, akzeptiert jedoch einige zusätzliche Parameter. Sie können den gewünschten Namen und das Format der Ausgabedatei angeben. Verwenden Sie für eine JSON-Datei namens *diagnostics.json* den folgenden Befehl:

```console
dotnet-counters collect --process-id 2196 --format json -o diagnostics.json --counters Sample.EventCounter.Minimal,Microsoft.AspNetCore.Hosting[total-requests,requests-per-second],System.Runtime[cpu-usage]
```

Während der Befehl ausgeführt wird, halten Sie erneut <kbd>F5</kbd> im Browser gedrückt, um mit der Ausgabe fortlaufender Anforderungen an den `https://localhost:5001/api/values`-Endpunkt zu beginnen. Beenden Sie den Vorgang nach einigen Sekunden durch Drücken von <kbd>q</kbd>. Die Datei *diagnostics.json* wird geschrieben. Die JSON-Datei, die geschrieben wird, verwendet keine Einzüge. Zur besseren Lesbarkeit werden die Informationen hier jedoch mit Einzug dargestellt.

```json
{
  "TargetProcess": "DiagnosticScenarios",
  "StartTime": "8/5/2020 3:02:45 PM",
  "Events": [
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    }
  ]
}
```

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [EventCounters](event-counters.md)
