---
title: 'Anwendungs Leistungsverwaltung: GrpC für WCF-Entwickler'
description: Protokollierung, Metriken und Ablauf Verfolgung für ASP.net Core GrpC-Anwendungen.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6ba67fd069e7efc232f912e50c0e283facb79e9c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841684"
---
# <a name="application-performance-management"></a>Application Performance Management

In modernen Produktionsumgebungen wie Kubernetes ist es sehr wichtig, dass Sie Anwendungen überwachen können, um sicherzustellen, dass Sie optimal ausgeführt werden. Probleme wie Protokollierung und Metriken waren nie wichtiger. ASP.net Core, einschließlich GrpC, bietet erstklassige Unterstützung für das Erstellen und Verwalten von Protokollnachrichten und Metrikdaten sowie die Ablauf *Verfolgung* von Daten. In diesem Abschnitt werden diese Bereiche ausführlicher erläutert.

## <a name="logging-vs-metrics"></a>Protokollierung und Metriken

Vor der Betrachtung der Implementierungsdetails ist es erforderlich, den Unterschied zwischen Protokollierung und Metriken zu verstehen.

Bei der Protokollierung werden Textnachrichten behandelt, in denen ausführliche Informationen zu den Vorgängen im System aufgezeichnet werden. Protokollmeldungen können Ausnahme Daten wie Stapel Überwachungen oder strukturierte Daten enthalten, die den Kontext der Nachricht bereitstellen. Die Protokollierungs Ausgabe wird häufig in einen durchsuchbaren Text Speicher geschrieben.

Metriken beziehen sich auf numerische Daten, die für die Zusammenfassung und Darstellung mithilfe von Diagrammen und Diagrammen in einem Dashboard entwickelt wurden, das eine Übersicht über die allgemeine Integrität und Leistung einer Anwendung bietet. Metrikdaten können auch verwendet werden, um automatisierte Warnungen zu initiieren, wenn ein Schwellenwert überschritten wird. Die folgende Liste zeigt einige Beispiele für Metrikdaten:

- Benötigte Zeit für die Verarbeitung von Anforderungen.
- Die Anzahl der Anforderungen pro Sekunde, die von einer Instanz eines Dienstanbieter verarbeitet werden.
- Die Anzahl der fehlerhaften Anforderungen auf einer-Instanz.

## <a name="logging-in-aspnet-core-grpc"></a>Anmelden ASP.net Core GrpC

