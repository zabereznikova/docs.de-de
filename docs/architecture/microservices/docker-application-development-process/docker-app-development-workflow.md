---
title: Entwicklungsworkflow für Docker-Apps
description: Erläuterungen zu den Workflowdetails für die Entwicklung von auf Docker basierenden Anwendungen. Beginnen Sie mit den Grundlagen. Gehen Sie dann ausführlicher auf das Optimieren von Dockerfiles ein. Arbeiten Sie zum Schluss mit dem vereinfachten Workflow, der bei der Verwendung mit Visual Studio verfügbar ist.
ms.date: 01/07/2019
ms.openlocfilehash: 0c2789377bc388b8ac7373ee7fa46e3141f1b518
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "73740359"
---
# <a name="development-workflow-for-docker-apps"></a>Entwicklungsworkflow für Docker-Apps

Der Lebenszyklus der Anwendungsentwicklung beginnt auf Ihrem Computer. Als Entwickler programmieren Sie die Anwendung mit Ihrer bevorzugten Programmiersprache und testen sie lokal. Mit diesem Workflow entwickeln und testen Sie Docker-Container stets lokal, unabhängig davon, welche Sprache, welches Framework und welche Plattform Sie verwenden.

Jeder Container (eine Instanz eines Docker-Images) umfasst die folgenden Komponenten:

- Eine Betriebssystemauswahl, z. B. eine Linux-Distribution, Windows Nano Server oder Windows Server Core

- Dateien, die während der Entwicklung hinzugefügt wurden, z. B. Quellcode- und Anwendungsbinärdateien

- Konfigurationsinformationen, z. B. Umgebungseinstellungen und Abhängigkeiten

## <a name="workflow-for-developing-docker-container-based-applications"></a>Workflow für die Entwicklung von Docker-Container-basierten Anwendungen

In diesem Abschnitt wird der *Entwicklungsworkflow* für Docker-Container-basierte Anwendungen beschrieben. Der innere Entwicklungsworkflow berücksichtigt nicht den breiteren DevOps-Workflow, der bis zur Produktionsbereitstellung reichen kann. Stattdessen liegt der Fokus nur auf der Entwicklungsarbeit, die auf dem Computer des Entwicklers vorgenommen wird. Die ersten Schritte zum Einrichten der Umgebung wurden nicht berücksichtigt, da diese nur einmal durchgeführt werden.

Eine Anwendung besteht aus Ihren eigenen Diensten sowie zusätzlichen Bibliotheken (Abhängigkeiten). Im Folgenden sind die grundlegenden Schritte dargestellt, die Sie normalerweise beim Erstellen einer Docker-Anwendung ausführen, wie in Abbildung 5-1 dargestellt.

:::image type="complex" source="./media/docker-app-development-workflow/life-cycle-containerized-apps-docker-cli.png" alt-text="Diagramm, das die erforderlichen 7 Schritte zum Erstellen einer Container-App zeigt.":::
Der Entwicklungsprozess für Docker-Apps: 1. Programmieren der App, 2. Schreiben der Dockerfile(s), 3. Erstellen der in der Dockerfile definierten Images, 4. Erstellen von Diensten in der docker-compose.yml-Datei (optional), 5. Ausführen des Containers oder der docker-compose-App, 6. Testen der App oder des Microservices, 7. Mithilfe von Push an das Repository übertragen und Prozedur wiederholen
:::image-end:::

**Abbildung 5-1.** Workflowschritte für die Entwicklung von Containeranwendungen für Docker

In diesem Abschnitt wird der gesamte Prozess ausführlich beschrieben, und jeder wichtige Schritt wird unter besonderer Berücksichtigung einer Visual Studio-Umgebung erläutert.

