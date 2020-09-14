---
title: Implementieren von API-Gateways mit Ocelot
description: Hier erfahren Sie, wie Sie API-Gateways mit Ocelot implementieren und Ocelot in einer containerbasierten Umgebung verwenden.
ms.date: 03/02/2020
ms.openlocfilehash: 3611ffa7a163ff632ca854fafb910fcd3e228306
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "89358985"
---
# <a name="implement-api-gateways-with-ocelot"></a>Implementieren von API-Gateways mit Ocelot

> [!IMPORTANT]
> Die Referenzanwendung für Microservices [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) verwendet derzeit Features, die von [Envoy](https://www.envoyproxy.io/) zur Verfügung gestellt werden, um das API-Gateway anstelle des bereits erwähnten [Ocelot](https://github.com/ThreeMammals/Ocelot) zu implementieren.
> Wir haben uns aufgrund der integrierten Unterstützung des WebSocket-Protokolls durch Envoy für die neue, in eShopOnContainers implementierte gRPC-Kommunikation zwischen den Diensten für diese Lösung entschieden.
> Wir haben diesen Abschnitt jedoch im Leitfaden beibehalten, damit Sie Ocelot als ein einfaches, leistungsfähiges und schlankes API-Gateway in Betracht ziehen können, das sich für Produktionsszenarien eignet.
> Zudem enthält die neueste Version von Ocelot einen Breaking Change in Bezug auf das JSON-Schema. Verwenden Sie ggf. eine ältere Ocelot-Version als 16.0.0 oder die Haupt-Routes-Objekte statt ReRoutes-Objekten.

## <a name="architect-and-design-your-api-gateways"></a>Erstellen und Entwerfen der API-Gateways

Das folgende Architekturdiagramm zeigt die Implementierung von API-Gateways mit Ocelot in eShopOnContainers.

![Diagramm, das die eShopOnContainers-Architektur zeigt.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture.png)

**Abbildung 6-28**. eShopOnContainers-Architektur mit API-Gateways

In dieser Abbildung wird dargestellt, wie die gesamte Anwendung in einem Docker-Host oder Entwicklungs-PC mit Docker für Windows oder Docker für Mac bereitgestellt wird. Die Bereitstellung in einem Orchestrator erfolgt auf ähnliche Weise, jedoch können alle Container in der Abbildung im Orchestrator horizontal skaliert werden.

Ferner müssen die Infrastrukturressourcen wie Datenbanken, Cache und Nachrichtenbroker vom Orchestrator ausgelagert und in hochverfügbaren Systemen für Infrastruktur wie Azure SQL-Datenbank, Azure Cosmos DB, Azure Redis, Azure Service Bus oder in einer lokalen Clusterlösung mit Hochverfügbarkeit bereitgestellt werden.

Wie der Abbildung außerdem zu entnehmen ist, können bei Verwendung mehrerer API-Gateways mehrere Entwicklungsteams autonom (in diesem Beispiel Marketingfeatures und Einkaufsfeatures) bei der Entwicklung und Bereitstellung ihrer Microservices und ihrer eigenen zugehörigen API-Gateways arbeiten.

Bei nur einem monolithischen API-Gateway müsste eine zentrale Stelle von verschiedenen Entwicklungsteams aktualisiert werden, wodurch alle Microservices mit einem Teil der Anwendung gekoppelt werden könnten.

Wesentlich weiter im Design kann ein differenziertes API-Gateway je nach gewählter Architektur mitunter auf einen einzelnen Unternehmensmicroservice beschränkt sein. Wenn die Einschränkungen des API-Gateways vom Unternehmen oder von der Domäne vorgegeben sind, können Sie auf einfache Weise ein besseres Design erstellen.

Auf der Ebene des API-Gateways kann Granularität beispielsweise für erweiterte zusammengesetzte Benutzeroberflächenanwendungen, die auf Microservices basieren, besonders nützlich sein, da das Konzept eines präzisen API-Gateways einem Dienst zur Benutzeroberflächenkomposition ähnelt.

Im vorherigen Abschnitt [Creating composite UI based on microservices (Erstellen einer zusammengesetzten Benutzeroberfläche auf der Grundlage von Microservices)](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md) haben wir uns damit eingehend befasst.

Wichtig ist, dass sich bei vielen mittelgroßen und großen Anwendungen die Verwendung eines kundenspezifischen API-Gatewayprodukts anbietet. Dieses API-Gateway sollte jedoch nur dann als einzelner monolithischer Aggregator oder als exklusives benutzerdefiniertes zentrales API-Gateway eingesetzt werden, wenn es für die verschiedenen Entwicklungsteams, die autonome Microservices erstellen, mehrere unabhängige Konfigurationsbereiche zulässt.

### <a name="sample-microservicescontainers-to-reroute-through-the-api-gateways"></a>Beispiele für Microservices bzw. Container, die über die API-Gateways umgeleitet werden

eShopOnContainers enthält beispielsweise etwa sechs interne Microservicetypen, die, wie in der Abbildung dargestellt, über die API-Gateways veröffentlicht werden sollen.

![Screenshot des Ordners „Dienste“ mit seinen Unterordnern](./media/implement-api-gateways-with-ocelot/eshoponcontainers-microservice-folders.png)

**Abbildung 6-29**. Microserviceordner in eShopOnContainers-Projektmappe in Visual Studio

Der Microservice „Identity“ wurde im Design aus dem API-Gatewayrouting ausgelassen, da es sich hierbei um den einzigen übergreifenden Belang im System handelt. Mit Ocelot kann er jedoch auch als Teil der Umleitungslisten einbezogen werden.

Wie anhand des Codes zu erkennen ist, sind diese Microservices derzeit alle als ASP.NET Core Web-API-Microservices implementiert. Betrachten wir nun einen der Microservices etwas genauer, wie etwa den Code des Microservices „Catalog“.

![Screenshot des Projektmappen-Explorers mit dem Inhalt des Catalog.API-Projekts.](./media/implement-api-gateways-with-ocelot/catalog-api-microservice-folders.png)

**Abbildung 6-30**. Beispiel für einen Web-API-Microservice (Microservice „Catalog“)

Es ist zu erkennen, dass der Microservice „Catalog“ ein typisches ASP.NET Core Web-API-Projekt mit mehreren Controllern und Methoden wie im folgenden Code ist.

```csharp
[HttpGet]
[Route("items/{id:int}")]
[ProducesResponseType((int)HttpStatusCode.BadRequest)]
[ProducesResponseType((int)HttpStatusCode.NotFound)]
[ProducesResponseType(typeof(CatalogItem),(int)HttpStatusCode.OK)]
public async Task<IActionResult> GetItemById(int id)
{
    if (id <= 0)
    {
        return BadRequest();
    }
    var item = await _catalogContext.CatalogItems.
                                          SingleOrDefaultAsync(ci => ci.Id == id);
    //…

    if (item != null)
    {
        return Ok(item);
    }
    return NotFound();
}
```

Die HTTP-Anforderung führt letztendlich diese Art von C#-Code durch Zugriff auf die Microservicedatenbank sowie alle weiteren erforderlichen Aktionen aus.

Mit Blick auf die Microservice-URL wird bei der Bereitstellung der Container auf dem lokalen Entwicklungs-PC (lokaler Docker-Host) wie im folgenden Beispiel zu sehen ist für jeden Container eines Microservices immer ein interner Port (meist Port 80) im entsprechenden Dockerfile angegeben:

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80
```

Der im Code angegebene Port 80 ist ein interner Port im Docker-Host, auf den Client-Apps nicht zugreifen können.

Client-Apps können nur auf die externen Ports zugreifen (sofern vorhanden), die bei der Bereitstellung mit `docker-compose` veröffentlicht werden.

Diese externen Ports dürfen bei der Bereitstellung in einer Produktionsumgebung nicht veröffentlicht werden. Aus diesem Grund sollten Sie das API-Gateway verwenden, um die direkte Kommunikation zwischen den Client-Apps und den Microservices zu vermeiden.

Beim Entwickeln möchten Sie jedoch auf den Microservice bzw. auf den Container direkt zugreifen und den Microservice bzw. den Container über Swagger ausführen. Daher werden die externen Ports in eShopOnContainers dennoch angegeben, auch wenn sie vom API-Gateway oder den Client-Apps nicht verwendet werden.

Das folgende Beispiel zeigt die Datei `docker-compose.override.yml` für den Microservice „Catalog“:

```yml
catalog-api:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:80
    - ConnectionString=YOUR_VALUE
    - ... Other Environment Variables
  ports:
    - "5101:80"   # Important: In a production environment you should remove the external port (5101) kept here for microservice debugging purposes.
                  # The API Gateway redirects and access through the internal port (80).
```

Wie Sie sehen, wurde in der Datei „docker-compose.override.yml“ Port 80 als interner Port für den Container „Catalog“ konfiguriert, für den externen Zugriff jedoch Port 5101. Dieser Port sollte bei Verwendung eines API-Gateways von der Anwendung jedoch nur zum Debuggen, Ausführen und Testen des Microservice „Catalog“ verwendet werden.

Normalerweise würde die Bereitstellung mit „docker-compose“ nicht in einer Produktionsumgebung stattfinden, da die richtige Produktionsbereitstellungsumgebung für Microservices ein Orchestrator wie Kubernetes oder Service Fabric ist. Bei einer Bereitstellung in diesen Umgebungen verwenden Sie unterschiedliche Konfigurationsdateien, wenn Sie nicht direkt einen externen Port für Microservices veröffentlichen möchten. Sie verwenden jedoch immer den Reverseproxy aus dem API-Gateway.

Führen Sie den Microservice „Catalog“ auf Ihrem lokalen Docker-Host aus. Dazu haben Sie zwei Möglichkeiten. Führen Sie entweder die gesamte eShopOnContainers-Projektmappe über Visual Studio aus (dabei werden alle Microservices in den „docker-compose“-Dateien ausgeführt), oder verwenden Sie den folgenden „docker-compose“-Befehl in CMD oder PowerShell, um den Microservice „Catalog“ aus dem Ordner zu starten, in dem sich die Dateien `docker-compose.yml` und `docker-compose.override.yml` befinden.

```console
docker-compose run --service-ports catalog-api
```

Mit diesem Befehl werden nur der Dienstcontainer „catalog-api“ sowie die Abhängigkeiten ausgeführt, die in der Datei „docker-compose.yml“ angegeben sind. In diesem Beispiel sind das die Container „SQL Server“ und „RabbitMQ“.

Anschließend können Sie direkt auf den Microservice „Catalog“ zugreifen und sich die zugehörigen Methoden über die Swagger-Benutzeroberfläche direkt über diesen „externen“ Port (in diesem Beispiel `http://localhost:5101/swagger`) anzeigen lassen:

![Browseransicht der Swagger-Benutzeroberfläche mit der Catalog.API-REST-API.](./media/implement-api-gateways-with-ocelot/test-catalog-microservice.png)

**Abbildung 6-31**. Testen des Microservice „Catalog“ mit der Swagger-Benutzeroberfläche

An dieser Stelle könnten Sie einen Haltepunkt im C#-Code in Visual Studio festlegen, den Microservice mit den in der Swagger-Benutzeroberfläche angezeigten Methoden testen und schließlich mit dem Befehl `docker-compose down` alles bereinigen.

Direkte Kommunikation mit dem Microservice, in diesem Beispiel über den externen Port 5101, sollten Sie in Ihrer Anwendung jedoch vermeiden. Sie können sie vermeiden, indem Sie die zusätzliche Dereferenzierungsebene des API-Gateways (in diesem Beispiel Ocelot) festlegen. Auf diese Weise greift die Client-App nicht direkt auf den Microservice zu.

## <a name="implementing-your-api-gateways-with-ocelot"></a>Implementieren von API-Gateways mit Ocelot

Bei Ocelot handelt es sich im Grunde um mehrere Middlewares, die Sie in einer bestimmten Reihenfolge anwenden können.

Ocelot wurde speziell nur für ASP.NET Core entwickelt. Die neueste Version des Pakets ist auf `.NETCoreApp 3.1` ausgerichtet und daher nicht für .NET Framework-Anwendungen geeignet.

Installieren Sie Ocelot und die zugehörigen Abhängigkeiten in Ihrem ASP.NET Core-Projekt mit dem [NuGet-Paket für Ocelot](https://www.nuget.org/packages/Ocelot/) über Visual Studio.

```powershell
Install-Package Ocelot
```

In eShopOnContainers ist die API-Gateway-Implementierung ein einfaches ASP.NET Core-WebHost-Projekt. Für die API-Gatewayfeatures ist wie in der folgenden Abbildung dargestellt die Middleware von Ocelot zuständig:

![Screenshot des Projektmappen-Explorers mit dem Ocelot-API-Gatewayprojekt.](./media/implement-api-gateways-with-ocelot/ocelotapigw-base-project.png)

**Abbildung 6-32**. Das Basisprojekt „OcelotApiGw“ in eShopOnContainers

Dieses ASP.NET Core-WebHost-Projekt besteht im Grunde aus zwei einfachen Dateien: `Program.cs` und `Startup.cs`.

Mit der Datei „Program.cs“ wird lediglich die typische ASP.NET Core-Methode „BuildWebHost“ erstellt und konfiguriert.

```csharp
namespace OcelotApiGw
{
    public class Program
    {
        public static void Main(string[] args)
        {
            BuildWebHost(args).Run();
        }

        public static IWebHost BuildWebHost(string[] args)
        {
            var builder = WebHost.CreateDefaultBuilder(args);

            builder.ConfigureServices(s => s.AddSingleton(builder))
                    .ConfigureAppConfiguration(
                          ic => ic.AddJsonFile(Path.Combine("configuration",
                                                            "configuration.json")))
                    .UseStartup<Startup>();
            var host = builder.Build();
            return host;
        }
    }
}
```

Wichtig für Ocelot ist die Datei `configuration.json`, die Sie dem Generator über die Methode `AddJsonFile()` bereitstellen müssen. In dieser `configuration.json`-Datei werden alle API-Gateway-Umleitungen, d.h. die externen Endpunkte mit bestimmten Ports und die entsprechenden internen Endpunkte (meist mit anderen Ports), angegeben.

```json
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

Für die Konfiguration gibt es zwei Abschnitte: „ReRoutes“ und „GlobalConfiguration“. Bei „ReRoutes“ handelt es sich um die Objekte, die Ocelot mitteilen, wie eine Upstreamanforderung behandelt werden soll. Mit „GlobalConfiguration“ können „ReRoute“-spezifische Einstellungen außer Kraft gesetzt werden. Das ist hilfreich, wenn Sie vermeiden möchten, dass Sie zahlreiche „ReRoute“-spezifische Einstellungen verwalten müssen.

Das folgende Beispiel zeigt eine vereinfachte [ReRoute-Konfigurationsdatei](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) aus einem der API-Gateways aus eShopOnContainers.

```json
{
  "ReRoutes": [
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "catalog-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/c/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ]
    },
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }

  ],
    "GlobalConfiguration": {
      "RequestIdKey": "OcRequestId",
      "AdministrationPath": "/administration"
    }
  }
