---
title: "Entwicklungsworkflow für Docker-apps"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Entwicklungsworkflow für Docker-apps"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5a53aee4261a5a0bfc25b3520c50cf505b84f287
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="development-workflow-for-docker-apps"></a>Entwicklungsworkflow für Docker-apps

Lebenszyklus der Anwendungsentwicklung beginnt bei jeder Entwickler-Computer, wie der Entwickler codes die Anwendung, die ihre bevorzugte Programmiersprache und wird lokal überprüft. Unabhängig davon, welche Sprache, Framework- und Plattform, die der Entwickler mit diesem Workflow, wählt ist der Entwickler immer entwickeln und Testen des Docker-Containern, aber auf diese Weise lokal.

Jeder Container (eine Instanz des Docker-Images) umfasst die folgenden Komponenten:

-   Eine Auswahl des Betriebssystems (z. B. eine Linux-Distribution, Windows Nano Server oder Windows Server Core).

-   Dateien, die vom Entwickler (Binärdateien der Anwendung usw.) hinzugefügt werden.

-   Konfigurationsinformationen (umgebungseinstellungen und Abhängigkeiten).

## <a name="workflow-for-developing-docker-container-based-applications"></a>Workflow für die Entwicklung von Docker Container-basierte Anwendungen

In diesem Abschnitt wird beschrieben, die *innere Schleife* Entwicklungsworkflow für Docker-Container-basierte Anwendungen. Die innere Schleife Workflow bedeutet, dass sie wird ohne Berücksichtigung den größeren DevOps-Workflow und konzentriert sich nur auf die Entwicklungsarbeit, die auf dem Computer des Entwicklers vorgenommen. Die ersten Schritte zum Einrichten der Umgebung sind nicht eingeschlossen werden, da diese nur einmal gemacht werden.

Eine Anwendung besteht aus Ihrer eigenen Services plus zusätzliche Bibliotheken (Abhängigkeiten). Im folgenden sind die grundlegenden Schritte, die Sie normalerweise beim Erstellen einer Anwendung mit Docker ausführen wie in Abbildung 5 – 1 veranschaulicht.

![](./media/image1.png)

**Abbildung 5 – 1.** Schrittweise Workflow für die Entwicklung von apps für Docker-Containern

In diesem Handbuch werden der gesamte Vorgang beschrieben und in jedem wichtiger Schritt wird durch die Fokussierung auf einer Visual Studio-Umgebung erläutert.

