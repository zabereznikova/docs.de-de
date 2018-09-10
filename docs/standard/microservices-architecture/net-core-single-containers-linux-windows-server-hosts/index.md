---
title: Bereitstellen von einzelnen auf Containern basierenden .NET Core-Webanwendungen auf Linux- oder Windows Nano Server-Hosts
description: .NET-Microservices-Architektur für .NET-Containeranwendungen | Bereitstellen von einzelnen auf Containern basierenden .NET Core-Webanwendungen auf Linux- oder Windows Nano Server-Hosts
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/27/2018
ms.openlocfilehash: 45be99a86a52ed450b795ca5f91c01ab82c7da47
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197354"
---
# <a name="deploying-single-container-based-net-core-web-applications-on-linux-or-windows-nano-server-hosts"></a>Bereitstellen von einzelnen auf Containern basierenden .NET Core-Webanwendungen auf Linux- oder Windows Nano Server-Hosts

_Sie können Docker-Container für die monolithische Bereitstellung von einfachen Webanwendungen verwenden. Dies verbessert die fortlaufende Integration und die fortlaufenden Bereitstellungspipelines und unterstützt Sie bei der erfolgreichen Bereitstellung in der Produktion. Sie müssen sich nie wieder fragen, warum die Anwendung auf Ihrem Computer, aber nicht in der Produktion funktioniert._

Eine auf Microservices basierende Architektur hat viele Vorteile, die jedoch eine erhöhte Komplexität mit sich bringen. In manchen Fällen sind die Kosten der ausschlaggebende Faktor und nicht die Vorteile, und eine monolithische Bereitstellung einer Anwendung, die in einem oder in wenigen Containern ausgeführt wird, ist eine bessere Option.

Eine monolithische Anwendung in gut getrennte Microservices zu zerteilen, ist nicht einfach. Sie haben gelernt, dass diese Microservices nach Funktion partitioniert werden sollten: Sie sollten unabhängig voneinander funktionieren, um eine widerstandsfähigere Anwendung bereitzustellen. Wenn Sie keine Feature Slices der Anwendung bereitstellen können, führt das Trennen derselben nur zu erhöhter Komplexität.

Eine Anwendung muss möglicherweise noch keine Features unabhängig voneinander skalieren. Nehmen wir an, dass der Datenverkehr in der Frühphase der `eShopOnContainers`-Referenzanwendung nicht gerechtfertigt hat, dass die Features in verschiedene Microservices aufgeteilt werden. Der Datenverkehr war gering genug, sodass das Hinzufügen von Ressourcen zu einem Dienst üblicherweise bedeutet hat, dass Ressourcen zu allen Diensten hinzugefügt werden. Die zusätzliche Arbeit, die Anwendung in diskrete Dienste aufzuteilen, resultiert nur in minimalen Vorteilen.

Zudem haben Sie zu einem frühen Zeitpunkt während der Entwicklung einer Anwendung möglicherweise noch keine Vorstellung davon, wo die natürlichen funktionalen Grenzen liegen. Beim Entwickeln eines mindestens anwendungsfähigen Produkts könnte die natürliche Trennung noch nicht verfügbar sein.

Einige dieser Bedingungen können temporär sein. Sie können mit dem Erstellen einer monolithischen Anwendung beginnen und später einige Features trennen, damit diese als Microservices entwickelt und bereitgestellt werden. Andere Bedingungen können entscheidend für den Problembereich der Anwendung sein. Das bedeutet, dass die Anwendung möglicherweise nicht in mehrere Microservices unterteilt werden kann.

Das Trennen einer Anwendung in viele diskrete Prozesse führt außerdem zu Mehraufwand. Durch das Teilen der Features in verschiedene Prozesse wird die Komplexität erhöht. Die Kommunikationsprotokolle werden komplexer. Anstelle von Methodenaufrufen müssen Sie asynchrone Kommunikationen zwischen den Diensten verwenden. Wenn Sie zu einer Microservicesarchitektur übergehen, müssen Sie viele der Bausteine hinzufügen, die in die Microservicesversion der `eShopOnContainers`-Anwendung implementiert sind: Eventbusbehandlung, Meldungsstabilität und -wiederholungen, Eventual Consistency usw.

