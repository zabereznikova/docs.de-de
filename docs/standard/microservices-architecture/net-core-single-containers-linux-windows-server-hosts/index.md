---
title: Bereitstellen von einzelnen auf Containern basierenden .NET Core-Webanwendungen auf Linux- oder Windows Nano Server-Hosts
description: ".NET-Microservices-Architektur für .NET-Containeranwendungen | Bereitstellen von einzelnen auf Containern basierenden .NET Core-Webanwendungen auf Linux- oder Windows Nano Server-Hosts"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 73d733a45837d047319312ea7b2e558a02b39eba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-single-container-based-net-core-web-applications-on-linux-or-windows-nano-server-hosts"></a>Bereitstellen von einzelnen auf Containern basierenden .NET Core-Webanwendungen auf Linux- oder Windows Nano Server-Hosts

*Sie können Docker-Container für die monolithische Bereitstellung von einfachen Webanwendungen verwenden. Dies verbessert die fortlaufende Integration und die fortlaufenden Bereitstellungspipelines und unterstützt Sie bei der erfolgreichen Bereitstellung in der Produktion. Sie müssen sich nie wieder fragen, warum die Anwendung auf Ihrem Computer, aber nicht in der Produktion funktioniert.*

Eine auf Microservices basierende Architektur hat viele Vorteile, die jedoch eine erhöhte Komplexität mit sich bringen. In manchen Fällen überwiegen die Kosten die Vorteile. Dann ist die monolithische Bereitstellung einer Anwendung, die in einem einzigen oder in wenigen Containern ausgeführt wird, besser geeignet. 

Eine monolithische Anwendung in gut getrennte Microservices zu zerteilen, ist nicht einfach. Sie haben gelernt, dass diese nach Funktion partitioniert werden sollten: Microservices sollten unabhängig voneinander funktionieren, um eine widerstandsfähigere Anwendung bereitzustellen. Wenn Sie keine Feature Slices der Anwendung bereitstellen können, führt das Trennen derselben nur zu erhöhter Komplexität.

Eine Anwendung muss möglicherweise noch keine Features unabhängig voneinander skalieren. Nehmen wir an, dass der Datenverkehr es zu einem frühen Zeitpunkt im Lebenszyklus Ihrer eShopOnContainers-Verweisanwendung nicht gerechtfertigt hat, dass die Features in verschiedene Microservices aufgeteilt werden. Der Datenverkehr war gering genug, sodass das Hinzufügen von Ressourcen zu einem Dienst üblicherweise bedeutet hat, dass Ressourcen zu allen Diensten hinzugefügt werden. Die zusätzliche Arbeit, die Anwendung in diskrete Dienste aufzuteilen, resultiert nur in minimalen Vorteilen.

Zudem haben Sie zu einem frühen Zeitpunkt während der Entwicklung einer Anwendung möglicherweise noch keine Vorstellung davon, wo die natürlichen funktionalen Grenzen liegen. Beim Entwickeln eines mindestens anwendungsfähigen Produkts könnte die natürliche Trennung noch nicht verfügbar sein.

Einige dieser Bedingungen können temporär sein. Sie können mit dem Erstellen einer monolithischen Anwendung beginnen und später einige Features trennen, damit diese als Microservices entwickelt und bereitgestellt werden. Andere Bedingungen können entscheidend für den Problembereich der Anwendung sein. Das bedeutet, dass die Anwendung möglicherweise nicht in mehrere Microservices unterteilt werden kann.

Das Trennen einer Anwendung in viele diskrete Prozesse führt außerdem zu Mehraufwand. Durch das Teilen der Features in verschiedene Prozesse wird die Komplexität erhöht. Die Kommunikationsprotokolle werden komplexer. Anstelle von Methodenaufrufen müssen Sie asynchrone Kommunikationen zwischen den Diensten verwenden. Wenn Sie eine Microservices-Architektur verschieben, müssen Sie viele der Bausteine hinzufügen, die in die Microservices-Version der eShopOnContainers-Anwendung implementiert sind: Eventbusbehandlung, Meldungsstabilität und -wiederholungen, Eventual Consistency usw.

Eine wesentlich vereinfachte Version von eShopOnContainers (namens [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic), im selben GitHub-Repository enthalten) wird als monolithische MVC-Anwendung ausgeführt. Wie gerade beschrieben, entstehen durch diese Entwurfsentscheidung Vorteile. Sie können die Quelle für diese Anwendung von GitHub herunterladen und diese lokal ausführen. Auch die monolithische Anwendung profitiert von der Bereitstellung in einer Containerumgebung.

Durch die Containerumgebung wird jede Instanz der Anwendung in derselben Umgebung ausgeführt. Dies schließt die Entwicklungsumgebung ein, in der das frühe Testen und die Entwicklung stattfinden. Das Entwicklungsteam kann die Anwendung in einer Containerumgebung ausführen, die der Produktionsumgebung entspricht.

Zusätzlich können Containeranwendungen zu geringeren Kosten skaliert werden. Wie zuvor gezeigt wurde, ermöglicht die Containerumgebung eine größere Ressourcenfreigabe als die herkömmlichen VM-Umgebungen.

