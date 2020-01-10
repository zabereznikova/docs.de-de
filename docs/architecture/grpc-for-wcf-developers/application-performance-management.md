---
title: 'Anwendungs Leistungsverwaltung: GrpC für WCF-Entwickler'
description: Protokollierung, Metriken und Ablauf Verfolgung für ASP.net Core GrpC-Anwendungen.
ms.date: 09/02/2019
ms.openlocfilehash: 98da6c5391f021011e281a57e8f775709fa128ef
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740969"
---
# <a name="application-performance-management"></a>Application Performance Management

In Produktionsumgebungen wie Kubernetes ist es wichtig, Anwendungen zu überwachen, um sicherzustellen, dass Sie optimal ausgeführt werden. Protokollierung und Metriken sind besonders wichtig. ASP.net Core, einschließlich GrpC, bietet integrierte Unterstützung für das Erstellen und Verwalten von Protokollnachrichten und Metrikdaten sowie die Ablauf *Verfolgung* von Daten.

## <a name="the-difference-between-logging-and-metrics"></a>Der Unterschied zwischen Protokollierung und Metriken

Bei der *Protokollierung* werden Textnachrichten behandelt, in denen ausführliche Informationen zu den Vorgängen im System aufgezeichnet werden. Protokollmeldungen können Ausnahme Daten wie Stapel Überwachungen oder strukturierte Daten enthalten, die den Kontext der Nachricht bereitstellen. Die Protokollierungs Ausgabe wird häufig in einen durchsuchbaren Text Speicher geschrieben.

*Metriken* beziehen sich auf numerische Daten, die mithilfe von Diagrammen und Diagrammen in einem Dashboard aggregiert und präsentiert werden sollen. Das Dashboard bietet eine Übersicht über die Gesamt Integrität und Leistung einer Anwendung. Metrikdaten können auch verwendet werden, um automatisierte Warnungen zu initiieren, wenn ein Schwellenwert überschritten wird. Im folgenden finden Sie einige Beispiele für Metrikdaten:

- Benötigte Zeit für die Verarbeitung von Anforderungen.
- Die Anzahl der Anforderungen pro Sekunde, die von einer Instanz eines Dienstanbieter verarbeitet werden.
- Die Anzahl der fehlerhaften Anforderungen auf einer-Instanz.

## <a name="logging-in-aspnet-core-grpc"></a>Anmelden ASP.net Core GrpC