Bei Verwendung einer Entwicklungsansatz-Editor/CLI (z. B. Visual Studio Code plus Docker-Befehlszeilenschnittstelle auf MacOS oder Windows), müssen Sie wissen, in jedem Schritt in der Regel im Detail, als wenn Sie Visual Studio verwenden. Weitere Informationen zum Arbeiten in einer Umgebung CLI finden Sie in der e-Book [Docker Anwendungslebenszyklus in Containern mit Microsoft-Platforms und Tools](http://aka.ms/dockerlifecycleebook/).

Wenn Sie Visual Studio 2015 oder Visual Studio 2017 verwenden, sind viele dieser Schritte für Sie behandelt, die die Produktivität erheblich verbessert. Dies gilt insbesondere, wenn Sie mithilfe von Visual Studio 2017 und Multi-containeranwendungen abzielt. Für die Instanz, fügt Visual Studio die dockerfile-Datei und Docker-compose.yml-Datei mit nur einem Mausklick zu Projekten mit der Konfiguration für Ihre Anwendung. Wenn Sie die Anwendung in Visual Studio ausführen, erstellt das Docker-Image und führt die Anwendung mit mehreren Container direkt im Docker; Sie können Sie sogar mehreren Containern auf einmal zu debuggen. Diese Funktionen werden Ihre entwicklungsgeschwindigkeit verstärken.

Allerdings nur daran, dass Visual Studio werden die Schritte im automatischen wird bedeutet nicht, dass Sie nicht benötigen, zu wissen, was passiert bei unterhalb mit Docker. Daher ausführliche Informationen in den Anleitungen, wir in jedem Schritt.

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>Schritt 1. Codieren beginnen Sie, und erstellen Sie Ihrer ersten Anwendung oder Dienst Basislinie

Entwickeln einer Anwendung Docker ist ähnlich wie bei eine Anwendung ohne Docker zu entwickeln. Der Unterschied besteht darin, dass beim Entwickeln für Docker kann Sie bereitstellen und Testen Ihrer Anwendung oder Dienste, die in Docker-Containern in Ihrer lokalen Umgebung ausgeführt wird. Der Container kann es sich um ein Linux-Container oder ein Windows-Container sein.

### <a name="set-up-your-local-environment-with-visual-studio"></a>Einrichten der lokalen Umgebung mit Visual Studio

Um zu beginnen, stellen Sie sicher, dass [Docker Community Edition (CE)](https://www.docker.com/community-edition) für Windows installiert werden, wie nachfolgend erläutert:

[Erste Schritte mit Docker CE für Windows](https://docs.docker.com/docker-for-windows/)

Darüber hinaus benötigen Sie Visual Studio 2017 installiert. Grund hierfür ist bevorzugte über Visual Studio 2015 mit Visual Studio-Tools für Docker-add-ins 2017 von Visual Studio-Unterstützung für Docker, z. B. Unterstützung für das Debuggen von Containern komplexeren hat. 2017 von Visual Studio enthält die Tools für Docker bei Auswahl der **.NET Core und Docker** arbeitsauslastung während der Installation, wie in Abbildung 5 – 2 dargestellt.

![](./media/image3.png)

**Abbildung 5 – 2**. Auswählen der **.NET Core und Docker** arbeitsauslastung während der Installation von Visual Studio 2017

Sie können sogar vor dem Aktivieren von Docker in Ihrer Anwendung und zum Bereitstellen und Testen in Docker starten codieren Ihre Anwendung in einfachen .NET (normalerweise in .NET Core, wenn Sie beabsichtigen, den Container verwenden). Allerdings wird empfohlen, dass Sie auf Docker so bald wie möglich, arbeiten da, der echten Umgebung werden und so bald wie möglich alle Probleme ermittelt werden können. Dies wird empfohlen, da Visual Studio es daher erleichtert mit Docker arbeiten, es fast transparent ist – das beste Beispiel beim Debuggen mit mehreren containeranwendungen aus Visual Studio.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Erste Schritte mit Docker CE für Windows**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

-   **Visual Studio-2017**
    [*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>Schritt 2 Erstellen Sie eine dockerfile-Datei im Zusammenhang mit einem vorhandenen .NET-Basis-image

Für jeden benutzerdefinierten Images, die Sie erstellen möchten, benötigen Sie eine dockerfile-Datei; Sie benötigen auch eine dockerfile-Datei für jeden Container bereitgestellt werden, an, ob Sie automatisch von Visual Studio oder manuell mithilfe der Docker-Befehlszeilenschnittstelle bereitstellen ("Docker run" als auch Docker-Befehle erstellen). Wenn Ihre Anwendung eine benutzerdefinierte Einzelgerät enthält, benötigen Sie eine einzelne dockerfile-Datei. Wenn Ihre Anwendung mehrere Dienste (wie eine Microservices-Architektur) enthält, benötigen Sie eine dockerfile-Datei für jeden Dienst ein.

Die dockerfile-Datei befindet sich im Stammordner Ihrer Anwendung oder Dienst. Es enthält die Befehle, die Docker Bereitstellen von Informationen zum Einrichten und Ausführen Ihrer Anwendung oder Ihrem Dienst in einem Container. Sie können manuell erstellen Sie eine dockerfile-Datei im Code und zusammen mit Ihrem .NET Abhängigkeiten zu Ihrem Projekt hinzufügen.

Mit Visual Studio und die Tools für Docker erfordert diese Aufgabe nur wenigen Mausklicks. Beim Erstellen eines neuen Projekts in Visual Studio 2017 besteht jedoch eine Möglichkeit, die mit dem Namen **aktivieren (Docker) Containerunterstützung**, wie in Abbildung 5 – 3 dargestellt.

![](./media/image5.png)

**Abbildung 5 – 3**. Aktivieren der Unterstützung für Docker beim Erstellen eines neuen Projekts in Visual Studio 2017

Sie können auch Docker-Unterstützung für ein neues oder vorhandenes Projekt aktivieren, indem Sie mit der rechten Maustaste der Projektdatei in Visual Studio und wählen Sie die Option **hinzufügen Docker Projekt unterstützt**, wie in Abbildung 5-4 dargestellt.

![](./media/image6.png)

**Abbildung 5-4**. Aktivieren der Unterstützung für Docker in einem vorhandenen 2017 von Visual Studio-Projekt

Diese Aktion für ein Projekt (z. B. eine ASP.NET-Webanwendung oder Web-API-Dienst) wird das Projekt mit der erforderlichen Konfiguration einer dockerfile-Datei hinzugefügt. Darüber hinaus wird eine Docker-compose.yml-Datei für die gesamte Projektmappe hinzugefügt. In den folgenden Abschnitten beschreiben wir die Informationen, die in jede dieser Dateien aufgenommen wird. Visual Studio können Sie dieses Werk führt, es ist jedoch hilfreich zu verstehen, was in einer dockerfile-Datei aufgenommen wird.

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a>Option A: Erstellen eines Projekts mit einem vorhandenen offizielle .NET Docker-image

Sie erstellen ein benutzerdefiniertes Image in der Regel für den Container über eine Basis-Image erhalten Sie von einem offiziellen-Repository auf der [Docker Hub](https://hub.docker.com/) Registrierung. Das ist genau an, was im Hintergrund geschieht, wenn Sie die Docker-Unterstützung in Visual Studio aktivieren. Die dockerfile-Datei wird ein vorhandenes Aspnetcore Image verwenden.

Zuvor erläutert wir die Docker-Images und Repositorys, die Sie verwenden können, abhängig von der Framework und das Betriebssystem, die Sie ausgewählt haben. Wenn Sie ASP.NET Core (Linux- oder Windows) verwenden möchten, wird das Bild, z. B. Microsoft / Aspnetcore:2.0. Aus diesem Grund müssen Sie nur angeben, welche Docker-Basisimages für den Container verwendet wird. Sie dies tun, indem Hinzufügen von Microsoft / Aspnetcore:2.0 auf Ihr dockerfile-Datei. Dies wird automatisch von Visual Studio ausgeführt werden, aber würden Sie die Version aktualisieren möchten, aktualisieren Sie diesen Wert.

Verwenden eine offizielle .NET Image-Repository von Docker Hub mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (einschließlich Entwicklungs-, Test- und Produktionszwecke) verfügbar sind.

Das folgende Beispiel zeigt ein Beispiel für dockerfile-Datei für eine ASP.NET Core-Container.

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

In diesem Fall basiert die Container in Version 2.0 des offiziellen ASP.NET Core Docker-Images (mit mehreren Arch für Linux und Windows). Dies ist die Einstellung `FROM microsoft/aspnetcore:2.0`. (Weitere Informationen zu dieser Basis-Image finden Sie unter der [ASP.NET Core Docker Bild](https://hub.docker.com/r/microsoft/aspnetcore/) Seite und die [.NET Core Docker-Image](https://hub.docker.com/r/microsoft/dotnet/) Seite.) In der dockerfile-Datei müssen Sie auch weisen Docker an den TCP-Port lauschen, die Sie zur Laufzeit (in diesem Fall Port 80, wie mit der Einstellung verfügbar machen) verwenden.

Sie können zusätzliche Konfigurationseinstellungen angeben, in die dockerfile-Datei, je nach Sprache und Framework, die Sie verwenden. Für die Instanz, die ENTRYPOINT-Zeile mit \["Dotnet", "MySingleContainerWebApp.dll"\] weist Docker zum Ausführen einer .NET Core-Anwendung. Bei Verwendung des SDK und die .NET Core-CLI (Dotnet CLI) zu erstellen, und führen Sie die Anwendung .NET, würden diese Einstellung abweichen. Entscheidend ist, dass die ENTRYPOINT-Zeile und andere Einstellungen können variieren, je nachdem das Sprache und Plattform, die Sie für Ihre Anwendung auswählen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Erstellen von Docker-Images für .NET Core-Anwendungen**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)

-   **Erstellen Sie Ihr eigenes Image**. In der offiziellen Docker-Dokumentation.
    [*https://docs.docker.com/Engine/Tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a>Verwenden mehrerer arch Image-Repositorys

Einem einzelnen Repository kann Plattform Varianten, z. B. ein Linux-Image und ein Windows-Image enthalten. Dieses Feature ermöglicht Anbietern wie Microsoft (Ersteller-Basis-Image) auf einem einzelnen Repository um decken mehrere Plattformen erstellen (Linux und Windows). Z. B. die [Microsoft/Dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) Repository verfügbar in der Docker Hub-Registrierung bietet Unterstützung für Linux und Windows Nano Server mit dem Namen der dieselbe Repository.

Wenn Sie eine Webplattform, die explizit ist ein Tag angeben, wie in den folgenden Fällen:

-   **Microsoft/aspnetcore:2.0.0-jessie**

        .NET Core 2.0 runtime-only on Linux 

-   **Microsoft/aspnetcore:2.0.0-nanoserver**

        .NET Core 2.0 runtime-only on Windows Nano Server

Aber dies ist neuer seit Mitte 2017 bei Angabe der gleichen ImageName auch mit dem gleichen Tag und die neuen mit mehreren arch Bilder (z. B. das Aspnetcore-Bild mit mehreren Arch unterstützt) verwenden die Linux- oder Windows-Version abhängig von der Docker-Host OS, das Sie bereitstellen , wie im folgenden Beispiel gezeigt:

-   **Microsoft / Aspnetcore:2.0**

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

Auf diese Weise ein Abbild von einem Windows-Host ziehen, ziehen sie die Windows-Variante, und der gleiche Name für das Ausführen von Pull aus einem Linux-Host Ruft die Linux-Variante.

### <a name="option-b-creating-your-base-image-from-scratch"></a>Option B: Erstellen des Basis-Image von Grund auf neu

Sie können eigene Docker-Basis-Image von Grund auf neu erstellen. Dieses Szenario wird nicht empfohlen, für eine Person, die mit Docker gestartet wird, aber wenn Sie die bestimmte Bits des eigene Basisimage festlegen möchten, können Sie dies tun.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Mit mehreren arch .NET Core Bilder**.
https://github.com/dotnet/Announcements/issues/14 
-   **Erstellen Sie eine base-Image**. Offizieller Docker-Dokumentation.
    [*https://docs.docker.com/Engine/UserGuide/eng-Image/BaseImages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>Schritt 3 Erstellen Sie Ihre benutzerdefinierten Docker-Images und betten Ihrer Anwendung oder Ihrem Dienst darin ein

Für jeden Dienst in Ihrer Anwendung müssen Sie eine verwandte Image zu erstellen. Wenn Ihre Anwendung von einem Einzelgerät oder Webanwendung vorgenommen wird, benötigen Sie nur ein einziges Bild.

Beachten Sie, dass der Docker-Images in Visual Studio automatisch für Sie erstellt werden. Die folgenden Schritte sind nur für den Workflow-Editor/CLI erforderlich und aus Gründen der Übersichtlichkeit Informationen dazu, was unter erläutert.

Sie als Entwickler benötigen, entwickeln und Testen lokal, bis Sie eine abgeschlossene push Features, und ändern Sie in Ihr Quellcodeverwaltungssystem (z. B. auf GitHub). Dies bedeutet, dass Sie den Docker-Images erstellen und Bereitstellen von Containern zu einem lokalen Docker-Host (Windows oder Linux-VM) und ausführen, testen und Debuggen für diese lokalen Container müssen.

Um ein benutzerdefiniertes Image mit Docker-Befehlszeilenschnittstelle und Ihr Dockerfile in Ihrer lokalen Umgebung zu erstellen, können Sie den Befehl "Docker Build", wie in Abbildung 5 bis 5.

![](./media/image8.png)

**Abbildung 5 – 5**. Erstellen eines benutzerdefinierten Docker-Images

Optional, können statt direkt Docker Build aus dem Projektordner, Sie zuerst einen bereitstellbaren Ordner mit den erforderlichen Bibliotheken für .NET und erstellen Binärdateien Treiberdienst Dotnet veröffentlichen und verwenden Sie den Befehl "Docker Build".

Dadurch wird ein Docker Bild erstellt, mit dem Namen Cesardl/Netcore-Webapi-Microservice-Docker: zuerst. In diesem Fall: zuerst wird ein Tag, das eine bestimmte Version darstellt. Sie können diesen Schritt für jeden benutzerdefinierten Abbilds wiederholen, die Sie für Ihre verfassten Docker-Anwendung erstellen müssen.

Wenn eine Anwendung mehrere Container erfolgt (d. h. es ist eine Anwendung mit mehreren Container), können Sie auch die Docker Verfassen Sie--Buildbefehl, um die zugehörige Bilder mit einem einzigen Befehl zu erstellen, anhand der Metadaten in den zugehörigen verfügbar gemacht Docker-compose.yml-Dateien.

Sie können vorhandenen Images in Ihr lokales Repository Suchbefehl mit Docker Images, wie in Abbildung 5 bis 6 dargestellt.

![](./media/image9.png)

**Abbildung 5 bis 6.** Anzeigen von vorhandenen Images, die mit dem Befehl "Docker Images"

### <a name="creating-docker-images-with-visual-studio"></a>Erstellen von Docker-Images mit Visual Studio

Wenn Sie Visual Studio zum Erstellen eines Projekts mit Unterstützung für Docker verwenden, Sie nicht explizit ein Image erstellen. Stattdessen wird das Bild für Sie erstellt, beim Drücken Sie F5, und die dockerized Anwendung oder den Dienst ausführen. Dieser Schritt ist automatisch in Visual Studio und nicht sehen Sie es der Fall sein, aber es ist wichtig, dass Sie wissen, was passiert bei unterhalb.

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>Schritt 4. Definieren Sie Ihre Dienste in Docker-compose.yml, beim Erstellen einer Docker-Anwendung mit mehreren container

Die [Docker compose.yml](https://docs.docker.com/compose/compose-file/) der Datei können Sie definieren einen Satz verwandter Dienste als einer zusammengesetzten Anwendung mit Bereitstellungsbefehlen bereitgestellt werden.

Eine Docker-compose.yml-Datei verwenden möchten, müssen Sie die Datei in die Main oder Lösung Stammordner mit Inhalt ähnelt der im folgenden Beispiel erstellen:

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

Beachten Sie, dass diese Datei Docker compose.yml eine vereinfachte und zusammengeführte Version ist. Es enthält die Konfiguration der statischen Daten für jeden Container (z. B. den Namen des benutzerdefinierten Images), die immer, sowie Informationen zur Konfiguration gilt, die die bereitstellungsumgebung, z. B. die Verbindungszeichenfolge möglicherweise abhängig ist. In späteren Abschnitten erfahren Sie, wie Sie die Konfiguration der Docker-compose.yml in mehreren Teilen können Docker verfassen, Dateien und Überschreibungswerte je nach Umgebung und Ausführung (Debug oder Release).

Im Beispiel der Docker-compose.yml-Datei definiert fünf Dienste: Webmvc-Dienst (Webanwendung), zwei Microservices (catalog.api und ordering.api) und eine Quelle Datencontainer, sql.data, basierend auf SQL Server für Linux, ausgeführt als Container. Jeder Dienst wird als ein Container bereitgestellt, ein Docker Bild für jede erforderlich ist.

Die Docker-compose.yml-Datei gibt nicht nur welche Container verwendet werden, sondern wie diese einzeln konfiguriert werden. Für die Instanz, die Webmvc Container Definition in der Datei .yml:

-   Verwendet eine vorgefertigte Shopping / Web: neueste Image. Könnten jedoch das Bild, das als Teil des zu erstellenden auch Festlegen der Docker-verfassen Ausführung eine zusätzliche Konfiguration auf Grundlage eines Builds: Abschnitt in der Datei Docker-compose.

-   Initialisiert die zwei Umgebungsvariablen (CatalogUrl und OrderingUrl).

-   Leitet die verfügbar gemachten Port 80 für den Container an den externen Port 80 auf dem Hostcomputer an.

-   Verknüpft die Web-app auf den Katalog und die Reihenfolge der Dienst mit der abhängt\_-Einstellung. Dies bewirkt, dass den Dienst wartet, bis diese Dienste gestartet werden.

Wir beschäftigt sich erneut mit die Docker-compose.yml-Datei in einem späteren Abschnitt beim beschrieben, wie Microservices und apps mit mehreren Container implementiert.

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>Arbeiten mit Docker-compose.yml in Visual Studio 2017

Wenn Sie Unterstützung für Docker-Lösung zu einem Service-Projekt in Visual Studio-Projektmappe, hinzufügen, wie in Abbildung 5-7 dargestellt, fügt Visual Studio eine dockerfile-Datei dem Projekt, und einen Abschnitt "Dienst" (Projekt) in der Projektmappe mit den Docker-compose.yml Dateien hinzugefügt. Es ist eine einfache Möglichkeit zum Verfassen von der Projektmappe mehrere Container starten. Sie können die Docker-compose.yml-Dateien öffnen und mit zusätzlichen Funktionen zu aktualisieren.

![](./media/image6.png)

**Abbildung 5-7**. Hinzufügen von Docker-Unterstützung in Visual Studio 2017 durch Rechtsklick auf ein Projekt ASP.NET Core

Hinzufügen von Docker-Unterstützung in Visual Studio nicht nur die dockerfile-Datei dem Projekt hinzugefügt, sondern mehrere globale Docker-compose.yml-Dateien, die auf Projektmappenebene festgelegt werden die Konfigurationsinformationen hinzugefügt.

Nachdem Sie die Projektmappe in Visual Studio Docker-Unterstützung hinzugefügt haben, sehen Sie auch einen neuen Knoten (in der Docker-compose.dcproj-Projektdatei) im Projektmappen-Explorer mit den hinzugefügten Docker-compose.yml Dateien, wie in Abbildung 5 bis 8 dargestellt.

![](./media/image11.PNG)

**Abbildung 5 bis 8**. Die **Docker verfassen** Strukturknoten im Projektmappen-Explorer von Visual Studio 2017 hinzugefügt

Eine Anwendung mit mehreren Container konnte mit einer einzelnen Docker-compose.yml-Datei bereitgestellt werden, mithilfe der Befehl Docker verfassen. Visual Studio fügt jedoch eine Gruppe von ihnen, damit Sie, abhängig von der Umgebung (Entwicklung im Vergleich zur Produktion) und die Ausführung überschreiben können Typ (Version im Vergleich zu Debug). Diese Funktion wird in späteren Abschnitten erläutert werden.

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a>Schritt 5. Erstellen und Ausführen der Docker-Anwendung

Wenn die Anwendung nur einen einzelnen Container verfügt, können Sie ihn ausführen, durch die Bereitstellung mit Ihrem Docker-Host (VM oder physischer Server). Jedoch, wenn Ihre Anwendung mehrere Dienste enthält, können Sie es bereitstellen als einer zusammengesetzten Anwendung entweder mit einem einzelnen CLI-Befehl (Docker-verfassen oben), oder mit Visual Studio wird die verwenden Sie den Befehl im Hintergrund. Sehen wir uns auf die verschiedenen Optionen.

### <a name="option-a-running-a-single-container-with-docker-cli"></a>Option A: Ausführen eines einzelnen-Containers mit Docker-Befehlszeilenschnittstelle

Sie können einen Docker-Container, die mit "Docker run" Befehl, wie in Abbildung 5 bis 9 ausführen:

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

**Abbildung 5 bis 9**. Einen Docker-Container mithilfe von "Docker run" Befehl ausgeführt wird

In diesem Fall wird der Befehl den internen Port 5000 des Containers an Port 80 des Hostcomputers gebunden. Dies bedeutet, dass der Host an Port 80 lauscht und Weiterleitung an Port 5000 für den Container.

### <a name="option-b-running-a-multi-container-application"></a>Option B: Ausführen einer Anwendung mit mehreren container

In den meisten Unternehmensszenarien wird eine Docker-Anwendung zusammengesetzt werden mehrere Dienste dies, dass Sie zum Ausführen einer Anwendung mit mehreren Container benötigen bedeutet, wie in Abbildung 5 bis 10 angezeigt.

![](./media/image14.png)

**Abbildung 5 bis 10**. VM mit Docker-Containern bereitgestellt

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a>Ausführen einer Anwendung mit mehreren Container mit Docker-Befehlszeilenschnittstelle

Zum Ausführen einer Anwendung mit mehreren Container mit Docker-Befehlszeilenschnittstelle können Sie führen Sie den Docker-Befehl zu erstellen. Dieser Befehl verwendet den Docker-compose.yml-Datei, dass Sie auf Projektmappenebene bereitstellen eine Anwendung mit mehreren Container verfügen. Abbildung 5 – 11 zeigt die Ergebnisse beim Ausführen des Befehls aus Ihrem Verzeichnis Hauptprojekt, das die Docker-compose.yml-Datei enthält.

![](./media/image15.png)

**Abbildung 5 bis 11**. Beispiel erhalten Sie beim Ausführen den Befehl Docker verfassen

Nachdem der Docker-verfassen Befehl ausgeführt wird, die Anwendung und seine zugehörigen Container in Ihrem Docker-Host bereitgestellt werden, wie in der VM-Darstellung in Abbildung 5 bis 10 veranschaulicht.

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a>Ausführen und Debuggen einer Anwendung mit mehreren Container mit Visual Studio 

Ausführen einer Multi-Container-Anwendung mit Visual Studio 2017 kann nicht einfacher abgerufen. Die Anwendung mehrere Container können nicht nur ausgeführt, jedoch können Sie alle ihre Container direkt in Visual Studio zu debuggen, indem Sie reguläre Haltepunkte festlegen.

Wie bereits erwähnt, bevor jedes Mal Sie Unterstützung für Docker-Projektmappe ein Projekt in einer Projektmappe hinzufügen, ist dieses Projekt in der Datei global (Projektmappenebene) Docker-compose.yml konfiguriert, mit der Sie ausführen oder die gesamte Projektmappe gleichzeitig zu debuggen. Visual Studio startet ein Container für jedes Projekt, das Docker-Lösung-Unterstützung aktiviert wurde, und führen Sie die internen Schritte aus, für die Sie (Dotnet veröffentlichen, Docker Build usw..).

Wichtig dabei ist, wie in Abbildung 5 – 12 dargestellt, in Visual Studio 2017 ergibt sich ein zusätzliches **Docker** Befehl für die F5-Key-Aktion. Diese Option können Sie die ausführen oder Debuggen einer Anwendung mit mehreren Container durch Ausführen von allen Containern, die in den Docker-compose.yml-Dateien auf Projektmappenebene definiert sind. Die Fähigkeit zum Debuggen von mehreren-containerlösungen bedeutet, dass Sie mehrere Breakpoints, die jedem Haltepunkt, in einem anderen Projekt (Container festlegen können), und während des Debuggens in Visual Studio hält an Haltepunkten in unterschiedlichen Projekten definiert und unter unterschiedliche Container.

![](./media/image16.png)

**Abbildung 5 – 12**. Ausführen von Multi-Container-apps in Visual Studio 2017

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Stellen Sie einen ASP.NET Container bereit, mit einem Docker-Remotehost**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>Ein Hinweis zum Testen und Bereitstellen mit orchestrators

Der Docker-verfassen einrichten und die Befehle "Docker run" (oder ausgeführt wird und der Container in Visual Studio Debuggen) für den Container in der Entwicklungsumgebung testen geeignet sind. Jedoch sollten Sie diese Methode nicht verwenden, wenn Sie Docker-Cluster als Ziel dient und Orchestrators wie Docker Containerhostclustern, Mesosphere DC/OS oder Kubernetes. Bei Verwendung von einem Cluster wie [Docker Containerhostclustern Modus](https://docs.docker.com/engine/swarm/) (verfügbar in Docker CE für Windows- und Mac seit Version 1.12), müssen Sie zum Bereitstellen und Testen mit zusätzlichen Befehlen wie [Docker-Dienst erstellen](https://docs.docker.com/engine/reference/commandline/service_create/) für einzelne Dienste. Wenn Sie eine Anwendung besteht aus mehreren Containern bereitstellen, verwenden Sie [Docker verfassen Bundle](https://docs.docker.com/compose/reference/bundle/) und [Docker bereitstellen MyBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) zum Bereitstellen der zusammengesetzten Anwendung als eine *Stapel*. Weitere Informationen finden Sie im Blogbeitrag [Einführung in experimentellen verteilte Anwendung Bündel](https://blog.docker.com/2016/06/docker-app-bundle/) in der Docker-Dokumentation. auf der Docker-Website.

Für [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) und [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) verwenden Sie unterschiedliche Bereitstellung Befehle und Skripts als auch.

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>Schritt 6. Testen Sie die Docker-Anwendung, die mit Ihrem lokalen Docker-host

Dieser Schritt hängen davon ab, welche Vorgänge die Anwendung ausführt. In einer einfachen .NET Core-Web-Anwendung, die als eine einzelne Container oder einen Dienst bereitgestellt wird, können Sie den Dienst zugreifen, öffnen einen Browser auf dem Docker-Host, und navigieren zu diesem Standort, wie in Abbildung 5 bis 13 gezeigt. (Wenn die Konfiguration in die dockerfile-Datei den Container mit einem Port auf dem Host zugeordnet ist, das etwas anderes als 80 ist, enthalten Sie die Hosts nach dem in der URL.)

![](./media/image18.png)

**Abbildung 5 bis 13**. Beispiel für das Testen der Docker-Anwendung, die lokal mithilfe von "localhost"

Wenn der Docker nicht "localhost" verweist, host-IP-(wird standardmäßig bei Verwendung von Docker CE, es sollte), um mit dem Dienst zu navigieren, verwenden Sie die IP-Adresse der Netzwerkkarte des Computers.

Beachten Sie, dass diese URL im Browser beispielsweise bestimmten Container besprochen wird Port 80 verwendet. Allerdings werden intern die Anforderungen zu-Port 5000, umgeleitet wird, da wie mit "Docker run" Befehl bereitgestellt wurde wie in einem vorherigen Schritt beschrieben wurde.

Sie können auch die Anwendung mit Curl aus der Terminaldienste testen, wie in Abbildung 5-14 gezeigt. Bei einer Installation Docker unter Windows ist die Standardeinstellung Docker-Host-IP-immer 10.0.75.1 zusätzlich zu Ihrem Computer tatsächlichen IP-Adresse.

![](./media/image19.png)

**Abbildung 5 – 14**. Beispiel für das Testen der Docker-Anwendung, die lokal mithilfe von curl

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>Testen und Debuggen mit Visual Studio 2017 Container

Beim Ausführen und Debuggen den Container mit Visual Studio 2017, können Sie die Anwendung .NET im großen und ganzen genauso Debuggen, wie beim ohne Container ausgeführt.

### <a name="testing-and-debugging-without-visual-studio"></a>Testen und Debuggen, ohne Visual Studio

Wenn Sie mit dem Editor/CLI-Ansatz entwickeln, Debuggen von Containern ist schwieriger und Debuggen, indem Sie ablaufverfolgungen generiert werden sollen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Debuggen von apps in einem lokalen Docker-Container**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

-   **Steve Lasker. Erstellen, Debuggen, Bereitstellen von ASP.NET Core-Apps mit Docker.** Video.
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Vereinfachte Workflow bei der Entwicklung von Containern mit Visual Studio

Tatsächlich ist der Workflow bei der Verwendung von Visual Studio viel einfacher als das Verwenden des Ansatzes-Editor/CLI. In den meisten Docker erforderlichen Schritten im Zusammenhang mit der dockerfile-Datei und Docker-compose.yml Dateien durch Visual Studio vereinfacht, wie in Abbildung 5-15 gezeigt oder ausgeblendet werden.

![](./media/image20.png)

**Abbildung 5-15**. Vereinfachte Workflow bei der Entwicklung mit Visual Studio

Darüber hinaus müssen Sie Schritt 2 (Hinzufügen von Docker-Unterstützung in Ihren Projekten) nur einmal ausführen. Aus diesem Grund ähnelt der Workflow der üblichen Entwicklungsaufgaben bei .NET für andere Entwicklungen verwenden. Sie müssen wissen, was passiert im Hintergrund (wird den imageerstellungsprozess, welche zugrundeliegenden Images, die Sie verwenden, die Bereitstellung der Container usw.) und in einigen Fällen müssen Sie auch bearbeiten Sie die Datei dockerfile-Datei oder Docker compose.yml Verhalten anzupassen. Aber Großteil der Arbeit mit Visual Studio, wodurch Sie viel höhere Produktivität erheblich vereinfacht wird.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Steve Lasker. .NET Docker Entwicklung mit Visual Studio 2017**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

-   **Jeffrey T. Fritz. Versetzen einer .NET Core-App in einem Container mit den neuen Docker-Tools für Visual Studio**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Mithilfe von PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Containern 

[Windows-Containern](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) ermöglichen es Ihnen, Ihre vorhandenen Windows-Anwendungen in Docker-Images konvertieren und diese mit den gleichen Tools wie der Rest des Docker-Ökosystem bereitstellen. Um Windows-Container verwendet werden, führen Sie PowerShell-Befehle in die dockerfile-Datei, wie im folgenden Beispiel gezeigt:

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

In diesem Fall werden wir mithilfe einer Windows Server Core-Basis-Image (die FROM-Einstellung) und Installieren von IIS mit einer PowerShell-Befehl (die Einstellung ausführen). Auf ähnliche Weise können Sie auch PowerShell-Befehle verwenden, um zusätzliche Komponenten wie ASP.NET 4.x, .NET 4.6 oder andere Windows-Software eingerichtet. Der folgende Befehl in einer dockerfile-Datei richtet z. B. ASP.NET 4.5:

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **ASPNET-Docker/dockerfile-Datei.** Beispiel-Powershell-Befehle zum Ausführen von dockerfile-Dateien auf Windows-Funktionen enthalten.
    [*https://github.com/Microsoft/ASPNET-docker/BLOB/Master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (.. / net-core-single-containers-linux-windows-server-hosts/index.md)
