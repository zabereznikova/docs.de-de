---
title: Systemüberwachung
description: Entdecken Sie eine Möglichkeit zum Implementieren der Systemüberwachung.
ms.date: 01/13/2021
ms.openlocfilehash: 4b85193c260b950b0c7a1c97ca5c83dfc87e5fb3
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189062"
---
# <a name="health-monitoring"></a>Systemüberwachung

Über die Systemüberwachung können Sie nahezu in Echtzeit Informationen zum Zustand Ihrer Container und Microservices erhalten. Die Systemüberwachung ist für verschieden Aspekte von Betriebsmicroservices wichtig und ist von besonderer Bedeutung, wenn Orchestratoren wie im Folgenden beschrieben ein Anwendungsupgrade in Phasen ausführen.

Auf einem Microservice basierende Anwendungen verwenden häufig Takte oder Integritätsüberprüfungen, damit ihre Systemmonitore, Zeitpläne und Orchestratoren die verschiedenen Dienste überwachen können. Wenn Dienste nicht dazu fähig sind, nach Bedarf oder nach einem Plan Lebenszeichen von sich zu geben, können Risiken für Ihre Anwendung entstehen, wenn Sie Updates bereitstellen. Möglicherweise können Fehler auch zu spät ermittelt werden, wodurch kaskadierende Fehler nicht vermieden werden können, die zu größeren Ausfällen führen können.

Dienste in ihrer allgemeinen Form senden Zustandsberichte. Diese Informationen werden dann aggregiert, sodass eine allgemeine Übersicht zum Integritätsstatus Ihrer Anwendung erstellt werden kann. Wenn Sie einen Orchestrator verwenden, können Sie Integritätsinformationen zum Cluster Ihres Orchestratoren hinzufügen, damit der Cluster entsprechend agieren kann. Wenn Sie in Integritätsberichte von hoher Qualität investieren, die an Ihre Anwendung angepasst werden, können Sie Fehler der ausgeführte Anwendung viel einfacher ermitteln und beheben.

## <a name="implement-health-checks-in-aspnet-core-services"></a>Implementieren von Integritätsüberprüfungen in ASP.NET Core-Diensten