```

Ein Ocelot-API-Gateway hat in erster Linie die Aufgabe, eingehende HTTP-Anforderungen derzeit als eine andere HTTP-Anforderung an einen Downstreamdienst weiterzuleiten. Bei Ocelot wird die Weiterleitung einer Anforderung an eine andere Anforderung als ReRoute beschrieben.

Betrachten Sie beispielsweise eines der ReRoute-Objekte in der Datei „configuration.json“ weiter oben; die Konfiguration des Microservice „Basket“.

```json
{
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
}
```

„DownstreamPathTemplate“, „Scheme“ und „DownstreamHostAndPorts“ ergeben die interne Microservice-URL, an die diese Anforderung weitergeleitet wird.

Als Port wird der vom Microservice verwendete interne Port verwendet. Bei Verwendung von Containern wird der Port in der entsprechenden Dockerfile angegeben.

`Host` ist ein Dienstname, der von der verwendeten Dienstnamensauflösung abhängt. Bei Verwendung von „docker-compose“ werden die Dienstnamen vom Docker-Host bereitgestellt, der die in den „docker-compose“-Dateien bereitgestellten Dienstnamen verwendet. Bei Verwendung eines Orchestrators wie Kubernetes oder Service Fabric sollte dieser Name durch die vom jeweiligen Orchestrator bereitgestellte DNS- oder Namensauflösung aufgelöst werden.

Bei „DownstreamHostAndPorts“ handelt es sich um ein Array, das den Host und Port aller Downstreamdienste enthält, an die Sie Anforderungen weiterleiten möchten. In der Regel ist nur ein Eintrag enthalten. Es kann jedoch vorkommen, dass Sie für Anforderungen einen Lastausgleich in Ihren Downstreamdiensten vornehmen möchten. Mit Ocelot können Sie mehrere Einträge hinzufügen und einen Lastausgleich auswählen. Wenn Sie jedoch Azure und einen Orchestrator verwenden, sollten Sie einen Lastausgleich mit der Cloud- oder Orchestratorinfrastruktur vornehmen.

„UpstreamPathTemplate“ ist die URL, die von Ocelot verwendet wird, um zu bestimmen, welches DownstreamPathTemplate-Objekt für eine bestimmte Anforderung vom Client verwendet wird. „UpstreamHttpMethod“ wird verwendet, damit Ocelot zwischen unterschiedlichen Anforderungen (GET, POST, PUT) an dieselbe URL unterscheiden kann.

An dieser Stelle können Sie ein Ocelot-API-Gateway (ASP.NET Core WebHost) zusammen mit einem oder [mehreren zusammengeführten configuration.json-Dateien](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) verwenden oder die [Konfiguration in einem Consul-Schlüsselwertspeicher](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul) speichern.

Wie in den Abschnitten über Architektur und Design bereits erwähnt, sollten Sie bei Verwendung von autonomen Microservices dieses monolithische API-Gateway jedoch in mehrere API-Gateways und/oder BFFs (Backend for Frontend) aufteilen. Betrachten wir dazu, wie dieser Ansatz mit Docker-Containern implementiert wird.

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a>Verwenden eines Docker-Containerimages zum Ausführen von verschiedenen API-Gateway-/BFF-Containertypen

In eShopOnContainers verwenden wir ein Docker-Containerimage mit dem Ocelot-API-Gateway. Zur Laufzeit erstellen wir für die einzelnen API-Gatewaytypen/BFF-Typen jedoch andere Microservices bzw. Container, indem eine andere configuration.json-Datei bereitgestellt wird. Dazu wird ein Docker-Volume verwendet, um für jeden Dienst auf einen anderen PC-Ordner zuzugreifen.

![Diagramm eines einzigen Docker-Images des Ocelot-Gateways für alle API-Gateways.](./media/implement-api-gateways-with-ocelot/reusing-single-ocelot-docker-image.png)

**Abbildung 6-33**. Wiederverwenden eines Ocelot-Docker-Images für mehrere API-Gatewaytypen

In eShopOnContainers wird das „generische Ocelot-API-Gateway-Docker-Image“ mit dem Projekt „OcelotApiGw“ und dem Imagenamen „eshop/ocelotapigw“ erstellt, das in der Datei „docker-compose.yml“ angegeben ist. Bei der Bereitstellung in Docker werden aus diesem Docker-Image wie im folgenden Auszug aus der Datei „docker-compose.yml“ vier API-Gateway-Container erstellt.

```yml
  mobileshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  mobilemarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webmarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile
```

Wie Sie im folgenden Auszug aus der Datei „docker-compose.override.yml“ erkennen können, unterscheiden sich diese API-Gateway-Container außerdem nur durch die Ocelot-Konfigurationsdatei. Diese Datei ist für jeden Dienstcontainer anders, und sie wird bei Laufzeit über ein Docker-Volume angegeben.

```yml
mobileshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5200:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Shopping/apigw:/app/configuration

mobilemarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5201:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Marketing/apigw:/app/configuration

webshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5202:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Shopping/apigw:/app/configuration

webmarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5203:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Marketing/apigw:/app/configuration
```

Aufgrund dieses vorherigen Codes und wie im Visual Studio-Explorer weiter veranschaulicht wird, ist zum Definieren der einzelnen Business/BFF-API-Gateways nur eine configuration.json-Datei erforderlich, da die vier API-Gateways auf demselben Docker-Image basieren.

![Screenshot, der alle API-Gateways mit „configuration.json“-Dateien zeigt.](./media/implement-api-gateways-with-ocelot/ocelot-configuration-files.png)

**Abbildung 6-34**. Zum Definieren der einzelnen API-Gateways/BFF mit Ocelot ist nur eine Konfigurationsdatei erforderlich.

Wenn das API-Gateway in mehrere API-Gateways aufgeteilt wird, können verschiedene Entwicklungsteams, die sich auf unterschiedliche Teilmengen von Microservices konzentrieren, ihre eigenen API-Gateways mithilfe von unabhängigen Ocelot-Konfigurationsdateien verwalten. Zudem können sie gleichzeitig dasselbe Ocelot-Docker-Image wiederverwenden.

Wenn Sie nun beim Öffnen der Projektmappe „eShopOnContainers-ServicesAndWebApps.sln“ oder beim Ausführen von „docker-compose up“ eShopOnContainers mit den API-Gateways ausführen (standardmäßig in VS enthalten), werden die folgenden Beispielrouten ausgeführt.

Beim Aufrufen der vom API-Gateway „webshoppingapigw“ unterstützten Upstream-URL `http://localhost:5202/api/v1/c/catalog/items/2/` erhalten Sie beispielsweise dasselbe Ergebnis von der internen Downstream-URL `http://catalog-api/api/v1/2` im Docker-Host, als in dem folgenden Browser zu sehen ist.