Eine wesentlich vereinfachte Version von eShopOnContainers (namens [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic), im selben GitHub-Repository enthalten) wird als monolithische MVC-Anwendung ausgeführt. Wie gerade beschrieben, entstehen durch diese Entwurfsentscheidung Vorteile. Sie können die Quelle für diese Anwendung von GitHub herunterladen und diese lokal ausführen. Auch die monolithische Anwendung profitiert von der Bereitstellung in einer Containerumgebung.

Durch die Containerumgebung wird jede Instanz der Anwendung in derselben Umgebung ausgeführt. Dies schließt die Entwicklungsumgebung ein, in der das frühe Testen und die Entwicklung stattfinden. Das Entwicklungsteam kann die Anwendung in einer Containerumgebung ausführen, die der Produktionsumgebung entspricht.

Zudem können Containeranwendungen zu geringeren Kosten skaliert werden. Wie zuvor gezeigt wurde, ermöglicht die Containerumgebung eine größere Ressourcenfreigabe als die herkömmlichen VM-Umgebungen.

Schließlich erzwingt das Containerisieren einer Anwendung eine Trennung zwischen der Geschäftslogik und dem Speicherserver. Wenn die Anwendung skaliert wird, verwenden unterschiedliche Container ein einziges physisches Speichermedium. In der Regel ist dieser Speicher ein Hochverfügbarkeitsserver, auf dem eine SQL Server-Datenbank ausgeführt wird.

## <a name="application-tour"></a>Überblick über die Anwendung

Die [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic)-Anwendung stellt einige der eShopOnContainers-Anwendungen dar, die als monolithische Anwendungen ausgeführt werden, und zwar eine auf ASP.NET Core MVC-basierte Anwendung, die auf .NET Core ausgeführt wird. Wie im vorherigen Abschnitt beschrieben, stellt diese hauptsächlich die Funktionen zum Durchsuchen des Katalogs bereit.

Die Anwendung verwendet eine SQL Server-Datenbank für den Katalogspeicher. In auf Containern basierten Bereitstellungen kann diese monolithische Anwendung auf denselben Datenspeicher wie die auf Microservices basierte Anwendung zugreifen. Die Anwendung wird dafür konfiguriert, SQL Server in einem Container neben der monolithischen Anwendung auszuführen. In einer Produktionsumgebung wird SQL Server auf einem Hochverfügbarkeitscomputer außerhalb des Docker-Hosts ausgeführt. Zur Vereinfachung wird empfohlen, SQL Server in einer Entwicklungs- oder Testumgebung in einem eigenen Container auszuführen.