Beim Entwickeln eines ASP.NET Core-Microservice oder einer -Webanwendung können Sie das integrierte Feature für Integritätsprüfungen verwenden, das mit ASP.NET Core 2.2 veröffentlicht wurde ([Microsoft.Extensions.Diagnostics.HealthChecks](https://www.nuget.org/packages/Microsoft.Extensions.Diagnostics.HealthChecks)). Wie viele andere ASP.NET Core-Features enthalten die Integritätsprüfungen mehrere Dienste und eine Middleware.

Dienste und Middleware zur Überprüfung der Integrität sind einfach zu verwenden und stellen Funktionen bereit, mit denen Sie überprüfen können, ob eine beliebige externe Ressource, die für Ihre Anwendung (z. B. eine SQL Server-Datenbank oder eine Remote-API) erforderlich ist, ordnungsgemäß funktioniert. Wenn Sie dieses Feature verwenden, können Sie außerdem die Voraussetzungen für die Integrität der Ressource festlegen. Dies wird nachfolgend näher erläutert.

Damit Sie dieses Feature effektiv nutzen können, müssen Sie zunächst Dienste in Ihren Microservices konfigurieren. Außerdem ist eine Front-End-Anwendung erforderlich, die Integritätsberichte abfragt. Bei dieser Front-End-Anwendung kann es sich z.B. um eine benutzerdefinierte Anwendung zur Berichterstattung oder einen Orchestrator an sich handeln, der im Hinblick auf den Integritätszustand angemessen reagieren kann.

### <a name="use-the-healthchecks-feature-in-your-back-end-aspnet-microservices"></a>Verwenden des HealthChecks-Features in Ihren Back-End-ASP.NET-Microservices

In diesem Abschnitt erfahren Sie, wie das HealthChecks-Feature in einer ASP.NET Core 3.1 Web-API-Beispielanwendung implementiert wird, wenn das Paket [Microsoft.Extensions.Diagnostics.HealthChecks](https://www.nuget.org/packages/Microsoft.Extensions.Diagnostics.HealthChecks) verwendet wird. Die Implementierung dieses Features in großen Microservices wie eShopOnContainers wird im nächsten Abschnitt erläutert.

Damit Sie beginnen können, müssen Sie definieren, was die Integritätsstatus für die einzelnen Microservices ausmacht. In der Beispielanwendung wird definiert, dass der Microservice fehlerfrei ist, wenn seine API über HTTP zugänglich und die zugehörige SQL Server-Datenbank ebenfalls verfügbar ist.

In .NET 5 können Sie die integrierten APIs nutzen, um wie folgt die Dienste zu konfigurieren und eine Integritätsprüfung für den Microservice sowie die abhängige SQL Server-Datenbank hinzuzufügen:

```csharp
// Startup.cs from .NET 5 Web API sample
//
public void ConfigureServices(IServiceCollection services)
{
    //...
    // Registers required services for health checks
    services.AddHealthChecks()
        // Add a health check for a SQL Server database
        .AddCheck(
            "OrderingDB-check",
            new SqlConnectionHealthCheck(Configuration["ConnectionString"]),
            HealthStatus.Unhealthy,
            new string[] { "orderingdb" });
}
```

Im obigen Code konfiguriert die `services.AddHealthChecks()`-Methode eine einfache HTTP-Überprüfung, die den Statuscode **200** mit der Meldung „Fehlerfrei“ zurückgibt.  Außerdem konfiguriert die `AddCheck()`-Erweiterungsmethode eine benutzerdefinierte `SqlConnectionHealthCheck`-Klasse, mit der die Integrität der zugehörigen SQL-Datenbank-Instanz geprüft wird.

Die `AddCheck()`-Methode fügt eine neue Integritätsprüfung mit einem festgelegten Namen und der Implementierung vom Typ `IHealthCheck` hinzu. Mit der Methode „AddCheck“ können Sie mehrere Integritätsprüfungen hinzufügen, sodass ein Microservice erst einen „fehlerfreien“ Status meldet, wenn alle Prüfungen den Status „Fehlerfrei“ zurückgeben.

`SqlConnectionHealthCheck` ist eine benutzerdefinierte Klasse, die `IHealthCheck` implementiert, wodurch eine Verbindungszeichenfolge als Konstruktorparameter interpretiert und eine einfache Abfrage durchgeführt wird, um zu überprüfen, ob die Verbindung mit der SQL-Datenbank-Instanz erfolgreich ist. Sie gibt `HealthCheckResult.Healthy()` zurück, wenn die Abfrage erfolgreich ausgeführt wurde, und Sie gibt `FailureStatus` mit der tatsächlichen Ausnahme zurück, wenn sie fehlschlägt.

```csharp
// Sample SQL Connection Health Check
public class SqlConnectionHealthCheck : IHealthCheck
{
    private static readonly string DefaultTestQuery = "Select 1";

    public string ConnectionString { get; }

    public string TestQuery { get; }

    public SqlConnectionHealthCheck(string connectionString)
        : this(connectionString, testQuery: DefaultTestQuery)
    {
    }

    public SqlConnectionHealthCheck(string connectionString, string testQuery)
    {
        ConnectionString = connectionString ?? throw new ArgumentNullException(nameof(connectionString));
        TestQuery = testQuery;
    }

    public async Task<HealthCheckResult> CheckHealthAsync(HealthCheckContext context, CancellationToken cancellationToken = default(CancellationToken))
    {
        using (var connection = new SqlConnection(ConnectionString))
        {
            try
            {
                await connection.OpenAsync(cancellationToken);

                if (TestQuery != null)
                {
                    var command = connection.CreateCommand();
                    command.CommandText = TestQuery;

                    await command.ExecuteNonQueryAsync(cancellationToken);
                }
            }
            catch (DbException ex)
            {
                return new HealthCheckResult(status: context.Registration.FailureStatus, exception: ex);
            }
        }

        return HealthCheckResult.Healthy();
    }
}
```

Beachten Sie, dass `Select 1` die Abfrage ist, die im obigen Code zur Überprüfung der Integrität der Datenbank verwendet wird. Orchestratoren wie Kubernetes führen regelmäßig zur Überwachung der Verfügbarkeit Ihrer Microservices Integritätsüberprüfungen durch, indem sie Anforderungen senden, um die Microservices zu testen. Es ist wichtig, dass Ihre Datenbankabfragen effizient sind, damit diese Vorgänge schnell durchgeführt werden können und zu keiner erhöhten Ressourcennutzung führen.

Fügen Sie abschließend eine Middleware hinzu, die auf den URL-Pfad `/hc` antwortet:

```csharp
// Startup.cs from .NET 5 Web Api sample
//
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
        endpoints.MapHealthChecks("/hc");
        //...
    });
    //…
}
```

Wenn der Endpunkt `<yourmicroservice>/hc` aufgerufen wird, werden alle Integritätsüberprüfungen ausgeführt, die in der Startklasse in der `AddHealthChecks()`-Methode konfiguriert sind, und das Ergebnis wird angezeigt.

### <a name="healthchecks-implementation-in-eshoponcontainers"></a>Implementieren des HealthChecks-Features in eShopOnContainers

Microservices in eShopOnContainers hängen bei der Ausführung ihrer Aufgaben von mehreren Diensten ab. Der `Catalog.API`-Microservice von eShopOnContainers hängt beispielsweise von mehreren Diensten wie Azure Blob Storage, SQL Server und RabbitMQ ab. Daher wurden ihm mit der `AddCheck()`-Methode mehrere Integritätsprüfungen hinzugefügt. Für jeden abhängigen Dienst müsste eine benutzerdefinierte `IHealthCheck`-Implementierung hinzugefügt werden, die den jeweiligen Integritätsstatus definiert.

Beim Open-Source-Projekt [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) wird dieses Problem mit benutzerdefinierten Implementierungen von Integritätsprüfungen für jeden dieser auf .NET 5 basierenden Unternehmensdiensten gelöst. Jede Integritätsprüfung steht als individuelles NuGet-Paket zur Verfügung, das dem Projekt mühelos hinzugefügt werden kann. In eShopOnContainers werden sie in allen enthaltenen Microservices verwendet.

Zum `Catalog.API`-Microservice wurden beispielsweise folgende NuGet-Pakete hinzugefügt:

![Screenshot des NuGet-Pakets „AspNetCore.Diagnostics.HealthChecks“.](./media/monitor-app-health/aspnet-core-diagnostics-health-checks.png)

**Abbildung 8-7.** Mit AspNetCore.Diagnostics.HealthChecks in Catalog.API implementierte benutzerdefinierte Integritätsprüfungen

Im folgenden Code werden die Implementierungen der Integritätsprüfungen für jeden abhängigen Dienst hinzugefügt, und anschließend wird die Middleware konfiguriert:

```csharp
// Startup.cs from Catalog.api microservice
//
public static IServiceCollection AddCustomHealthCheck(this IServiceCollection services, IConfiguration configuration)
{
    var accountName = configuration.GetValue<string>("AzureStorageAccountName");
    var accountKey = configuration.GetValue<string>("AzureStorageAccountKey");

    var hcBuilder = services.AddHealthChecks();

    hcBuilder
        .AddSqlServer(
            configuration["ConnectionString"],
            name: "CatalogDB-check",
            tags: new string[] { "catalogdb" });

    if (!string.IsNullOrEmpty(accountName) && !string.IsNullOrEmpty(accountKey))
    {
        hcBuilder
            .AddAzureBlobStorage(
                $"DefaultEndpointsProtocol=https;AccountName={accountName};AccountKey={accountKey};EndpointSuffix=core.windows.net",
                name: "catalog-storage-check",
                tags: new string[] { "catalogstorage" });
    }
    if (configuration.GetValue<bool>("AzureServiceBusEnabled"))
    {
        hcBuilder
            .AddAzureServiceBusTopic(
                configuration["EventBusConnection"],
                topicName: "eshop_event_bus",
                name: "catalog-servicebus-check",
                tags: new string[] { "servicebus" });
    }
    else
    {
        hcBuilder
            .AddRabbitMQ(
                $"amqp://{configuration["EventBusConnection"]}",
                name: "catalog-rabbitmqbus-check",
                tags: new string[] { "rabbitmqbus" });
    }

    return services;
}
```

Fügen Sie abschließend die HealthCheck-Middleware hinzu, die am Endpunkt /hc lauscht:

```csharp
// HealthCheck middleware
app.UseHealthChecks("/hc", new HealthCheckOptions()
{
    Predicate = _ => true,
    ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
});
```

### <a name="query-your-microservices-to-report-about-their-health-status"></a>Abfragen eines Berichts zum Integritätsstatus der Microservices

Wenn Sie wie in diesem Artikel beschrieben Integritätsüberprüfungen konfiguriert haben, können Sie direkt über den Browser überprüfen, ob der Microservice einwandfrei funktioniert, sobald dieser in Docker ausgeführt wird. Sie müssen den Containerport im Docker-Host veröffentlichen, damit Sie über die externe Docker-Host-IP-Adresse oder `localhost` auf den Container zugreifen können, wie in Abbildung 8-8 gezeigt.

![Screenshot der von einer Integritätsprüfung zurückgegebenen JSON-Antwort.](./media/monitor-app-health/health-check-json-response.png)

**Abbildung 8-8.** Überprüfen des Integritätsstaus eines einzelnen Diensts über einen Browser

In diesem Test können Sie sehen, dass der Microservice `Catalog.API` (der auf Port 5101 ausgeführt wird) einwandfrei funktioniert, da er den HTTP-Status 200 und Statusinformationen im JSON-Format zurückgibt. Der Dienst hat die Integrität seiner SQL Server-Datenbankabhängigkeit und RabbitMQ ebenfalls überprüft, weshalb die Integritätsprüfung sich selbst als „Fehlerfrei“ meldet.

## <a name="use-watchdogs"></a>Verwenden von Überwachungselementen

Bei einem Überwachungselement handelt es sich um einen separaten Dienst, der die Integrität überprüfen und in mehreren Diensten geladen werden kann. Außerdem kann es Berichte zur Integrität der Microservices erstellen, indem es eine Abfrage an die bereit eingeführte `HealthChecks`-Bibliothek sendet. Dadurch können Fehler vermieden werden, die anhand der Ansicht eines einzelnen Diensts nicht ermittelt werden könnten. Überwachungselemente eignen sich außerdem zum Hosten von Code, über den ohne Benutzerinteraktion Abhilfemaßnahmen für bekannte Bedingungen ausgeführt werden können.

Das eShopOnContainers-Beispiel enthält eine Webseite, auf der wie in Abbildung 8-9 dargestellt Beispielberichte zur Integritätsüberprüfung angezeigt werden. Dabei handelt es sich um das einfachste Überwachungselement, da es nur den Zustand der Microservices und Webanwendungen in eShopOnContainers anzeigt. In der Regel führt ein Überwachungselement Aktionen aus, wenn der Status „Fehlerhaft“ ermittelt wird.

[AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) stellt auch das NuGet-Paket [AspNetCore.HealthChecks.UI](https://www.nuget.org/packages/AspNetCore.HealthChecks.UI/) bereit, das zum Anzeigen der Ergebnisse der Integritätsprüfung der konfigurierten URIs verwendet werden kann.

![Screenshot des Integritätsstatus von eShopOnContainers in der Integritätsüberprüfungs-Benutzeroberfläche.](./media/monitor-app-health/health-check-status-ui.png)

**Abbildung 8-9.** Beispielbericht zur Integritätsüberprüfung in eShopOnContainers

Dieser Überwachungsdienst fragt also den Endpunkt „/hc“ aller Microservices ab. Dadurch werden alle darin definierten Integritätsüberprüfungen ausgeführt und ein allgemeiner Integritätsstatus zurückgegeben, der von diesen Überprüfungen abhängig ist. Die Bedienung der Benutzeroberfläche der Integritätsüberprüfung ist einfach, da der Datei *Startup.cs* des Überwachungsdiensts nur einige Konfigurationseinträge und zwei Codezeilen hinzugefügt werden müssen.

Beispielkonfigurationsdatei für HealthChecksUI:

```json
// Configuration
{
  "HealthChecks-UI": {
    "HealthChecks": [
      {
        "Name": "Ordering HTTP Check",
        "Uri": "http://localhost:5102/hc"
      },
      {
        "Name": "Ordering HTTP Background Check",
        "Uri": "http://localhost:5111/hc"
      },
      //...
    ]}
}
```

„HealthChecksUI“ wird der Datei *Startup.cs* hinzufügt:

```csharp
// Startup.cs from WebStatus(Watch Dog) service
//
public void ConfigureServices(IServiceCollection services)
{
    //…
    // Registers required services for health checks
    services.AddHealthChecksUI();
}
//…
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseHealthChecksUI(config => config.UIPath = "/hc-ui");
    //…
}
```

## <a name="health-checks-when-using-orchestrators"></a>Integritätsüberprüfungen, wenn Orchestratoren verwendet werden

Orchestratoren wie Kubernetes und Service Fabric führen regelmäßig zur Überwachung der Verfügbarkeit Ihrer Microservices Integritätsüberprüfungen durch, indem sie Anforderungen senden, um diese Microservices zu testen. Wenn ein Orchestrator ermittelt, dass ein Dienst bzw. ein Container fehlerhaft ist, leitet er keine Anforderungen mehr an diese Instanz weiter. Außerdem erstellt er dann in der Regel eine neue Instanz dieses Containers.

Beispielsweise können die meisten Orchestratoren Integritätsüberprüfungen verwenden, um Bereitstellungen ohne Ausfallzeit zu verwalten. Erst wenn sich der Status des Diensts bzw. Containers in „healthy“ (OK) ändert, leitet der Orchestrator wieder Datenverkehr an die Instanzen des Diensts bzw. Containers weiter.

Die Systemüberwachung ist besonders wichtig, wenn ein Orchestrator ein Anwendungsupgrade ausführt. Einige Orchestratoren (wie Azure Service Fabric) führen in Phasen Updates für Dienste aus. Sie aktualisieren also z.B. ein Fünftel der Clusteroberfläche für jedes Anwendungsupgrade. Die Knoten, für die zur selben Zeit ein Upgrade ausgeführt wird, werden als *Upgradedomäne* bezeichnet. Wenn für alle Upgradedomänen ein Upgrade ausgeführt wurde und für die Benutzer verfügbar sind, muss diese Upgradedomäne Integritätsüberprüfungen übergeben, bevor die Bereitstellung auf die nächste Upgradedomäne verschoben wird.

Berichtsmetriken des Diensts machen einen weiteren Aspekt der Dienstintegrität aus. Dabei handelt es sich um eine erweiterte Funktion des Integritätsmodells einiger Orchestratoren wie Service Fabric. Metriken sind von Bedeutung, wenn Orchestratoren verwendet werden, da sie einen Ausgleich für die Ressourcennutzung schaffen. Metriken können außerdem auf Systemintegrität hindeuten. Beispielsweise kann es sein, dass Sie über eine Anwendung mit vielen Microservices verfügen, wobei jede Instanz einen Bericht zu einer „Anforderungen pro Sekunde“-Metrik erstellt. Wenn ein Dienst mehre Ressourcen (z.B. den Arbeitsspeicher oder den Prozessor) als ein anderer Dienst verwendet, kann der Orchestrator Dienstinstanzen innerhalb des Clusters verschieben, um zu versuchen, die Ressourcenverwendung zu verwalten.

Beachten Sie, dass Azure Service Fabric ein eigenes [Modell zur Systemüberwachung](/azure/service-fabric/service-fabric-health-introduction) umfasst, das umfassender ist als einfache Integritätsüberprüfungen.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>Erweiterte Überwachung: Visualisierung, Analyse und Warnungen

Als letzter Schritt im Rahmen der Überwachung wird der Ereignisdatenstrom visualisiert, ein Bericht zur Leistung des Diensts wird erstellt, und es wird eine Warnung ausgegeben, wenn ein Problem erkannt wird. Sie können für diesen Bestandteil der Überwachung mehrere Lösungen verwenden.

Einerseits können Sie einfache benutzerdefinierte Anwendungen verwenden, die den Status Ihrer Dienste anzeigen, z. B. die im Zusammenhang mit [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) erwähnten benutzerdefinierten Seiten. Andererseits können Sie auch Tools mit erweiterten Funktionen wie [Azure Monitor](https://azure.microsoft.com/services/monitor/) verwenden, um Warnungen anhand des Datenstroms der Ereignisse auszulösen.

Außerdem können Sie Microsoft Power BI oder andere Lösungen (z.B. Kibana oder Splunk) verwenden, um Daten zu visualisieren, wenn Sie alle Ereignisdatenströme gespeichert haben.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **HealthChecks und HealthChecksUI für ASP.NET Core** \
  <https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks>

- **Einführung in die Systemüberwachung mit Service Fabric** \
  [https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction](/azure/service-fabric/service-fabric-health-introduction)

- **Azure Monitor** \
  <https://azure.microsoft.com/services/monitor/>

>[!div class="step-by-step"]
>[Zurück](implement-circuit-breaker-pattern.md)
>[Weiter](../secure-net-microservices-web-applications/index.md)