![Screenshot eines Browsers mit einer Antwort, die das API-Gateway durchläuft.](./media/implement-api-gateways-with-ocelot/access-microservice-through-url.png)

**Abbildung 6-35**. Zugriff auf einen Microservice über eine vom API-Gateway bereitgestellten URL

Wenn Sie – weil „catalog-api“ eine interne DNS-Auflösung im Docker-Host (für die Dienstermittlung sind „docker-compose“-Dienstnamen verantwortlich) ist – zum Testen oder Debuggen ohne Umweg über das API-Gateway direkt auf den Docker-Container „Catalog“ (nur in der Entwicklungsumgebung) zugreifen möchten, haben Sie nur die Möglichkeit, über den in der Datei „docker-compose.override.yml“ veröffentlichten externen Port auf diesen Container zuzugreifen. Diese Datei wird nur für Entwicklungstests (wie `http://localhost:5101/api/v1/Catalog/items/1` im folgenden Browser) bereitgestellt.

![Screenshot eines Browsers mit einer direkten Antwort an die Catalog.api.](./media/implement-api-gateways-with-ocelot/direct-access-microservice-testing.png)

**Abbildung 6-36**. Direktzugriff auf einen Microservice zum Testen

Die Anwendung ist jedoch so konfiguriert, dass sie auf alle Microservices über das API-Gateway zugreift und nicht über die direkten „Portverknüpfungen“.

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a>Das Gateway-Aggregationsmuster in eShopOnContainers

