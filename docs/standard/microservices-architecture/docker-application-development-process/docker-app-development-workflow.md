---
title: Entwicklungsworkflow für Docker-Apps
description: .NET Microservices-Architektur für .NET-Containeranwendungen | Entwicklungsworkflow für Docker-Apps
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 2e29e88a104050230b7816da6793120d61de7bc6
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314951"
---
# <a name="development-workflow-for-docker-apps"></a>Entwicklungsworkflow für Docker-Apps

Der Lebenszyklus der Anwendungsentwicklung beginnt am Computer eines Entwicklers, an dem dieser die Anwendung mithilfe seiner bevorzugten Sprache codiert und lokal testet. Unabhängig davon, welche Sprache, welches Framework und welche Plattform die Entwickler wählen, entwickeln und testen sie mit diesem Workflow Docker-Container stets lokal.

Jeder Container (eine Instanz eines Docker-Images) umfasst die folgenden Komponenten:

-   Eine Betriebssystemauswahl (z.B. eine Linux-Distribution, Windows Nano Server oder Windows Server Core).

-   Dateien, die vom Entwickler hinzugefügt wurden (Anwendungsbinärdateien usw.).

-   Konfigurationsinformationen (Umgebungseinstellungen und Abhängigkeiten).

## <a name="workflow-for-developing-docker-container-based-applications"></a>Workflow für die Entwicklung von Docker-Container-basierten Anwendungen

In diesem Abschnitt wird der *Entwicklungsworkflow* für Docker-Container-basierte Anwendungen beschrieben. Der Entwicklungsworkflow berücksichtigt den größeren DevOps-Workflow nicht und konzentriert sich nur auf die Entwicklungsarbeit, die am Computer des Entwicklers vorgenommen wird. Die ersten Schritte zum Einrichten der Umgebung wurden nicht berücksichtigt, da diese nur einmal durchgeführt werden.

Eine Anwendung besteht aus Ihren eigenen Diensten sowie zusätzlichen Bibliotheken (Abhängigkeiten). Im Folgenden sind die grundlegenden Schritte dargestellt, die Sie normalerweise beim Erstellen einer Docker-Anwendung ausführen, wie in Abbildung 5-1 dargestellt.

![](./media/image1.png)

**Abbildung 5-1.** Workflowschritte für die Entwicklung von Containeranwendungen für Docker

In diesem Handbuch wird der gesamte Prozess ausführlich beschrieben, und jeder wichtige Schritt wird unter besonderer Berücksichtigung einer Visual Studio-Umgebung erläutert.

