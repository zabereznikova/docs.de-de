---
title: Definieren Ihrer Anwendung mit mehreren Containern mit docker-compose.yml
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Definieren Ihrer Anwendung mit mehreren Containern mit docker-compose.yml
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/30/2017
ms.openlocfilehash: ded2e5399938be25005776963b0310b6a49d0353
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>Definieren Ihrer Anwendung mit mehreren Containern mit docker-compose.yml 

In diesem Leitfaden wurde die Datei [docker-compose.yml](https://docs.docker.com/compose/compose-file/) in Abschnitt [Schritt 4: Definieren Ihrer Dienste beim Erstellen einer Docker-Anwendung mit mehreren Containern in docker-compose.yml](#step4_define_svcs_in_docker_compose_yml) eingeführt. Es gibt jedoch weitere Möglichkeiten, die docker-compose-Dateien zu verwenden, ausführlicherer betrachtet werden sollten.

Beispielsweise können Sie explizit beschreiben, wie Sie Ihre Anwendung mit mehreren Containern in der docker-compose.yml-Datei bereitstellen möchten. Optional können Sie auch beschreiben, wie Sie Ihre benutzerdefinierten Docker-Images erstellen werden. (Benutzerdefinierte Docker-Images können ebenso mit der Docker-CLI erstellt werden.)

Im Grunde genommen definieren Sie jeden der Container, den Sie bereitstellen möchten, und dazu noch bestimmte Eigenschaften für jede Containerbereitstellung. Sobald Sie über eine Datei mit der Beschreibung der Bereitstellung von mehreren Containern verfügen, können Sie die gesamte Projektmappe in einer einzelnen Aktion, die von dem CLI-Befehl [docker-compose up](https://docs.docker.com/compose/overview/) orchestriert wird, bereitstellen, oder Sie können diese transparent von Visual Studio bereitstellen. Andernfalls müssen Sie die Docker-CLI verwenden, um die Container nacheinander in mehreren Schritten bereitzustellen, indem Sie den Befehl „docker run“ über die Befehlszeile verwenden. Daher muss jeder in der Datei „docker-compose.yml“ definierte Dienst genau ein Image oder einen Build definieren. Andere Schlüssel sind optional und analog zu ihren Gegenstücken von „docker run“ aus der Befehlszeile.

Der folgende YAML-Code ist die Definition einer möglichen globalen aber einzelnen docker-compose.yml-Datei für das eShopOnContainers-Beispiel. Dies ist nicht die tatsächliche docker-compose-Datei von eShopOnContainers. Stattdessen handelt es sich um eine vereinfachte und konsolidierte Version in einer einzelnen Datei, die zum Arbeiten mit docker-compose-Datei nicht die beste Lösung ist. Dies wird im Verlauf des Artikels erläutert.

```yml
version: '2'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
    ports:
      - "5100:80"
    depends_on:
      - catalog.api
      - ordering.api
      - basket.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  basket.api:
    image: eshop/basket.api
    environment:
      - ConnectionString=sql.data
    ports:
      - "5103:80"
    depends_on:
      - sql.data

  sql.data:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basket.data:
    image: redis
```

Der Stammschlüssel in dieser Datei ist „services“. Unter diesem Schlüssel definieren Sie die Dienste, die Sie bereitstellen und ausführen möchten, wenn Sie den Befehl „docker-compose up“ ausführen, oder wenn Sie von Visual Studio aus mithilfe dieser docker-compose.yml-Datei bereitstellen. In diesem Fall sind wie in der folgenden Liste beschrieben mehrere Dienste für die docker-compose.yml-Datei definiert.

-   webmvc-Container, einschließlich der ASP.NET Core-MVC-Anwendung, die die Microservices der serverseitigen Programmiersprache C\# verwendet

-   catalog.api-Container, einschließlich dem Katalogmicroservice für die ASP.NET Core-Web-API

-   ordering.api-Container, einschließlich dem Microservice für Bestellungen für die ASP.NET Core-Web-API

-   sql.data-Container unter SQL Server für Linux, einschließlich der Microservicesdatenbanken

-   basket.api-Container mit dem Microservice von ASP.NET Core-Web-API für Basket

-   basket.data-Container unter dem REDIS-Cachedienst mit der basket-Datenbank als REDIS-Cache

### <a name="a-simple-web-service-api-container"></a>Ein einfacher Container für die Webdienst-API

Der Containermicroservice „catalog.api“ hat mit Fokus auf einen einzelnen Container eine klare Definition:

```yml
  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=catalog.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data
```

Dieser Containerdienst verfügt über die folgende grundlegende Konfiguration:

-   Er basiert auf dem benutzerdefinierten „eshop/catalog.api“-Image. Der Einfachheit halber gibt es keine „build: key“-Einstellung in der Datei. Das bedeutet, dass das Image zuvor erstellt worden (mit „docker build“) oder aus einer beliebigen Docker-Registrierung heruntergeladen sein muss (mit dem docker pull-Befehl).

-   Er definiert die Umgebungsvariable mit der Bezeichnung „ConnectionString“ mit der Verbindungszeichenfolge, die von Entity Framework für den Zugriff auf die SQL Server-Instanz, die das Katalogdatenmodell enthält, verwendet werden soll. In diesem Fall enthält der gleicher SQL Server-Container mehrere Datenbanken. Aus diesem Grund benötigen Sie weniger Arbeitsspeicher in Ihrem Entwicklungscomputer für Docker. Allerdings können Sie auch einen SQL Server-Container für jede Microservicedatenbank bereitstellen.

-   Der SQL Server-Name lautet „sql.data“. Dies ist derselbe Name, der für den Container verwendet wird, der die SQL Server-Instanz für Linux ausführt. Das ist wirklich praktisch, denn die Möglichkeit, diese Namensauflösung (intern für den Docker-Host) zu verwenden, löst die Netzwerkadresse auf. Sie müssen die interne IP-Adresse für die Container also nicht kennen, auf die Sie von anderen Container aus zugreifen.

Da die Verbindungszeichenfolge von einer Umgebungsvariable definiert ist, können Sie die Variable über einen anderen Mechanismus und zu einer anderen Zeit festlegen. Sie können beispielsweise eine andere Verbindungszeichenfolge festlegen, wenn Sie eine Bereitstellung zur Produktion in den finalen Hosts durchführen, oder von Ihren CI/CD-Pipelines in VSTS bzw. von Ihrem bevorzugten DevOps-System aus.

-   Er stellt Port 80 für den internen Zugriff auf den catalog.api-Dienst im Docker-Host zur Verfügung. Der Host ist derzeit eine Linux-VM, da er auf einem Docker-Image für Linux basiert. Sie können den Container jedoch auch so konfigurieren, dass er stattdessen auf einem Windows-Image ausgeführt wird.

-   Er leitet den zur Verfügung gestellten Port 80 auf dem Container zu Port 5101 auf dem Docker-Hostcomputer (der Linux-VM) weiter.

-   Er verknüpft den Webdienst mit dem sql.data-Dienst (der SQL Server-Instanz für die Linux-Datenbank, die in einem Container ausgeführt wird). Bei Angabe dieser Abhängigkeit wird der catalog.api-Container nicht gestartet, bis der sql.data-Container gestartet wird. Dies ist wichtig, da catalog.api erfordert, dass zunächst die SQL Server-Datenbank verfügbar ist und ausgeführt wird. Diese Art der Containerabhängigkeit reicht jedoch in vielen Fällen nicht aus, da Docker nur auf Containerebene prüft. Manchmal ist der Dienst (in diesem Fall SQL Server) womöglich noch immer nicht verfügbar, deshalb ist es ratsam, die Wiederholungsversuchslogik mit exponentiellem Backoff in Ihren Clientmicroservices zu implementieren. Auf diese Weise ist die Anwendung noch immer widerstandsfähig, wenn ein Abhängigkeitscontainer für kurze Zeit nicht bereit ist.

-   Er ist so konfiguriert, dass er Zugriff auf externe Server zulässt: Die Einstellung „extra\_hosts“ ermöglicht Ihnen, auf externe Server oder Computer außerhalb des Docker-Hosts zuzugreifen (das heißt, außerhalb der standardmäßigen Linux-VM, die einen Docker-Entwicklungshost darstellt), z.B. auf eine lokalen SQL Server-Instanz auf Ihrem Entwicklungs-PC.

Es sind auch andere, leistungsstärkere docker-compose.yml-Einstellungen verfügbar, die in den folgenden Abschnitten erläutert werden.

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>Verwenden von docker-compose-Dateien für mehrere Umgebungen

Die docker-compose.yml-Dateien sind Definitionsdateien und können von mehreren Infrastrukturen verwendet werden, die dieses Format verwenden können. Das einfachste Tool ist der „docker-compose“-Befehl. Andere Tools wie Orchestratoren, z.B Docker Swarm, können diese Datei ebenso verwenden.

Aus diesem Grund können Sie durch die Verwendung des „docker-compose“-Befehls auf die folgenden Hauptszenarios abzielen.

#### <a name="development-environments"></a>Entwicklungsumgebungen

Wenn Sie Anwendungen entwickeln, ist es wichtig, dass Sie eine Anwendung in einer isolierten Entwicklungsumgebung ausführen können. Sie können den CLI-Befehl „docker-compose“ verwenden, um diese Umgebung zu erstellen, oder Visual Studio im Hintergrund ausführen, was „docker-compose“ verwendet.

Die docker-compose.yml-Datei ermöglicht Ihnen, alle Dienstabhängigkeiten Ihrer Anwendung (andere Dienste, Caches, Datenbanken, Warteschlangen usw.) zu konfigurieren und zu dokumentieren. Mithilfe des CLI-Befehls „docker-compose“ können Sie einen oder mehrere Container für jede Abhängigkeit mit einem einzelnen Befehl (docker-compose up) erstellen und starten.

Die docker-compose.yml-Dateien sind Konfigurationsdateien, die von der Docker-Engine interpretiert werden, sie dienen aber auch als praktische Dokumentationsdateien über den Aufbau Ihrer Anwendung mit mehreren Container.

#### <a name="testing-environments"></a>Testumgebungen

Ein wichtiger Teil des Prozesses jeder fortlaufenden Bereitstellung (Continuous Deployment, CD) oder fortlaufenden Integration (Continuous Integration, CI) sind die Komponententests und Integrationstests. Diese automatisierten Tests erfordern eine isolierte Umgebung, damit sie nicht von den Benutzern oder anderen Änderungen in den Daten der Anwendung betroffen sind.

Mit Docker Compose können Sie diese isolierte Umgebung sehr einfach mithilfe von ein paar Befehlen aus Ihrer Eingabeaufforderung oder Skripts, die nachfolgend aufgeführt sind, erstellen und zerstören:

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a>Produktionsbereitstellungen

Sie können Compose auch zum Bereitstellen auf eine Docker-Remote-Engine verwenden. Ein typischer Fall hier ist die Bereitstellung auf eine einzelne Docker-Hostinstanz (z.B. eine Produktions-VM oder ein Server, der mit einem [Docker-Computer](https://docs.docker.com/machine/overview/) bereitgestellt wird). Es kann jedoch auch ein ganzer [Docker Swarm](https://docs.docker.com/swarm/overview/)-Cluster sein, da Cluster auch mit den docker-compose.yml-Dateien kompatibel sind.

Wenn Sie einen anderen Orchestrator verwenden (Azure Service Fabric, Mesos DC/OS, Kubernetes usw.), müssen Sie möglicherweise Setup- und Metadatenkonfigurationseinstellungen (wie jene in docker-compose.yml) hinzufügen, jedoch im Format, das vom anderen Orchestrator verlangt wird.

In jedem Fall ist „docker-compose“ ein nützliches Tool und Metadatenformat für die Entwicklung, das Testen und für Produktionsworkflows, obwohl der Produktionsworkflow je nach verwendetem Orchestrator variieren kann.

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>Verwenden mehrerer docker-compose-Dateien zum Verarbeiten mehrerer Umgebungen

Wenn unterschiedliche Umgebungen angezielt werden sollen, verwenden Sie mehrere Compose-Dateien. Dadurch können Sie mehrere Konfigurationsvarianten auf Grundlage der Umgebung erstellen.

#### <a name="overriding-the-base-docker-compose-file"></a>Überschreiben der docker-compose-Basisdatei

Sie können eine einzelne docker-compose-Datei verwenden. Dies wird in den vorherigen Abschnitten in vereinfachten Beispielen dargestellt. Diese Verfahren sind jedoch für die meisten Anwendungen nicht empfehlenswert.

Standardmäßig liest Compose zwei Dateien: eine docker-compose.yml- und eine optionale docker-compose.override.yml-Datei. Wie in Abbildung 8-11 dargestellt ist, erstellt Visual Studio, wenn Sie Visual Studio verwenden und Docker-Support aktivieren, eine zusätzliche docker-compose.ci.build.yml-Datei für Sie, die Sie aus Ihren CI/CD-Pipelines wie VSTS verwenden können.

![](./media/image12.png)

**Abbildung 8-11**. docker-compose-Dateien in Visual Studio 2017

Sie können die docker-compose-Dateien mit jedem beliebigen Editor bearbeiten, z.B. Visual Studio Code oder Sublime, und die Anwendung mit dem Befehl „docker-compose up“ ausführen.

Gemäß der Konvention enthält die docker-compose.yml-Datei Ihre Basiskonfiguration sowie andere statische Einstellungen. Das bedeutet, dass die Dienstkonfiguration nicht in Abhängigkeit von der Entwicklungsumgebung geändert werden muss.

Die docker-compose.override.yml-Datei enthält – wie der Name vermuten lässt – Konfigurationsdateien, die die Basiskonfiguration außer Kraft setzen, also z.B. die Konfiguration, die von der Bereitstellungsumgebung abhängt. Sie können auch mehrere Außerkraftsetzungsdateien mit unterschiedlichem Namen besitzen. Die Außerkraftsetzungsdateien enthalten in der Regel zusätzliche Informationen, die von der Anwendung benötigt werden, die jedoch für eine Umgebung oder eine Bereitstellung spezifisch sind.

#### <a name="targeting-multiple-environments"></a>Anzielen mehrerer Umgebungen

Ein typischer Anwendungsfall ist, wenn Sie mehrere Compose-Dateien definieren, damit Sie auf mehrere Umgebungen abzielen können, z.B. auf die Produktion, das Staging, CI oder die Entwicklung. Sie können Ihre Compose-Konfiguration wie in Abbildung 8-12 dargestellt in mehrere Dateien aufteilen, um diese Unterschiede zu unterstützen.

![](./media/image13.png)

**Abbildung 8-12**. Mehrere docker-compose-Dateien, die Werte in der docker-compose.yml-Basisdatei überschreiben

Sie beginnen mit der docker-compose.yml-Basisdatei. Diese Basisdatei muss die Basis- oder statischen Konfigurationseinstellungen enthalten, die sich nicht in Abhängigkeit von der Umgebung ändern. Beispielsweise verfügt eShopOnContainers über die folgende docker-compose.yml-Datei als Basisdatei.

```yml
#docker-compose.yml (Base)
version: '3'
services:
  basket.api:
    image: eshop/basket.api:${TAG:-latest}
    build:
      context: ./src/Services/Basket/Basket.API
      dockerfile: Dockerfile    
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api:${TAG:-latest}
    build:
      context: ./src/Services/Catalog/Catalog.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - rabbitmq

  marketing.api:
    image: eshop/marketing.api:${TAG:-latest}
    build:
      context: ./src/Services/Marketing/Marketing.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - nosql.data
      - identity.api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: ./src/Web/WebMVC
      dockerfile: Dockerfile    
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api
      - marketing.api

  sql.data:
    image: microsoft/mssql-server-linux:2017-latest

  nosql.data:
    image: mongo

  basket.data:
    image: redis
      
  rabbitmq:
    image: rabbitmq:3-management

```

Die Werte in der docker-compose.yml-Basisdatei dürfen sich aufgrund der unterschiedlichen Zielbereitstellungsumgebungen nicht ändern.

Wenn Sie den Fokus z.B. auf die webmvc-Dienstdefinition legen, können Sie sehen, dass diese Information unabhängig von der Zielumgebung mehr oder weniger gleich bleibt. Sie verfügen über folgende Informationen:

-   Der Dienstname: webmvc.

-   Das benutzerdefinierte Image des Containers: eshop/webmvc.

-   Der Befehl, mit dem das benutzerdefinierte Docker-Image erstellt wird, und der angibt, welche Docker-Datei verwendet werden soll.

-   Abhängigkeiten auf anderen Diensten, damit dieser Container nicht gestartet wird, bevor die anderen Abhängigkeitscontainer nicht gestartet wurden.

Sie verfügen über zusätzliche Konfigurationen. Der wichtigste Punkt ist jedoch, dass Sie in der docker-compose.yml-Basisdatei nur die Informationen festlegen möchten, die in mehreren Umgebungen verwendet werden. Sie müssen in der docker-compose.override.yml-Datei,oder in ähnlichen Dateien für die Produktion oder das Staging, eine Konfiguration platzieren, die für jede Umgebung spezifisch ist.

Normalerweise wird die docker-compose.override.yml- Datei wie im folgenden Beispiel von eShopOnContainers dargestellt für die Entwicklungsumgebung verwendet:

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3'

services: 
# Simplified number of services here: 
      
  basket.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basket.data}
      - identityUrl=http://identity.api              
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

  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5101/api/v1/catalog/items/[0]/pic/}   
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

  marketing.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}          
      - identityUrl=http://identity.api              
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
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
      - LocationsUrl=http://locations.api
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://marketing.api                                                    
      - CatalogUrlHC=http://catalog.api/hc
      - OrderingUrlHC=http://ordering.api/hc
      - IdentityUrlHC=http://identity.api/hc     
      - BasketUrlHC=http://basket.api/hc
      - MarketingUrlHC=http://marketing.api/hc
      - PaymentUrlHC=http://payment.api/hc
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sql.data:
    environment:
      - MSSQL_SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
      - MSSQL_PID=Developer
    ports:
      - "5433:1433"
  nosql.data:
    ports:
      - "27017:27017"
  basket.data:
    ports:
      - "6379:6379"      
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

In diesem Beispiel macht die Konfiguration zur Entwicklungsaußerkraftsetzung dem Host einige Ports verfügbar, definiert Umgebungsvariablen mit Umleitungs-URLs und gibt Verbindungszeichenfolgen für die Entwicklungsumgebung an. Diese Einstellungen sind alle nur für die Entwicklungsumgebung gedacht.

Wenn Sie `docker-compose up` ausführen (oder von Visual Studio aus starten), liest der Befehl die Außerkraftsetzungen automatisch so, als ob er beide Dateien zusammenführen würde.

Angenommen, Sie möchten eine andere Compose-Datei mit unterschiedlichen Konfigurationswerten, Ports oder Verbindungszeichenfolgen für die Produktionsumgebung verwenden. Sie können eine weitere Außerkraftsetzungsdatei (z.B. eine Datei namens `docker-compose.prod.yml`) mit verschiedenen Einstellungen und Umgebungsvariablen erstellen.  Diese Datei kann in einem anderen Git-Repository oder von einem anderen Team verwaltet und gesichert werden.

#### <a name="how-to-deploy-with-a-specific-override-file"></a>Durchführen einer Bereitstellung mit einer bestimmten Außerkraftsetzungsdatei

Um mehrere Außerkraftsetzungsdateien oder eine Außerkraftsetzungsdatei mit einem anderen Namen zu verwenden, können Sie die Option „-f“ mit dem „docker-compose“-Befehl verwenden und die Dateien angeben. Erstellen Sie Mergedateien in der Reihenfolge, in der sie in der Befehlszeile angegeben sind. Im folgenden Beispiel sehen Sie, wie eine Bereitstellung mit Außerkraftsetzungsdateien durchgeführt wird.

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>Verwenden von Umgebungsvariablen in docker-compose-Dateien

Es ist besonders in Produktionsumgebungen nützlich, Konfigurationsinformationen aus Umgebungsvariablen abrufen zu können. Dies wurde in vorherigen Beispielen bereits dargestellt. Sie verweisen in Ihren docker-compose-Dateien mithilfe der Syntax \${MY\_VAR} auf eine Umgebungsvariable. Die folgende Zeile aus einer docker-compose.prod.yml-Datei zeigt, wie Sie auf den Wert einer Umgebungsvariable verweisen.

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

Umgebungsvariablen werden unterschiedlich erstellt und initialisiert. Dies hängt von Ihrer Hostumgebung (Linux, Windows, Cloud-Cluster usw.) ab. Eine geeignete Herangehensweise ist die Verwendung einer ENV-Datei. Die docker-compose-Dateien unterstützen das Deklarieren von Standardumgebungsvariablen in der ENV-Datei. Diese Werte für die Umgebungsvariablen sind die Standardwerte. Sie können jedoch von den Werten überschrieben werden, die Sie möglicherweise in jeder Umgebung (Hostbetriebssystem oder Umgebungsvariablen aus Ihrem Cluster) definiert haben. Sie fügen die ENV-Datei in den Ordner ein, aus dem der docker-compose-Befehl ausgeführt wird.

Das folgende Beispiel zeigt eine ENV-Datei wie die [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env)-Datei für die eShopOnContainers-Anwendung.

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Docker-compose erwartet, dass jede Zeile in einer ENV-Datei im Format &lt;variable&gt;=&lt;wert&gt; ist.

Beachten Sie, dass die in der Laufzeitumgebung festgelegten Werte immer die innerhalb der ENV-Datei definierten Werte außer Kraft setzen. Auf ähnliche Weise setzen Werte, die über die Befehlsargumente der Befehlszeile übergeben werden, die in der ENV-Datei festgelegten Standardwerte außer Kraft.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Overview of Docker Compose (Übersicht zu Docker Compose)**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)