Die anfänglich festgelegten Features ermöglichen nur das Durchsuchen des Katalogs. Updates aktivieren die vollständige Featuregruppe der Containeranwendung. Eine erweiterte Architektur mit einer monolithischen Webanwendung wird im E-Book [ASP.NET Web Application architecture practices (Methoden zur ASP.NET-Webanwendungarchitektur)](https://aka.ms/webappebook) und der dazugehörenden [eShopOnWeb-Beispielanwendung](https://aka.ms/WebAppArchitecture) beschrieben.

## <a name="docker-support"></a>Docker-Unterstützung

Das eShopOnWeb-Projekt wird auf .NET Core ausgeführt. Darum kann sie entweder auf Linux- oder auf Windows-basierten Containern ausgeführt werden. Beachten Sie, dass Sie für die Docker-Bereitstellung den gleichen Hosttyp für SQL Server verwenden sollten. Linux-basierte Container haben einen geringeren Speicherbedarf und werden bevorzugt.

Visual Studio stellt eine Projektvorlage bereit, die die Unterstützung von Docker zu einer Projektmappe hinzufügt. Klicken Sie mit der rechten Maustaste auf das Projekt und dann auf **Hinzufügen** und **Docker-Unterstützung**. Die Vorlage fügt eine Dockerfile und ein neues **Docker-Compose**-Projekt, das die Startdatei *docker-compose.yml* bereitstellt, zu Ihrem Projekt hinzu. Dieser Schritt wurde bereits in dem eShopOnWeb-Projekt durchgeführt, das von GitHub heruntergeladen wurde. Es wird angezeigt, dass die Projektmappe die Projekte **eShopOnWeb** und **Docker-Compose** wie in Abbildung 6-1 dargestellt enthält.

![](./media/image1.png)

**Abbildung 6-1**. Das **Docker-Compose**-Projekt in einer einzigen Container-Webanwendung

Bei diesen Dateien handelt es sich um Standarddateien von Docker-Compose, die mit jedem Docker-Projekt konsistent sind. Sie können diese mit Visual Studio oder über die Befehlszeile verwenden. Diese Anwendung wird in .NET Core ausgeführt und verwendet Linux-Container. Sie können sie also auf einem Mac- oder Linux-Computer programmieren, erstellen und ausführen.

Die Datei *docker-compose.yml* enthält Informationen darüber, welche Images erstellt und welche Container gestartet werden müssen. Die Vorlagen geben an, wie das `eshopweb`-Image erstellt und der Container der Anwendung ausgeführt wird. Sie müssen die Abhängigkeit von SQL Server hinzufügen, indem Sie ein Image (z.B. `mssql-server-linux`) integrieren sowie einen Dienst für das Image „sql.data“, damit Docker diesen Container erstellen und starten kann. Diese Einstellungen sind im folgenden Beispiel dargestellt:

```yml
version: '2'

services:
  eshopweb:
    image: eshop/web
    build:
    context: ./eShopWeb
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  sql.data:
    image: microsoft/mssql-server-linux
```

Die Anweisung `depends_on` teilt Docker mit, dass das eShopWeb-Image vom sql.data-Image abhängig ist. Die Zeilen unter `depends_on` sind die Anweisungen zum Erstellen des Images `sql.data` mithilfe des Images `microsoft/mssql-server-linux`.

Das **Docker-Compose**-Projekt zeigt die anderen Docker-Compose-Dateien unter dem Hauptknoten *docker-compose.yml* an, damit die Verknüpfung dieser Dateien erkennbar ist. Die Datei *docker-compose-override.yml* enthält Einstellungen für beide Dienste, z.B. Verbindungszeichenfolgen und andere Anwendungseinstellungen.

Das folgende Beispiel zeigt die Datei *docker-compose.vs.debug.yml*, die Einstellungen enthält, die für das Debuggen in Visual Studio verwendet werden. In dieser Datei ist dem eShopWeb-Image der Entwicklungstag angefügt. Dadurch können Debug-Images besser von Release-Images getrennt werden, sodass Sie die Debuginformationen nicht versehentlich in einer Produktionsumgebung bereitstellen:

```yml
version: '2'

services:
  eshopweb:
    image: eshop/web:dev
    build:
    args:
    source: ${DOCKER_BUILD_SOURCE}
    environment:
      - DOTNET_USE_POLLING_FILE_WATCHER=1
    volumes:
      - ./eShopWeb:/app
      - ~/.nuget/packages:/root/.nuget/packages:ro
      - ~/clrdbg:/clrdbg:ro
    entrypoint: tail -f /dev/null
    labels:
      - "com.microsoft.visualstudio.targetoperatingsystem=linux"
```

Die letzte hinzugefügte Datei ist *docker-compose.ci.build.yml*. Diese Datei wird über die Befehlszeile verwendet, um das Projekt von einem CI-Server zu erstellen. Diese compose-Datei startet einen Docker-Container, der das für die Anwendung benötigte Image erstellt. Das folgende Beispiel zeigt die Inhalte der Datei *docker-compose.ci.build.yml*.

```yml
version: '2'

services:
  ci-build:
    image: microsoft/aspnetcore-build:latest
    volumes:
      - .:/src
    working_dir: /src
  command: /bin/bash -c "dotnet restore ./eShopWeb.sln && dotnet publish  ./eShopWeb.sln -c Release -o ./obj/Docker/publish"
```

> [!NOTE]
> Ab .NET Core 2.0 wird der Befehl [dotnet restore](../../../core/tools/dotnet-restore.md) automatisch beim Ausführen von [dotnet publish](../../../core/tools/dotnet-publish.md) ausgeführt.

Beachten Sie, dass das Image ein ASP.NET Core-Buildimage ist. Dieses Image enthält das SDK und Buildtools, um Ihre Anwendung und die erforderlichen Images zu erstellen. Das Ausführen des **Docker-Compose**-Projekts mit dieser Datei startet den Buildcontainer aus dem Image und erstellt dann das Image der Anwendung in diesem Container. Sie geben die *Docker-Compose*-Datei als Teil der Befehlszeile an, um Ihre Anwendung in einem Docker-Container zu erstellen und diese anschließend zu starten.

In Visual Studio können Sie Ihre Anwendung in Docker-Containern starten, indem Sie das **Docker-Compose**-Projekt als Startprojekt auswählen und dann wie bei jeder anderen Anwendung STRG+F5 (F5 zum Debuggen) drücken. Wenn Sie das **Docker-Compose**-Projekt starten, führt Visual Studio **Docker-Compose** mithilfe der Dateien *docker-compose.yml* und *docker-compose.override.yml* sowie einer der docker-compose.vs.\*-Dateien aus. Nachdem die Anwendung gestartet wurde, startet Visual Studio den Browser für Sie.

Wenn Sie die Anwendung im Debugger ausführen, wird Visual Studio an die ausgeführte Anwendung in Docker angefügt.

## <a name="troubleshooting"></a>Problembehandlung

Dieser Abschnitt beschreibt einige Probleme, die auftreten können, wenn Sie Container lokal ausführen und schlägt einige Lösungen vor.

### <a name="stop-docker-containers"></a>Anhalten von Docker-Containern

Nachdem Sie die Containeranwendung gestartet haben, wird der Container weiter ausgeführt, auch nachdem Sie das Debuggen beendet haben. Sie können den Befehl `docker ps` von der Befehlszeile aus ausführen, um die ausgeführten Container anzuzeigen. Der Befehl `docker stop` hält wie in Abbildung 6-2 gezeigt den ausgeführten Container an.

![](./media/image2.png)

**Abbildung 6-2**. Auflisten und Anhalten von Containern mit den CLI-Befehlen „docker ps“ und „docker stop“

Sie sollten ausgeführte Prozesse beenden, wenn Sie zwischen verschiedenen Konfigurationen wechseln. Andernfalls verwendet der Container, der die Webanwendung ausführt, den Port für Ihre Anwendung (in diesem Beispiel 5106).

### <a name="add-docker-to-your-projects"></a>Hinzufügen von Docker zu Ihren Projekten

Der Assistent, der die Docker-Unterstützung hinzufügt, kommuniziert mit dem ausgeführten Docker-Prozess. Der Assistent wird nicht ordnungsgemäß ausgeführt, wenn Docker beim Starten des Assistenten nicht ausgeführt wird. Der Assistent überprüft Ihre aktuelle Containerwahl, um die richtige Docker-Unterstützung hinzuzufügen. Führen Sie den Assistenten aus, während Docker mit der Konfiguration für Windows-Container ausgeführt wird, um Unterstützung für Windows-Container hinzuzufügen. Führen Sie den Assistenten aus, während Docker mit der Konfiguration für Linux-Container ausgeführt wird, um Unterstützung für Linux-Container hinzuzufügen.

>[!div class="step-by-step"]
[Zurück](../docker-application-development-process/docker-app-development-workflow.md)
[Weiter](../containerize-net-framework-applications/index.md)
