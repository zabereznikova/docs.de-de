---
title: "Systemüberwachung"
description: ".NET-Microservicesarchitektur für .NET-Containeranwendungen | Systemüberwachung"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 76821e27613335609527b867a6b94dac551f6235
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2018
---
# <a name="health-monitoring"></a>Systemüberwachung

Über die Systemüberwachung können Sie nahezu in Echtzeit Informationen zum Zustand Ihrer Container und Microservices erhalten. Die Systemüberwachung ist für verschieden Aspekte von Betriebsmicroservices wichtig und ist von besonderer Bedeutung, wenn Orchestratoren wie im Folgenden beschrieben ein Anwendungsupgrade in Phasen ausführen.

Auf einem Microservice basierende Anwendungen verwenden häufig Takte oder Integritätsüberprüfungen, damit ihre Systemmonitore, Zeitpläne und Orchestratoren die verschiedenen Dienste überwachen können. Wenn Dienste auf Verlangen oder nach Zeitplan kein Signal senden können, um deutlich zu machen, dass sie noch funktionieren, können für Ihre Anwendung Risiken entstehen, wenn Sie Updates bereitstellen. Zudem kann es auch vorkommen, dass Fehler zu spät erkannt werden, wodurch kaskadierende Fehler nicht vermieden werden können, die zu größeren Ausfällen führen können.

Dienste in ihrer allgemeinen Form senden Zustandsberichte. Diese Informationen werden dann aggregiert, sodass eine allgemeine Übersicht zum Integritätsstatus Ihrer Anwendung erstellt werden kann. Wenn Sie einen Orchestrator verwenden, können Sie Integritätsinformationen zum Cluster Ihrer Orchestratoren hinzufügen, damit der Cluster entsprechend agieren kann. Wenn Sie in Integritätsberichte von hoher Qualität investieren, die an Ihre Anwendung angepasst werden, können Sie Fehler der ausgeführte Anwendung viel einfacher ermitteln und beheben.

## <a name="implementing-health-checks-in-aspnet-core-services"></a>Implementieren von Integritätsüberprüfungen in ASP.NET Core-Diensten

