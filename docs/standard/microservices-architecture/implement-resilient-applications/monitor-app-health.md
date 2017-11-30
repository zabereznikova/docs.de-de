---
title: "Systemüberwachung"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Systemüberwachung"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: cbbad72f06bcaa882bc50083d9103b0872f51754
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="health-monitoring"></a>Systemüberwachung

Systemüberwachung kann in der Nähe von Echtzeit Informationen über den Status von Containern und Microservices erlauben. Systemüberwachung für zahlreiche Aspekte Microservices Betrieb von entscheidender Bedeutung ist, und ist besonders wichtig bei Orchestrators partielle Anwendungsupgrades in Phasen durchführen, wie weiter unten erläutert.

Microservices-basierte Anwendungen verwenden häufig Takte oder Integrität überprüft, um ihre Systemmonitore Planern und Orchestrators zum Nachverfolgen der Vielzahl von Diensten zu aktivieren. Wenn Dienste irgendeine "Ich verwende alive" Signal bei Bedarf oder nach einem Zeitplan senden können, kann Ihre Anwendung Risiken stoßen, wenn Bereitstellen von Updates oder Fehlern zu spät einfach zu erkennen und nicht in der Lage zu kaskadierende Fehler beenden, die größere Ausfälle annehmen können.

Im typischen Modell Dienste senden Berichte über ihren Status, und diese Informationen um einen allgemeinen Überblick über den Zustand der Anwendung bereitzustellen zusammengefasst. Bei Verwendung einer Orchestrator können Sie Integritätsinformationen für Ihre Orchestrator-Cluster bereitstellen, damit der Cluster entsprechend reagieren kann. Wenn Sie investieren Sie in qualitativ hochwertige Clientintegritätsberichte, die für Ihre Anwendung angepasst ist, können Sie erkennen und Beheben von Problemen für die ausgeführte Anwendung wesentlich einfacher.

## <a name="implementing-health-checks-in-aspnet-core-services"></a>Implementieren die Integrität überprüft in ASP.NET Core services

Wenn Sie eine ASP.NET Core Microservice oder Web-Anwendung entwickeln, können Sie eine Bibliothek mit dem Namen HealthChecks vom Team ASP.NET verwenden. (Ab Mai 2017 ist eine frühe Version auf GitHub verfügbar).

Diese Bibliothek ist einfach zu verwenden und bietet Funktionen, mit denen Sie überprüfen, ob eine bestimmte externe Ressource, die für Ihre Anwendung (z. B. eine SQL Server-Datenbank oder eine remote-API) benötigt ordnungsgemäß ausgeführt wird. Wenn Sie diese Bibliothek verwenden, können Sie auch entscheiden, was es bedeutet, dass die Ressource fehlerfrei ist, wie weiter unten erläutert.

Um diese Bibliothek verwenden, müssen Sie zuerst die Bibliothek in Ihr Microservices verwenden. Zweitens brauchen Sie eine Front-End-Anwendung, die Abfragen für die Statusberichte. Die front-End-Anwendung ist möglicherweise eine benutzerdefinierte Berichterstellungsanwendung, oder es ist möglicherweise ein Orchestrator selbst, der entsprechend reagieren kann den Integritätsstatus.

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a>Mithilfe der HealthChecks-Bibliothek in Ihrem Back-End-ASP.NET microservices

Sie können sehen, wie die HealthChecks-Bibliothek in der beispielanwendung eShopOnContainers verwendet wird. Um zu beginnen, müssen Sie definieren, was einen fehlerfreien Status für jede Microservice ausmacht. In der beispielanwendung sind die Microservices fehlerfrei, wenn die Microservice API wird über HTTP und auch die zugehörige SQL Server-Datenbank verfügbar ist.

In der Zukunft werden Sie die Bibliothek HealthChecks als NuGet-Paket installieren. Aber Verfassung dieses Dokuments herunterladen und kompilieren Sie den Code als Teil der Projektmappe werden müssen. Klonen Sie den Code unter https://github.com/aspnet/HealthChecks, und kopieren Sie die folgenden Ordnern der Projektmappe.

  - Src/allgemeinen
  - src/Microsoft.AspNetCore.HealthChecks
  - src/Microsoft.Extensions.HealthChecks
  - src/Microsoft.Extensions.HealthChecks.SqlServer