Bei Verwendung eines Editor-/CLI-Entwicklungsansatzes (z.B. Visual Studio Code plus Docker-CLI auf MacOS oder Windows) müssen Sie die einzelnen Schritte in der Regel detaillierter kennen als bei Verwendung von Visual Studio. Weitere Informationen zum Arbeiten in einer CLI-Umgebung finden Sie im E-Book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools (Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools)](http://aka.ms/dockerlifecycleebook/).

Wenn Sie Visual Studio 2015 oder Visual Studio 2017 verwenden, werden viele dieser Schritte für Sie ausgeführt, wodurch sich Ihre Produktivität entscheidend erhöht. Dies gilt insbesondere, Visual Studio 2017 verwenden und Anwendungen mit mehreren Containern das Ziel sind. Visual Studio fügt beispielsweise mit nur einem Mausklick die Dateien Dockerfile und docker-compose.yml mit der Konfiguration für Ihre Anwendung Ihren Projekten hinzu. Wenn Sie die Anwendung in Visual Studio ausführen, wird das Docker-Image erstellt und die Anwendung mit mehreren Containern wird direkt in Docker ausgeführt. Sie haben sogar die Möglichkeit, mehrere Container auf einmal zu debuggen. Diese Features erhöhen Ihre Entwicklungsgeschwindigkeit.

Allerdings bedeutet die Tatsache, dass Visual Studio die Schritte automatisch ausführt, nicht, dass Sie nicht wissen müssen, was im Hintergrund mit Docker geschieht. Daher werden die einzelnen Schritte im Folgenden ausführlich beschrieben.

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>Schritt 1. Beginnen Sie mit dem Codieren, und erstellen Sie eine erste Anwendungs- oder Dienstbaseline

Das Entwickeln einer Docker-Anwendung ist mit der Art und Weise vergleichbar, wie Anwendungen ohne Docker entwickelt werden. Der Unterschied besteht darin, dass Sie beim Entwickeln für Docker eine Anwendung oder Dienste bereitstellen und testen, die in Docker-Containern in Ihrer lokalen Umgebung ausgeführt werden. Bei dem Container kann es sich um einen Linux-Container oder einen Windows-Container handeln.

### <a name="set-up-your-local-environment-with-visual-studio"></a>Einrichten der lokalen Umgebung mit Visual Studio

Stellen Sie zuerst sicher, dass [Docker Community Edition (CE)](https://www.docker.com/community-edition) für Windows wie nachfolgend erläutert installiert wurde:

[Get started with Docker CE for Windows (Erste Schritte mit Docker CE für Windows)](https://docs.docker.com/docker-for-windows/)

Darüber hinaus muss Visual Studio 2017 installiert sein. Diese Version erhält den Vorzug vor Visual Studio 2015 mit dem Add-In Visual Studio-Tools für Docker, da Visual Studio 2017 eine fortschrittlichere Unterstützung für Docker bietet, z.B. Unterstützung für das Debuggen von Containern. Visual Studio 2017 umfasst die Tools für Docker, wenn Sie die **.NET Core und Docker**-Workload während der Installation, wie in Abbildung 5-2 dargestellt, ausgewählt haben.

![](./media/image3.png)

**Abbildung 5-2**. Auswählen der **.NET Core und Docker**-Workload während der Installation von Visual Studio 2017

Sie können sogar vor dem Aktivieren von Docker in der Anwendung und Bereitstellen und Testen in Docker mit dem Codieren der Anwendung im einfachen .NET (normalerweise in .NET Core, wenn Sie Container verwenden möchten) beginnen. Allerdings wird empfohlen, dass Sie so bald wie möglich mit Docker arbeiten, d.h. in der realen Umgebung, sodass etwaige Probleme schnellstmöglich erkannt werden können. Dies wird empfohlen, da Visual Studio die Arbeit mit Docker so erleichtert, dass sie fast transparent erscheint – insbesondere beim Debuggen von Anwendungen mit mehreren Containern über Visual Studio.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Get started with Docker CE for Windows (Erste Schritte mit Docker CE für Windows)**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

-   **Visual Studio 2017**
    [*https://visualstudio.microsoft.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>Schritt 2 Erstellen Sie eine Dockerfile-Datei im Zusammenhang mit einem vorhandenen .NET-Basisimage

Für jedes benutzerdefinierte Image, das Sie erstellen möchten, benötigen Sie eine Dockerfile-Datei. Außerdem benötigen Sie eine Dockerfile-Datei für jeden bereitzustellenden Container unabhängig davon, ob Sie automatisch über Visual Studio oder manuell mithilfe der Docker-CLI bereitstellen (Befehle „docker run“ und „docker-compose“). Wenn Ihre Anwendung einen benutzerdefinierten Dienst enthält, benötigen Sie eine einzelne Dockerfile-Datei. Wenn Ihre Anwendung mehrere Dienste enthält (wie in einer Microservicearchitektur), benötigen Sie pro Dienst eine Dockerfile-Datei.

Die Dockerfile-Datei befindet sich im Stammordner der Anwendung oder des Diensts. Sie enthält die Befehle, die Docker mitteilen, wie die Anwendung oder der Dienst in einem Container eingerichtet und ausgeführt werden sollen. Sie können eine Dockerfile-Datei manuell im Code erstellen und mit Ihren .NET-Abhängigkeiten Ihrem Projekt hinzufügen.

Mit Visual Studio und den Tools für Docker erledigen Sie diese Aufgabe mit einigen wenigen Mausklicks. Beim Erstellen eines neuen Projekts in Visual Studio 2017 ist die Option **Enable Container (Docker) Support** (Containerunterstützung (Docker) aktivieren) verfügbar, wie in Abbildung 5-3 dargestellt.

![](./media/image5.png)

**Abbildung 5-3**. Aktivieren der Unterstützung für Docker beim Erstellen eines neuen Projekts in Visual Studio 2017

Sie können auch Docker-Unterstützung für ein neues oder vorhandenes Projekt aktivieren, indem Sie mit der rechten Maustaste auf der Projektdatei in Visual Studio klicken und die Option **Add-Docker Project Support** (Docker-Projektunterstützung hinzufügen), wie in Abbildung 5-4 dargestellt, auswählen.

![](./media/image6.png)

**Abbildung 5-4**. Aktivieren der Unterstützung für Docker in einem vorhandenen Visual Studio 2017-Projekt

Diese Aktion für ein Projekt (z.B. eine ASP.NET-Webanwendung oder ein Web-API-Dienst) fügt dem Projekt mit der erforderlichen Konfiguration eine Dockerfile-Datei hinzu. Darüber hinaus wird eine docker-compose.yml-Datei für die gesamte Projektmappe hinzugefügt. In den folgenden Abschnitten werden die Informationen beschrieben, die in diese Dateien übernommen werden. Obwohl Visual Studio Ihnen diese Aufgabe abnehmen kann, ist es ist wichtig zu wissen, was in eine Dockerfile-Datei übernommen wird.

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a>Option A: Erstellen eines Projekts mit einem vorhandenen offiziellen .NET Docker-Image

Sie erstellen ein benutzerdefiniertes Image für den Container in der Regel auf einem Basisimage, das Sie von einem offiziellen-Repository in der [Docker-Hub](https://hub.docker.com/)-Registrierung erhalten. Das ist genau das, was im Hintergrund geschieht, wenn Sie die Docker-Unterstützung in Visual Studio aktivieren. Die Dockerfile-Datei verwendet ein vorhandenes Aspnetcore-Image.

Es wurde bereits erläutert, welche Docker-Images und Repositorys Sie abhängig vom Framework und Betriebssystem, das Sie ausgewählt haben, verwenden können. Wenn Sie beispielsweise ASP.NET Core (Linux oder Windows) verwenden möchten, muss das Image microsoft/aspnetcore:2.0 verwendet werden. Aus diesem Grund müssen Sie nur angeben, welche Docker-Basisimages Sie für den Container verwenden werden. Fügen Sie zu diesem Zweck FROM microsoft/aspnetcore:2.0 in die Dockerfile-Datei ein. Dies wird automatisch von Visual Studio ausgeführt, aber wenn Sie die Version aktualisieren müssen, aktualisieren Sie diesen Wert.

Durch Verwendung eines offiziellen .NET Image-Repositorys von Docker-Hub mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (Entwicklung, Test und Produktion) verfügbar sind.

Das folgende Beispiel veranschaulicht eine Dockerfile-Beispieldatei für einen ASP.NET Core-Container.

```Dockerfile
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

In diesem Fall basiert der Container auf Version 2.0 des offiziellen ASP.NET Core-Docker-Images (Multi-Arch für Linux und Windows). Dies ist die Einstellung `FROM microsoft/aspnetcore:2.0`. (Weitere Details zu diesem Basisimage finden Sie auf den Seiten [ASP.NET Core Docker Image (ASP.NET Core-Docker-Image)](https://hub.docker.com/r/microsoft/aspnetcore/) und [.NET Core Docker Image (.NET Core-Docker-Image)](https://hub.docker.com/r/microsoft/dotnet/).) In der Dockerfile-Datei müssen Sie auch angeben, dass Docker an dem TCP-Port lauscht, den Sie zur Runtime verwenden (in diesem Fall Port 80 gemäß Konfiguration mit der EXPOSE-Einstellung).

Je nach Sprache und Framework, die Sie verwenden, können Sie zusätzliche Konfigurationseinstellungen in der Dockerfile-Datei angeben. Beispielsweise weist die ENTRYPOINT-Zeile mit \["dotnet", "MySingleContainerWebApp.dll"\] Docker an, eine .NET Core-Anwendung auszuführen. Wenn Sie das SDK und die .NET Core-CLI (Dotnet CLI) verwenden, um die .NET-Anwendung zu entwickeln und auszuführen, wird eine andere Einstellung verwendet. Entscheidend ist, dass die ENTRYPOINT-Zeile und andere Einstellungen je nach Sprache und Plattform variieren können, die Sie für Ihre Anwendung auswählen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Erstellen von Docker-Images für .NET Core-Anwendungen**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)

-   **Build your own image (Entwickeln eines eigenen Images)**. In der offiziellen Docker-Dokumentation.
    [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a>Verwenden von Repositorys für Images für mehrere Architekturen

Ein Repository kann Plattformvarianten enthalten, wie z.B. ein Linux-Image und ein Windows-Image. Dieses Feature ermöglicht Anbietern wie Microsoft (Basisimageentwickler), ein Repository für mehrere Plattformen (Linux und Windows) zu entwickeln. Das in der Docker-Hub-Registrierung verfügbare [Microsoft/Dotnet](https://hub.docker.com/r/microsoft/aspnetcore/)-Repository bietet beispielsweise Unterstützung für Linux und Windows Nano Server dadurch, dass der gleiche Repositoryname verwendet wird.

Wenn Sie ein explizites Tag für eine bestimmte Plattform angeben, wie in den folgenden Fällen:

-   **microsoft/aspnetcore:2.0.0-jessie**

        .NET Core 2.0 runtime-only on Linux 

-   **microsoft/aspnetcore:2.0.0-nanoserver**

        .NET Core 2.0 runtime-only on Windows Nano Server

Neu seit Mitte 2017 ist jedoch, dass die neuen Images für mehrere Architekturen (z.B. das aspnetcore-Image, das mehrere Architekturen unterstützt) bei Angabe des gleichen Imagenamens, auch des gleichen Tags, je nach dem von Ihnen bereitgestellten Docker-Host-Betriebssystem die Linux- oder die Windows-Version verwenden, was im folgenden Beispiel dargestellt wird:

-   **microsoft/aspnetcore:2.0**

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

Wenn Sie also ein Image von einem Windows-Host pullen, wird die Windows-Variante gepullt. Wenn der gleiche Imagename von einem Linux-Host gepullt wird, wird die Linux-Variante gepullt.

### <a name="option-b-creating-your-base-image-from-scratch"></a>Option B: Neuerstellung des Basisimages

Sie können ein eigenes Docker-Basisimage von Grund auf neu erstellen. Dieses Szenario wird Docker-Einsteigern nicht empfohlen, aber wenn Sie die bestimmten Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Multi-arch .NET Core images (.NET Core-Images für mehrere Architekturen)**.
https://github.com/dotnet/announcements/issues/14 
-   **Create a base image (Erstellen eines Basisimages)**. Offizielle Docker-Dokumentation.
    [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>Schritt 3 Erstellen Sie Ihre benutzerdefinierten Docker-Images, und betten Sie Ihre Anwendung oder Ihren Dienst in diese ein

Sie müssen für jeden Dienst in Ihrer Anwendung ein zugehöriges Image erstellen. Wenn Ihre Anwendung aus einem einzelnen Dienst oder einer einzelnen Webanwendung besteht, benötigen Sie nur ein Image.

Beachten Sie, dass die Docker-Images in Visual Studio automatisch erstellt werden. Die folgenden Schritte sind nur für den Editor-/CLI-Workflow und zur Erläuterung der Vorgänge, die im Hintergrund ablaufen, erforderlich.

Als Entwickler entwickeln und testen Sie so lange lokal, bis Sie ein abgeschlossenes Feature pushen oder zu Ihrem Quellkontrollsystem wechseln (z.B. zu GitHub). Dies bedeutet, dass Sie die Docker-Images erstellen und Container auf einem lokalen Docker-Host (Windows- oder Linux-VM) bereitstellen und für die lokalen Container ausführen, testen und debuggen müssen.

Mithilfe des Befehls „docker build“ können Sie, wie in Abbildung 5-5 gezeigt, unter Verwendung der Docker-CLI und Ihrer Dockerfile-Datei ein benutzerdefiniertes Image in ihrer lokalen Umgebung erstellen.

![](./media/image8.png)

**Abbildung 5-5**. Erstellen eines benutzerdefinierten Docker-Images

Optional können Sie, anstatt „docker build“ über den Projektordner direkt auszuführen, zuerst einen bereitstellbaren Ordner mit den erforderlichen .NET-Bibliotheken und Binärdateien generieren, indem Sie „dotnet publish“ ausführen und dann den Befehl „docker build“ verwenden.

Dadurch wird ein Docker-Image namens cesardl/netcore-webapi-microservice-docker:first erstellt. In diesem Fall ist :first ein Tag, das eine bestimmte Version darstellt. Sie können diesen Schritt für jedes benutzerdefinierte Image wiederholen, das Sie für Ihre zusammengesetzte Docker-Anwendung erstellen müssen.

Wenn eine Anwendung aus mehreren Containern besteht (d.h. es handelt sich um eine Anwendung mit mehreren Containern), können Sie auch den Befehl „docker-compose up --build“ verwenden, um alle zugehörigen Images mit einem Befehl unter Verwendung der in den zugehörigen docker-compose.yml-Dateien verfügbar gemachten Metadaten zu erstellen.

Sie können die vorhandenen Images in Ihrem lokalen Repository suchen, indem Sie den „docker images“-Befehl, wie in Abbildung 5-6 dargestellt, verwenden.

![](./media/image9.png)

**Abbildung 5-6.** Anzeigen vorhandener Images mithilfe des Befehls „docker images“

### <a name="creating-docker-images-with-visual-studio"></a>Erstellen von Docker-Images mit Visual Studio

Wenn Sie Visual Studio zum Erstellen eines Projekts mit Unterstützung für Docker verwenden, erstellen Sie nicht explizit ein Image. Stattdessen wird das Image für Sie erstellt, wenn Sie F5 drücken und die in Docker bereitgestellte Anwendung oder den Dienst ausführen. Dieser Schritt wird in Visual Studio automatisch und für Sie nicht erkennbar ausgeführt, aber es ist wichtig, dass Sie wissen, was im Hintergrund passiert.

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>Schritt 4. Definieren Sie Ihre Dienste in der Datei docker-compose.yml beim Erstellen einer Docker-Anwendung mit mehreren Containern

Mithilfe der Datei [docker compose.yml](https://docs.docker.com/compose/compose-file/) können Sie mehrere verwandte Dienste definieren, die als zusammengesetzte Anwendung mit Bereitstellungsbefehlen bereitgestellt werden sollen.

Wenn Sie eine docker-compose.yml-Datei verwenden möchten, müssen Sie die Datei in Ihrem Haupt- oder Stammlösungsordner mit Inhalt erstellen, der mit dem in dem folgenden Beispiel verwendeten vergleichbar ist:

```yml
version: '3'
  
services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment: 
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"

```

Beachten Sie, dass diese docker-compose.yml-Datei eine vereinfachte und zusammengeführte Version ist. Sie enthält die statischen Konfigurationsdaten für jeden Container (z.B. den Namen des benutzerdefinierten Images), das stets anwendbar sind, sowie Konfigurationsinformationen, die sich nach der Bereitstellungsumgebung richten können, z.B. die Verbindungszeichenfolge. In späteren Abschnitten erfahren Sie, wie Sie die Konfiguration der docker-compose.yml-Datei in mehrere docker-compose-Dateien aufteilen und Werte je nach Umgebung und Ausführungstyp (Debug oder Release) außer Kraft setzen können.

Im Beispiel der docker-compose.yml-Datei werden fünf Dienste definiert: webmvc-Dienst (Webanwendung), zwei Microservices (catalog.api und ordering.api) und ein Datenquellcontainer, sql.data, basierend auf von als Container ausgeführtem SQL Server für Linux. Da jeder Dienst als ein Container bereitgestellt wird, ist für jeden ein Docker-Image erforderlich.

Die docker-compose.yml-Datei gibt nicht nur an, welche Container verwendet werden, sondern auch, wie diese einzeln konfiguriert werden. Die webmvc-Containerdefinition in der .yml-Datei:

-   Verwendet ein vorab erstelltes eshop/web:latest-Image. Sie können jedoch das als Teil der docker-compose-Ausführung zu erstellende Image mit einer zusätzlichen, auf einem build:-Abschnitt in der docker-compose-Datei basierenden Konfiguration konfigurieren.

-   Initialisiert die beiden Umgebungsvariablen (CatalogUrl und OrderingUrl).

-   Leitet den verfügbar gemachten Port 80 für den Container an den externen Port 80 auf dem Hostcomputer weiter.

-   Verknüpft die Web-App mit dem Katalog- und Bestelldienst mit der depends\_-Einstellung. Dies bewirkt, dass der Dienst wartet, bis diese Dienste gestartet werden.

Wir gehen in einem der folgenden Abschnitte erneut auf die Datei docker-compose.yml ein, wenn wir uns damit beschäftigen, wie Microservices und Apps mit mehreren Containern implementiert werden.

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>Arbeiten mit docker-compose.yml in Visual Studio 2017

Wenn Sie Unterstützung für die Docker-Lösung einem Dienstprojekt in einer Visual Studio-Projektmappe hinzufügen, wie in Abbildung 5-7 dargestellt, fügt Visual Studio dem Projekt eine Dockerfile-Datei hinzu. Außerdem wird ein Dienstabschnitt (Projekt) mit den docker-compose.yml-Dateien in der Lösung hinzugefügt. Die Lösung mit mehreren Containern kann nun auf einfache Weise erstellt werden. Sie können dann die docker-compose.yml-Dateien öffnen und mit zusätzlichen Features aktualisieren.

![](./media/image6.png)

**Abbildung 5-7**. Hinzufügen von Docker-Unterstützung in Visual Studio 2017 durch Rechtsklick auf ein ASP.NET Core-Projekt

Wenn Sie Docker-Unterstützung in Visual Studio hinzufügen, wird nicht nur die Dockerfile-Datei zu Ihrem Projekt hinzugefügt, sondern auch die Konfigurationsinformationen werden zu mehreren globalen docker-compose.yml-Dateien hinzugefügt, die auf Lösungsebene festgelegt werden.

Nachdem Sie der Lösung in Visual Studio Docker-Unterstützung hinzugefügt haben, sehen Sie auch einen neuen Knoten (in der docker-compose.dcproj-Projektdatei) im Projektmappen-Explorer mit den hinzugefügten docker-compose.yml-Dateien, wie in Abbildung 5-8 dargestellt.

![](./media/image11.PNG)

**Abbildung 5-8**. Der im Projektmappen-Editor in Visual Studio 2017 hinzugefügte **docker-compose**-Strukturknoten

Eine Anwendung mit mehreren Containern konnte bisher unter Verwendung des Befehls docker-compose mit einer einzelnen docker-compose.yml-Datei bereitgestellt werden. Da Visual Studio jedoch eine Gruppe von Dateien hinzufügt, können Sie abhängig von der Umgebung (Entwicklung im Vergleich zur Produktion) und vom Ausführungstyp (Release im Vergleich zu Debug) Werte außer Kraft setzen. Diese Funktion wird in späteren Abschnitten erläutert.

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a>Schritt 5. Erstellen Sie Ihre Docker-Anwendung, und führen Sie sie aus

Wenn die Anwendung nur über einen einzelnen Container verfügt, können Sie sie ausführen, indem Sie sie auf dem Docker-Host (VM oder physischer Server) bereitstellen. Enthält Ihre Anwendung dagegen mehrere Dienste, können Sie sie als zusammengesetzte Anwendung bereitstellen, indem Sie entweder einen einzelnen CLI-Befehl (docker-compose up) oder Visual Studio verwenden, wobei der Befehl dann im Hintergrund ausgeführt wird. Betrachten wir die unterschiedlichen Optionen.

### <a name="option-a-running-a-single-container-with-docker-cli"></a>Option A: Ausführen eines einzelnen-Containers mit Docker-CLI

Sie können einen Docker-Container mit dem Befehl „docker run“, wie in Abbildung 5-9 dargestellt, ausführen:

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

**Abbildung 5-9**. Ausführen eines Docker-Containers mithilfe des Befehls „docker run“

In diesem Fall bindet der Befehl den internen Port 5000 des Containers an Port 80 des Hostcomputers. Dies bedeutet, dass der Host an Port 80 lauscht und an Port 5000 des Containers weiterleitet.

### <a name="option-b-running-a-multi-container-application"></a>Option B: Ausführen einer Anwendung mit mehreren Containern

In den meisten Unternehmensszenarios setzt sich eine Docker-Anwendung aus mehreren Diensten zusammen. Dies bedeutet, dass Sie eine Anwendung mit mehreren Containern, wie in Abbildung 5-10 dargestellt, ausführen müssen.

![](./media/image14.png)

**Abbildung 5-10**. VM mit bereitgestellten Docker-Containern

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a>Ausführen einer Anwendung mit mehreren Containern mithilfe der Docker-CLI

Zum Ausführen einer Anwendung mit mehreren Containern mithilfe der Docker-CLI können Sie den Befehl „docker-compose up“ ausführen. Dieser Befehl stellt mithilfe der docker-compose.yml-Datei, die auf Projektmappenebene verfügbar ist, eine Anwendung mit mehreren Containern bereit. Abbildung 5-11 zeigt die Ergebnisse an, wenn der Befehl aus Ihrem Hauptprojektverzeichnis ausgeführt wird, das die docker-compose.yml-Datei enthält.

![](./media/image15.png)

**Abbildung 5-11**. Beispielergebnisse bei der Ausführung des Befehls „docker-compose up“

Nachdem der Befehl „docker-compose up“ ausgeführt wurde, werden die Anwendung und ihre zugehörigen Container in Ihrem Docker-Host bereitgestellt, wie in der VM-Darstellung in Abbildung 5-10 dargestellt.

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a>Ausführen und Debuggen einer Anwendung mit mehreren Containern mithilfe von Visual Studio 

Das Ausführen einer Anwendung mit mehreren Containern mit Visual Studio 2017 ist denkbar einfach. Sie können nicht nur die Anwendung mit mehreren Containern ausführen, sondern alle Container direkt in Visual Studio debuggen, indem Sie reguläre Haltepunkte festlegen.

Wie bereits erwähnt, wird jedes Mal, wenn Sie Unterstützung für die Docker-Projektmappe einem Projekt in einer Projektmappe hinzufügen, das Projekt in der globalen docker-compose.yml-Datei (Projektmappenebene) konfiguriert wird, wodurch Sie die gesamte Projektmappe auf einmal ausführen oder debuggen können. Visual Studio startet einen Container für jede Projektmappe, für die die Docker-Projektmappenunterstützung aktiviert ist, und führt alle internen Schritte aus (dotnet publish, docker build usw.).

Wichtig dabei ist, dass Visual Studio 2017, wie in Abbildung 5-12 dargestellt, über einen zusätzlichen **Docker**-Befehl für die Aktion der F5-Taste verfügt. Diese Option ermöglicht Ihnen, eine Anwendung mit mehreren Containern auszuführen oder zu debuggen, indem Sie alle in den docker-compose.yml-Dateien auf Projektmappenebene definierten Container ausführen. Die Möglichkeit, Lösungen mit mehreren Containern zu debuggen, bedeutet, das Sie mehrere Haltepunkte festlegen und jeden Haltepunkt in einem anderen Projekt (Container) festlegen können. Während des Debuggings in Visual Studio halten Sie an Haltepunkten an, die in verschiedenen Projekten definiert sind und in verschiedenen Containern ausgeführt werden.

![](./media/image16.png)

**Abbildung 5-12**. Ausführen von Apps mit mehreren Containern in Visual Studio 2017

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Bereitstellen eines ASP.NET-Containers mit einem Docker-Remotehost**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>Ein Hinweis zum Testen und Bereitstellen mit Orchestratoren

Die Befehle „docker-compose up“ und „docker run“ (oder Ausführen und Debuggen der Container in Visual Studio) sind zum Testen von Containern in der Entwicklungsumgebung geeignet. Sie sollten diese Methode jedoch nicht verwenden, wenn Docker-Cluster und Orchestratoren wie Docker Swarm, Mesosphere DC/OS oder Kubernetes als Ziel dienen. Wenn Sie einen Cluster wie [Docker Swarm-Modus](https://docs.docker.com/engine/swarm/) (in Docker CE für Windows und Mac ab Version 1.12 verfügbar) verwenden, müssen Sie mit zusätzlichen Befehlen wie [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) für einzelne Dienste bereitstellen und testen. Wenn Sie eine aus mehreren Containern bestehende Anwendung bereitstellen, verwenden Sie [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) und [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/), um die zusammengesetzte Anwendung als *Stapel* bereitzustellen. Weitere Informationen finden Sie im Blogbeitrag [Introducing Experimental Distributed Application Bundles (Einführung in experimentelle verteilte Anwendungsbündel Bündel)](https://blog.docker.com/2016/06/docker-app-bundle/) in der Docker-Dokumentation. auf der Docker-Website.

Für [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) und [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) verwenden Sie ebenfalls unterschiedliche Bereitstellungsbefehle und Skripts.

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>Schritt 6. Testen Sie die Docker-Anwendung mithilfe des lokalen Docker-Hosts

Dieser Schritt hängt davon ab, welche Vorgänge die Anwendung ausführt. In einer einfachen .NET Core-Webanwendung, die als einzelner Container oder Dienst bereitgestellt wird, können Sie auf den Dienst zugreifen, indem Sie einen Browser auf dem Docker-Host öffnen und, wie in Abbildung 5-13 gezeigt, zu dieser Site navigieren. (Wenn die Konfiguration in der Docker-Datei den Container einem anderen Port als Port 80 auf dem Host zuordnet, berücksichtigen Sie den Host-Port in der URL.)

![](./media/image18.png)

**Abbildung 5-13**. Beispiel für das lokale Testen der Docker-Anwendung mithilfe von „localhost“

Wenn „localhost“ nicht auf die Docker-Host-IP verweist (was bei Verwendung von Docker CE jedoch standardmäßig der Fall sein sollte), verwenden Sie die IP-Adresse der Netzwerkkarte Ihres Computers, um zum Dienst zu navigieren.

Beachten Sie, dass diese URL im Browser Port 80 für das besprochene Containerbeispiel verwendet. Allerdings werden intern die Anforderungen zu Port 5000 umgeleitet, da die Bereitstellung, wie in einem vorherigen Schritt beschrieben, mit dem Befehl „docker run“ erfolgte.

Sie können die Anwendung auch mithilfe von „curl“ über das Terminal testen, was in Abbildung 5-14 dargestellt wird. Bei einer Docker-Installation unter Windows lautet die standardmäßige Docker-Host-IP zusätzlich zur eigentlichen IP-Adresse Ihres Computers stets 10.0.75.1.

![](./media/image19.png)

**Abbildung 5-14**. Beispiel für das Testen der Docker-Anwendung mithilfe von „curl“

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>Testen und Debuggen von Containern mit Visual Studio 2017

Beim Ausführen und Debuggen des Containers mit Visual Studio 2017 können Sie die .NET-Anwendung in etwa so debuggen wie ohne Ausführung von Containern.

### <a name="testing-and-debugging-without-visual-studio"></a>Testen und Debuggen ohne Visual Studio

Wenn Sie mit dem Editor-/CLI-Ansatz entwickeln, ist das Debuggen von Containern schwieriger. Es ist ratsam zu debuggen, indem Traces generiert werden.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Debuggen von Apps in einem lokalen Docker-Container**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

-   **Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker (Erstellen, Debuggen, Bereitstellen von ASP.NET Core-Apps mit Docker).** Video.
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Vereinfachter Workflow bei der Entwicklung von Containern mit Visual Studio

Der Workflow bei Verwendung von Visual Studio ist wesentlich einfacher als bei Verwendung des Editor/CLI-Ansatzes. Die meisten der von Docker vorausgesetzten Schritte in Zusammenhang mit der Dockerfile-Datei und den docker-compose.yml-Dateien werden, wie in Abbildung 5-15 gezeigt, von Visual Studio ausgeblendet oder vereinfacht.

![](./media/image20.png)

**Abbildung 5-15**. Vereinfachter Workflow bei der Entwicklung mit Visual Studio

Darüber hinaus müssen Sie Schritt 2 (Hinzufügen von Docker-Unterstützung in Ihren Projekten) nur einmal ausführen. Aus diesem Grund ähnelt der Workflow den üblichen Entwicklungsaufgaben bei Verwendung von .NET für andere Entwicklungsarbeiten. Sie müssen wissen, was im Hintergrund passiert (Imageerstellungsprozess, verwendete Basisimages, Bereitstellung von Containern usw.), und in einigen Fällen müssen Sie auch die Dockerfile-Datei oder die docker-compose.yml-Datei bearbeiten. Aber der Großteil der Arbeit wird durch Verwendung von Visual Studio, stark vereinfacht, und Ihre Produktivität wird entscheidend erhöht.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **.NET Docker Development with Visual Studio 2017 (.NET-Docker-Entwicklung mit Visual Studio 2017)**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

-   **Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio (Versetzen einer .NET Core-App in einen Container mit den neuen Docker-Tools für Visual Studio)**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Verwenden von PowerShell-Befehlen in einer Dockerfile-Datei zum Einrichten von Windows-Containern 

[Windows-Container](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) ermöglichen es Ihnen, Ihre vorhandenen Windows-Anwendungen in Docker-Images zu konvertieren und diese mit den gleichen Tools wie den Rest des Docker-Ökosystems bereitzustellen. Um Windows-Container zu verwenden, führen Sie PowerShell-Befehle in der Dockerfile-Datei aus, was im folgenden Beispiel gezeigt wird:

```Dockerfile
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

In diesem Fall wird ein Windows Server Core-Basisimage (FROM-Einstellung) verwendet und IIS wird mit einem PowerShell-Befehl ausgeführt (RUN-Einstellung). Auf ähnliche Weise können Sie auch PowerShell-Befehle verwenden, um zusätzliche Komponenten wie ASP.NET 4.x, .NET 4.6 oder andere Windows-Software einzurichten. Der folgende Befehl in einer Dockerfile-Datei richtet z.B. ASP.NET 4.5 ein:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **aspnet-docker/Dockerfile.** PowerShell-Beispielbefehle, die über Dockerfile-Dateien ausgeführt werden, um Windows-Features zu berücksichtigen.
    [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
[Zurück] (index.md) [Weiter] (../net-core-single-containers-linux-windows-server-hosts/index.md)