ASP.net Core bietet integrierte Unterstützung für die Protokollierung in Form des [Microsoft. Extensions. Logging](https://www.nuget.org/packages/Microsoft.Extensions.Logging) -nuget-Pakets. Die Kernteile dieser Bibliothek sind im Web-SDK enthalten, sodass es nicht erforderlich ist, es manuell zu installieren. Standardmäßig werden Protokollmeldungen in die Standardausgabe ("Console") und in einen beliebigen angefügten Debugger geschrieben. Wenn Sie Protokolle in persistente externe Datenspeicher schreiben möchten, müssen Sie möglicherweise [optionale Protokollierungs-senkenpakete](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0#third-party-logging-providers)importieren.

Das ASP.net Core GrpC-Framework schreibt ausführliche Diagnose Protokollierungs Meldungen in dieses Protokollierungs Framework, damit Sie zusammen mit den eigenen Nachrichten Ihrer Anwendung verarbeitet/gespeichert werden können.

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

Viele Protokollmeldungen zu Anforderungen, Ausnahmen usw. werden von den ASP.net Core-und GrpC-Framework-Komponenten bereitgestellt. Fügen Sie eigene Protokollnachrichten hinzu, um Details und Kontext zur Anwendungslogik bereitzustellen, anstatt Probleme auf niedrigerer Ebene zu bieten.

Weitere Informationen zum Schreiben von Protokollmeldungen und verfügbaren Protokollierungs senken und-Zielen finden Sie im Artikel [Protokollierung in .net Core und ASP.net Core](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) .

## <a name="metrics-in-aspnet-core-grpc"></a>Metriken in ASP.net Core GrpC

Die .net Core-Laufzeit stellt eine Reihe von Komponenten zum ausgeben und beobachten von Metriken bereit, die APIs enthalten, wie z. b. die Klassen <xref:System.Diagnostics.Tracing.EventSource> und <xref:System.Diagnostics.Tracing.EventCounter>. Diese APIs können verwendet werden, um grundlegende numerische Daten auszugeben, die von externen Prozessen wie dem [globalen dotnet-Counters-Tool](https://github.com/dotnet/diagnostics/blob/master/documentation/dotnet-counters-instructions.md)oder der Ereignis Ablauf Verfolgung für Windows genutzt werden können. Weitere Informationen zum Verwenden von `EventCounter` in Ihrem eigenen Code finden Sie im [Event Counter Introduction](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md) -Tutorial.

Für erweiterte Metriken und zum Schreiben von Metrikdaten in eine größere Anzahl von Daten speichern gibt es ein hervorragendes Open Source-Projekt mit dem Namen [App-Metriken](https://www.app-metrics.io). Diese Sammlung von Bibliotheken bietet einen umfangreichen Satz von Typen, um Ihren Code zu instrumentieren. Außerdem werden Pakete zum Schreiben von Metriken in verschiedene Arten von Zielen angeboten, die Zeitreihen Datenbanken wie z. b. Prometheus und Einfluss xdb, [Azure-Anwendung Einblicke](https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview)und vieles mehr enthalten. Das nuget-Paket [app. Metrics. aspnetcore. MVC](https://www.nuget.org/packages/App.Metrics.AspNetCore.Mvc/) fügt sogar einen umfassenden Satz grundlegender Metriken hinzu, die automatisch über die Integration in das ASP.net Core Framework generiert werden. die Website stellt [Vorlagen](https://www.app-metrics.io/samples/grafana/) zum Anzeigen dieser Metriken mit der [grafana](https://grafana.com/) -Visualisierungsplattform bereit.

Weitere Informationen und Dokumentation zu app-Metriken finden Sie auf der [App-Metrics.IO](https://app-metrics.io) -Website.

### <a name="produce-metrics"></a>Metriken

Die meisten metrikplattformen unterstützen fünf Grundtypen von Metriken, die in der folgenden Tabelle aufgeführt sind:

| Metriktyp | Beschreibung |
| ----------- | ----------- |
| Zähler     | Verfolgt, wie oft etwas passiert, z. b. Anforderungen, Fehler usw. |
| Mess Gerät       | Zeichnet einen einzelnen Wert auf, der sich im Laufe der Zeit ändert, beispielsweise aktive Verbindungen. |
| Histogramm   | Misst eine Verteilung von Werten über beliebige Grenzen hinweg. Ein Histogramm könnte z. b. die Größe des Datasets verfolgen und zählen, wie viele < 10 Datensätze enthalten sind, wie viele 11-100 und 101-1000, und > 1000 Datensätze. |
| Messen       | Misst die Rate, mit der ein Ereignis in verschiedenen Zeitspannen auftritt. |
| Zeitgeber       | Verfolgt die Dauer der Ereignisse und die Rate, mit der es eintritt, als Histogramm gespeichert. |

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

Die aktuelle Lösung für die Visualisierung von Metrikdaten ist " [grafana](https://grafana.com)", die mit einer Vielzahl von Speicheranbietern wie Azure Monitor, Einfluss xdb und Prometheus funktioniert. Die folgende Abbildung zeigt ein Beispiel für ein grafana-Dashboard, das Metriken aus dem linkerd-dienstmesh anzeigt, das das StockData-Beispiel enthält:

![Grafana-Dashboard](media/application-performance-management/grafana-screenshot.png)

### <a name="metrics-based-alerting"></a>Metrikbasierte Warnungen

Die numerische Natur von Metrikdaten bedeutet, dass Sie idealerweise für Warnsysteme geeignet ist, die Entwickler oder Support Techniker Benachrichtigen, wenn ein Wert außerhalb der definierten Toleranz liegt. Die bereits erwähnten Plattformen bieten Unterstützung für Warnungen über eine Reihe von Optionen, einschließlich e-Mails, Textnachrichten oder Dashboards in Dashboards.

## <a name="distributed-tracing"></a>Verteilte Ablauf Verfolgung

Die *verteilte Ablauf Verfolgung* ist eine relativ aktuelle Entwicklung in der Überwachung, die aus der zunehmenden Verwendung von microservices und verteilten Architekturen entstanden ist. Eine einzelne Anforderung von einem Client Browser, einer Anwendung oder einem Gerät kann in viele Schritte und untergeordnete Anforderungen aufgeteilt werden und umfasst die Verwendung vieler Dienste in einem Netzwerk. Dadurch wird es schwierig, Protokollmeldungen und Metriken mit der jeweiligen Anforderung zu korrelieren, durch die Sie ausgelöst wurden. Die verteilte Ablauf Verfolgung wendet Bezeichner auf Anforderungen an, die das korrelieren von Protokollen und Metriken mit einem bestimmten Vorgang ermöglichen. Dies ist vergleichbar mit [der End-to-End-Ablauf Verfolgung von WCF](https://docs.microsoft.com/dotnet/framework/wcf/diagnostics/tracing/end-to-end-tracing), wird jedoch auf mehrere Plattformen angewendet.

Obwohl es sich immer noch um einen bereits laufenden Technologiebereich handelt, wurde die verteilte Ablauf Verfolgung schnell und durch einen Standardisierungsprozess erweitert. Die Cloud Native Computing Foundation erstellte den [offenen Ablauf Verfolgungs Standard](https://opentracing.io)und versuchte, Anbieter neutrale Bibliotheken für das Arbeiten mit Back-Ends wie z. b. [Jaeger](https://www.jaegertracing.io/) und [elastisches apm](https://www.elastic.co/products/apm)bereitzustellen. Gleichzeitig hat Google das [opencensus-Projekt](https://opencensus.io/) erstellt, um die gleichen Probleme zu beheben. Diese beiden Projekte werden nun in einem neuen Projekt ( [opentelemetry](https://opentelemetry.io)) zusammengeführt, das als zukünftiger Industriestandard dienen soll.

### <a name="how-distributed-tracing-works"></a>Funktionsweise der verteilten Ablauf Verfolgung

Die verteilte Ablauf Verfolgung basiert auf dem Konzept der *Spannen*: benannte, zeitgesteuerte *Vorgänge, die Teil einer einzelnen Ablauf*Verfolgung sind, die möglicherweise die Verarbeitung auf mehreren Knoten eines Systems einschließt. Wenn ein neuer Vorgang initiiert wird, wird eine Ablauf Verfolgung mit einem eindeutigen Bezeichner erstellt. Für jeden unter Vorgang wird eine Spanne mit eigenem Bezeichner und Ablauf Verfolgungs Bezeichner erstellt. Wenn die Anforderung das System durchläuft, können verschiedene Komponenten untergeordnete *Spannen erstellen* , die den Bezeichner des über *geordneten*Elements enthalten. Eine Spanne verfügt über einen *Kontext*, der die Ablaufverfolgungs-und Span-IDs sowie nützliche Daten in Form von Schlüssel-Wert-Paaren (als *Gepäck*bezeichnet) enthält.

### <a name="distributed-tracing-with-diagnosticsource"></a>Verteilte Ablauf Verfolgung mit diagnosticsource

.Net Core verfügt über ein internes Modul, das sich gut für verteilte Ablauf Verfolgungen und spannen zuordnet: [diagnosticsource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#diagnosticsource-users-guide). Und eine einfache Möglichkeit zum erzeugen und Nutzen von Diagnosen innerhalb eines Prozesses bietet das `DiagnosticSource` Modul das Konzept einer *Aktivität*, bei der es sich um eine Implementierung einer verteilten Ablauf Verfolgung oder eine Spanne innerhalb einer Ablauf Verfolgung handelt. Die internale des Moduls kümmern sich um über-und untergeordnete Aktivitäten, einschließlich der Zuordnung von bezeichtern. Weitere Informationen zur Verwendung des `Activity` Typs finden Sie im [Benutzerhandbuch für Aktivitäten auf GitHub](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-user-guide) .

Da diagnosticsource Teil des Kern-Frameworks ist, wird es von mehreren Kernkomponenten unterstützt, einschließlich <xref:System.Net.Http.HttpClient>, Entity Framework Core und ASP.net Core, einschließlich expliziter Unterstützung im GrpC-Framework. Wenn ASP.net Core eine Anforderung empfängt, überprüft er, ob ein paar von HTTP-Headern mit dem W3C-Ablauf [Verfolgungs Kontext](https://www.w3.org/TR/trace-context) Standard übereinstimmt. Wenn die Header gefunden werden, wird eine Aktivität mithilfe der Identitäts Werte und des Kontexts aus den Headern gestartet. Wenn keine Header gefunden werden, wird eine Aktivität mit generierten Identitäts Werten gestartet, die dem Standardformat entsprechen. Alle Diagnosen, die während der Lebensdauer dieser Aktivität vom Framework oder Anwendungscode generiert werden, können mit der Ablauf Verfolgung und den spannen Bezeichner gekennzeichnet werden. Die `HttpClient`-Unterstützung erweitert dies, indem bei jeder Anforderung eine aktuelle Aktivität überprüft und der ausgehenden Anforderung automatisch die Ablauf Verfolgungs Header hinzugefügt werden.

Die ASP.net Core GrpC-Client und-Server Bibliotheken umfassen explizite Unterstützung für diagnosticsource und Activity und erstellen Aktivitäten und wenden Header Informationen automatisch an und verwenden Sie.

> [!NOTE]
> All dies geschieht nur, wenn ein *Listener* die Diagnoseinformationen nutzt. Wenn kein Listener vorhanden ist, werden keine Diagnosen geschrieben, und es werden keine Aktivitäten erstellt.

### <a name="add-your-own-diagnosticsources-and-activities"></a>Hinzufügen eigener diagnosticsources-und-Aktivitäten

Obwohl eine gute Menge von Daten automatisch durch ASP.net Core generiert wird, einschließlich GrpC sowie Entity Framework Core und `HttpClient`, können Sie Ihre eigene Diagnose hinzufügen oder explizite Spannen innerhalb Ihres Anwendungs Codes erstellen. Ausführliche Informationen zum Implementieren ihrer eigenen Diagnose finden Sie im [Benutzerhandbuch zu diagnosticsource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#instrumenting-with-diagnosticsourcediagnosticlistener) und [Aktivitäts Benutzerhandbuch](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-usage) .

### <a name="store-distributed-trace-data"></a>Speichern verteilter Ablauf Verfolgungs Daten

Zum Zeitpunkt der Erstellung des Projekts "opentelemetry" befindet sich noch in den frühen Phasen, und für .NET-Anwendungen sind nur Alpha-Qualitäts Pakete verfügbar. Das opentracing-Projekt bietet ausgereifte Bibliotheken, die jedoch in Zukunft durch die opentelemetry-Bibliotheken abgelöst werden.

Die opentracing-API wird unten beschrieben. Wenn Sie die neuere opentelemetry-API in Ihrer Anwendung verwenden möchten, finden Sie weitere Informationen im [opentelemetry .NET SDK-Repository auf GitHub](https://github.com/open-telemetry/opentelemetry-dotnet).

#### <a name="use-the-opentracing-package-to-store-distributed-trace-data"></a>Verwenden des opentracing-Pakets zum Speichern verteilter Ablauf Verfolgungs Daten

[Ein opentrace-nuget-Paket](https://www.nuget.org/packages/OpenTracing/) , das alle mit opentrace kompatiblen Back-Ends unterstützt (die unabhängig von `DiagnosticSource`verwendet werden können). Es gibt ein zusätzliches Paket aus dem opentracing-API-Beitrags Projekt, [opentracing. contrib. Netcore](https://www.nuget.org/packages/OpenTracing.Contrib.NetCore/), das einen `DiagnosticSource` Listener hinzufügt und Ereignisse und Aktivitäten automatisch in ein Back-End schreibt. Das Aktivieren dieses Pakets ist so einfach wie das Installieren von nuget und das Hinzufügen als Dienst in ihrer `Startup`-Klasse.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddOpenTracing();
    }
}
```

Das opentracing-Paket ist eine Abstraktionsschicht und erfordert daher eine Back-End-spezifische Implementierung. Opentrace-API-Implementierungen sind für die folgenden Open Source-Back-Ends verfügbar.

| -Name | Package | Website |
| ---- | ------- | -------- |
| Jaeger | [Jaeger](https://www.nuget.org/packages/Jaeger/) | [jaegertracing.io](https://jaegertracing.io) |
| Elastisches apm | [Elastisches apm. netcoreall](https://www.nuget.org/packages/Elastic.Apm.NetCoreAll/) | [elastic.co/products/apm](https://www.elastic.co/products/apm) |

Weitere Informationen zur opentrace-API für .net finden Sie unter [opentracing für C# ](https://github.com/opentracing/opentracing-csharp) und [opentracing contrib C#/.net kernrepository](https://github.com/opentracing-contrib/csharp-netcore) auf GitHub.

>[!div class="step-by-step"]
>[Zurück](load-balancing.md)
>[Weiter](appendix.md)