Wie bereits erwähnt, bieten benutzerdefinierte Dienste eine flexible Möglichkeit, Anforderungsaggregationen nach Code zu implementieren. Anforderungsaggregationen können auch mit dem [Feature für Anforderungsaggregationen in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation) implementiert werden. Dieses Feature ist jedoch möglicherweise weniger flexibel. Daher wurde zum Implementieren von Aggregationen in eShopOnContainers für jeden Aggregator ein eigener ASP.NET Core Web-API-Dienst ausgewählt.

Diesem Konzept zufolge ist die Abbildung zur API-Gatewayzusammensetzung in Wirklichkeit und unter Berücksichtigung der Aggregatordienste, die in der vereinfachten globalen Architektur weiter oben nicht dargestellt sind, etwas umfassender.

In der folgenden Abbildung ist ferner zu erkennen, wie die Aggregatordienste die jeweiligen API-Gateways nutzen.

![Diagramm, der eShopOnContainers-Architektur mit Aggregatordiensten.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture-aggregator-services.png)

**Abbildung 6-37**. eShopOnContainers-Architektur mit Aggregatordiensten

Wenn wir den Geschäftsbereich „Shopping“ in der folgenden Abbildung genauer betrachten, erkennen Sie, dass das hohe Kommunikationsaufkommen der Client-Apps mit den Microservices reduziert wird, wenn die Aggregatordienste in den API-Gateways verwendet werden.