Sie können auch zusätzliche Überprüfungen wie diejenigen für Azure (Microsoft.Extensions.HealthChecks.AzureStorage), aber da diese Version des eShopOnContainers keine Abhängigkeit auf Azure verwenden, Sie ist nicht erforderlich. Sie benötigen keine der integritätsprüfungen ASP.NET, da ASP.NET Core eShopOnContainers basiert.

Abbildung 10 – 6 zeigt die HealthChecks-Bibliothek in Visual Studio bereit als ein grundlegender Baustein von jeder Microservices verwendet werden.

![](./media/image6.png)

**Abbildung 10 – 6**. ASP.NET Core HealthChecks Bibliothek Quellcode in Visual Studio-Projektmappe

Wie zuvor eingeführt wird, ist die erste Vorgehensweise in jedem Projekt Microservice einen Verweis auf die drei HealthChecks Bibliotheken hinzufügen. Danach fügen Sie die Integrität Aktionen, die Sie in diesem Microservice ausführen möchten. Diese Aktionen sind im Grunde Abhängigkeiten von anderen Microservices (HttpUrlCheck) oder Datenbanken (derzeit SqlCheck\* für SQL Server-Datenbanken). Fügen Sie die Aktion in die Startklasse. jedes Microservice ASP.NET oder ASP.NET Web-Anwendung.

Jeder Dienst oder einer Website-Anwendung sollte alle Abhängigkeiten für die HTTP- oder die Datenbank als eine AddHealthCheck Methode hinzufügen konfiguriert werden. Z. B. die MVC-Webanwendung aus eShopOnContainers hängt von vielen Diensten, daher verfügt über mehrere AddCheck-Methoden, die die integritätsprüfungen hinzugefügt.

Z. B. im folgenden Codebeispiel sehen Sie wie die Katalog-Microservice eine Abhängigkeit auf der SQL Server-Datenbank hinzugefügt.

```csharp
// Startup.cs from Catalog.api microservice
//
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Add framework services
        services.AddHealthChecks(checks =>
        {
            checks.AddSqlCheck("CatalogDb", Configuration["ConnectionString"]);
        });
        // Other services
    }
}
```

Die MVC-Webanwendung der eShopOnContainers hat jedoch mehrere Abhängigkeiten auf den übrigen der Microservices an. Aus diesem Grund wird eine AddUrlCheck-Methode für jede Microservice wie im folgenden Beispiel gezeigt:

```csharp
// Startup.cs from the MVC web app
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
        services.Configure<AppSettings>(Configuration);
        services.AddHealthChecks(checks =>
        {
            checks.AddUrlCheck(Configuration["CatalogUrl"]);
            checks.AddUrlCheck(Configuration["OrderingUrl"]);
            checks.AddUrlCheck(Configuration["BasketUrl"]);
            checks.AddUrlCheck(Configuration["IdentityUrl"]);
        });
    }
}
```

Daher gebe ein Microservice keinen Status "fehlerfreien", bis alle seine Überprüfungen ebenfalls fehlerfrei sind.

Wenn die Microservice keine Abhängigkeit auf einen Dienst oder SQL Server verfügt, sollten Sie nur eine Prüfung Healthy("Ok") hinzufügen. Der folgende Code stammt aus dem eShopOnContainers basket.api Microservice. (Die Warenkorb-Microservice verwendet den Redis-Cache, aber die Bibliothek enthält noch keinen Redis Health Check-Anbieter).

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