Wenn Sie einen ASP.NET Core-Microservice oder eine -Webanwendung entwickeln, können Sie eine Bibliothek mit dem Namen `HealthChecks` des ASP-NET-Teams verwenden. Eine frühe Veröffentlichung wird über diese [GitHub-Repository](https://github.com/dotnet-architecture/HealthChecks) bereitgestellt.

Die Verwendung dieser Bibliothek ist einfach. Außerdem stellt sie Features bereit, mit denen Sie überprüfen können, ob eine beliebige externe Ressource einwandfrei funktioniert, die für Ihre Anwendung benötigt wird (z.B. eine SQL Server-Datenbank oder eine Remote-API). Wenn Sie diese Bibliothek verwenden, bedeutet das, dass die Ressource einwandfrei funktioniert. Dies wird nachfolgend näher erläutert.

Damit Sie diese Bibliothek verwenden können, müssen Sie sie zunächst in Ihren Microservices verwenden. Außerdem ist eine Front-End-Anwendung erforderlich, die Integritätsberichte abfragt. Bei dieser Front-End-Anwendung kann es sich z.B. um eine benutzerdefinierte Anwendung zur Berichterstattung oder einen Orchestrator an sich handeln, der im Hinblick auf den Integritätszustand angemessen reagieren kann.

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a>Verwenden der HealthChecks-Bibliothek in Ihren Back-End-ASP.NET-Microservices

In der Beispielanwendung eShopOnContainers können Sie sehen, wie die HealthChecks-Bibliothek verwendet wird. Damit Sie beginnen können, müssen Sie definieren, was die Integritätsstatus für die einzelnen Microservices ausmacht. In der Beispielanwendung funktionieren die Microservices einwandfrei, wenn über HTTP auf die Microservice-API zugegriffen werden kann und wenn die jeweilige SQL Server-Datenbank verfügbar ist.

Zukünftig soll die HealthChecks-Bibliothek als NuGet-Paket installiert werden können. Derzeit müssen Sie den Code aber noch als Teil Ihrer Projektmappe herunterladen oder kompilieren. Klonen Sie den Code unter https://github.com/dotnet-architecture/HealthChecks , und kopieren Sie die folgenden Ordnern der Projektmappe:

  - src/common
  - src/Microsoft.AspNetCore.HealthChecks
  - src/Microsoft.Extensions.HealthChecks
  - src/Microsoft.Extensions.HealthChecks.SqlServer

Außerdem können Sie auch zusätzliche Überprüfungen wie die für Azure verwenden (Microsoft.Extensions.HealthChecks.AzureStorage), aber da diese eShopOnContainers-Version nicht von Azure abhängig ist, ist dies nicht erforderlich. Die Überprüfungen der Integrität von ASP.NET sind nicht erforderlich, da eShopOnContainers auf ASP.NET Core basiert.

In Abbildung 10-6 wird die HealthChecks-Bibliothek in Visual Studio dargestellt, die von sämtlichen Microservices als Baustein verwendet werden kann.

![](./media/image6.png)

**Abbildung 10-6.** Quellcode der HealthChecks-Bibliothek von ASP.NET Core in einer Visual Studio-Projektmappe

Wie zuvor bereits erwähnt, müssen Sie als ersten Schritt für jedes Microserviceprojekt einen Verweis auf die drei HealthChecks-Bibliotheken hinzufügen. Fügen Sie anschließend die Aktionen zur Überprüfung der Integrität hinzu, die Sie in diesem Microservice ausführen möchten. Bei diesen Aktionen handelt es sich im Grunde genommen um Abhängigkeiten von anderen Microservices (HttpUrlCheck) oder Datenbanken (derzeit SqlCheck\* für SQL Server-Datenbanken). Fügen Sie die Aktion innerhalb der Startklasse jedes ASP.NET-Microservice oder jeder ASP.NET-Webanwendung hinzu.

Sie sollten jeden Dienst bzw. jede Webanwendung konfigurieren, indem Sie alle HTTP- oder Datenbankabhängigkeiten als genau eine AddHealthCheck-Methode hinzufügen. Beispielsweise ist die MVC-Webanwendung von eShopOnContainers von vielen Diensten abhängig und verfügt daher über verschiedene AddCheck-Methoden, die zu den Integritätsüberprüfungen hinzugefügt werden.

Beispielsweise können Sie im folgenden Code sehen, wie der Katalogmicroservice eine Abhängigkeit von dessen SQL Server-Datenbank hinzufügt.

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

Jedoch verfügt die MVC-Webanwendung von eShopOnContainers über mehrere Abhängigkeiten von den restlichen Microservices. Daher ruft diese wie im folgenden Beispiel dargestellt genau eine AddUrlCheck-Methode für jeden Microservice auf:

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

Somit gibt ein Microservice erst den Status „healthy“ (OK) zurück, wenn alle Überprüfungen einwandfrei durchgeführt werden konnten.

Wenn der Microservice nicht über eine Abhängigkeit von einem Dienst oder einem SQL Server verfügt, sollten Sie die Überprüfung „Healthy("Ok")“ hinzufügen. Der folgende Code wurde dem eShopOnContainers-Microservice „basket.api“ entnommen. (Der Warenkorbmicroservice verwendet zwar den Redis-Cache, jedoch enthält die Bibliothek noch keinen Redis-Anbieter für Integritätsüberprüfungen.)

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

Damit ein Dienst oder eine Webanwendung die Endpunkte zur Integritätsüberprüfung zur Verfügung stellen kann, muss die UseHealthChecks-Erweiterungsmethode (\[*URL\_für\_Integritätsüberprüfungen*\]) aktiviert sein. Diese Methode wird auf der WebHostBuilder-Ebene in der Hauptmethode der Programmklasse Ihres ASP.NET Core-Diensts oder Ihrer Anwendung unmittelbar nach UseKestrel ausgeführt (wie im folgenden Code dargestellt).

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

Der Prozess funktioniert wie folgt: Jeder Microservice stellt den Endpunkt „/hc“ zur Verfügung. Dieser Endpunkt wird von der ASP.NET Core-Middleware „HealthChecks-Bibliothek“ erstellt. Wenn dieser Endpunkt aufgerufen wird, werden alle Integritätsüberprüfungen ausgeführt, die in der Startklasse in der AddHealthChecks-Methode konfiguriert sind.

Die Methode „UseHealthChecks“ geht davon aus, dass es einen Port oder einen Pfad gibt. Dieser Port bzw. Pfad wird als Endpunkt verwendet, um den Integritätsstatus dieses Diensts zu überprüfen. Beispielsweise verwendet der Katalogmicroservice den Pfad „/hc“.

### <a name="caching-health-check-responses"></a>Zwischenspeichern der Antworten der Integritätsüberprüfung

Damit in Ihrem Dienst kein Denial of Service (DoS) festgestellt wird, oder wenn die Leistung des Diensts nicht beeinträchtigt werden soll, indem die Ressourcen zu häufig überprüft werden, können Sie die Rückgaben zwischenspeichern und eine Cachedauer für jede Integritätsüberprüfung konfigurieren.

Standardmäßig ist die Cachedauer intern auf 5 Minuten festgelegt. Sie können diese Cachedauer allerdings wie im folgenden Code bei jeder Integritätsüberprüfung ändern:

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a>Abfragen eines Berichts zum Integritätsstatus der Microservices

Wenn Sie wie hier beschrieben Integritätsüberprüfungen konfiguriert haben, können Sie direkt über den Browser überprüfen, ob der Microservice einwandfrei funktioniert, sobald dieser in Docker ausgeführt wird. (Dafür müssen Sie den Containerport außerhalb des Docker-Hosts veröffentlichen, damit Sie über einen Localhost oder das externe Docker-Host-IP auf den Container zugreifen können.) In Abbildung 10-7 wird eine Abfrage in einem Browser mit der zugehörigen Antwort dargestellt.

![](./media/image7.png)

**Abbildung 10-7.** Überprüfen des Integritätsstaus eines einzelnen Diensts über einen Browser

In diesem Test können Sie sehen, dass der Microservice „catalog.api“ (der auf Port 5101 ausgeführt wird) einwandfrei funktioniert, da er den HTTP-Status 200 und Statusinformationen im JSON-Format zurückgibt. Das bedeutet außerdem, dass der Dienst intern ebenfalls die Integrität seiner SQL Server-Datenbankabhängigkeit überprüft hat und für die Integritätsüberprüfung „OK“ zurückgegeben wurde.

## <a name="using-watchdogs"></a>Verwenden von Überwachungselementen

Bei einem Überwachungselement handelt es sich um einen separaten Dienst, der die Integrität überprüfen und in mehreren Diensten geladen werden kann. Außerdem kann es Berichte zur Integrität der Microservices erstellen, indem es eine Abfrage an die bereit eingeführte HealthChecks-Bibliothek sendet. Dadurch können Fehler vermieden werden, die anhand der Ansicht eines einzelnen Diensts nicht ermittelt werden könnten. Überwachungselemente eignen sich außerdem zum Hosten von Code, über den ohne Benutzerinteraktion Abhilfemaßnahmen für bekannte Bedingungen ausgeführt werden können.

Das eShopOnContainers-Beispiel enthält eine Webseite, auf der wie in Abbildung 10-8 dargestellt Beispielberichte zur Integritätsüberprüfung angezeigt werden. Dabei handelt es sich um das einfachste Überwachungselement, da es nur den Zustand der Microservices und Webanwendungen in eShopOnContainers anzeigt. In der Regel führt ein Überwachungselement Aktionen aus, wenn der Status „Fehlerhaft“ ermittelt wird.

![](./media/image8.png)

**Abbildung 10-8.** Beispielbericht zur Integritätsüberprüfung in eShopOnContainers

Die ASP.NET-Middleware der HealthChecks-Bibliothek von ASP.NET Core stellt also für jeden Microservice genau einen Endpunkt zur Integritätsüberprüfung bereit. Dadurch werden alle darin definierten Integritätsüberprüfungen ausgeführt und ein allgemeiner Integritätsstatus zurückgegeben, der von diesen Überprüfungen abhängig ist.

Die HealthChecks-Bibliothek ist über neue Integritätsüberprüfungen im Zusammenhang mit externen Ressourcen erweiterbar. Beispielsweise wird erwartet, dass in Zukunft die Bibliothek Integritätsüberprüfungen für den Redis-Cache und andere Datenbanken verfügbar ist. Über die Bibliothek können mithilfe von Dienst- oder Anwendungsabhängigkeiten Berichte zur Integrität erstellt werden. Anhand dieser Integritätsüberprüfungen können Sie Aktionen durchführen.

## <a name="health-checks-when-using-orchestrators"></a>Integritätsüberprüfungen, wenn Orchestratoren verwendet werden

Orchestratoren wie Docker Swarm, Kubernetes und Service Fabric führen regelmäßig zur Überwachung der Verfügbarkeit Ihrer Microservices Integritätsüberprüfungen durch, indem sie Anforderungen senden, um diese Microservices zu testen. Wenn ein Orchestrator ermittelt, dass ein Dienst bzw. ein Container fehlerhaft ist, leitet er keine Anforderungen mehr an diese Instanz weiter. Außerdem erstellt er dann in der Regel eine neue Instanz dieses Containers.

Beispielsweise können die meisten Orchestratoren Integritätsüberprüfungen verwenden, um Bereitstellungen ohne Ausfallzeit zu verwalten. Erst wenn sich der Status des Diensts bzw. Containers in „healthy“ (OK) ändert, leitet der Orchestrator wieder Datenverkehr an die Instanzen des Diensts bzw. Containers weiter.

Die Systemüberwachung ist besonders wichtig, wenn ein Orchestrator ein Anwendungsupgrade ausführt. Einige Orchestratoren (wie Azure Service Fabric) führen in Phasen Updates für Dienste aus. Sie aktualisieren also z.B. ein Fünftel der Clusteroberfläche für jedes Anwendungsupgrade. Die Knoten, für die zur selben Zeit ein Upgrade ausgeführt wird, werden als *Upgradedomäne* bezeichnet. Wenn für alle Upgradedomänen ein Upgrade ausgeführt wurde und für die Benutzer verfügbar sind, muss diese Upgradedomäne Integritätsüberprüfungen übergeben, bevor die Bereitstellung auf die nächste Upgradedomäne verschoben wird.

Berichtsmetriken des Diensts machen einen weiteren Aspekt der Dienstintegrität aus. Dabei handelt es sich um eine erweiterte Funktion des Integritätsmodells einiger Orchestratoren wie Service Fabric. Metriken sind von Bedeutung, wenn Orchestratoren verwendet werden, da sie einen Ausgleich für die Ressourcennutzung schaffen. Metriken können außerdem auf Systemintegrität hindeuten. Beispielsweise kann es sein, dass Sie über eine Anwendung mit vielen Microservices verfügen, wobei jede Instanz einen Bericht zu einer „Anforderungen pro Sekunde“-Metrik erstellt. Wenn ein Dienst mehre Ressourcen (z.B. den Arbeitsspeicher oder den Prozessor) als ein anderer Dienst verwendet, kann der Orchestrator Dienstinstanzen innerhalb des Clusters verschieben, um zu versuchen, die Ressourcenverwendung zu verwalten.

Beachten Sie, dass Azure Service Fabric ein eigenes [Modell zur Systemüberwachung](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction) umfasst, das umfassender ist als einfache Integritätsüberprüfungen.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>Erweiterte Überwachung: Visualisierung, Analyse und Warnungen

Als letzter Schritt im Rahmen der Überwachung wird der Ereignisdatenstrom visualisiert, ein Bericht zur Leistung des Diensts wird erstellt, und es wird eine Warnung ausgegeben, wenn ein Problem erkannt wird. Sie können für diesen Bestandteil der Überwachung mehrere Lösungen verwenden.

Einerseits können Sie einfache benutzerdefinierte Anwendungen verwenden, die den Status Ihrer Dienste anzeigen, z.B. die im Zusammenhang mit [ASP.NET Core-Integritätsüberprüfungen](https://github.com/aspnet/HealthChecks) erwähnten benutzerdefinierten Seiten. Andererseits können Sie auch Tools mit erweiterten Funktionen wie Azure Application Insights und Operations Management Suite verwenden, um Warnungen anhand des Datenstroms der Ereignisse auszulösen.

Außerdem können Sie Microsoft Power BI oder die Lösung eines Drittanbieters (z.B. Kibana oder Splunk) verwenden, um Daten zu visualisieren, wenn Sie alle Ereignisdatenströme gespeichert haben.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **ASP.NET Core HealthChecks** (frühe Version) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)

-   **Einführung in Service Fabric-Integritätsüberwachung**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)

-   **Azure Application Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

-   **Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
[Zurück] (implement-circuit-breaker-pattern.md) [Weiter] (../secure-net-microservices-web-applications/index.md)
