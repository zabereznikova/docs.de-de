---
title: Definieren Ihrer Anwendung mit mehreren Containern mit docker-compose.yml
description: Festlegen der Zusammensetzung von Microservices für eine Anwendung mit mehreren Containern mit „docker-compose.yml“
ms.date: 01/30/2020
ms.openlocfilehash: c375d328ab9064315682fab91cb5e49e9a384b56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682665"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>Definieren Ihrer Anwendung mit mehreren Containern mit docker-compose.yml

In diesem Leitfaden wurde die Datei [docker-compose.yml](https://docs.docker.com/compose/compose-file/) in Abschnitt [Schritt 4: Definieren Ihrer Dienste beim Erstellen einer Docker-Anwendung mit mehreren Containern in docker-compose.yml](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application) eingeführt. Es gibt jedoch weitere Möglichkeiten, die docker-compose-Dateien zu verwenden, ausführlicherer betrachtet werden sollten.

Beispielsweise können Sie explizit beschreiben, wie Sie Ihre Anwendung mit mehreren Containern in der docker-compose.yml-Datei bereitstellen möchten. Optional können Sie auch beschreiben, wie Sie Ihre benutzerdefinierten Docker-Images erstellen werden. (Benutzerdefinierte Docker-Images können ebenso mit der Docker-CLI erstellt werden.)

Im Grunde genommen definieren Sie jeden der Container, den Sie bereitstellen möchten, und dazu noch bestimmte Eigenschaften für jede Containerbereitstellung. Sobald Sie über eine Datei mit der Beschreibung der Bereitstellung von mehreren Containern verfügen, können Sie die gesamte Projektmappe in einer einzelnen Aktion, die von dem CLI-Befehl [docker-compose up](https://docs.docker.com/compose/overview/) orchestriert wird, bereitstellen, oder Sie können diese transparent von Visual Studio bereitstellen. Andernfalls müssen Sie die Docker-CLI verwenden, um die Container nacheinander in mehreren Schritten bereitzustellen, indem Sie den Befehl `docker run` über die Befehlszeile verwenden. Daher muss jeder in der Datei „docker-compose.yml“ definierte Dienst genau ein Image oder einen Build definieren. Andere Schlüssel sind optional und analog zu ihren Gegenstücken von `docker run` aus der Befehlszeile.

Der folgende YAML-Code ist die Definition einer möglichen globalen aber einzelnen docker-compose.yml-Datei für das eShopOnContainers-Beispiel. Dies ist nicht die tatsächliche docker-compose-Datei von eShopOnContainers. Stattdessen handelt es sich um eine vereinfachte und konsolidierte Version in einer einzelnen Datei, die zum Arbeiten mit docker-compose-Datei nicht die beste Lösung ist. Dies wird im Verlauf des Artikels erläutert.

```yml
version: '3.4'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog-api
      - OrderingUrl=http://ordering-api
      - BasketUrl=http://basket-api
    ports:
      - "5100:80"
    depends_on:
      - catalog-api
      - ordering-api
      - basket-api

  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  ordering-api:
    image: eshop/ordering-api
    environment:
      - ConnectionString=Server=sqldata;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  basket-api:
    image: eshop/basket-api
    environment:
      - ConnectionString=sqldata
    ports:
      - "5103:80"
    depends_on:
      - sqldata

  sqldata:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basketdata:
    image: redis
```

Der Stammschlüssel in dieser Datei ist „services“. Unter diesem Schlüssel definieren Sie die Dienste, die Sie bereitstellen und ausführen möchten, wenn Sie den Befehl `docker-compose up` ausführen oder wenn Sie die Bereitstellung von Visual Studio aus mithilfe dieser docker-compose.yml-Datei durchführen. In diesem Fall sind wie in der folgenden Tabelle beschrieben mehrere Dienste für die docker-compose.yml-Datei definiert.

| Dienstname | Beschreibung |
|--------------|-------------|
| webmvc       | Container, einschließlich der ASP.NET Core-MVC-Anwendung, die die Microservices der serverseitigen Programmiersprache C\# verwendet|
| catalog-api  | Container, einschließlich des Katalogmicroservice für die ASP.NET Core-Web-API |
| ordering-api | Container, einschließlich des Microservice für Bestellungen für die ASP.NET Core-Web-API |
| sqldata     | Container unter SQL Server für Linux, einschließlich der Microservicesdatenbanken |
| basket-api   | Container mit dem Warenkorbmicroservice für die ASP.NET Core-Web-API |
| basketdata  | Container, der den REDIS-Cachedienst mit der basket-Datenbank als REDIS-Cache ausführt |

### <a name="a-simple-web-service-api-container"></a>Ein einfacher Container für die Webdienst-API

Der Containermicroservice „catalog.api“ hat mit Fokus auf einen einzelnen Container eine klare Definition:

```yml
  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata
```

Dieser Containerdienst verfügt über die folgende grundlegende Konfiguration:

- Er basiert auf dem benutzerdefinierten Image **eshop/catalog-api**. Der Einfachheit halber gibt es keine „build: key“-Einstellung in der Datei. Das bedeutet, dass das Image zuvor erstellt worden (mit „docker build“) oder aus einer beliebigen Docker-Registrierung heruntergeladen sein muss (mit dem docker pull-Befehl).

- Er definiert die Umgebungsvariable mit der Bezeichnung „ConnectionString“ mit der Verbindungszeichenfolge, die von Entity Framework für den Zugriff auf die SQL Server-Instanz, die das Katalogdatenmodell enthält, verwendet werden soll. In diesem Fall enthält der gleicher SQL Server-Container mehrere Datenbanken. Aus diesem Grund benötigen Sie weniger Arbeitsspeicher in Ihrem Entwicklungscomputer für Docker. Allerdings können Sie auch einen SQL Server-Container für jede Microservicedatenbank bereitstellen.

- Der SQL Server-Name lautet **sqldata**. Dies ist derselbe Name, der für den Container verwendet wird, der die SQL Server-Instanz für Linux ausführt. Das ist praktisch, denn die Möglichkeit, diese Namensauflösung (intern für den Docker-Host) zu verwenden, löst die Netzwerkadresse auf. Sie müssen die interne IP-Adresse für die Container also nicht kennen, auf die Sie von anderen Container aus zugreifen.

Da die Verbindungszeichenfolge von einer Umgebungsvariable definiert ist, können Sie die Variable über einen anderen Mechanismus und zu einer anderen Zeit festlegen. Sie können beispielsweise eine andere Verbindungszeichenfolge festlegen, wenn Sie eine Bereitstellung zur Produktion in den finalen Hosts durchführen, oder von Ihren CI/CD-Pipelines in Azure DevOps Services bzw. von Ihrem bevorzugten DevOps-System aus.

- Er stellt Port 80 für den internen Zugriff auf den Dienst **catalog.api** im Docker-Host zur Verfügung. Der Host ist derzeit eine Linux-VM, da er auf einem Docker-Image für Linux basiert. Sie können den Container jedoch auch so konfigurieren, dass er stattdessen auf einem Windows-Image ausgeführt wird.

- Er leitet den zur Verfügung gestellten Port 80 auf dem Container zu Port 5101 auf dem Docker-Hostcomputer (der Linux-VM) weiter.

- Er verknüpft den Webdienst mit dem Dienst **sqldata** (der SQL Server-Instanz für die Linux-Datenbank, die in einem Container ausgeführt wird). Bei Angabe dieser Abhängigkeit wird der Container „catalog-api“ nicht gestartet, bis der Container „sqldata“ gestartet wird. Dies ist wichtig, da „catalog-api“ verlangt, dass zunächst die SQL Server-Datenbank verfügbar ist und ausgeführt wird. Diese Art der Containerabhängigkeit reicht jedoch in vielen Fällen nicht aus, da Docker nur auf Containerebene prüft. Manchmal ist der Dienst (in diesem Fall SQL Server) womöglich noch immer nicht verfügbar, deshalb ist es ratsam, die Wiederholungsversuchslogik mit exponentiellem Backoff in Ihren Clientmicroservices zu implementieren. Auf diese Weise ist die Anwendung noch immer widerstandsfähig, wenn ein Abhängigkeitscontainer für kurze Zeit nicht bereit ist.

- Er ist so konfiguriert, dass er Zugriff auf externe Server zulässt: Die Einstellung „extra\_hosts“ ermöglicht es Ihnen, auf externe Server oder Computer außerhalb des Docker-Hosts zuzugreifen (das heißt, außerhalb der standardmäßigen Linux-VM, die einen Docker-Entwicklungshost darstellt), z. B. auf eine lokale SQL Server-Instanz auf Ihrem Entwicklungs-PC.

Es sind auch andere, leistungsstärkere `docker-compose.yml`-Einstellungen verfügbar, die in den folgenden Abschnitten erläutert werden.

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>Verwenden von docker-compose-Dateien für mehrere Umgebungen

Die `docker-compose.*.yml`-Dateien sind Definitionsdateien und können von mehreren Infrastrukturen verwendet werden, die dieses Format verwenden können. Das einfachste Tool ist der Befehl „docker-compose“.

Aus diesem Grund können Sie durch die Verwendung des „docker-compose“-Befehls auf die folgenden Hauptszenarios abzielen.

#### <a name="development-environments"></a>Entwicklungsumgebungen

Wenn Sie Anwendungen entwickeln, ist es wichtig, dass Sie eine Anwendung in einer isolierten Entwicklungsumgebung ausführen können. Sie können diese Umgebung mithilfe des CLI-Befehls „docker-compose“ oder in Visual Studio erstellen. Visual Studio verwendet „docker-compose“ im Hintergrund.

Die Datei „docker-compose.yml“ ermöglicht Ihnen, alle Dienstabhängigkeiten Ihrer Anwendung (andere Dienste, Caches, Datenbanken, Warteschlangen usw.) zu konfigurieren und zu dokumentieren. Mithilfe des CLI-Befehls „docker-compose“ können Sie einen oder mehrere Container für jede Abhängigkeit mit einem einzelnen Befehl (docker-compose up) erstellen und starten.

Die docker-compose.yml-Dateien sind Konfigurationsdateien, die von der Docker-Engine interpretiert werden, sie dienen aber auch als praktische Dokumentationsdateien über den Aufbau Ihrer Anwendung mit mehreren Container.

#### <a name="testing-environments"></a>Testumgebungen

Ein wichtiger Teil des Prozesses jeder fortlaufenden Bereitstellung (Continuous Deployment, CD) oder fortlaufenden Integration (Continuous Integration, CI) sind die Komponententests und Integrationstests. Diese automatisierten Tests erfordern eine isolierte Umgebung, damit sie nicht von den Benutzern oder anderen Änderungen in den Daten der Anwendung betroffen sind.

Mit Docker Compose können Sie diese isolierte Umgebung sehr einfach mit einigen wenigen Befehlen an der Eingabeaufforderung oder in Skripts erstellen und zerstören. Hier einige Beispiele für diese Befehle:

```console
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml up -d
./run_unit_tests
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml down
```

#### <a name="production-deployments"></a>Produktionsbereitstellungen

Sie können Compose auch zum Bereitstellen auf eine Docker-Remote-Engine verwenden. Ein typischer Fall hier ist die Bereitstellung auf eine einzelne Docker-Hostinstanz (z.B. eine Produktions-VM oder ein Server, der mit einem [Docker-Computer](https://docs.docker.com/machine/overview/) bereitgestellt wird).

Wenn Sie einen anderen Orchestrator verwenden (Azure Service Fabric, Kubernetes usw.), müssen Sie möglicherweise Setup- und Metadatenkonfigurationseinstellungen wie jene in „docker-compose.yml“ hinzufügen, jedoch in dem Format, das vom anderen Orchestrator verlangt wird.

In jedem Fall ist „docker-compose“ ein nützliches Tool und Metadatenformat für die Entwicklung, das Testen und für Produktionsworkflows, obwohl der Produktionsworkflow je nach verwendetem Orchestrator variieren kann.

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>Verwenden mehrerer docker-compose-Dateien zum Verarbeiten mehrerer Umgebungen

Wenn unterschiedliche Umgebungen angezielt werden sollen, verwenden Sie mehrere Compose-Dateien. Dadurch können Sie mehrere Konfigurationsvarianten auf Grundlage der Umgebung erstellen.

#### <a name="overriding-the-base-docker-compose-file"></a>Überschreiben der docker-compose-Basisdatei

Sie können eine einzelne docker-compose-Datei verwenden. Dies wird in den vorherigen Abschnitten in vereinfachten Beispielen dargestellt. Diese Verfahren sind jedoch für die meisten Anwendungen nicht empfehlenswert.

Standardmäßig liest Compose zwei Dateien: eine docker-compose.yml- und eine optionale docker-compose.override.yml-Datei. Wenn Sie Visual Studio verwenden und die Docker-Unterstützung aktivieren, erstellt Visual Studio wie in Abbildung 6-11 dargestellt eine zusätzliche „docker-compose.vs.debug.g.yml“-Datei zum Debuggen der Anwendung. Sie können sich diese Datei im Ordner obj\\Docker\\ im Projektmappenhauptordner ansehen.

![Dateien in einem Docker Compose-Projekt](./media/multi-container-applications-docker-compose/docker-compose-file-visual-studio.png)

**Abbildung 6-11**. docker-compose-Dateien in Visual Studio 2019

**docker-compose**-Projektdateistruktur:

- *.dockerignore*: wird zum Ignorieren von Dateien verwendet.
- *docker-compose.yml*: wird zum Verfassen von Microservices verwendet.
- *docker-compose.override.yml*: wird zum Konfigurieren der Microservices-Umgebung verwendet.

Sie können die docker-compose-Dateien mit jedem beliebigen Editor bearbeiten, z.B. Visual Studio Code oder Sublime, und die Anwendung mit dem Befehl „docker-compose up“ ausführen.

Gemäß der Konvention enthält die docker-compose.yml-Datei Ihre Basiskonfiguration sowie andere statische Einstellungen. Das bedeutet, dass die Dienstkonfiguration nicht in Abhängigkeit von der Entwicklungsumgebung geändert werden muss.

Die docker-compose.override.yml-Datei enthält – wie der Name vermuten lässt – Konfigurationsdateien, die die Basiskonfiguration außer Kraft setzen, also z.B. die Konfiguration, die von der Bereitstellungsumgebung abhängt. Sie können auch mehrere Außerkraftsetzungsdateien mit unterschiedlichem Namen besitzen. Die Außerkraftsetzungsdateien enthalten in der Regel zusätzliche Informationen, die von der Anwendung benötigt werden, die jedoch für eine Umgebung oder eine Bereitstellung spezifisch sind.

#### <a name="targeting-multiple-environments"></a>Anzielen mehrerer Umgebungen

Ein typischer Anwendungsfall ist, wenn Sie mehrere Compose-Dateien definieren, damit Sie auf mehrere Umgebungen abzielen können, z.B. auf die Produktion, das Staging, CI oder die Entwicklung. Sie können Ihre Compose-Konfiguration wie in Abbildung 6-12 dargestellt in mehrere Dateien aufteilen, um diese Unterschiede zu unterstützen.

![Diagramm mit drei Docker Compose-Dateien, die zum Überschreiben der Basisdatei festgelegt sind.](./media/multi-container-applications-docker-compose/multiple-docker-compose-files-override-base.png)

**Abbildung 6-12**. Mehrere docker-compose-Dateien, die Werte in der docker-compose.yml-Basisdatei überschreiben

Sie können mehrere docker.compose*.yml-Dateien kombinieren, wenn verschiedene Umgebungen abgedeckt werden müssen. Sie beginnen mit der docker-compose.yml-Basisdatei. Diese Basisdatei enthält die Basis- oder statischen Konfigurationseinstellungen, die sich nicht aufgrund der Umgebung ändern. Beispielsweise enthält die App „eShopOnContainers“ über die folgende Datei „docker-compose.yml“ (zur Vereinfachung mit weniger Diensten) als Basisdatei.

```yml
#docker-compose.yml (Base)
version: '3.4'
services:
  basket-api:
    image: eshop/basket-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Basket/Basket.API/Dockerfile
    depends_on:
      - basketdata
      - identity-api
      - rabbitmq

  catalog-api:
    image: eshop/catalog-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Catalog/Catalog.API/Dockerfile
    depends_on:
      - sqldata
      - rabbitmq

  marketing-api:
    image: eshop/marketing-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Marketing/Marketing.API/Dockerfile
    depends_on:
      - sqldata
      - nosqldata
      - identity-api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Web/WebMVC/Dockerfile
    depends_on:
      - catalog-api
      - ordering-api
      - identity-api
      - basket-api
      - marketing-api

  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest

  nosqldata:
    image: mongo

  basketdata:
    image: redis

  rabbitmq:
    image: rabbitmq:3-management

```

Die Werte in der docker-compose.yml-Basisdatei dürfen sich aufgrund der unterschiedlichen Zielbereitstellungsumgebungen nicht ändern.

Wenn Sie den Fokus z.B. auf die webmvc-Dienstdefinition legen, können Sie sehen, dass diese Information unabhängig von der Zielumgebung mehr oder weniger gleich bleibt. Sie verfügen über folgende Informationen:

- Der Dienstname: webmvc.

- Das benutzerdefinierte Image des Containers: eshop/webmvc.

- Der Befehl, mit dem das benutzerdefinierte Docker-Image erstellt wird, und der angibt, welche Docker-Datei verwendet werden soll.

- Abhängigkeiten auf anderen Diensten, damit dieser Container nicht gestartet wird, bevor die anderen Abhängigkeitscontainer nicht gestartet wurden.

Sie verfügen über zusätzliche Konfigurationen. Der wichtigste Punkt ist jedoch, dass Sie in der docker-compose.yml-Basisdatei nur die Informationen festlegen möchten, die in mehreren Umgebungen verwendet werden. Sie müssen in der docker-compose.override.yml-Datei,oder in ähnlichen Dateien für die Produktion oder das Staging, eine Konfiguration platzieren, die für jede Umgebung spezifisch ist.

Normalerweise wird die docker-compose.override.yml- Datei wie im folgenden Beispiel von eShopOnContainers dargestellt für die Entwicklungsumgebung verwendet:

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3.4'

services:
# Simplified number of services here:

  basket-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basketdata}
      - identityUrl=http://identity-api
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - AzureServiceBusEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}

    ports:
      - "5103:80"

  catalog-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5202/api/v1/catalog/items/[0]/pic/}
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_CATALOG_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_CATALOG_KEY}
      - UseCustomizationData=True
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
    ports:
      - "5101:80"

  marketing-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosqldata}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - identityUrl=http://identity-api
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - CampaignDetailFunctionUri=${ESHOP_AZUREFUNC_CAMPAIGN_DETAILS_URI}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_MARKETING_URL:-http://localhost:5110/api/v1/campaigns/[0]/pic/}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_MARKETING_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_MARKETING_KEY}
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5110:80"

  webmvc:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - PurchaseUrl=http://webshoppingapigw
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://webmarketingapigw
      - CatalogUrlHC=http://catalog-api/hc
      - OrderingUrlHC=http://ordering-api/hc
      - IdentityUrlHC=http://identity-api/hc
      - BasketUrlHC=http://basket-api/hc
      - MarketingUrlHC=http://marketing-api/hc
      - PaymentUrlHC=http://payment-api/hc
      - SignalrHubUrl=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5202
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sqldata:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosqldata:
    ports:
      - "27017:27017"
  basketdata:
    ports:
      - "6379:6379"
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