Für einen Dienst oder einer Website Anwendung den Health Check-Endpunkt verfügbar machen, muss er die UseHealthChecks aktivieren (\[*Url\_für\_Integrität\_überprüft*\]) Erweiterung Methode. Diese Methode wird an die WebHostBuilder Ebene in der main-Methode der Program-Klasse der ASP.NET Core Dienst oder einer Website Anwendung direkt nach UseKestrel wie im folgenden Code gezeigt.

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseIISIntegration()
                .UseStartup<Startup>()
                .Build();
            host.Run();
        }
    }
}
```

Der Prozess funktioniert wie folgt: jede Microservice macht den Endpunkt HC. Dieser Endpunkt wird von der Bibliothek HealthChecks ASP.NET Core-Middleware erstellt. Wenn es sich bei diesen Endpunkt aufgerufen wird, führt er alle integritätsprüfungen, die in der AddHealthChecks-Methode in die Startklasse konfiguriert sind.

Die UseHealthChecks Methode erwartet einen Port oder einen Pfad an. Dieser Port oder der Pfad ist der Endpunkt verwendet, um den Integritätsstatus des Diensts zu überprüfen. Der Katalog Microservice verwendet z. B. die HC Pfad.

### <a name="caching-health-check-responses"></a>Health Check-Antworten Zwischenspeichern

Seit nicht dazu führen, dass ein Denial-of-Service (DoS) in Ihre Dienste möchten, oder Sie einfach keine Service Leistungseinbußen sollten durch Überprüfen von Ressourcen zu häufig können Sie cache zurückgegeben und Konfigurieren einer Cachedauer für jede integritätsprüfung durchgeführt werden.

Wird standardmäßig können die Cachedauer intern auf 5 Minuten festgelegt ist, Sie jedoch ändern, Cachedauer auf jede integritätsprüfung durchgeführt werden, wie im folgenden Code:

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a>Abfragen von Ihrer Microservices Bericht zu ihrem Integritätsstatus

Wenn Sie eine integritätsprüfung konfiguriert haben, wie hier beschrieben wird, sobald die Microservice in Docker ausgeführt wird, können Sie direkt über einen Browser überprüfen, ob es fehlerfrei ist. (Dies erfordert, dass Sie den Container Port außerhalb des Docker-Host veröffentlichen, damit Sie über "localhost" oder über die externe IP Docker-Host-Container zugreifen können.) Abbildung 10 – 7 zeigt eine Anforderung in einem Browser und die entsprechende Antwort.

![](./media/image7.png)

**Abbildung 10 – 7**. Überprüfen des Integritätsstatus von einem einzigen Dienst in einem browser

In diesen Test sehen Sie, dass die catalog.api Microservice (Port 5101 ausgeführt) fehlerfrei ist HTTP-Statuscode 200 und Statusinformationen im JSON-Format zurückgeben. Dies bedeutet auch, dass intern der Dienst auch die Integrität ihrer SQL Server-Datenbank-Abhängigkeit aktiviert und integritätsprüfung selbst als fehlerfrei gemeldet wurde.

## <a name="using-watchdogs"></a>Verwenden von watchdogs

Watchdog ist einem separaten Dienst, der Überwachen der Integrität und Dienste, und melden der Integrität zu den Microservices durch Erstellen von Abfragen mit der bereits vorgestellten HealthChecks-Bibliothek laden kann. Dies hilft zu verhindern, dass Fehler, die nicht erkannt würden, basierend auf den Überblick über einen einzelnen Dienst. Watchdogs sind auch eine gute zum Hosten von Code, die Aktionen zur Problembehebung für bekannte Bedingungen ohne Benutzerinteraktion ausführen können.

Das eShopOnContainers-Beispiel enthält eine Webseite, die Integritätsberichte Kontrollkästchen Beispiel zeigt, wie in Abbildung 10 – 8 dargestellt. Dies ist der einfachste Watchdog, die Sie möglicherweise, da sie lediglich zeigt der Status des Microservices und Web-Anwendungen in eShopOnContainers werden. In der Regel führt Watchdog auch Aktionen aus, wenn sich in einem fehlerhaften Status erkannt wird.

![](./media/image8.png)

**Abbildung 10 – 8**. Beispielbericht Health Check in eShopOnContainers

Zusammengefasst bietet die Middleware ASP.NET der ASP.NET Core HealthChecks Bibliothek einen einzelnen Health Check-Endpunkt für jede Microservice. Alle darin definierten integritätsprüfungen auszuführen werden und gesamtintegritätsstatus je nach der alle diese Überprüfungen zurückgeben.

Die Bibliothek HealthChecks ist erweiterbar, durch neue Systemdiagnosen zukünftige externer Ressourcen. Beispielsweise erwarten wir, dass in Zukunft die Bibliothek integritätsprüfungen für Redis-Cache und für andere Datenbanken vorhanden sind. Die Bibliothek ermöglicht integritätsberichterstellung durch mehrere Dienst oder diese Anwendung Abhängigkeiten, und Sie können anschließend Aktionen basierend auf diesen Systemdiagnosen.

## <a name="health-checks-when-using-orchestrators"></a>Integritätsprüfungen Verwendung orchestrators

Informationen zum Überwachen der Verfügbarkeit Ihrer Microservices integritätsprüfungen Orchestrators wie Docker Containerhostclustern, Kubernetes und-Dienststrukturen in regelmäßigen Abständen durch Senden von Anforderungen an die Microservices zu testen. Wenn ein Orchestrator feststellt, dass ein Dienstcontainer fehlerhaft ist, Weiterleiten von Anforderungen an diese Instanz wird beendet. Es erstellt auch in der Regel eine neue Instanz der betreffenden Container.

Für die Instanz, können die meisten Orchestrators Systemdiagnosen Sie Ausfallzeiten Deployments verwalten. Nur, wenn der Status einer Dienstcontainer/ändert fehlerfrei wird die Orchestrator routing des Datenverkehrs Dienstcontainer/Instanzen starten.

Systemüberwachung ist besonders wichtig, wenn ein Orchestrator ein Anwendungsupgrade ausführt. Einige Orchestrators (z. B. Azure Service Fabric) aktualisieren von Diensten in Phasen – sie können z. B. ein Fünftel der Cluster-Oberfläche für jedes Anwendungsupgrade aktualisieren. Die Gruppe der Knoten, die zur gleichen Zeit aktualisiert wird als bezeichnet ein *upgradedomäne*. Nachdem jede upgradedomäne aktualisiert wurde und für Benutzer verfügbar ist, muss dieser upgradedomäne integritätsprüfungen übergeben, bevor die Bereitstellung mit der nächsten upgradedomäne fortfährt.

Ein weiterer Aspekt der Integrität des Diensts meldet Metriken aus dem Dienst. Dies ist eine erweiterte Funktion von das Integritätsmodell des einige Orchestrators, wie Service Fabric. Metriken sind wichtig, wenn ein Orchestrator verwendet werden, da sie verwendet werden, um den Ressourcenverbrauch auszugleichen. Metriken können auch ein Indikator der Systemintegrität sein. Angenommen, Sie möglicherweise eine Anwendung mit vielen Microservices, und jeder Instanz gibt eine Metrik der Anforderungen pro Sekunde (RPS). Wenn ein Dienst mehr Ressourcen (Arbeitsspeicher, Prozessor, usw.) als ein anderer Dienst verwendet wird, konnte der Orchestrator-Dienstinstanzen im Cluster zu dem Versuch, sogar Ressourcenverwendung verwalten bewegen.

Beachten Sie, dass bei Verwendung von Azure Service Fabric eigene darüber [Systemüberwachung Modell](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), also komplexer als einfache Systemdiagnosen.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>Erweiterte Überwachung: Visualisierung, Analyse und Warnungen

Der letzte Teil des Überwachung ist Visualisieren von den Datenstrom, auf die Leistung des Service reporting und warnen, wenn ein Problem festgestellt wird. Sie können verschiedene Lösungen für dieses Aspekts der Überwachung verwenden.

Können Sie einfache benutzerdefinierte Anwendungen, die mit dem Status der Dienste, wie benutzerdefinierte Seite wurde wir gezeigt, wenn wir erläutert [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks). Oder Sie mithilfe von Tools mit erweiterter Funktionalität wie Azure Application Insights und Operations Management Suite Warnungen basierend auf den Datenstrom von Ereignissen ausgelöst werden sollen.

Abschließend, wenn Sie die ereignisdatenströme gespeichert wurden, können Sie Microsoft Power BI oder eine Lösung eines Drittanbieters, wie Kibana oder Splunk verwenden zum Visualisieren der Daten.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **ASP.NET Core HealthChecks** (frühen Release) [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)

-   **Einführung in Service Fabric-Integritätsüberwachung**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)

-   **Azure Application Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

-   **Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
[Vorherigen] (implementieren-Circuit-Breaker-pattern.md) [weiter] (.. /Secure-NET-microservices-Web-Applications/Index.MD)