Schließlich erzwingt das Containerisieren einer Anwendung eine Trennung zwischen der Geschäftslogik und dem Speicherserver. Wenn die Anwendung skaliert wird, verwenden alle Container ein einziges physisches Speichermedium. In der Regel ist dies ein Hochverfügbarkeitsserver, auf dem eine SQL Server-Datenbank ausgeführt wird.

## <a name="application-tour"></a>Überblick über die Anwendung

Die [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic)-Anwendung stellt einige der eShopOnContainers-Anwendungen dar, die als monolithische Anwendungen ausgeführt werden – eine auf ASP.NET Core MVC basierte Anwendung, die auf .NET Core ausgeführt wird. Diese stellt hauptsächlich die Funktionen zum Durchsuchen des Katalogs bereit, die in vorherigen Abschnitten beschrieben wurden.

Die Anwendung verwendet eine SQL Server-Datenbank für den Katalogspeicher. In auf Containern basierten Bereitstellungen kann diese monolithische Anwendung auf denselben Datenspeicher wie die auf Microservices basierte Anwendung zugreifen. Die Anwendung wird dafür konfiguriert, SQL Server in einem Container neben der monolithischen Anwendung auszuführen. In einer Produktionsumgebung wird SQL Server auf einem Hochverfügbarkeitscomputer außerhalb des Docker-Hosts ausgeführt. Zur Vereinfachung wird empfohlen, SQL Server in einer Entwicklungs- oder Testumgebung in einem eigenen Container auszuführen.