In diesem Beispiel macht die Konfiguration zur Entwicklungsaußerkraftsetzung dem Host einige Ports verfügbar, definiert Umgebungsvariablen mit Umleitungs-URLs und gibt Verbindungszeichenfolgen für die Entwicklungsumgebung an. Diese Einstellungen sind alle nur für die Entwicklungsumgebung gedacht.

Wenn Sie `docker-compose up` ausführen (oder von Visual Studio aus starten), liest der Befehl die Außerkraftsetzungen automatisch so, als ob er beide Dateien zusammenführen würde.

Angenommen, Sie möchten eine andere Compose-Datei mit anderen Konfigurationswerten, Ports oder Verbindungszeichenfolgen für die Produktionsumgebung verwenden. Sie können eine weitere Außerkraftsetzungsdatei (z.B. eine Datei namens `docker-compose.prod.yml`) mit verschiedenen Einstellungen und Umgebungsvariablen erstellen. Diese Datei kann in einem anderen Git-Repository oder von einem anderen Team verwaltet und gesichert werden.

#### <a name="how-to-deploy-with-a-specific-override-file"></a>Durchführen einer Bereitstellung mit einer bestimmten Außerkraftsetzungsdatei

Um mehrere Außerkraftsetzungsdateien oder eine Außerkraftsetzungsdatei mit einem anderen Namen zu verwenden, können Sie die Option „-f“ mit dem „docker-compose“-Befehl verwenden und die Dateien angeben. Erstellen Sie Mergedateien in der Reihenfolge, in der sie in der Befehlszeile angegeben sind. Im folgenden Beispiel sehen Sie, wie eine Bereitstellung mit Außerkraftsetzungsdateien durchgeführt wird.