Bei Verwendung eines Editor-/CLI-Entwicklungsansatzes (z. B. Visual Studio Code plus Docker-CLI auf macOS oder Windows) müssen Sie die einzelnen Schritte in der Regel detaillierter kennen als bei Verwendung von Visual Studio. Weitere Informationen zum Arbeiten in einer CLI-Umgebung finden Sie im E-Book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools (Lebenszyklus von Docker-Containeranwendungen mit Microsoft-Plattformen und Tools)](https://aka.ms/dockerlifecycleebook/).

Wenn Sie Visual Studio 2017 verwenden, werden viele dieser Schritte für Sie ausgeführt, wodurch sich Ihre Produktivität entscheidend erhöht. Dies gilt insbesondere, wenn Sie Visual Studio 2017 verwenden und Anwendungen mit mehreren Containern das Ziel sind. Visual Studio fügt beispielsweise mit nur einem Mausklick die Dateien Dockerfile und docker-compose.yml mit der Konfiguration für Ihre Anwendung Ihren Projekten hinzu. Wenn Sie die Anwendung in Visual Studio ausführen, wird das Docker-Image erstellt und die Anwendung mit mehreren Containern wird direkt in Docker ausgeführt. Sie haben sogar die Möglichkeit, mehrere Container auf einmal zu debuggen. Diese Features erhöhen Ihre Entwicklungsgeschwindigkeit.

Allerdings bedeutet die Tatsache, dass Visual Studio die Schritte automatisch ausführt, nicht, dass Sie nicht wissen müssen, was im Hintergrund mit Docker geschieht. Aus diesem Grund werden im folgenden Leitfaden alle Schritte ausführlich erläutert.

![Abbildung für Schritt 1.](./media/docker-app-development-workflow/step-1-code-your-app.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>Schritt 1. Beginnen Sie mit dem Codieren, und erstellen Sie eine erste Anwendungs- oder Dienstbaseline

Das Entwickeln einer Docker-Anwendung ist mit der Art und Weise vergleichbar, wie Anwendungen ohne Docker entwickelt werden. Der Unterschied besteht darin, dass Sie beim Entwickeln für Docker Ihre Anwendung oder Dienste bereitstellen und testen, die in Docker-Containern in Ihrer lokalen Umgebung ausgeführt werden (entweder in einem Setup für eine Linux-VM von Docker oder direkt unter Windows, wenn Sie Windows-Container verwenden).

### <a name="set-up-your-local-environment-with-visual-studio"></a>Einrichten der lokalen Umgebung mit Visual Studio

Stellen Sie zuerst sicher, dass [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) für Windows wie nachfolgend erläutert installiert wurde:

[Get started with Docker CE for Windows (Erste Schritte mit Docker CE für Windows)](https://docs.docker.com/docker-for-windows/)

Zudem benötigen Sie Visual Studio 2017, Version 15.7 oder höher, mit installierter Workload für die **plattformübergreifende .NET Core-Entwicklung**, wie in Abbildung 5.2 dargestellt.

![Screenshot der Auswahl der plattformübergreifenden .NET Core-Entwicklung.](./media/docker-app-development-workflow/dotnet-core-cross-platform-development.png)

**Abbildung 5-2**. Auswahl der **Workload für die plattformübergreifende .NET Core-Entwicklung** während des Setups in Visual Studio 2017

Sie können mit dem Codieren Ihrer Anwendung in einer einfachen .NET-Umgebung beginnen (normalerweise in .NET Core, wenn Sie Container verwenden möchten), noch bevor Sie Docker in Ihrer Anwendung aktivieren und in Docker Bereitstellungsprozesse und Tests durchführen. Allerdings wird empfohlen, dass Sie so bald wie möglich mit Docker arbeiten, d.h. in der realen Umgebung, sodass etwaige Probleme schnellstmöglich erkannt werden können. Dies wird empfohlen, da Visual Studio die Arbeit mit Docker so erleichtert, dass sie fast transparent erscheint – insbesondere beim Debuggen von Anwendungen mit mehreren Containern über Visual Studio.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Get started with Docker CE for Windows (Erste Schritte mit Docker CE für Windows)**  \
  <https://docs.docker.com/docker-for-windows/>

- **Visual Studio 2017** \
  [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)

![Abbildung für Schritt 2.](./media/docker-app-development-workflow/step-2-write-dockerfile.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>Schritt 2 Erstellen Sie eine Dockerfile-Datei im Zusammenhang mit einem vorhandenen .NET-Basisimage

Für jedes benutzerdefinierte Image, das Sie erstellen möchten, benötigen Sie eine Dockerfile-Datei. Außerdem benötigen Sie eine Dockerfile-Datei für jeden bereitzustellenden Container unabhängig davon, ob Sie automatisch über Visual Studio oder manuell mithilfe der Docker-CLI bereitstellen (Befehle „docker run“ und „docker-compose“). Wenn Ihre Anwendung einen benutzerdefinierten Dienst enthält, benötigen Sie eine einzelne Dockerfile-Datei. Wenn Ihre Anwendung mehrere Dienste enthält (wie in einer Microservicearchitektur), benötigen Sie pro Dienst eine Dockerfile-Datei.

Die Dockerfile-Datei befindet sich im Stammordner der Anwendung oder des Diensts. Sie enthält die Befehle, die Docker mitteilen, wie die Anwendung oder der Dienst in einem Container eingerichtet und ausgeführt werden sollen. Sie können eine Dockerfile-Datei manuell im Code erstellen und mit Ihren .NET-Abhängigkeiten Ihrem Projekt hinzufügen.

Mit Visual Studio und den Tools für Docker erledigen Sie diese Aufgabe mit einigen wenigen Mausklicks. Beim Erstellen eines neuen Projekts in Visual Studio 2017 ist die Option **Enable Container (Docker) Support** (Containerunterstützung (Docker) aktivieren) verfügbar, wie in Abbildung 5.3 dargestellt.

![Screenshot, der das Kontrollkästchen „Docker-Unterstützung aktivieren“ zeigt.](./media/docker-app-development-workflow/enable-docker-support-check-box.png)

**Abbildung 5-3**. Aktivieren der Docker-Unterstützung beim Erstellen eines neuen ASP.NET Core-Projekts in Visual Studio 2017

Sie können die Docker-Unterstützung auch für ein vorhandenes ASP.NET Core-Web-App-Projekt aktivieren, indem Sie mit der rechten Maustaste auf das Projekt im **Projektmappen-Explorer** klicken und **Hinzufügen** > **Docker-Unterstützung** auswählen, wie in Abbildung 5.4 dargestellt.

![Screenshot, der die Option „Docker-Unterstützung“ im Menü „Hinzufügen“ zeigt.](./media/docker-app-development-workflow/add-docker-support-option.png)

**Abbildung 5-4**. Aktivieren der Unterstützung für Docker in einem vorhandenen Visual Studio 2017-Projekt

Durch diesen Vorgang wird dem Projekt eine *Dockerfile* mit der erforderlichen Konfiguration hinzugefügt, die nur für ASP.NET Core-Projekte verfügbar ist.

Visual Studio kann auf ganz ähnliche Weise eine docker-compose.yml-Datei für die gesamte Projektmappe hinzufügen. Dazu wird die Option **Add > Container Orchestrator Support** (Hinzufügen > Containerorchestratorunterstützung) verwendet. In Schritt 4 wird diese Option genauer erläutert.

### <a name="using-an-existing-official-net-docker-image"></a>Verwenden eines vorhandenen offiziellen .NET Docker-Images

Sie erstellen ein benutzerdefiniertes Image für den Container in der Regel auf einem Basisimage, das Sie von einem offiziellen Repository in der [Docker-Hub](https://hub.docker.com/)-Registrierung erhalten. Das ist genau das, was im Hintergrund geschieht, wenn Sie die Docker-Unterstützung in Visual Studio aktivieren. Die Dockerfile verwendet ein vorhandenes `aspnetcore`-Image.

Es wurde bereits erläutert, welche Docker-Images und Repositorys Sie abhängig vom Framework und Betriebssystem, das Sie ausgewählt haben, verwenden können. Wenn Sie beispielsweise ASP.NET Core (Linux oder Windows) verwenden möchten, muss das Image `mcr.microsoft.com/dotnet/core/aspnet:2.2` verwendet werden. Aus diesem Grund müssen Sie nur angeben, welche Docker-Basisimages Sie für den Container verwenden werden. Fügen Sie hierzu `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2` Ihrer Dockerfile hinzu. Dies wird automatisch von Visual Studio ausgeführt, aber wenn Sie die Version aktualisieren müssen, aktualisieren Sie diesen Wert.

Durch Verwendung eines offiziellen .NET Image-Repositorys von Docker-Hub mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (Entwicklung, Test und Produktion) verfügbar sind.

Das folgende Beispiel veranschaulicht eine Dockerfile-Beispieldatei für einen ASP.NET Core-Container.

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

In diesem Fall basiert das Image auf Version 2.2 des offiziellen ASP.NET Core-Docker-Images (mehrere Architekturen für Linux und Windows). Dies ist die Einstellung `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`. (Weitere Informationen zu diesem Basisimage finden Sie unter [.NET Core Docker Image (.NET Core-Docker-Image)](https://hub.docker.com/_/microsoft-dotnet-core/).) In der Dockerfile-Datei müssen Sie auch angeben, dass Docker an dem TCP-Port lauscht, den Sie zur Runtime verwenden (in diesem Fall Port 80 gemäß Konfiguration mit der EXPOSE-Einstellung).

Je nach Sprache und Framework, die Sie verwenden, können Sie zusätzliche Konfigurationseinstellungen in der Dockerfile angeben. Beispielsweise weist die ENTRYPOINT-Zeile mit `["dotnet", "MySingleContainerWebApp.dll"]` Docker an, eine .NET Core-Anwendung auszuführen. Wenn Sie das SDK und die .NET Core-CLI (Dotnet-CLI) verwenden, um die .NET-Anwendung zu entwickeln und auszuführen, wird eine andere Einstellung verwendet. Entscheidend ist, dass die ENTRYPOINT-Zeile und andere Einstellungen je nach Sprache und Plattform variieren können, die Sie für Ihre Anwendung auswählen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Erstellen von Docker-Images für .NET Core-Anwendungen** \
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

- **Build your own image (Entwickeln eines eigenen Images)** . In der offiziellen Docker-Dokumentation.\
  <https://docs.docker.com/engine/tutorials/dockerimages/>

- **Staying up-to-date with .NET Container Images (Immer auf dem neuesten Stand mit .NET-Containerimages)**  \
  <https://devblogs.microsoft.com/dotnet/staying-up-to-date-with-net-container-images/>

- **Using .NET and Docker together - DockerCon 2018 Update (Gemeinsame Verwendung von .NET und Docker: Update zu DockerCon 2018)**  \
  <https://devblogs.microsoft.com/dotnet/using-net-and-docker-together-dockercon-2018-update/>

### <a name="using-multi-arch-image-repositories"></a>Verwenden von Repositorys für Images für mehrere Architekturen

Ein Repository kann Plattformvarianten enthalten, wie z.B. ein Linux-Image und ein Windows-Image. Dieses Feature ermöglicht Anbietern wie Microsoft (Basisimageentwickler), ein Repository für mehrere Plattformen (Linux und Windows) zu entwickeln. Das in der Docker-Hub-Registrierung verfügbare [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/)-Repository bietet beispielsweise Unterstützung für Linux und Windows Nano Server dadurch, dass der gleiche Repositoryname verwendet wird.

Wenn Sie ein explizites Tag für eine bestimmte Plattform angeben, wie in den folgenden Fällen:

- `microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim` \
  Ziele: Nur .NET Core 2.2-Runtime unter Linux

- `microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1809` \
  Ziele: Nur .NET Core 2.2-Runtime unter Windows Nano Server

Die Images für mehrere Architekturen (z. B. das `aspnetcore`-Image) verwenden bei Angabe des gleichen Imagenamens, auch mit dem gleichen Tag, je nach dem von Ihnen bereitgestellten Docker-Host-Betriebssystem die Linux- oder die Windows-Version, was im folgenden Beispiel dargestellt wird:

- `microsoft/dotnet:2.2-aspnetcore-runtime` \
  Mehrfacharchitektur: Nur .NET Core 2.2-Runtime unter Linux und Windows Nano Server, abhängig vom Betriebssystem des Docker-Hosts

Wenn Sie also ein Image von einem Windows-Host pullen, wird die Windows-Variante gepullt. Wenn der gleiche Imagename von einem Linux-Host gepullt wird, wird die Linux-Variante gepullt.

### <a name="multi-stage-builds-in-dockerfile"></a>Mehrstufige Builds in einer Dockerfile

Die Dockerfile ähnelt einem Batchskript. Die Vorgehensweise ist in etwa so wie beim Einrichten des Computers über die Befehlszeile.

Sie beginnen mit einem Basisimage, das den Anfangskontext einrichtet, was dem Startdateisystem ähnelt, das sich auf dem Hostbetriebssystem befindet. Dabei handelt es sich jedoch nicht um ein Betriebssystem, Sie können es sich eher als „das“ Betriebssystem innerhalb des Containers vorstellen.

Durch die Ausführung jeder Befehlszeile wird eine neue Ebene im Dateisystem erstellt, wobei jede Ebene die Änderungen der vorherigen enthält. Das gesamte Konstrukt ergibt zusammen das Dateisystem.

Da jede Ebene auf der vorherigen „aufliegt“, und die daraus resultierende Imagegröße mit jedem Befehl zunimmt, können Images sehr groß werden, wenn darin beispielsweise das für die Erstellung und Veröffentlichung einer Anwendung benötigte SDK enthalten sein muss.

Zu diesem Zeitpunkt kommen mehrstufige Builds (ab Docker 17.05 und höher) ins Spiel.

Die Kernidee dahinter ist, dass Sie den Ausführungsprozess für die Dockerfile in Stufen aufteilen können, wobei jede Stufe ein anfängliches Image darstellt, auf das mindestens ein Befehl folgt. Die letzte Stufe bestimmt die endgültige Imagegröße.

Zusammengefasst bedeutet das also, dass für mehrstufige Builds die Erstellung in unterschiedlichen „Phasen“ ablaufen kann und das endgültige Image dann ausschließlich mit den relevanten Verzeichnissen aus den weiterführenden Stufen erstellt wird. Die allgemeine Strategie zur Verwendung dieses Features ist die folgende:

1. Verwenden Sie ein SDK-Basisimage (dabei ist die Größe nicht wichtig) mit allen Elementen, die zum Erstellen und Veröffentlichen der Anwendung in einem Ordner erforderlich sind.

2. Verwenden Sie anschließend ein kleines Image, das nur als Runtime dient, und kopieren Sie den Veröffentlichungsordner aus der vorherigen Stufe, um ein kleineres endgültiges Image zu erstellen.

Sie können den mehrstufigen Prozess am besten verstehen, wenn Sie eine Dockerfile ausführlich durchlaufen, und zwar Zeile für Zeile. Beginnen wir also mit der ursprünglichen Dockerfile, die von Visual Studio erstellt wird, wenn zu einem Projekt Docker-Unterstützung hinzugefügt wird. Später erhalten Sie noch mehr Informationen zu einigen Optimierungen.

Die ursprüngliche Dockerfile kann wie folgt aussehen:

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS build
 6  WORKDIR /src
 7  COPY src/Services/Catalog/Catalog.API/Catalog.API.csproj …
 8  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.AspNetCore.HealthChecks …
 9  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions.HealthChecks …
10  COPY src/BuildingBlocks/EventBus/IntegrationEventLogEF/ …
11  COPY src/BuildingBlocks/EventBus/EventBus/EventBus.csproj …
12  COPY src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.csproj …
13  COPY src/BuildingBlocks/EventBus/EventBusServiceBus/EventBusServiceBus.csproj …
14  COPY src/BuildingBlocks/WebHostCustomization/WebHost.Customization …
15  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
16  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
17  RUN dotnet restore src/Services/Catalog/Catalog.API/Catalog.API.csproj
18  COPY . .
19  WORKDIR /src/src/Services/Catalog/Catalog.API
20  RUN dotnet build Catalog.API.csproj -c Release -o /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -o /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app .
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

Hier sind die Details zeilenweise dargestellt:

- **Linie 1:** Beginnen Sie eine Stufe mit einem „kleinen“ Basisimage, das nur als Runtime dient. Nennen Sie es zu Referenzzwecken **base**.

- **Zeile 2:** Erstellen Sie das Verzeichnis **/app** im Image.

- **Zeilen 3:** Machen Sie den Port **80** verfügbar.

- **Zeilen 5:** Beginnen Sie eine neue Stufe mit einem „großen“ Image zur Erstellung/Veröffentlichung. Nennen Sie es zu Referenzzwecken **build**.

- **Zeilen 6:** Erstellen Sie das **/src**-Verzeichnis im Image.

- **Zeilen 7:** Kopieren Sie bis zur Zeile 16 die **CSPROJ**-Projektdateien, auf die verwiesen wird, damit Sie Pakete zu einem späteren Zeitpunkt wiederherstellen können.

- **Zeile 17:** Stellen Sie die Pakete für das **Catalog.API**-Projekt und die Projekte, auf die verwiesen wird, wieder her.

- **Zeilen 18:** Kopieren Sie **alle Verzeichnisstrukturen für die Projektmappe** (mit Ausnahme der Dateien und Verzeichnisse in der **DOCKERIGNORE**-Datei) in das Verzeichnis **/src** im Image.

- **Zeilen 19:** Ändern Sie den aktuellen Ordner in das **Catalog.API**-Projekt.

- **Zeilen 20:** Erstellen Sie das Projekt (und andere Projektabhängigkeiten) sowie die Ausgabe im Verzeichnis **/app** im Image.

- **Zeile 22:** Beginnen Sie eine weitere neue Stufe aus dem Build. Nennen Sie sie zu Verweiszwecken **publish**.

- **Zeile 23:** Veröffentlichen Sie das Projekt (und die Abhängigkeiten) sowie die Ausgabe im Verzeichnis **/app** im Image.

- **Zeile 25:** Beginnen Sie eine neue Stufe aus dem Image **base**, und nennen Sie sie **final**.

- **Zeile 26:** Ändern Sie das aktuelle Verzeichnis in **/app**.

- **Zeile 27:** Kopieren Sie das Verzeichnis **/app** aus der Stufe **publish** in das aktuelle Verzeichnis.

- **Zeile 28:** Definieren Sie den Befehl, der ausgeführt werden soll, sobald der Container gestartet wird.

Lernen Sie nun einige Optimierungen kennen, die Ihnen dabei helfen, die gesamte Prozessleistung zu verbessern. Im Falle von eShopOnContainers bedeutet dies, dass es 22 Minuten oder länger dauert, um die gesamte Projektmappe in Linux-Containern zu erstellen.

Sie nutzen die Cachefunktion für die Ebenen in Docker. Das ist ganz einfach: Wenn sich das Basisimage und die Befehle nicht von den zuvor ausgeführten unterscheiden, kann einfach die sich daraus resultierende Ebene verwendet werden, ohne dass die Befehle ausgeführt werden müssen, wodurch Sie Zeit sparen.

Konzentrieren wir uns daher auf die **build**-Stufe: Die Zeilen 5–6 unterscheiden sich kaum, jedoch unterscheiden sich die Zeilen 7–17 für jeden eShopOnContainers-Dienst, weshalb sie jedes Mal ausgeführt werden müssen. Ganz anders sieht es aus, wenn Sie die Zeilen 7–16 wie folgt ändern:

```Dockerfile
COPY . .
```

Die Vorgehensweise wäre dann für jeden Dienst die gleiche: Die gesamte Projektmappe wird kopiert, und es wird eine größere Ebene erstellt. Dazu ist jedoch Folgendes zu beachten:

1. Der Kopiervorgang würde nur zum ersten Mal ausgeführt (und bei einer Neuerstellung, wenn eine Datei geändert wird) und würde den Cache für alle anderen Dienste verwenden.

2. Da das größere Image in einem Zwischenstadium auftritt, wirkt es sich nicht auf die endgültige Imagegröße aus.

Die nächste wichtige Optimierung umfasst den `restore`-Befehl, der in Zeile 17 ausgeführt wird, der sich jedoch auch für jeden Dienst von eShopOnContainers unterscheidet. Wenn Sie also diese Zeile nur wie folgt ändern...

```Dockerfile
RUN dotnet restore
```

...dann werden die Pakete für die gesamte Projektmappe wiederhergestellt. Dies geschieht jedoch nur ein einziges Mal und nicht 15 Mal wie bei der aktuellen Strategie.

Jedoch wird `dotnet restore` nur ausgeführt, wenn sich ein einzelnes Projekt oder eine einzelne Projektmappendatei im Ordner befindet. Der Weg dahin ist etwas komplizierter, und der Lösungsweg (ohne dass Sie sich in zu vielen Details verlieren) sieht wie folgt aus:

1. Fügen Sie der **.dockerignore**-Datei die folgenden Zeilen hinzu:

   - `*.sln`, um alle Projektmappendateien in der Hauptordnerstruktur zu ignorieren

   - `!eShopOnContainers-ServicesAndWebApps.sln`, um nur diese Projektmappendatei einzufügen

2. Schließen Sie das `/ignoreprojectextensions:.dcproj`-Argument in `dotnet restore` ein, damit auch das docker-compose-Projekt ignoriert und nur das Paket für die Projektmappe „eShopOnContainers-ServicesAndWebApps“ wiederhergestellt wird.

Für die letzte Optimierung kann es der Fall sein, dass Zeile 20 redundant wird, da Zeile 23 ebenso die Anwendung erstellt und im Grunde genommen gleich auf Zeile 20 folgt. So sparen Sie sich daher einen weiteren zeitaufwändigen Befehl.

Die Datei, die sich daraus ergibt, sieht wie folgt aus:

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a>Neuerstellung des Basisimages

Sie können ein eigenes Docker-Basisimage von Grund auf neu erstellen. Dieses Szenario wird Docker-Einsteigern nicht empfohlen, aber wenn Sie die bestimmten Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Multi-arch .NET Core images** (.NET Core-Images für mehrere Architekturen).\
  <https://github.com/dotnet/announcements/issues/14>

- **Create a base image (Erstellen eines Basisimages)** . Offizielle Docker-Dokumentation.\
  <https://docs.docker.com/develop/develop-images/baseimages/>

![Abbildung für Schritt 3.](./media/docker-app-development-workflow/step-3-create-dockerfile-defined-images.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>Schritt 3 Erstellen Sie Ihre benutzerdefinierten Docker-Images, und betten Sie Ihre Anwendung oder Ihren Dienst in diese ein

Sie müssen für jeden Dienst in Ihrer Anwendung ein zugehöriges Image erstellen. Wenn Ihre Anwendung aus einem einzelnen Dienst oder einer einzelnen Webanwendung besteht, benötigen Sie nur ein Image.

Beachten Sie, dass die Docker-Images in Visual Studio automatisch erstellt werden. Die folgenden Schritte sind nur für den Editor-/CLI-Workflow und zur Erläuterung der Vorgänge, die im Hintergrund ablaufen, erforderlich.

Als Entwickler entwickeln und testen Sie so lange lokal, bis Sie ein abgeschlossenes Feature pushen oder zu Ihrem Quellkontrollsystem wechseln (z.B. zu GitHub). Dies bedeutet, dass Sie die Docker-Images erstellen und Container auf einem lokalen Docker-Host (Windows- oder Linux-VM) bereitstellen und für die lokalen Container ausführen, testen und debuggen müssen.

Mithilfe des Befehls „docker build“ können Sie, wie in Abbildung 5-5 gezeigt, unter Verwendung der Docker-CLI und Ihrer Dockerfile-Datei ein benutzerdefiniertes Image in ihrer lokalen Umgebung erstellen.

![Der Screenshot zeigt die Konsolenausgabe des Befehls „docker build“.](./media/docker-app-development-workflow/run-docker-build-command.png)

**Abbildung 5-5**. Erstellen eines benutzerdefinierten Docker-Images

Optional können Sie, anstatt „docker build“ über den Projektordner direkt auszuführen, zuerst einen bereitstellbaren Ordner mit den erforderlichen .NET-Bibliotheken und Binärdateien generieren, indem Sie erst `dotnet publish` ausführen und dann den Befehl `docker build` verwenden.

Dadurch wird ein Docker-Image mit dem Namen `cesardl/netcore-webapi-microservice-docker:first` erstellt. In diesem Fall ist :first ein Tag, das eine bestimmte Version darstellt. Sie können diesen Schritt für jedes benutzerdefinierte Image wiederholen, das Sie für Ihre zusammengesetzte Docker-Anwendung erstellen müssen.

Wenn eine Anwendung aus mehreren Containern besteht, können Sie auch den Befehl `docker-compose up --build` verwenden, um alle zugehörigen Images mit einem Befehl unter Verwendung der in den zugehörigen docker-compose.yml-Dateien verfügbar gemachten Metadaten zu erstellen.

Sie können die vorhandenen Images in Ihrem lokalen Repository suchen, indem Sie den „docker images“-Befehl, wie in Abbildung 5-6 dargestellt, verwenden.

![Konsolenausgabe des Befehls „docker images“, gezeigt werden vorhandene Images.](./media/docker-app-development-workflow/view-existing-images-with-docker-images.png)

**Abbildung 5-6.** Anzeigen vorhandener Images mithilfe des Befehls „docker images“

### <a name="creating-docker-images-with-visual-studio"></a>Erstellen von Docker-Images mit Visual Studio

Wenn Sie Visual Studio zum Erstellen eines Projekts mit Docker-Unterstützung verwenden, erstellen Sie nicht explizit ein Image. Stattdessen wird das Image für Sie erstellt, wenn Sie **F5** (oder **STRG+F5**) drücken und die dockerisierte Anwendung oder den dockerisierten Dienst ausführen. Dieser Schritt wird in Visual Studio automatisch und für Sie nicht erkennbar ausgeführt, aber es ist wichtig, dass Sie wissen, was im Hintergrund passiert.

![Abbildung für den optionalen Schritt 4.](./media/docker-app-development-workflow/step-4-define-services-docker-compose-yml.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>Schritt 4. Definieren Sie Ihre Dienste in der Datei docker-compose.yml beim Erstellen einer Docker-Anwendung mit mehreren Containern

Mithilfe der Datei [docker compose.yml](https://docs.docker.com/compose/compose-file/) können Sie mehrere verwandte Dienste definieren, die als zusammengesetzte Anwendung mit Bereitstellungsbefehlen bereitgestellt werden sollen. Dadurch werden ebenso die Abhängigkeitsbeziehungen und die Laufzeitkonfiguration konfiguriert.

Wenn Sie eine docker-compose.yml-Datei verwenden möchten, müssen Sie die Datei in Ihrem Haupt- oder Stammlösungsordner mit Inhalt erstellen, der mit dem in dem folgenden Beispiel verwendeten vergleichbar ist:

```yml
version: '3.4'

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
      - ConnectionString=Server=sql.data;Port=1433;Database=CatalogDB;…
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

Diese „docker-compose.yml“-Datei ist eine vereinfachte und zusammengeführte Version. Sie enthält die statischen Konfigurationsdaten für jeden Container (z. B. den Namen des benutzerdefinierten Images), das erforderlich ist, sowie Konfigurationsinformationen, die sich nach der Bereitstellungsumgebung richten können, z. B. die Verbindungszeichenfolge. In späteren Abschnitten erfahren Sie, wie Sie die Konfiguration der docker-compose.yml-Datei in mehrere docker-compose-Dateien aufteilen und Werte je nach Umgebung und Ausführungstyp (Debug oder Release) außer Kraft setzen können.

Im Beispiel der Datei „docker-compose.yml“ werden vier Dienste definiert: der `webmvc`-Dienst (eine Webanwendung), zwei Microservices (`ordering.api` und `basket.api`) und ein Datenquellcontainer, `sql.data`, basierend auf von als Container ausgeführtem SQL Server für Linux. Da jeder Dienst als ein Container bereitgestellt wird, ist für jeden ein Docker-Image erforderlich.

Die docker-compose.yml-Datei gibt nicht nur an, welche Container verwendet werden, sondern auch, wie diese einzeln konfiguriert werden. Die `webmvc`-Containerdefinition in der .yml-Datei:

- Verwendet ein vorab erstelltes `eshop/web:latest`-Image. Sie können jedoch das als Teil der docker-compose-Ausführung zu erstellende Image mit einer zusätzlichen, auf einem build:-Abschnitt in der docker-compose-Datei basierenden Konfiguration konfigurieren.

- Initialisiert die beiden Umgebungsvariablen (CatalogUrl und OrderingUrl).

- Leitet den verfügbar gemachten Port 80 für den Container an den externen Port 80 auf dem Hostcomputer weiter.

- Verknüpft die Web-App mit dem Katalog- und Bestelldienst mit der depends_on-Einstellung. Dies bewirkt, dass der Dienst wartet, bis diese Dienste gestartet werden.

Wir gehen in einem der folgenden Abschnitte erneut auf die Datei docker-compose.yml ein, wenn wir uns damit beschäftigen, wie Microservices und Apps mit mehreren Containern implementiert werden.

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>Arbeiten mit docker-compose.yml in Visual Studio 2017

Visual Studio 2017 (ab Version 15.8) kann, wie zuvor erwähnt, eine Dockerfile zu einem Projekt hinzufügen und zusätzlich noch Orchestratorunterstützung für Docker Compose zu einer Projektmappe.

Wenn Sie zum ersten Mal Containerorchestratorunterstützung hinzufügen, wie in Abbildung 5.7 gezeigt, erstellt Visual Studio die Dockerfile für das Projekt sowie ein neues Projekt (Dienstbereich) in Ihrer Projektmappe mit mehreren globalen `docker-compose*.yml`-Dateien. Anschließend wird das Projekt diesen Dateien hinzugefügt. Sie können dann die docker-compose.yml-Dateien öffnen und mit zusätzlichen Features aktualisieren.

Sie müssen diesen Vorgang für alle Projekte wiederholen, die Sie in die docker-compose.yml-Datei einfügen möchten.

Zum Zeitpunkt der Erstellung dieses Dokuments unterstützt Visual Studio Docker Compose- und Service Fabric-Orchestratoren.

![Screenshot, der die Option „Unterstützung für Containerorchestrator“ im Kontextmenü des Projekts zeigt.](./media/docker-app-development-workflow/add-container-orchestrator-support-option.png)

**Abbildung 5-7**. Hinzufügen von Docker-Unterstützung in Visual Studio 2017 durch Rechtsklick auf ein ASP.NET Core-Projekt

Nachdem Sie der Projektmappe in Visual Studio Orchestratorunterstützung hinzugefügt haben, sehen Sie auch einen neuen Knoten (in der `docker-compose.dcproj`Projektdatei) im Projektmappen-Explorer mit den hinzugefügten docker-compose.yml-Dateien, wie in Abbildung 5.8 dargestellt.

![Screenshot des Knotens „docker-compose“ im Projektmappen-Explorer.](./media/docker-app-development-workflow/docker-compose-tree-node.png)

**Abbildung 5-8**. Der im Projektmappen-Editor in Visual Studio 2017 hinzugefügte **docker-compose**-Strukturknoten

Eine Anwendung mit mehreren Containern kann unter Verwendung des Befehls `docker-compose up` mit einer einzelnen „docker-compose.yml“-Datei bereitgestellt werden. Da Visual Studio jedoch eine Gruppe von Dateien hinzufügt, können Sie abhängig von der Umgebung (Entwicklung oder Produktion) und vom Ausführungstyp (Release oder Debug) Werte außer Kraft setzen. Diese Funktion wird in späteren Abschnitten erläutert.

![Abbildung für Schritt 5.](./media/docker-app-development-workflow/step-5-run-containers-compose-app.png)

## <a name="step-5-build-and-run-your-docker-application"></a>Schritt 5. Erstellen Sie Ihre Docker-Anwendung, und führen Sie sie aus

Wenn die Anwendung nur über einen einzelnen Container verfügt, können Sie sie ausführen, indem Sie sie auf dem Docker-Host (VM oder physischer Server) bereitstellen. Enthält Ihre Anwendung dagegen mehrere Dienste, können Sie sie als zusammengesetzte Anwendung bereitstellen, indem Sie entweder einen einzelnen CLI-Befehl (docker-compose up) oder Visual Studio verwenden, wobei der Befehl dann im Hintergrund ausgeführt wird. Betrachten wir die unterschiedlichen Optionen.

### <a name="option-a-running-a-single-container-application"></a>Option A: Ausführen einer Anwendung mit einem einzelnen Container

#### <a name="using-docker-cli"></a>Verwendung von Docker-CLI

Sie können einen Docker-Container mit dem Befehl `docker run`, wie in Abbildung 5.9 dargestellt, ausführen:

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

Der obige Befehl erstellt bei jeder Ausführung eine neue Containerinstanz aus dem angegebenen Image. Sie können den `--name`-Parameter verwenden, um dem Container einen Namen zu geben und anschließend `docker start {name}` (alternativ die Container-ID oder den automatischen Namen), um eine vorhandene Containerinstanz auszuführen.

![Screenshot, in dem ein Docker-Container mithilfe des Befehls „docker run“ ausgeführt wird.](./media/docker-app-development-workflow/use-docker-run-command.png)

**Abbildung 5-9**. Ausführen eines Docker-Containers mithilfe des Befehls „docker run“

In diesem Fall bindet der Befehl den internen Port 5000 des Containers an Port 80 des Hostcomputers. Dies bedeutet, dass der Host an Port 80 lauscht und an Port 5000 des Containers weiterleitet.

Der dargestellte Hash ist die Container-ID, zudem wird ihm ein zufälliger lesbarer Name zugewiesen, wenn die `--name`-Option nicht verwendet wird.

#### <a name="using-visual-studio"></a>Verwenden von Visual Studio

Wenn Sie die Containerorchestratorunterstützung nicht hinzugefügt haben, können Sie auch eine einzelne Container-App in Visual Studio ausführen, indem Sie **STRG+F5** drücken. Sie können auch **F5** drücken, um die Anwendung innerhalb des Containers zu debuggen. Der Container wird lokal mit „docker run“ ausgeführt.

### <a name="option-b-running-a-multi-container-application"></a>Option B: Ausführen einer Anwendung mit mehreren Containern

In den meisten Unternehmensszenarios setzt sich eine Docker-Anwendung aus mehreren Diensten zusammen. Dies bedeutet, dass Sie eine Anwendung mit mehreren Containern, wie in Abbildung 5-10 dargestellt, ausführen müssen.

![VM mit mehreren Docker-Containern](./media/docker-app-development-workflow/vm-with-docker-containers-deployed.png)

**Abbildung 5-10**. VM mit bereitgestellten Docker-Containern

#### <a name="using-docker-cli"></a>Verwendung von Docker-CLI

Verwenden Sie den `docker-compose up`-Befehl, um eine Anwendung mit mehreren Containern mithilfe der Docker-CLI auszuführen. Dieser Befehl stellt mithilfe der **docker-compose.yml**-Datei, die auf Projektmappenebene verfügbar ist, eine Anwendung mit mehreren Containern bereit. Abbildung 5.11 zeigt die Ergebnisse an, wenn der Befehl aus Ihrem Hauptprojektmappenverzeichnis ausgeführt wird, das die docker-compose.yml-Datei enthält.

![Bildschirmansicht bei der Ausführung des Befehls „docker-compose up“](./media/docker-app-development-workflow/results-docker-compose-up.png)

**Abbildung 5-11**. Beispielergebnisse bei der Ausführung des Befehls „docker-compose up“

Nachdem der Befehl „docker-compose up“ ausgeführt wurde, werden wie in Abbildung 5.10 die Anwendung und ihre zugehörigen Container in Ihrem Docker-Host bereitgestellt.

#### <a name="using-visual-studio"></a>Verwenden von Visual Studio

Das Ausführen einer Anwendung mit mehreren Containern mit Visual Studio 2017 ist denkbar einfach. Drücken Sie einfach **STRG+F5** oder nur **F5**, um den Debugvorgang zu starten und wie üblich dabei das **docker-compose**-Projekt als Startprojekt festlegen.  Visual Studio kümmert sich um das erforderliche Setup. Sie können sich also darauf konzentrieren, Breakpoints zu erstellen und unabhängige Prozesse zu debuggen, die auf Remoteservern ausgeführt werden.

Wie bereits erwähnt, wird jedes Mal, wenn Sie Unterstützung für die Docker-Projektmappe einem Projekt in einer Projektmappe hinzufügen, das Projekt in der globalen docker-compose.yml-Datei (Projektmappenebene) konfiguriert wird, wodurch Sie die gesamte Projektmappe auf einmal ausführen oder debuggen können. Visual Studio startet einen Container für jede Projektmappe, für die die Docker-Projektmappenunterstützung aktiviert ist, und führt alle internen Schritte aus (dotnet publish, docker build usw.).

Wenn Sie einen Blick auf Ihre bisherige Arbeit werfen möchten, sehen Sie sich diese Datei an:

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

Wichtig dabei ist, dass Visual Studio 2017, wie in Abbildung 5-12 dargestellt, über einen zusätzlichen **Docker**-Befehl für die Aktion der F5-Taste verfügt. Diese Option ermöglicht Ihnen, eine Anwendung mit mehreren Containern auszuführen oder zu debuggen, indem Sie alle in den docker-compose.yml-Dateien auf Projektmappenebene definierten Container ausführen. Die Möglichkeit, Lösungen mit mehreren Containern zu debuggen, bedeutet, das Sie mehrere Haltepunkte festlegen und jeden Haltepunkt in einem anderen Projekt (Container) festlegen können. Während des Debuggings in Visual Studio halten Sie an Haltepunkten an, die in verschiedenen Projekten definiert sind und in verschiedenen Containern ausgeführt werden.

![Screenshot der Symbolleiste zum Debuggen, über die ein docker-compose-Projekt ausgeführt wird.](./media/docker-app-development-workflow/debug-toolbar-docker-compose-project.png)

**Abbildung 5-12**. Ausführen von Apps mit mehreren Containern in Visual Studio 2017

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Deploy an ASP.NET container to a remote Docker host (Bereitstellen eines ASP.NET-Containers in einem Docker-Remotehost)**  \
  <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>Ein Hinweis zum Testen und Bereitstellen mit Orchestratoren

Die Befehle „docker-compose up“ und „docker run“ (oder Ausführen und Debuggen der Container in Visual Studio) sind zum Testen von Containern in der Entwicklungsumgebung geeignet. Verwenden Sie diesen Ansatz jedoch nicht für Produktionsbereitstellungen. Für diese sollten Sie Orchestratoren wie [Kubernetes](https://kubernetes.io/) oder [Service Fabric](https://azure.microsoft.com/services/service-fabric/) anzielen. Wenn Sie Kubernetes verwenden, müssen Sie [Pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) zum Organisieren von Container verwenden sowie [Dienste](https://kubernetes.io/docs/concepts/services-networking/service/), um diese zu vernetzen. Sie können ebenso [Bereitstellungen](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) verwenden, um die Erstellung und Änderung von Pods zu organisieren.

![Abbildung für Schritt 6.](./media/docker-app-development-workflow/step-6-test-app-microservices.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>Schritt 6. Testen Sie die Docker-Anwendung mithilfe des lokalen Docker-Hosts

Dieser Schritt hängt davon ab, welche Vorgänge die Anwendung ausführt. In einer einfachen .NET Core-Webanwendung, die als einzelner Container oder Dienst bereitgestellt wird, können Sie auf den Dienst zugreifen, indem Sie einen Browser auf dem Docker-Host öffnen und, wie in Abbildung 5-13 gezeigt, zu dieser Site navigieren. (Wenn die Konfiguration in der Docker-Datei den Container einem anderen Port als Port 80 auf dem Host zuordnet, berücksichtigen Sie den Host-Port in der URL.)

![Screenshot der Antwort von „localhost/API/values“.](./media/docker-app-development-workflow/test-docker-app-locally-localhost.png)

**Abbildung 5-13**. Beispiel für das lokale Testen der Docker-Anwendung mithilfe von „localhost“

Wenn „localhost“ nicht auf die Docker-Host-IP verweist (was bei Verwendung von Docker CE jedoch standardmäßig der Fall sein sollte), verwenden Sie die IP-Adresse der Netzwerkkarte Ihres Computers, um zum Dienst zu navigieren.

Beachten Sie, dass diese URL im Browser Port 80 für das besprochene Containerbeispiel verwendet. Allerdings werden intern die Anforderungen zu Port 5000 umgeleitet, da die Bereitstellung, wie in einem vorherigen Schritt beschrieben, mit dem Befehl „docker run“ erfolgte.

Sie können die Anwendung auch mithilfe von „curl“ über das Terminal testen, was in Abbildung 5-14 dargestellt wird. Bei einer Docker-Installation unter Windows lautet die standardmäßige Docker-Host-IP zusätzlich zur eigentlichen IP-Adresse Ihres Computers stets 10.0.75.1.

![Konsolenausgabe beim Abrufen von http://10.0.75.1/API/values mit curl.](./media/docker-app-development-workflow/test-docker-app-locally-curl.png)

**Abbildung 5-14**. Beispiel für das Testen der Docker-Anwendung mithilfe von „curl“

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>Testen und Debuggen von Containern mit Visual Studio 2017

Beim Ausführen und Debuggen des Containers mit Visual Studio 2017 können Sie die .NET-Anwendung in etwa so debuggen wie ohne Ausführung von Containern.

### <a name="testing-and-debugging-without-visual-studio"></a>Testen und Debuggen ohne Visual Studio

Wenn Sie mit dem Editor-/CLI-Ansatz entwickeln, ist das Debuggen von Containern schwieriger. Es ist ratsam zu debuggen, indem Traces generiert werden.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Debuggen von Apps in einem lokalen Docker-Container** \
  [https://docs.microsoft.com/visualstudio/containers/edit-and-refresh](/visualstudio/containers/edit-and-refresh)

- **Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker (Erstellen, Debuggen, Bereitstellen von ASP.NET Core-Apps mit Docker).** Video. \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115>

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Vereinfachter Workflow bei der Entwicklung von Containern mit Visual Studio

Der Workflow bei Verwendung von Visual Studio ist wesentlich einfacher als bei Verwendung des Editor/CLI-Ansatzes. Die meisten der von Docker vorausgesetzten Schritte in Zusammenhang mit der Dockerfile-Datei und den docker-compose.yml-Dateien werden, wie in Abbildung 5-15 gezeigt, von Visual Studio ausgeblendet oder vereinfacht.

:::image type="complex" source="./media/docker-app-development-workflow/simplified-life-cycle-containerized-apps-docker-cli.png" alt-text="Diagramm, das die vereinfachten fünf Schritte zum Erstellen einer App zeigt.":::
Der Entwicklungsprozess für Docker-Apps: 1. Programmieren der App, 2. Schreiben der Dockerfile(s), 3. Erstellen der in der Dockerfile definierten Images, 4. Erstellen von Diensten in der docker-compose.yml-Datei (optional), 5. Ausführen des Containers oder der docker-compose-App, 6. Testen der App oder des Microservices, 7. Mithilfe von Push an das Repository übertragen und Prozedur wiederholen
:::image-end:::

**Abbildung 5-15**. Vereinfachter Workflow bei der Entwicklung mit Visual Studio

Darüber hinaus müssen Sie Schritt 2 (Hinzufügen von Docker-Unterstützung in Ihren Projekten) nur einmal ausführen. Aus diesem Grund ähnelt der Workflow den üblichen Entwicklungsaufgaben bei Verwendung von .NET für andere Entwicklungsarbeiten. Sie müssen wissen, was im Hintergrund passiert (Imageerstellungsprozess, verwendete Basisimages, Bereitstellung von Containern usw.), und in einigen Fällen müssen Sie auch die Dockerfile oder die docker-compose.yml-Datei bearbeiten. Aber der Großteil der Arbeit wird durch Verwendung von Visual Studio, stark vereinfacht, und Ihre Produktivität wird entscheidend erhöht.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Steve Lasker. .NET Docker Development with Visual Studio 2017 (.NET-Docker-Entwicklung mit Visual Studio 2017)**  \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Verwenden von PowerShell-Befehlen in einer Dockerfile-Datei zum Einrichten von Windows-Containern

[Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/index) ermöglichen es Ihnen, Ihre vorhandenen Windows-Anwendungen in Docker-Images zu konvertieren und diese mit den gleichen Tools wie den Rest des Docker-Ökosystems bereitzustellen. Um Windows-Container zu verwenden, führen Sie PowerShell-Befehle in der Dockerfile-Datei aus, was im folgenden Beispiel gezeigt wird:

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

- **aspnet-docker/Dockerfile.** PowerShell-Beispielbefehle, die über Dockerfile-Dateien ausgeführt werden, um Windows-Features zu berücksichtigen.\
  <https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile>

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](../multi-container-microservice-net-applications/index.md)