![Diagramm, das eine vergrößerte Ansicht der eShopOnContainers-Architektur zeigt.](./media/implement-api-gateways-with-ocelot/zoom-in-vision-aggregator-services.png)

**Abbildung 6-38**. Größere Darstellung der Aggregatordienste

Wie Sie sehen, wird das Ganze recht komplex, wenn in der Abbildung die möglichen Anforderungen von den API-Gateways dargestellt werden. Sie können sehen, wie die blauen Pfeile aus der Sicht von Client-Apps bei Verwendung des Aggregatormusters deutlich vereinfacht wurden, indem das Kommunikationsaufkommen und die Latenz in der Kommunikation reduziert wurden. Dadurch wird insbesondere die Benutzerfreundlichkeit für die Remote-Apps (mobile Apps und SPA-Apps) erheblich verbessert.

Beim Geschäftsbereich „Marketing“ und den entsprechenden Microservices geht es um einen einfachen Anwendungsfall. Daher mussten keine Aggregatoren verwendet werden. Bei Bedarf wäre dies jedoch möglich.

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a>Authentifizierung und Autorisierung in Ocelot-API-Gateways

In einem Ocelot-API-Gateway können Sie den Authentifizierungsdienst wie etwa einen ASP.NET Core Web-API-Dienst mithilfe von [IdentityServer](https://identityserver.io/) zur Bereitstellung des Authentifizierungstokens innerhalb oder außerhalb des API-Gateways platzieren.

Da eShopOnContainers mehrere API-Gateways mit Grenzen verwendet, die auf BFF und Geschäftsbereichen basieren, wird der Dienst „Identity/Auth“ außerhalb des API-Gateways platziert (in der folgenden Abbildung gelb hervorgehoben).

![Diagramm, das den Microservice „Identity“ unterhalb des API-Gateways zeigt.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-identity-service-position.png)

**Abbildung 6-39**. Position des Microservice „Identity“ in eShopOnContainers

Wie in der folgenden Abbildung zu sehen ist, unterstützt Ocelot auch die Platzierung des Microservice „Identity/Auth“ innerhalb der API-Gateway-Grenze.

![Diagramm, das die Authentifizierung in einem Ocelot-API-Gateway zeigt.](./media/implement-api-gateways-with-ocelot/ocelot-authentication.png)

**Abbildung 6-40**. Authentifizierung in Ocelot

Wie das vorherige Diagramm zeigt, wenn sich der Microservice „Identity“ unterhalb des API-Gateways (AB) befindet: 1) AG fordert ein Authentifizierungstoken vom Microservice „Identity“ an, 2) Der Microservice „Identity“ gibt das Token zurück an AG, 3-4) AG fordert vom Microservice die Verwendung des Authentifizierungstokens. Da bei der Anwendung eShopOnContainers das API-Gateway in mehrere BFF-API-Gateways (Backend for Frontend) und Geschäftsbereich-API-Gateways aufgeteilt ist, wäre eine andere Möglichkeit gewesen, ein zusätzliches API-Gateway für übergreifende Belange zu erstellen. Diese Option wäre in einer komplexeren, auf Microservices basierenden Architektur mit mehreren Microservices für übergreifende Belange angemessen. Da es in eShopOnContainers nur einen übergreifenden Belang gibt, wurde entschieden, der Einfachheit halber aus dem Bereich des API-Gateways nur den Sicherheitsdienst zu unterstützen.

Wenn die App auf der API-Gateway-Ebene geschützt wird, wird bei Verwendung eines geschützten Microservice auf jeden Fall zuerst das Authentifizierungsmodul des Ocelot-API-Gateways aufgerufen. Dieses leitet die HTTP-Anforderung zum Aufrufen des Microservice „Identity“ oder „Auth“ um, um so das Zugriffstoken abzurufen, damit die geschützten Dienste mit dem Zugriffstoken aufgerufen werden können.