```console
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>Verwenden von Umgebungsvariablen in docker-compose-Dateien

Es ist besonders in Produktionsumgebungen nützlich, Konfigurationsinformationen aus Umgebungsvariablen abrufen zu können. Dies wurde in vorherigen Beispielen bereits dargestellt. Sie können in Ihren docker-compose-Dateien mithilfe der Syntax ${MY\_VAR} auf eine Umgebungsvariable verweisen. Die folgende Zeile aus einer docker-compose.prod.yml-Datei zeigt, wie Sie auf den Wert einer Umgebungsvariable verweisen.

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

Umgebungsvariablen werden unterschiedlich erstellt und initialisiert. Dies hängt von Ihrer Hostumgebung (Linux, Windows, Cloud-Cluster usw.) ab. Eine geeignete Herangehensweise ist die Verwendung einer ENV-Datei. Die docker-compose-Dateien unterstützen das Deklarieren von Standardumgebungsvariablen in der ENV-Datei. Diese Werte für die Umgebungsvariablen sind die Standardwerte. Sie können jedoch von den Werten überschrieben werden, die Sie möglicherweise in jeder Umgebung (Hostbetriebssystem oder Umgebungsvariablen aus Ihrem Cluster) definiert haben. Sie fügen die ENV-Datei in den Ordner ein, aus dem der docker-compose-Befehl ausgeführt wird.

Das folgende Beispiel zeigt eine ENV-Datei wie die [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env)-Datei für die eShopOnContainers-Anwendung.

```sh
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Docker-compose erwartet, dass jede Zeile in einer ENV-Datei das Format \<variable\>=\<value\> aufweist.