-   **Mehrere Compose-Dateien**
    [*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>Erstellen von optimierten Docker-Images für ASP.NET Core

Wenn Sie Docker und .NET Core in Internetquellen untersuchen, finden Sie Docker-Dateien, die die Einfachheit der Erstellung eines Docker-Images darstellen, indem die Quelle ganz einfach in einen Container kopiert wird. In diesen Beispielen wird empfohlen, dass Sie mithilfe einer einfachen Konfiguration ein Docker-Image besitzen, das die Umgebung zusammen mit Ihrer Anwendung enthält. Zu diesem Zweck wird im folgenden Beispiel eine einfache Docker-Datei gezeigt.

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

Eine Dockerfile-Datei wie diese funktioniert. Sie können jedoch im Wesentlichen Ihre Images optimieren, besonders bei Ihren Produktionsimages funktioniert das gut.

Sie starten im Container- und im Microservicesmodell ständig Container. Es wird kein inaktiver Container neu gestartet, wenn ein Container ganz normal verwendet wird, da der Container verwerfbar ist. Orchestratoren (z.B. Docker Swarm, Kubernetes DCOS oder Azure Service Fabric) erstellen einfach neue Instanzen eines Images. Das bedeutet, dass Sie eine Optimierung durch Vorkompilierung der Anwendung vornehmen müssten, wenn diese erstellt wird, damit der Instanziierungsprozess schneller wird. Wenn der Container gestartet wird, sollte er für die Ausführung bereit sein. Es sollte keine Wiederherstellung und Kompilierung mithilfe von „dotnet restore“ und „dotnet build“ aus der Dotnet-CLI zur Laufzeit durchgeführt werden, so wie es in vielen Blogbeiträgen über .NET Core und Docker gezeigt wird.

Das .NET-Team hat sich große Mühe gegeben, damit .NET Core und ASP.NET Core ein containeroptimiertes Framework ist. .NET Core ist nicht nur ein einfaches Framework mit wenig Arbeitsspeicherverbrauch, sondern das Team hat sich auf die Startleistung konzentriert und im Vergleich zu den herkömmlichen Images [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) oder [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) einige optimierte Docker-Images erstellt, z.B. das [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)-Image, das auf dem [Docker-Hub](https://hub.docker.com/r/microsoft/aspnetcore/) verfügbar ist. Das [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)-Image bietet die automatische Einstellung von aspnetcore\_urls auf Port 80 den Cache von Assemblys, bevor er mit NGEN.exe zu einem nativen Image kompiliert wurde. Diese Einstellungen ermöglichen einen schnelleren Start.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Building Optimized Docker Images with ASP.NET Core (Erstellen von optimierten Docker-Images mit ASP.NET Core)**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

### <a name="building-the-application-from-a-build-ci-container"></a>Erstellen der Anwendung aus einem Buildcontainer (CI)

Ein weiterer Vorteil von Docker ist, dass Sie Ihre Anwendung wie in Abbildung 8-13 dargestellt aus einem vordefinierten Container erstellen können. So müssen Sie keinen Buildcomputer oder virtuellen Computer erstellen, um Ihre Anwendung zu erstellen. Sie können diesen Buildcontainer verwenden oder testen, indem Sie ihn in Ihrem Entwicklungscomputer ausführen. Noch interessanter ist, dass Sie denselben Buildcontainer aus Ihrer CI-Pipeline (Continuous Integration) verwenden können.

![](./media/image14.png)

**Abbildung 8-13**. Docker-Buildcontainer, der Ihre .NET-Binärdateien kompiliert 

Für dieses Szenario stellen wir das [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/)-Image bereit, das Sie zum Kompilieren und Erstellen Ihrer ASP.NET Core-Apps verwenden können. Die Ausgabe wird auf einem Image basierend auf dem [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)-Image platziert, bei dem es sich wie bereits erwähnt um ein optimiertes Laufzeitimage handelt.

Das aspnetcore-build-Image enthält alles, was Sie zum Kompilieren einer ASP.NET Core-Anwendung benötigen, einschließlich .NET Core, dem ASP.NET SDK, npm, Bower, Gulp usw.

Wir benötigen diese Abhängigkeiten zur Buildzeit. Diese sollen jedoch nicht zur Laufzeit in der Anwendung enthalten sein, damit das Image nicht unnötig groß wird. In der eShopOnContainers-Anwendung können Sie die Anwendung aus einem Container erstellen, indem Sie einfach den folgenden docker-compose-Befehl ausführen.

```
  docker-compose -f docker-compose.ci.build.yml up
```

Abbildung 8-14 zeigt, wie dieser Befehl über die Befehlszeile ausgeführt wird.

![](./media/image15.png)

**Abbildung 8-14.** Erstellen Ihrer .NET-Anwendung aus einem Container

Wie Sie sehen können, ist der Container, der ausgeführt wird, der ci-build\_1-Container. Dieser basiert auf dem aspnetcore-build-Image. So kann Ihre gesamte Anwendung von innerhalb dieses Containers anstatt von Ihrem PC kompiliert und erstellt werden. Tatsächlich wird das Erstellen und Kompilieren der .NET Core-Projekte in Linux durchgeführt, da dieser Container auf dem Docker Linux-Standardhost ausgeführt wird.

Die [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml)-Datei für dieses Image (ein Teil von eShopOnContainers) enthält den folgenden Code. Sie können sehen, dass ein Buildcontainer mithilfe des [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/)-Images gestartet wird.

```yml
version: '3'

services:

  ci-build:

    image: microsoft/aspnetcore-build:2.0

    volumes:
      - .:/src

    working_dir: /src

    command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && popd && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"

```

* Ab **.NET Core 2.0** wird der `dotnet restore`-Befehl automatisch ausgeführt, wenn der `dotnet publish`-Befehl ausgeführt wird.

Sobald der Buildcontainer ausgeführt wird, führt er die .NET SDK-Befehle „dotnet restore“ und „dotnet publish“ für die Projekte in der Projektmappe aus, um die .NET-Bits zu kompilieren. In diesem Fall müssen auch JavaScript-Abhängigkeiten mit npm geprüft werden, da eShopOnContainers auch über eine SPA verfügt, die auf TypeScript und Angular für den Clientcode basiert. Diese Aktion steht jedoch nicht in Verbindung mit den .NET-Bits.

Der Befehl „dotnet publish“ erstellt und veröffentlicht wie in Abbildung 8-15 dargestellt die kompilierte Ausgabe innerhalb jedes Projektordners im Ordner „../obj/Docker/publish“.

![](./media/image16.png)

**Abbildung 8-15.** Binärdateien, die vom Befehl „dotnet publish“ generiert wurden

#### <a name="creating-the-docker-images-from-the-cli"></a>Erstellen der Docker-Images aus der CLI

Sobald die Anwendungsausgabe in den jeweiligen Ordnern (innerhalb jedes Projekts) veröffentlicht wurde, besteht der nächste Schritt darin, die Docker-Images tatsächlich zu erstellen. Zu diesem Zweck verwenden Sie die in Abbildung 8-16 gezeigten Befehle „docker-compose build“ und „docker-compose up“.

![](./media/image17.png)

**Abbildung 8-16.** Erstellen von Docker-Images und Ausführen des Containers

In Abbildung 8-17 sehen Sie, wie der „docker-compose build“-Befehl ausgeführt wird.

![](./media/image18.png)

**Abbildung 8-17**. Erstellen des Docker-Images mit dem „docker-compose build“-Befehl.

Der Unterschied zwischen den Befehlen „docker-compose build“ und „docker-compose up“ ist, dass „docker-compose up“ die Images jeweils erstellt und startet.

Wenn Sie Visual Studio verwenden, werden diese Schritte im Hintergrund ausgeführt. Visual Studio kompiliert Ihre .NET-Anwendung, erstellt die Docker-Images und stellt die Container im Docker-Host bereit. Visual Studio bietet zusätzliche Features, z.B. die Möglichkeit, Ihre Container direkt aus Visual Studio zu debuggen, die in Docker ausgeführt werden.

Zusammengefasst besteht der Vorteil daraus, dass Sie Ihre Anwendung genauso erstellen können, wie sie auch von Ihrer CI/CD-Pipeline erstellt werden würde: aus einem Container statt von einem lokalen Computer. Nachdem die Images erstellt wurden, müssen Sie nur noch die Docker-Images mithilfe des „docker-compose up“-Befehls ausführen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Erstellen von Bits aus einem Container: Einrichten der eShopOnContainers-Projektmappe in einer Windows CLI-Umgebung (dotnet CLI, Docker CLI und VS Code)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))


>[!div class="step-by-step"]
[Zurück] (data-driven-crud-microservice.md) [Weiter] (database-server-container.md)