Dienste werden auf der API-Gateway-Ebene mittels Authentifizierung geschützt, indem „AuthenticationProviderKey“ in den entsprechenden Einstellungen in der Datei „configuration.json“ festgelegt werden.

```json
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }
```

Wenn Ocelot ausgeführt wird, wird bei den ReRoutes „AuthenticationOptions.AuthenticationProviderKey“ geprüft, ob für den angegebenen Schlüssel ein Authentifizierungsanbieter registriert wurde. Ist kein Schlüssel vorhanden, wird Ocelot nicht gestartet. Ist ein Schlüssel vorhanden, wird der entsprechende Anbieter beim Ausführen von ReRoute verwendet.

Da der Ocelot-Webhost mit `authenticationProviderKey = "IdentityApiKey"` konfiguriert wurde, ist immer dann eine Authentifizierung erforderlich, wenn dieser Dienst Anforderungen ohne Authentifizierungstoken aufweist.

```csharp
namespace OcelotApiGw
{
    public class Startup
    {
        private readonly IConfiguration _cfg;

        public Startup(IConfiguration configuration) => _cfg = configuration;

        public void ConfigureServices(IServiceCollection services)
        {
            var identityUrl = _cfg.GetValue<string>("IdentityUrl");
            var authenticationProviderKey = "IdentityApiKey";
                         //…
            services.AddAuthentication()
                .AddJwtBearer(authenticationProviderKey, x =>
                {
                    x.Authority = identityUrl;
                    x.RequireHttpsMetadata = false;
                    x.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters()
                    {
                        ValidAudiences = new[] { "orders", "basket", "locations", "marketing", "mobileshoppingagg", "webshoppingagg" }
                    };
                });
            //...
        }
    }
}
```

Ferner müssen Sie wie beim folgenden Controller des Microservice „Basket“ die Autorisierung mit dem Attribut „[Authorize]“ für alle Ressourcen festlegen, auf die zugegriffen werden soll, wie etwa für die Microservices.

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class BasketController : Controller
    {
      //...
    }
}
```

ValidAudiences wie „basket“ sind wie im folgenden Code mit der in den einzelnen Microservices mit `AddJwtBearer()` in „ConfigureServices()“ der Startup-Klasse definierten Zielgruppe verknüpft.

```csharp
// prevent from mapping "sub" claim to nameidentifier.
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();

var identityUrl = Configuration.GetValue<string>("IdentityUrl");

services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

}).AddJwtBearer(options =>
{
    options.Authority = identityUrl;
    options.RequireHttpsMetadata = false;
    options.Audience = "basket";
});
```

Wenn Sie auf einen geschützten Microservice wie „Basket“ mit einer ReRoute-URL basierend auf einen API-Gateway wie `http://localhost:5202/api/v1/b/basket/1` zugreifen und kein gültiges Token angeben, erhalten Sie die Fehlermeldung „401 – Nicht autorisiert.“. Wenn eine ReRoute-URL jedoch authentifiziert wird, ruft Ocelot das damit (mit der internen Microservice-URL) verbundene Downstreamschema auf.

**Autorisierung auf der ReRoute-Ebene von Ocelot.**  Ocelot unterstützt die anspruchsbasierte Autorisierung, die nach der Authentifizierung ausgewertet wird. Sie können die Autorisierung auf Routenebene festlegen, indem Sie die folgenden Zeilen zur ReRoute-Konfiguration hinzufügen.