Die in der Laufzeitumgebung festgelegten Werte setzen immer die in der ENV-Datei definierten Werte außer Kraft. Auf ähnliche Weise setzen Werte, die über Befehlszeilenargumente übergeben werden, die in der ENV-Datei festgelegten Standardwerte außer Kraft.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Overview of Docker Compose (Übersicht über Docker Compose)**  \
    <https://docs.docker.com/compose/overview/>

- **Multiple Compose files (Mehrere Compose-Dateien)**  \
    [https://docs.docker.com/compose/extends/\#multiple-compose-files](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>Erstellen von optimierten Docker-Images für ASP.NET Core

Wenn Sie Docker und .NET Core in Internetquellen untersuchen, finden Sie Docker-Dateien, die die Einfachheit der Erstellung eines Docker-Images darstellen, indem die Quelle ganz einfach in einen Container kopiert wird. In diesen Beispielen wird empfohlen, dass Sie mithilfe einer einfachen Konfiguration ein Docker-Image besitzen, das die Umgebung zusammen mit Ihrer Anwendung enthält. Zu diesem Zweck wird im folgenden Beispiel eine einfache Docker-Datei gezeigt.

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:3.1
WORKDIR /app
ENV ASPNETCORE_URLS http://+:80
EXPOSE 80
COPY . .
RUN dotnet restore
ENTRYPOINT ["dotnet", "run"]
```

Eine Dockerfile-Datei wie diese funktioniert. Sie können jedoch im Wesentlichen Ihre Images optimieren, besonders bei Ihren Produktionsimages funktioniert das gut.

Sie starten im Container- und im Microservicesmodell ständig Container. Es wird kein inaktiver Container neu gestartet, wenn ein Container ganz normal verwendet wird, da der Container verwerfbar ist. Orchestratoren (z.B. Kubernetes und Azure Service Fabric) erstellen nur neue Instanzen von Images. Das bedeutet, dass Sie eine Optimierung durch Vorkompilierung der Anwendung vornehmen müssten, wenn diese erstellt wird, damit der Instanziierungsprozess schneller wird. Wenn der Container gestartet wird, sollte er für die Ausführung bereit sein. Führen Sie keine Wiederherstellung oder Kompilierung zur Laufzeit mit den CLI-Befehlen `dotnet restore` und `dotnet build` aus, wie es in einigen Blogbeiträgen zu .NET Core und Docker getan wird.

Das .NET-Team hat sich große Mühe gegeben, damit .NET Core und ASP.NET Core ein containeroptimiertes Framework ist. .NET Core ist nicht nur ein einfaches Framework mit geringem Speicherbedarf, sondern das Team hat sich auch auf optimierte Docker-Images für drei Hauptszenarios konzentriert und diese ab Version 2.1 in der Docker-Hub-Registrierung unter *dotnet/core* veröffentlicht:

1. **Entwicklung:** Die schnelle Iteration und das Debuggen von Änderungen hat Vorrang. Die Größe ist zweitrangig.

2. **Build:** Das Kompilieren der Anwendung hat Vorrang. Außerdem enthält das Image Binärdateien und andere Abhängigkeiten, um die Binärdateien zu optimieren.

3. **Produktion:** Das schnelle Bereitstellen und Starten von Containern hat Vorrang. Die Images sind deshalb auf Binärdateien und Inhalte beschränkt, die zum Ausführen der Anwendung erforderlich sind.

Das .NET-Team stellt vier grundlegende Varianten unter [dotnet/core](https://hub.docker.com/_/microsoft-dotnet/) (in Docker Hub) bereit:

1. **sdk:** für Entwicklungs- und Buildszenarien
1. **aspnet**: für ASP.NET-Produktionsszenarien
1. **runtime**: für .NET-Produktionsszenarien
1. **runtime-deps:** für Produktionsszenarios mit [eigenständigen Anwendungen](../../../core/deploying/index.md#publish-self-contained)

Für einen schnelleren Start setzen Runtimeimages auch automatisch aspnetcore\_urls auf Port 80 und verwenden Ngen, um einen nativen Imagecache von Assemblys zu erstellen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Building Optimized Docker Images with ASP.NET Core (Erstellen von optimierten Docker-Images mit ASP.NET Core)**  
  <https://docs.microsoft.com/archive/blogs/stevelasker/building-optimized-docker-images-with-asp-net-core>

- **Erstellen von Docker-Images für .NET Core-Anwendungen**  
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

> [!div class="step-by-step"]
> [Zurück](data-driven-crud-microservice.md)
> [Weiter](database-server-container.md)