ASP.net Core bietet integrierte Unterstützung für die Protokollierung in Form des [Microsoft. Extensions. Logging](https://www.nuget.org/packages/Microsoft.Extensions.Logging) -nuget-Pakets. Die Kernteile dieser Bibliothek sind im Web-SDK enthalten, sodass es nicht erforderlich ist, es manuell zu installieren. Standardmäßig werden Protokollmeldungen in die Standardausgabe ("Console") und in einen beliebigen angefügten Debugger geschrieben. Wenn Sie Protokolle in persistente externe Datenspeicher schreiben möchten, müssen Sie möglicherweise [optionale Protokollierungs-senkenpakete](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0#third-party-logging-providers)importieren.

Das ASP.net Core GrpC-Framework schreibt ausführliche Diagnose Protokollierungs Meldungen in dieses Protokollierungs Framework, sodass Sie zusammen mit den eigenen Nachrichten Ihrer Anwendung verarbeitet und gespeichert werden können.

### <a name="produce-log-messages"></a>Protokollmeldungen werden erzeugt.

Die Protokollierungs Erweiterung wird automatisch im Abhängigkeits Injektionssystem von ASP.net Core registriert, sodass Sie Protokollierungen als Konstruktorparameter für GrpC-Dienst Typen angeben können.

```csharp
public class StockData : Stocks.StocksBase
{
    private readonly ILogger<StockData> _logger;

    public StockData(ILogger<StockData> logger)
    {
        _logger = logger;
    }
}
```

Viele Protokollmeldungen, wie z. b. Anforderungen und Ausnahmen, werden von den ASP.net Core-und GrpC-Framework-Komponenten bereitgestellt. Fügen Sie eigene Protokollnachrichten hinzu, um Details und Kontext zur Anwendungslogik bereitzustellen, anstatt Probleme auf niedrigerer Ebene zu bieten.

Weitere Informationen zum Schreiben von Protokollmeldungen und verfügbaren Protokollierungs senken und-Zielen finden Sie unter [Protokollierung in .net Core und ASP.net Core](/aspnet/core/fundamentals/logging/).

## <a name="metrics-in-aspnet-core-grpc"></a>Metriken in ASP.net Core GrpC

Die .net Core-Laufzeit stellt eine Reihe von Komponenten zum ausgeben und beobachten von Metriken bereit. Dies schließt APIs ein, z. b. die Klassen <xref:System.Diagnostics.Tracing.EventSource> und <xref:System.Diagnostics.Tracing.EventCounter>. Diese APIs können grundlegende numerische Daten ausgeben, die von externen Prozessen wie dem [globalen dotnet-Counters-Tool](../../core/diagnostics/dotnet-counters.md)oder der Ereignis Ablauf Verfolgung für Windows genutzt werden können. Weitere Informationen zum Verwenden von `EventCounter` in Ihrem eigenen Code finden Sie unter [Einführung in eventcounter](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).

Für erweiterte Metriken und zum Schreiben von Metrikdaten in eine größere Anzahl von Daten speichern können Sie ein Open Source-Projekt mit dem Namen " [App-Metriken](https://www.app-metrics.io)" ausprobieren. Diese Sammlung von Bibliotheken bietet einen umfangreichen Satz von Typen, um Ihren Code zu instrumentieren. Außerdem werden Pakete zum Schreiben von Metriken in verschiedene Arten von Zielen angeboten, die Zeitreihen Datenbanken, wie z. b. Prometheus und Einfluss xdb, und [Application Insights](https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview)enthalten. Das nuget-Paket [app. Metrics. aspnetcore. MVC](https://www.nuget.org/packages/App.Metrics.AspNetCore.Mvc/) fügt sogar einen umfassenden Satz grundlegender Metriken hinzu, die automatisch über die Integration in das ASP.net Core Framework generiert werden. Die Projektwebsite stellt [Vorlagen](https://www.app-metrics.io/samples/grafana/) zum Anzeigen dieser Metriken mit der [grafana](https://grafana.com/) -Visualisierungsplattform bereit.

### <a name="produce-metrics"></a>Metriken

Die meisten metrikplattformen unterstützen die folgenden Typen:

| Metriktyp | Beschreibung |
| ----------- | ----------- |
| Zähler     | Verfolgt, wie oft etwas passiert, z. b. Anforderungen und Fehler. |
| Messgerät       | Zeichnet einen einzelnen Wert auf, der sich im Laufe der Zeit ändert, beispielsweise aktive Verbindungen. |
| Histogramm   | Misst eine Verteilung von Werten über beliebige Grenzen hinweg. Ein Histogramm kann z. b. die Größe des Datasets verfolgen und zählen, wie viele < 10 Datensätze enthalten sind, wie viele enthaltene 11-100-Einträge, wie viele enthaltene 101-1000-Einträge und wie viele > 1000 Datensätze enthalten sind. |
| Messen       | Misst die Rate, mit der ein Ereignis in verschiedenen Zeitspannen auftritt. |
| Timer       | Verfolgt die Dauer der Ereignisse und die Rate, mit der es eintritt, als Histogramm gespeichert. |

Mithilfe von *App-Metriken*kann eine `IMetrics` Schnittstelle über die Abhängigkeitsinjektion abgerufen und zum Aufzeichnen dieser Metriken für einen GrpC-Dienst verwendet werden. Im folgenden Beispiel wird gezeigt, wie die Anzahl von `Get` Anforderungen gezählt wird, die im Laufe der Zeit ausgeführt wurden:

```csharp
public class StockData : Stocks.StocksBase
{
    private static readonly CounterOptions GetRequestCounter = new CounterOptions
    {
        Name = "StockData_Get_Requests",
        MeasurementUnit = Unit.Calls
    };

    private readonly IStockRepository _repository;
    private readonly IMetrics _metrics;

    public StockData(IStockRepository repository, IMetrics metrics)
    {
        _repository = repository;
        _metrics = metrics;
    }

    public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
    {
        _metrics.Measure.Counter.Increment(GetRequestCounter);

        // Serve request...
    }
}
```

### <a name="store-and-visualize-metrics-data"></a>Speichern und Visualisieren von Metrikdaten

Die beste Möglichkeit zum Speichern von Metrikdaten befindet sich in einer *Zeitreihen Datenbank*, einem speziellen Datenspeicher, der für die Aufzeichnung numerischer Datenreihen konzipiert ist, die mit Zeitstempeln markiert sind. Die beliebtesten dieser Datenbanken sind [Prometheus](https://prometheus.io/) und [Einfluss xdb](https://www.influxdata.com/products/influxdb-overview/). Microsoft Azure bietet auch dedizierten metrikspeicher über den [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) -Dienst.

Die aktuelle Lösung für die Visualisierung von Metrikdaten ist [grafana](https://grafana.com), die mit einer Vielzahl von Speicheranbietern funktioniert. Die folgende Abbildung zeigt ein Beispiel für ein grafana-Dashboard, das Metriken aus dem linkerd-dienstmesh anzeigt, das das StockData-Beispiel enthält:

![Screenshot des grafana-Dashboards](media/application-performance-management/grafana-screenshot.png)

### <a name="metrics-based-alerting"></a>Metrikbasierte Warnungen

Die numerische Natur von Metrikdaten bedeutet, dass Sie idealerweise für Warnsysteme geeignet ist, die Entwickler oder Support Techniker Benachrichtigen, wenn ein Wert außerhalb der definierten Toleranz liegt. Die bereits erwähnten Plattformen bieten Unterstützung für Warnungen über eine Reihe von Optionen, einschließlich e-Mails, Textnachrichten oder Dashboards in Dashboards.

## <a name="distributed-tracing"></a>Verteilte Ablaufverfolgung

Die verteilte Ablauf Verfolgung ist eine relativ aktuelle Entwicklung in der Überwachung, die aus der zunehmenden Verwendung von microservices und verteilten Architekturen entstanden ist. Eine einzelne Anforderung von einem Client Browser, einer Anwendung oder einem Gerät kann in viele Schritte und untergeordnete Anforderungen aufgeteilt werden und umfasst die Verwendung vieler Dienste in einem Netzwerk. Dadurch wird es schwierig, Protokollmeldungen und Metriken mit der jeweiligen Anforderung zu korrelieren, durch die Sie ausgelöst wurden. Die verteilte Ablauf Verfolgung wendet Bezeichner auf Anforderungen an und ermöglicht das korrelieren von Protokollen und Metriken mit einem bestimmten Vorgang. Dies ist vergleichbar mit [der End-to-End-Ablauf Verfolgung von WCF](../../framework/wcf/diagnostics/tracing/end-to-end-tracing.md), wird jedoch auf mehrere Plattformen angewendet.

Die verteilte Ablauf Verfolgung hat sich sehr schnell vergrößert und beginnt mit der Standardisierung. Die Cloud Native Computing Foundation erstellte den [offenen Ablauf Verfolgungs Standard](https://opentracing.io)und versuchte, herstellerneutrale Bibliotheken für das Arbeiten mit Back-Ends wie z. b. [Jaeger](https://www.jaegertracing.io/) und [elastisches apm](https://www.elastic.co/products/apm)bereitzustellen. Gleichzeitig hat Google das [opencensus-Projekt](https://opencensus.io/) erstellt, um die gleichen Probleme zu beheben. Diese beiden Projekte werden in einem neuen Projekt ( [opentelemetry](https://opentelemetry.io)) zusammengeführt, das als Branchenstandard für die Zukunft dienen soll.

### <a name="how-distributed-tracing-works"></a>Funktionsweise der verteilten Ablauf Verfolgung

Die verteilte Ablauf Verfolgung basiert auf dem Konzept der *Spannen*: benannte, zeitgesteuerte *Vorgänge, die Teil einer einzelnen Ablauf*Verfolgung sind und die Verarbeitung auf mehreren Knoten eines Systems einschließen können. Wenn ein neuer Vorgang initiiert wird, wird eine Ablauf Verfolgung mit einem eindeutigen Bezeichner erstellt. Für jeden unter Vorgang wird eine Spanne mit eigenem Bezeichner und Ablauf Verfolgungs Bezeichner erstellt. Wenn die Anforderung das System durchläuft, können verschiedene Komponenten untergeordnete *Spannen erstellen* , die den Bezeichner des über *geordneten*Elements enthalten. Eine Spanne verfügt über einen *Kontext*, der die Ablaufverfolgungs-und Span-IDs sowie nützliche Daten in Form von Schlüssel-Wert-Paaren (als *Gepäck*bezeichnet) enthält.

### <a name="distributed-tracing-with-diagnosticsource"></a>Verteilte Ablauf Verfolgung mit `DiagnosticSource`

.Net Core verfügt über ein internes Modul, das sich gut für verteilte Ablauf Verfolgungen und spannen zuordnet: [diagnosticsource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#diagnosticsource-users-guide). Das `DiagnosticSource`-Modul verfügt über das Konzept einer *Aktivität*und bietet eine einfache Möglichkeit, die Diagnose innerhalb eines Prozesses zu erzeugen und zu nutzen. Bei einer Aktivität handelt es sich tatsächlich um eine Implementierung einer verteilten Ablauf Verfolgung oder um eine Spanne innerhalb einer Ablauf Verfolgung. Die internale des Moduls kümmern sich um über-und untergeordnete Aktivitäten, einschließlich der Zuordnung von bezeichtern. Weitere Informationen zur Verwendung des `Activity` Typs finden Sie im [Benutzerhandbuch für Aktivitäten auf GitHub](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-user-guide).

Da `DiagnosticSource` Teil des Kern-Frameworks ist, wird es von mehreren Kernkomponenten unterstützt. Hierzu gehören <xref:System.Net.Http.HttpClient>, Entity Framework Core und ASP.net Core, einschließlich expliziter Unterstützung im GrpC-Framework. Wenn ASP.net Core eine Anforderung empfängt, überprüft er, ob ein paar von HTTP-Headern mit dem W3C-Ablauf [Verfolgungs Kontext](https://www.w3.org/TR/trace-context) Standard übereinstimmt. Wenn die Header gefunden werden, wird eine Aktivität mithilfe der Identitäts Werte und des Kontexts aus den Headern gestartet. Wenn keine Header gefunden werden, wird eine Aktivität mit generierten Identitäts Werten gestartet, die dem Standardformat entsprechen. Alle Diagnosen, die während der Lebensdauer dieser Aktivität vom Framework oder Anwendungscode generiert werden, können mit der Ablauf Verfolgung und den spannen Bezeichner gekennzeichnet werden. Die `HttpClient`-Unterstützung erweitert dies, indem bei jeder Anforderung eine aktuelle Aktivität überprüft und die Ablauf Verfolgungs Header der ausgehenden Anforderung automatisch hinzugefügt werden.

Die ASP.net Core GrpC-Client-und-Server Bibliotheken enthalten explizite Unterstützung für `DiagnosticSource` und `Activity`sowie für die Erstellung von Aktivitäten sowie für die automatische Anwendung und Verwendung von Header Informationen.

> [!NOTE]
> All dies geschieht nur, wenn ein Listener die Diagnoseinformationen nutzt. Wenn kein Listener vorhanden ist, werden keine Diagnosen geschrieben, und es werden keine Aktivitäten erstellt.

### <a name="add-your-own-diagnosticsource-and-activity"></a>Fügen Sie Ihre eigenen `DiagnosticSource` und `Activity`

Informationen zum Hinzufügen Ihrer eigenen Diagnose oder zum Erstellen von expliziten Spannen innerhalb des Anwendungs Codes finden Sie im Benutzerhandbuch zu [diagnosticsource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#instrumenting-with-diagnosticsourcediagnosticlistener) und [Aktivitäts Benutzerhandbuch](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-usage).

### <a name="store-distributed-trace-data"></a>Speichern verteilter Ablauf Verfolgungs Daten

Zum Zeitpunkt des Schreibens ist das opentelemetry-Projekt noch in den frühen Phasen, und für .NET-Anwendungen sind nur Alpha-Qualitäts Pakete verfügbar. Das opentracing-Projekt bietet zurzeit ausgereifte Bibliotheken.

Die opentrace-API wird im folgenden Abschnitt beschrieben. Wenn Sie stattdessen die opentelemetry-API in Ihrer Anwendung verwenden möchten, finden Sie weitere Informationen im [opentelemetry .NET SDK-Repository](https://github.com/open-telemetry/opentelemetry-dotnet) auf GitHub.

#### <a name="use-the-opentracing-package-to-store-distributed-trace-data"></a>Verwenden des opentracing-Pakets zum Speichern verteilter Ablauf Verfolgungs Daten

Das [opentrace-nuget-Paket](https://www.nuget.org/packages/OpenTracing/) unterstützt alle opentrace-kompatiblen Back-Ends (die unabhängig von `DiagnosticSource`verwendet werden können). Es gibt ein zusätzliches Paket aus dem opentrace-API-Beitrags Projekt, [opentracing. contrib. Netcore](https://www.nuget.org/packages/OpenTracing.Contrib.NetCore/). Mit diesem Paket wird ein `DiagnosticSource` Listener hinzugefügt und Ereignisse und Aktivitäten automatisch in ein Back-End geschrieben. Das Aktivieren dieses Pakets ist so einfach wie das Installieren von nuget und das Hinzufügen als Dienst in ihrer `Startup`-Klasse.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddOpenTracing();
    }
}
```

Das opentracing-Paket ist eine Abstraktionsschicht und erfordert daher eine spezifische Implementierung für das Back-End. Opentrace-API-Implementierungen sind für die folgenden Open Source-Back-Ends verfügbar.

| -Name | Package | Website |
| ---- | ------- | -------- |
| Jaeger | [Jaeger](https://www.nuget.org/packages/Jaeger/) | [jaegertracing.io](https://jaegertracing.io) |
| Elastisches apm | [Elastisches apm. netcoreall](https://www.nuget.org/packages/Elastic.Apm.NetCoreAll/) | [elastic.co/products/apm](https://www.elastic.co/products/apm) |

Weitere Informationen zur opentrace-API für .net finden Sie unter [opentracing für C# ](https://github.com/opentracing/opentracing-csharp) und [opentracing contrib C#/.net kernrepository](https://github.com/opentracing-contrib/csharp-netcore) auf GitHub.

>[!div class="step-by-step"]
>[Zurück](load-balancing.md)
>[Weiter](appendix.md)