```json
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

Wenn die Autorisierungsmiddleware in diesem Beispiel aufgerufen wird, erkennt Ocelot, ob im Benutzer der Anspruchstyp „UserType“ im Token enthalten ist und ob der Wert dieses Anspruchs „employee“ lautet. Ist dies nicht der Fall, wird der Benutzer nicht autorisiert und die Antwort lautet „403 Verboten“.

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a>Verwenden von Kubernetes Ingress und Ocelot-API-Gateways

Wenn Sie Kubernetes (wie etwa in einem Azure Kubernetes Service-Cluster) verwenden, führen Sie in der Regel alle HTTP-Anforderungen über die [Kubernetes Ingress-Ebene](https://kubernetes.io/docs/concepts/services-networking/ingress/) basierend auf *Nginx* zusammen.

Wenn Sie in Kubernetes kein Ingress-Konzept verwenden, können die IPs Ihrer Dienste und Pods nur vom Clusternetzwerk geroutet werden.

Wenn jedoch ein Ingress-Konzept erkennbar ist, ist zwischen dem Internet und Ihren Diensten (und Ihren API-Gateways) eine mittlere Ebene vorhanden, die als Reverseproxy dient.

Ingress ist als eine Sammlung von Regeln definiert, die es eingehenden Verbindungen ermöglichen, die Clusterdienste zu erreichen. Ingress wird normalerweise konfiguriert, um Diensten extern erreichbare URLs, Lastausgleich für den Datenverkehr, SSL-Terminierung usw. bereitzustellen. Benutzer fordern Ingress an, indem sie die Ingress-Ressource an den API-Server senden.

Wenn Sie in eShopOnContainers lokal entwickeln und nur Ihren Entwicklungscomputer als Docker-Host verwenden, benötigen Sie Ingress nicht, sondern nur die API-Gateways.

Wenn Sie dagegen eine Produktionsumgebung basierend auf Kubernetes als Ziel festlegen, wird Ingress von eShopOnContainers vor die API-Gateways geschaltet. Auf diese Weise rufen die Clients weiterhin dieselbe Basis-URL auf, die Anforderungen werden jedoch an die API-Gateways oder BFF weitergeleitet.

API-Gateways sind Front-Ends oder Fassaden, die nur die Dienste, nicht jedoch die Webanwendungen bereitstellen, die in der Regel außerhalb deren Bereich liegen. Zudem können die API-Gateways bestimmte interne Microservices verbergen.

Ingress leitet dagegen nur HTTP-Anforderungen um und versucht nicht, Microservices oder Webanwendungen zu verbergen.

Eine Ingress-Nginx-Ebene in Kubernetes vor den Webanwendungen sowie mehrere Ocelot-API-Gateways/BFFs wie in der folgenden Abbildung ist die ideale Architektur.

![Ein Diagramm, das zeigt, wie eine Ingress-Ebene in die AKS-Umgebung passt.](./media/implement-api-gateways-with-ocelot/eshoponcontainer-ingress-tier.png)

**Abbildung 6-41**. Die Ingress-Ebene in eShopOnContainers bei Bereitstellung in Kubernetes

Kubernetes Ingress dient als Reverseproxy für den gesamten Datenverkehr zur App. Dies gilt auch für Web-Apps, die normalerweise außerhalb des API-Gateway-Bereichs liegen. Wenn Sie eShopOnContainers in Kubernetes bereitstellen, werden nur wenige Dienste oder Endpunkte über _ingress_ verfügbar gemacht. Hierbei handelt es sich im Wesentlichen um die folgende Liste mit Postfixes in den URLs:

- `/` für die SPA-Clientwebanwendung
- `/webmvc` für die MVC-Clientwebanwendung
- `/webstatus` für die Clientwebanwendung, zeigt den Status/Integritätsprüfungen an
- `/webshoppingapigw` für die BFF- und „Shopping“-Webgeschäftsprozesse
- `/webmarketingapigw` für die BFF- und „Marketing“-Webgeschäftsprozesse
- `/mobileshoppingapigw` für die mobilen BFF- und „Shopping“-Geschäftsprozesse
- `/mobilemarketingapigw` für die mobilen BFF- und „Marketing“-Geschäftsprozesse

Bei der Bereitstellung für Kubernetes verwendet jedes Ocelot-API-Gateway für jeden _Pod_, der die API-Gateways ausführt, eine andere configuration.json-Datei. Diese configuration.json-Dateien werden bereitgestellt, indem ein Volume (ursprünglich mit dem Skript „deploy.ps1“) eingebunden wird, das auf einer Kubernetes-_Konfigurationszuordnung_ mit dem Namen „ocelot“ basiert. Jeder Container bindet die entsprechende Konfigurationsdatei in den Containerordner namens `/app/configuration` ein.

In den Quellcodedateien von eShopOnContainers befinden sich die ursprünglichen configuration.json-Dateien im Ordner `k8s/ocelot/`. Für jedes BFF/API-Gateway gibt es eine Datei.

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a>Weitere übergreifende Features in einem Ocelot-API-Gateway

Bei Verwendung eines Ocelot-API-Gateways gibt es weitere wichtige Features zu erforschen und zu verwenden. Diese werden unter den folgenden Links beschrieben.

- **Dienstermittlung auf Clientseite mit Integration von Ocelot in Consul oder Eureka** \
  <https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html>

- **Zwischenspeichern auf der API-Gateway-Ebene** \
  <https://ocelot.readthedocs.io/en/latest/features/caching.html>

- **Protokollieren auf der API-Gateway-Ebene** \
  <https://ocelot.readthedocs.io/en/latest/features/logging.html>

- **Quality of Service (Wiederholungen und Schaltkreisunterbrecher) auf der API-Gateway-Ebene** \
  <https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html>

- **Bandbreitenbegrenzung** \
  [https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

> [!div class="step-by-step"]
> [Zurück](background-tasks-with-ihostedservice.md)
> [Weiter](../microservice-ddd-cqrs-patterns/index.md)