Die anfänglich festgelegten Features ermöglichen nur das Durchsuchen des Katalogs. Updates aktivieren die vollständige Featuregruppe der Containeranwendung. Eine erweiterte Architektur einer monolithischen Webanwendung wird im E-Book [Architekturmethoden für ASP.NET-Webanwendungen](https://aka.ms/webappebook) und in der zugehörigen [eShopOnWeb-Beispielanwendung](http://aka.ms/WebAppArchitecture) beschrieben. In diesem Fall wird diese jedoch nicht in Docker-Containern ausgeführt, da das Szenario sich auf die reine Webentwicklung mit ASP.NET Core konzentriert.

Die vereinfachte Version, die in eShopOnContainers (eShopWeb) verfügbar ist, wird jedoch in einem Docker-Container ausgeführt.

## <a name="docker-support"></a>Docker-Unterstützung

Das eShopOnWeb-Projekt wird auf .NET Core ausgeführt. Darum kann es entweder auf Linux- oder auf Windows-basierten Containern ausgeführt werden. Beachten Sie, dass Sie für die Docker-Bereitstellung den gleichen Hosttyp für SQL Server verwenden sollten. Linux-basierte Container haben einen geringeren Speicherbedarf und werden bevorzugt.

Visual Studio stellt eine Projektvorlage bereit, die die Unterstützung von Docker zu einer Projektmappe hinzufügt. Klicken Sie mit der rechten Maustaste auf das Projekt und dann auf **Hinzufügen** und **Docker-Unterstützung**. Die Vorlage fügt eine Dockerfile und ein neues **Docker-Compose**-Projekt, das die Startdatei „docker-compose.yml“ bereitstellt, zu Ihrem Projekt hinzu. Dieser Schritt wurde bereits in dem eShopOnWeb-Projekt durchgeführt, das von GitHub heruntergeladen wurde. Ihnen wird angezeigt, dass die Projektmappe die Projekte **eShopOnWeb** und **Docker-Compose** wie in Abbildung 6-1 dargestellt enthält.

![](./media/image1.png)

**Abbildung 6-1**. Das **Docker-Compose**-Projekt in einer einzigen Container-Webanwendung

Bei diesen Dateien handelt es sich um Standarddateien von Docker-Compose, die mit jedem Docker-Projekt konsistent sind. Sie können diese mit Visual Studio oder über die Befehlszeile verwenden. Diese Anwendung wird auf .NET Core ausgeführt und verwendet Linux-Container. Somit ist das Codieren, Erstellen und Ausführen auf einem Mac- oder einem Linux-Computer möglich.

Die Datei „docker-compose.yml“ enthält Informationen darüber, welche Images erstellt und welche Container gestartet werden müssen. Die Vorlagen geben an, wie das eShopWeb-Image erstellt und der Container der Anwendung ausgeführt wird. Sie müssen die Abhängigkeit von einem SQL Server hinzufügen, indem Sie ein Image für diesen (z.B. mssql-server-linux) integrieren sowie einen Dienst für das Image „sql.data“, damit Docker diesen Container erstellen und starten kann. Diese Einstellungen sind im folgenden Beispiel dargestellt:

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

Die Anweisung „depends\_on“ teilt Docker mit, dass das eShopWeb-Image vom sql.data-Image abhängig ist. Bei den nachfolgenden Zeilen handelt es sich um Anweisungen, um das Image „sql.data“ mithilfe des Images „microsoft/mssql-server-linux“ zu erstellen.

Das **Docker-Compose**-Projekt zeigt die anderen Docker-Compose-Dateien unter dem Hauptknoten „docker-compose.yml“ an, damit die Verknüpfung dieser Dateien erkennbar ist. Die Datei „docker-compose-override.yml“ enthält Einstellungen für beide Dienste, z.B. Verbindungszeichenfolgen und andere Anwendungseinstellungen.

Das folgende Beispiel zeigt die Datei „docker-compose.vs.debug.yml“, die Einstellungen enthält, die für das Debuggen in Visual Studio verwendet werden. In dieser Datei ist dem eShopWeb-Image der Entwicklungstag angefügt. Dadurch können Debug-Images besser von Release-Images getrennt werden, sodass Sie die Debuginformationen nicht versehentlich in einer Produktionsumgebung bereitstellen:

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

Die letzte hinzugefügte Datei ist „docker-compose.ci.build.yml“. Diese wird über die Befehlszeile verwendet, um das Projekt von einem CI-Server zu erstellen. Diese compose-Datei startet einen Docker-Container, der das für die Anwendung benötigte Image erstellt. Das folgende Beispiel zeigt die Inhalte der Datei „docker-compose.ci.build.yml“.

```yml
version: '2'
  
services:
  ci-build:
    image: microsoft/aspnetcore-build:1.0-1.1
    volumes:
      - .:/src
    working_dir: /src
  command: /bin/bash -c "dotnet restore ./eShopWeb.sln && dotnet publish  ./eShopWeb.sln -c Release -o ./obj/Docker/publish"
```

**Hinweis**: Ab .NET Core 2.0 wird der Befehl „dotnet restore“ automatisch beim Ausführen von „dotnet publish“ ausgeführt.

Beachten Sie, dass das Image ein ASP.NET Core-Buildimage ist. Dieses Image enthält das SDK und Buildtools, um Ihre Anwendung und die erforderlichen Images zu erstellen. Das Ausführen des **Docker-Compose**-Projekts mit dieser Datei startet den Buildcontainer aus dem Image und erstellt dann das Image der Anwendung in diesem Container. Sie geben die Docker-Compose-Datei als Teil der Befehlszeile an, um Ihre Anwendung in einem Docker-Container zu erstellen und diese anschließend zu starten.

In Visual Studio können Sie Ihre Anwendung in Docker-Containern starten, indem Sie das **Docker-Compose**-Projekt als Startprojekt auswählen und dann wie bei jeder anderen Anwendung STRG+F5 (F5 zum Debuggen) drücken. Wenn Sie das **Docker-Compose**-Projekt starten, führt Visual Studio **Docker-Compose** mithilfe der Dateien „docker-compose.yml“ und „compose.override.yml“ sowie einer der docker-compose.vs.\*-Dateien aus. Nachdem die Anwendung gestartet wurde, startet Visual Studio den Browser für Sie.

Wenn Sie die Anwendung im Debugger ausführen, wird Visual Studio an die ausgeführte Anwendung in Docker angefügt.

## <a name="troubleshooting"></a>Problembehandlung

Dieser Abschnitt beschreibt einige Probleme, die auftreten können, wenn Sie Container lokal ausführen und schlägt einige Lösungen vor.

### <a name="stopping-docker-containers"></a>Anhalten von Docker-Containern 

Nachdem Sie die Containeranwendung gestartet haben, wird der Container weiter ausgeführt, auch nachdem Sie das Debuggen beendet haben. Sie können den Befehl „docker ps“ von der Befehlszeile aus ausführen, um die ausgeführten Container anzuzeigen. Der Befehl „docker stop“ hält wie in Abbildung 6-2 gezeigt den ausgeführten Container an.

![](./media/image2.png)

**Abbildung 6-2**. Auflisten und Anhalten von Containern mit den CLI-Befehlen „docker ps“ und „docker stop“

Sie sollten ausgeführte Prozesse beenden, wenn Sie zwischen verschiedenen Konfigurationen wechseln. Andernfalls verwendet der Container, der die Webanwendung ausführt, den Port für Ihre Anwendung (in diesem Beispiel 5106).

### <a name="adding-docker-to-your-projects"></a>Hinzufügen von Docker zu Ihren Projekten

Der Assistent, der die Docker-Unterstützung hinzufügt, kommuniziert mit dem ausgeführten Docker-Prozess. Der Assistent wird nicht ordnungsgemäß ausgeführt, wenn Docker beim Starten des Assistenten nicht ausgeführt wird. Darüber hinaus überprüft der Assistent Ihre aktuelle Containerwahl, um die richtige Docker-Unterstützung hinzuzufügen. Wenn Sie Unterstützung für Windows-Container hinzufügen möchten, führen Sie den Assistenten aus, während Docker mit der Konfiguration für Windows-Container ausgeführt wird. Wenn Sie Unterstützung für Linux-Container hinzufügen möchten, führen Sie den Assistenten aus, während Docker mit der Konfiguration für Linux-Container ausgeführt wird.

>[!div class="step-by-step"]
[Zurück] (../docker-application-development-process/docker-app-development-workflow.md) [Weiter] (../containerize-net-framework-applications/index.md)
