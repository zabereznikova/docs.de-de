---
title: Definieren Ihre Anwendung mit mehreren Container mit Docker compose.yml
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Definieren Ihre Anwendung mit mehreren Container mit Docker compose.yml"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c5d4d2c9fb9fbb595f6f6ea195247474f353a32f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>Definieren Ihre Anwendung mit mehreren Container mit Docker compose.yml 

In diesem Handbuch sind die [Docker compose.yml](https://docs.docker.com/compose/compose-file/) Datei wurde im Abschnitt eingeführt [Schritt 4. Definieren Sie Ihre Dienste in Docker-compose.yml, beim Erstellen einer Docker-Anwendung mit mehreren Container](#step4_define_svcs_in_docker_compose_yml). Es gibt jedoch zusätzliche Möglichkeiten, die Docker-compose-Dateien zu verwenden, die noch ausführlicher untersuchen werden.

Beispielsweise können Sie explizit beschreiben, wie Sie Ihre Anwendung mehrere Container in der Docker-compose.yml-Datei bereitstellen möchten. Optional können Sie auch beschreiben, wie Sie möchten Ihre benutzerdefinierten Docker-Images zu erstellen. (Custom Docker-Images können auch mit der Docker-Befehlszeilenschnittstelle erstellt werden).

Im Grunde genommen, definieren Sie jeweils die Container, die Sie bereitstellen möchten, sowie bestimmte Merkmale für jede Bereitstellung Container. Nachdem Sie eine Bereitstellung mit mehreren Container-Beschreibungsdatei haben, können Sie die gesamte Projektmappe in einer einzigen Aktion von orchestriert Bereitstellen der [Docker Verfassen Sie](https://docs.docker.com/compose/overview/) CLI-Befehl, oder Sie können die Bereitstellung er transparent in Visual Studio. Andernfalls müssen Sie den Docker-Befehlszeilenschnittstelle zu verwenden, um die Container-durch-Container in mehreren Schritten, die mithilfe von "Docker run" Befehl über die Befehlszeile bereitstellen. Daher muss jeder Dienst in Docker-compose.yml definiert genau ein Bild angeben oder erstellen. Andere Schlüssel sind optional und werden analog zu ihren "Docker run" Befehlszeile-Entsprechungen.

Die folgende YAML Code ist die Definition einer möglichen globalen aber einzelne Docker-compose.yml-Datei für das eShopOnContainers-Beispiel. Dies ist nicht der tatsächliche Docker-compose Datei eShopOnContainers. Stattdessen ist er eine vereinfachte und konsolidierten Version in einer einzelnen Datei, die nicht die beste Möglichkeit zum Arbeiten mit Docker-bilden Dateien, wie weiter unten erläutert werden.

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

In dieser Datei der Stammschlüssel ist Services. Unter diesen Schlüssel, die Sie definieren die Dienste, die Sie bereitstellen möchten und führen Sie beim Ausführen der Docker-Befehl oder wenn Sie in Visual Studio bereitstellen mithilfe dieser Datei Docker compose.yml zusammensetzt. In diesem Fall hat die Docker-compose.yml-Datei mehrere Dienste, die definiert, wie in der folgenden Liste beschrieben.

-   Webmvc Container, einschließlich der Nutzung der Microservices von serverseitigen C ASP.NET Core MVC-Anwendung\#

-   Catalog.API Container, einschließlich der Microservice Katalog ASP.NET Core-Web-API

-   Ordering.API Container, einschließlich der Web-API für ASP.NET Core Sortierung microservice

-   SQL.Data Container, die mit SQL Server für Linux, halten die Microservices-Datenbanken

-   Basket.API Container mit dem Warenkorb ASP.NET Core-Web-API-microservice

-   Basket.Data Container mit den REDIS-Cache-Dienst muss die Warenkorb-Datenbank als eine REDIS-cache

### <a name="a-simple-web-service-api-container"></a>Ein einfacher Webdienst-API-container

Schwerpunkt auf einem einzelnen Container, hat die catalog.api Container-Microservice eine unkomplizierte Definition:

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

Dieser Dienst Datenvolumes hat die folgenden grundlegenden Konfiguration:

-   Es basiert auf dem Abbild eines benutzerdefinierten eshop/catalog.api. Der Einfachheit halber, es ist keine Build: key-Einstellung in der Datei. Dies bedeutet, dass das Bild muss zuvor (mit Docker Build) erstellt wurden, oder (mit dem Befehl "Docker Pull") aus der Registrierung Docker heruntergeladen wurden.

-   Es definiert eine Umgebungsvariable mit dem Namen "ConnectionString" mit der Verbindungszeichenfolge von Entity Framework verwendet werden, Zugriff auf die SQL Server-Instanz, die das Datenmodell für den Katalog enthält. In diesem Fall wird die gleiche SQL Server-Container mehrere Datenbanken enthalten. Aus diesem Grund benötigen Sie weniger Arbeitsspeicher in Ihrem Entwicklungscomputer für Docker ein. Allerdings können Sie auch eine SQL Server-Container für jede Datenbank Microservice bereitstellen.

-   Der SQL Server-Name ist sql.data, also den gleichen Namen verwendet, die für den Container, der die SQL Server-Instanz für Linux ausgeführt wird. Dies ist zweckmäßig, Diese namensauflösung (intern auf den Docker-Host) verwenden können wird die Netzwerkadresse aufgelöst werden, damit Sie nicht die interne IP-Adresse für den Container zu kennen, die in anderen Containern auf Sie zugreifen müssen.

Da die Verbindungszeichenfolge durch eine Umgebungsvariable definiert ist, können Sie diese Variable mithilfe eines anderen Mechanismus und zu einem anderen Zeitpunkt festlegen. Sie konnten z. B. eine andere Verbindungszeichenfolge festlegen, bei der Bereitstellung bis hin zur Produktion in die endgültige Hosts oder indem Sie es aus der CI-CD-Pipelines in VSTS oder Ihrem bevorzugten DevOps-System.

-   Er stellt die Port 80 für den internen Zugriff an den Dienst catalog.api der Docker-Host bereit. Der Host ist derzeit eine Linux-VM, da auf einem Docker-Images für Linux basiert, jedoch konnte, konfigurieren Sie den Container auf einem Windows-Abbild stattdessen ausgeführt.

-   Er leitet die verfügbar gemachten Port 80 für den Container an Port 5101 auf dem Docker-Hostcomputer (Linux-VM).

-   Den Webdienst verweist auf der sql.data-Dienst (SQL Server-Instanz für Linux-Datenbank, die in einem Container). Bei Angabe dieser Abhängigkeit beginnt catalog.api Container erst, wenn der Container sql.data bereits begonnen wurde; Dies ist wichtig, da catalog.api SQL Server-Datenbank benötigt einrichten und ausgeführten zuerst. Jedoch reicht diese Art der Abhängigkeit der Container nicht in vielen Fällen daran, dass nur auf Containerebene Docker überprüft. In einigen Fällen der Dienst (in dieser SQL Server mit Groß-/Kleinschreibung) nicht bereit ist, möglicherweise weiterhin daher ist es ratsam, Wiederholungslogik mit exponenzieller Wartezeit in Ihrem Client Microservices implementieren. Auf diese Weise ist ein Container für die Abhängigkeit nicht bereit für kurze Zeit, die Anwendung stabil bleiben.

-   Für den Zugriff mit externen Servern konfiguriert ist: die zusätzlichen\_Hosts festlegen können Sie den Zugriff auf externe Server oder Computer außerhalb der Docker-Host (d. h. außerhalb der Standardwert eine Entwicklung Docker ist Linux-VM gehostet), wie z. B. eine lokale SQL Server-Instanz auf Ihrem PC.

Es gibt auch andere, erweiterten Docker compose.yml-Einstellungen, die wir in den folgenden Abschnitten erläutert.

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>Mit Docker-verfassen Dateien auf mehrere Umgebung

Die Docker-compose.yml Dateien bestehen aus Berichtsdefinitionsdateien und können durch mehrere Infrastrukturen, die diesem Format verstehen verwendet werden. Das einfachste Tool wird der Docker-Befehl zu erstellen, jedoch andere tools, wie diese Datei auch die Orchestrators (z. B. Docker Containerhostclustern) vertraut sein.

Aus diesem Grund mithilfe der Docker-verfassen Befehl können Sie die folgenden Hauptszenarien abzielen.

#### <a name="development-environments"></a>Entwicklungsumgebungen

Wenn Sie Anwendungen entwickeln, ist es wichtig, um eine Anwendung in einer isolierten Entwicklungsumgebung ausführen zu können. Sie können die CLI-Befehl zum Erstellen der Umgebung oder verwenden Visual Studio die Verwendungsmöglichkeiten Docker-grundlegend verfassen Docker zu erstellen.

Der Docker-compose.yml-Datei können Sie zum Konfigurieren und alle Ihre Anwendung dienstabhängigkeiten (andere Dienste, Cache, Datenbanken, Warteschlangen usw.) zu dokumentieren. Mithilfe der CLI-Befehl Docker zu erstellen, können Sie erstellen und starten Sie einen oder mehrere Container für jede Abhängigkeit mit einem einzigen Befehl (Docker-verfassen oben).

Docker-compose.yml Dateien sind Konfigurationsdateien, die durch Docker-Modul interpretiert zu werden, aber auch als einfache Dokumentationsdateien über die Zusammensetzung der Anwendung mit mehreren Container dienen.

#### <a name="testing-environments"></a>Testumgebungen

Ein wichtiger Teil eines dauerhaften Bereitstellung (CD) oder fortlaufende Integration (CI) Prozess werden die Komponententests und Integrationstests erfolgreich. Diese automatisierten Tests erfordern eine isolierte Umgebung, damit sie nicht durch die Benutzer oder jede andere Änderung in die Anwendung Daten eingeschränkt werden.

Sie können mit Docker Compose erstellen und zerstören, isolierten Umgebung sehr einfach in wenigen Befehle von der Eingabeaufforderung oder Skripts, z. B. die folgenden Befehle:

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a>Produktionsbereitstellungen

Sie können auch verfassen zur Bereitstellung auf einem remote-Docker-Modul verwenden. Ein typischer Fall für eine einzelne Instanz des Docker-Host bereitgestellt ist (z. B. einer Produktions-VM oder einem Server bereitgestellt, mit [Docker-Computer](https://docs.docker.com/machine/overview/)). Aber unter Umständen liegen auch eine gesamte [Docker Containerhostclustern](https://docs.docker.com/swarm/overview/) -cluster, da Cluster auch mit der Docker-compose.yml-Dateien kompatibel sind.

Wenn Sie andere Orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes usw.) verwenden, müssen Sie Setup und Metadaten Konfigurationseinstellungen wie diejenigen in Docker-compose.yml, aber in der von den anderen Orchestrator erforderlichen Format hinzufügen.

In jedem Fall Docker-verfassen gängiges Format Tool und die Metadaten für Entwicklungs-, Test- und Produktionszwecke Workflows ist, auch wenn die Produktions-Workflow auf die Orchestrator stark variieren können Sie verwenden.

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>Verwenden mehrerer Docker-bilden Dateien, um mehrere Umgebungen zu behandeln.

Wenn Sie unterschiedliche Umgebungen verwenden zu können, sollten Sie verwenden Sie mehrere Dateien zu erstellen. Dies können Sie mehrere Konfigurationsvarianten abhängig von der Umgebung zu erstellen.

#### <a name="overriding-the-base-docker-compose-file"></a>Überschreiben die Basis Docker-compose-Datei

Sie können eine einzelne Docker-compose.yml-Datei wie in den vereinfachten Beispielen, die in vorherigen Abschnitten dargestellt. Allerdings wird, nicht für die meisten Anwendungen empfohlen.

Standardmäßig liest verfassen, zwei Dateien, ein Docker-compose.yml und eine optionale Docker-compose.override.yml-Datei. Wie in Abbildung 8 bis 11 dargestellt, wenn Sie Visual Studio verwenden, und Aktivieren der Unterstützung für Docker, Visual Studio auch erstellt diese Dateien und einige zusätzliche Dateien, die zum Debuggen verwendet.

![](./media/image12.png)

**Abbildung 8 bis 11**. Dateien in Visual Studio 2017 Docker zu erstellen

Sie können die Docker-compose-Dateien mit einem beliebigen Editor, z. B. Visual Studio Code oder Sublime, bearbeiten und Ausführen der Anwendung mit der Docker verfassen Befehl oben.

Gemäß der Konvention werden die Docker-compose.yml-Datei enthält, der Basiskonfiguration und andere Einstellungen für statischen. Das bedeutet, dass es sich bei die Dienstkonfiguration abhängig von der bereitstellungsumgebung Ihrer Zielgruppe, nicht ändern sollten.

Die Docker-compose.override.yml-Datei, enthält wie der Name andeutet, Konfigurationseinstellungen, die von der Basisklasse der Konfigurationselemente, z. B. Konfiguration außer Kraft setzen, von die die bereitstellungsumgebung abhängt. Sie können auch mehrere Außerkraftsetzung-Dateien mit unterschiedlichen Namen haben. Die Außerkraftsetzung-Dateien enthalten in der Regel zusätzlichen Informationen, die von der Anwendung jedoch bestimmte in einer Umgebung oder auf eine Bereitstellung benötigt werden.

#### <a name="targeting-multiple-environments"></a>Umgebungen mit mehreren abzielt

Ein typischer Anwendungsfall ist beim Definieren von mehreren bilden Dateien, damit Sie mehrere Umgebungen, z. B. Produktion abzielen können, staging, CI oder Entwicklungsmethode. Um diese Unterschiede zu unterstützen, können Sie Ihre Konfiguration verfassen in mehrere Dateien aufteilen, wie in Abbildung 8 – 12 gezeigt.

![](./media/image13.png)

**Abbildung 8 – 12**. Mehrere Docker-bilden Dateien, die Werte in der Basisklasse Docker-compose.yml Datei überschreiben

Beginnen Sie mit der Basis Docker-compose.yml-Datei. Diese Basis-Datei muss die Basistabelle oder statische Konfigurationseinstellungen enthält, die abhängig von der Umgebung nicht ändern. Die eShopOnContainers hat beispielsweise die folgende Docker-compose.yml-Datei als die Basisdatei.

```yml
#docker-compose.yml (Base)
version: '2'

services:
  basket.api:
    image: eshop/basket.api
    build:
    context: ./src/Services/Basket/Basket.API
    dockerfile: Dockerfile
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api
    build:
    context: ./src/Services/Catalog/Catalog.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  identity.api:
    image: eshop/identity.api
    build:
    context: ./src/Services/Identity/Identity.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    build:
    context: ./src/Services/Ordering/Ordering.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  webspa:
    image: eshop/webspa
    build:
    context: ./src/Web/WebSPA
    dockerfile: Dockerfile
    depends_on:
      - identity.api
      - basket.api

  webmvc:
    image: eshop/webmvc
    build:
    context: ./src/Web/WebMVC
    dockerfile: Dockerfile
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api

  sql.data:
    image: microsoft/mssql-server-linux
    basket.data:
    image: redis
    expose:
      - "6379"
    rabbitmq:
    image: rabbitmq
    ports:
      - "5672:5672"

  webstatus:
    image: eshop/webstatus
    build:
    context: ./src/Web/WebStatus
    dockerfile: Dockerfile
```

Die Werte in der Datei Basis Docker-compose.yml sollten aufgrund bereitstellungsumgebungen anderes Ziel nicht ändern.

Wenn Sie auf die Dienstdefinition Webmvc zu konzentrieren, für die Instanz, sehen Sie wie diese Informationen nahezu identisch, unabhängig davon, welche Umgebung ist, den Sie als Ziel sein können. Sie haben die folgende Informationen:

-   Der Dienstname: Webmvc.

-   Benutzerdefiniertes Image des Containers: Shopping/Webmvc.

-   Der Befehl zum Erstellen der benutzerdefinierten Docker-Images, der angibt, welche dockerfile-Datei verwenden.

-   Abhängigkeiten von anderen Diensten, damit dieser Container nicht gestartet wird, bis der andere Abhängigkeit Container gestartet haben.

Es können zusätzliche Konfigurationsschritte, aber der wichtige Punkt ist, dass in der Datei Basis Docker-compose.yml Sie nur die Informationen festlegen möchten, die über Umgebungen hinweg gemeinsam ist. Klicken Sie dann sollten Sie in der Docker-compose.override.yml oder ähnliche Dateien für die Produktion oder Staging, Konfiguration platzieren, die für jede Umgebung spezifisch sind.

In der Regel wird der Docker-compose.override.yml für Ihre Entwicklungsumgebung, wie im folgenden Beispiel aus eShopOnContainers verwendet:

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '2'

services:
# Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database=Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Pass@word
      - ExternalCatalogBaseUrl=http://localhost:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:5105
    - SpaClient=http://localhost:5104
    - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
    - MvcClient=http://localhost:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://localhost:5101
      - OrderingUrl=http://localhost:5102
      - IdentityUrl=http://localhost:5105
      - BasketUrl=http:// localhost:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

In diesem Beispiel wird die Entwicklungskonfiguration Außerkraftsetzung macht einige Ports auf dem Host, definiert der Umgebungsvariablen mit Umleiten von URLs und Verbindungszeichenfolgen für die Entwicklungsumgebung angibt. Diese Einstellungen sind alle nur für die Entwicklungsumgebung.

Beim Ausführen von Docker zusammensetzt (oder starten Sie ihn von Visual Studio), der Befehl liest die Außerkraftsetzungen automatisch, als ob sie beide Dateien zusammengeführt wurden.

Angenommen Sie, Sie eine andere Compose-Datei für die produktionsumgebung mit verschiedenen Konfigurationswerte möchten. Sie können eine andere Außerkraftsetzung-Datei wie folgt erstellen. (Diese Datei möglicherweise werden in einem anderen Git-Repository gespeichert oder verwaltet und von einem anderen Team gesichert werden.)

```yml
#docker-compose.prod.yml (Extended config for PRODUCTION env.)
version: '2'

services:
  # Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database = Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Prod@Pass
      - ExternalCatalogBaseUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5105
      - SpaClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5104
      - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
      - MvcClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT= Production
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
      - OrderingUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5102
      - IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
      - BasketUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Prod@Pass
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

#### <a name="how-to-deploy-with-a-specific-override-file"></a>Gewusst wie: Bereitstellen mit einer bestimmten Außerkraftsetzung-Datei

Um mehrere Außerkraftsetzung Dateien oder eine Überschreibung-Datei mit einem anderen Namen zu verwenden, können Sie die Option "-f" mit dem Befehl Docker zu erstellen, und geben Sie die Dateien. Verfassen Sie Zusammenführungen-Dateien in der Reihenfolge, die sie in der Befehlszeile angegeben wurden. Im folgende Beispiel wird gezeigt, wie mit Außerkraftsetzung Dateien bereitgestellt wird.

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>Verwenden von Umgebungsvariablen in Docker-zusammenstellen Dateien

Es ist sinnvoll, insbesondere in produktionsumgebungen, in der Lage, beim Abrufen von Konfigurationsinformationen aus der Umgebungsvariablen, sein, wie es in den vorherigen Beispielen gezeigt haben. Sie verweisen eine Umgebungsvariablen in Ihren Docker-compose-Dateien, die mit der Syntax \${MY\_VAR}. Die folgende Zeile aus einer Datei Docker compose.prod.yml zeigt, wie der Wert einer Umgebungsvariablen zu verweisen.

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

Umgebungsvariablen werden erstellt und initialisiert Sie verschiedene Möglichkeiten, je nach Ihrer hostumgebung (Linux, Windows, Cloud-Cluster usw..). Ist jedoch ein geeigneten Ansatz eine .env-Datei zu verwenden. Deklarieren von Standard-Umgebungsvariablen in der Datei .env Docker-compose Dateien unterstützen. Diese Werte für die Umgebungsvariablen sind die Standardwerte. Sie können jedoch überschrieben werden durch die Werte, die Sie möglicherweise in den einzelnen Ihrer Umgebungen (Host-BS oder Umgebungsvariablen aus Ihrem Cluster) definiert haben. Sie fügen diese .env-Datei in den Ordner, in dem der Docker-verfassen Befehl ausgeführt wird.

Das folgende Beispiel zeigt eine Datei .env wie die [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) Datei für die Anwendung eShopOnContainers.

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Verfassen von Docker erwartet, dass jede Zeile in einer Datei .env werden im Format &lt;Variable&gt;=&lt;Wert&gt;.

Beachten Sie, dass die Werte in der Common Language Runtime-Umgebung immer in der Datei .env definierten Werte überschreiben. Auf ähnliche Weise überschreiben die Werte, die über die Befehlszeile Argumente übergeben auch die Standardwerte, die in der Datei .env festgelegt.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Übersicht über Docker verfassen**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)

-   **Mehrere verfassen Dateien**
    [*https://docs.docker.com/compose/extends/\#mehrere verfassen Dateien*](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>Erstellen von optimiert ASP.NET Core Docker-images

Wenn Sie Docker und .NET Core auf Quellen im Internet untersuchen, finden Sie dockerfile-Dateien, die die Einfachheit der Erstellung eines Images von Docker durch Kopieren von Quellcode in einen Container zu veranschaulichen. In diesen Beispielen wird empfohlen, eine einfache Konfiguration, ein Docker Bild mit der Umgebung, die mit der Anwendung verpackt verfügen können. Das folgende Beispiel zeigt einen einfachen dockerfile-Datei in diesem Vein.

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

Eine dockerfile-Datei wie folgt funktioniert. Sie können jedoch im Wesentlichen der Bilder, insbesondere der Produktions-Bilder optimieren.

In den Container und Microservices Modell beginnen Sie ständig Container. Die gewohnte Weise von mithilfe von Containern wird keinen inaktiven Container neu gestartet, da der Container gelöscht wird. Orchestrators (z. B. Docker Containerhostclustern, Kubernetes, DCOS oder Azure Service Fabric) erstellen Sie einfach neue Instanzen von Bildern. Dies bedeutet, dass Sie optimieren, indem Sie das Vorkompilieren von der Anwendung, wenn sie erstellt wird, damit der Prozess Instanziierung schneller werden müssten. Wenn der Container gestartet wird, sollte er für die Ausführung bereit. Sie sollte nicht wiederherstellen und Kompilieren zur Laufzeit, mithilfe Dotnet wiederherstellen und Dotnet build-Befehle von der CLI-Dotnet, die die in den zahlreichen Blogbeiträgen zu .NET Core und Docker angezeigt.

Das Team .NET verfügt über wichtige Schritte, um .NET Core und ASP.NET Core stellen ein Framework Container optimiert ausgeführt wurden. Ist nicht nur .NET Core eine einfache Framework mit einer geringen speicherbeanspruchung; vom Team konzentriert sich auf die Leistung beim Start und einige optimierte Docker-Images, z. B. erzeugt der [Microsoft/Aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) Bild unter [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), im Vergleich zu normalen [ Microsoft/Dotnet](https://hub.docker.com/r/microsoft/dotnet/) oder [Microsoft/Nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) Bilder. Die [Microsoft/Aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) Grafik automatische Aspnetcore-Einstellung\_Urls für den Port 80 und Cache vor Ngend von Assemblys aus; beide Einstellungen dazu führen, den Start zu beschleunigen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Erstellen von optimiert Docker-Images mit ASP.NET Core**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

### <a name="building-the-application-from-a-build-ci-container"></a>Erstellen der Anwendung aus einem Build (CI)-container

Ein weiterer Vorteil der Docker ist, dass Sie die Anwendung aus einem vorkonfigurierten Container erstellen können, wie in Abbildung 8 bis 13 gezeigt werden, damit Sie nicht benötigen, um einen Buildcomputer oder VM zur Erstellung der Anwendung erstellen. Sie können verwenden oder diesen Build-Container testen, indem Sie es auf Ihrem Entwicklungscomputer ausgeführt wird. Doch interessanteres ist, dass Sie den gleichen Build-Container aus der Pipeline CI (Continuous Integration) verwenden können.

![](./media/image14.png)

**Abbildung 8 bis 13**. Komponenten, die .NET Bits aus einem Container erstellen

Geben Sie in diesem Szenario wird die [Microsoft/Aspnetcore-Build](https://hub.docker.com/r/microsoft/aspnetcore-build/) Image, das Sie zum Kompilieren und erstellen Ihre ASP.NET Core apps verwenden können. Die Ausgabe befindet sich in einem Bild auf der Grundlage der [Microsoft/Aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) Image, das eine optimierte Common Language Runtime-Image, wie bereits erwähnt ist.

Aspnetcore-buildabbild enthält alles, was Sie benötigen, um das Kompilieren einer ASP.NET Core-Anwendung, einschließlich .NET Core, die ASP.NET SDK, Npm, Bower, Gulp usw..

Wir benötigen diese Abhängigkeiten zur Buildzeit. Wir nicht möchten, jedoch mit der Anwendung zur Laufzeit ausführen, da sie das Bild unnötig große machen würden. In der Anwendung eShopOnContainers erstellen Sie die Anwendung aus einem Container, indem Sie nur Ausführen folgender Docker-verfassen Befehl.

```
  docker-compose -f docker-compose.ci.build.yml up
```

Abbildung 8 – 14 zeigt diesen Befehl an der Befehlszeile ausführen.

![](./media/image15.png)

**Abbildung 8 – 14.** Erstellen der Anwendung .NET aus einem container

Wie Sie sehen können, ist der Container, der ausgeführt wird, wird der Ci-Build\_1 Container. Dies basiert auf der Aspnetcore buildabbild, damit sie kompilieren und die gesamte Anwendung aus innerhalb dieses Containers statt von Ihrem PC erstellen kann. D. h. warum in Wirklichkeit es ist erstellen und Kompilieren die Projekte von .NET Core in Linux – da diesen Container auf die Standard-Docker-Linux-Host ausgeführt wird.

Die [Docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) -Konfigurationsdatei für dieses Abbilds (eShopOnContainers Teil) der folgende Code enthält. Beachten Sie, dass Sie einen Build-Container mit Beginn der [Microsoft/Aspnetcore-Build](https://hub.docker.com/r/microsoft/aspnetcore-build/) Bild.

```yml
version: '2'
  services:
    ci-build:
      image: microsoft/aspnetcore-build:1.0-1.1
      volumes:
        - .:/src
      working_dir: /src
      command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && pushd ./../../.. && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"
```

* Beginnend mit **.NET Core 2.0**, `dotnet restore` Befehl führt automatisch bei der `dotnet publish` -Befehl ausgeführt wird.

Nachdem der Build-Container ausgeführt wird, die .NET SDK-Dotnet-Wiederherstellung ausführen und Dotnet veröffentlichen Befehle für alle Projekte in der Projektmappe, um die .NET Bits zu kompilieren. In diesem Fall da eShopOnContainers auch ein SPA basierend auf TypeScript und Angular für den Clientcode verfügt, muss sie außerdem Überprüfen von JavaScript-Abhängigkeiten mit Npm, aber diese Aktion nicht mit dem .NET Bits verknüpft ist.

Die Dotnet Befehl Builds veröffentlichen und die kompilierte Ausgabe im Ordner des Projekts veröffentlicht die... /obj/Docker/Publish-Ordner, wie in Abbildung 8-15 gezeigt.

![](./media/image16.png)

**Abbildung 8-15.** Binärdateien, die von der Dotnet generierten veröffentlichen (Befehl)

#### <a name="creating-the-docker-images-from-the-cli"></a>Erstellen der Docker-Images von der CLI

Nachdem die Anwendungsausgabe auf die zugehörigen Ordner (innerhalb eines Projekts) veröffentlicht wurde, besteht der nächste Schritt der Docker-Images zu erstellen. Zu diesem Zweck verwenden den Build Docker-compose und Docker-verfassen Befehle, wie in Abbildung 8 bis 16 dargestellt.

![](./media/image17.png)

**Abbildung 8-16.** Docker-Images erstellen und Ausführen von den Containern

In Abbildung 8 bis 17, sehen Sie, wie die Docker-compose befehlsausführung erstellen.

![](./media/image18.png)

**Abbildung 8 bis 17**. Beim Erstellen der Docker-Images mit Docker-Buildbefehl verfassen

Der Unterschied zwischen der Docker-compose erstellen und Docker Verfassen Sie Befehle ist, die Docker-Verfassen Sie Builds und startet die Bilder.

Wenn Sie Visual Studio verwenden, werden all diese Schritte im Hintergrund ausgeführt. Visual Studio kompiliert Ihre Anwendung .NET, erstellt das Docker-Images und die Container in der Docker-Host bereitgestellt. Visual Studio bietet zusätzliche Funktionen, z. B. die Fähigkeit, die Container, die in Docker ausgeführt wird, direkt in Visual Studio debuggen.

Die gesamte Takeway hier besteht darin, dass kann zum Erstellen der Anwendung die gleiche Weise Ihre Pipeline CI-CD sollten erstellt werden – aus einem Container anstatt von einem lokalen Computer. Haben Sie die Bilder, die erstellt wurden, dann müssen Sie nur führen Sie den Docker-Images mit Docker-Befehl zu erstellen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Erstellen von Bits von einem Container: Einrichten der eShopOnContainers-Lösung in einer Windows-CLI-Umgebung (Dotnet CLI, Docker-Befehlszeilenschnittstelle und Visual Studio Code)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/ 03.-Setting-the-eShopOnContainers-Solution-Up-in-a-Windows-CLI-Environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))


>[!div class="step-by-step"]
[Vorherigen] (Data-driven-Crud-microservice.md) [weiter] (Datenbank-Server-container.md)
