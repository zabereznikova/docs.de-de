---
title: Inner-Loop-Entwicklungsworkflow für Docker-Apps
description: Informationen zum „Inner-Loop“-Entwicklungsworkflow für Docker-Anwendungen.
ms.date: 01/06/2021
ms.openlocfilehash: 78c593890d56a6888d4c4ea6752497918222ebee
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970584"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Inner-Loop-Entwicklungsworkflow für Docker-Apps

Bevor der Workflow der äußeren Schleife ausgelöst wird, der den gesamten DevOps-Zyklus umspannt, beginnt alle auf den Computern der einzelnen Entwickler, die den eigentlichen Code für die App in den bevorzugten Sprachen oder auf den bevorzugten Plattformen erstellen und ihn lokal testen (Abbildung 4–21). In jedem Fall haben Sie aber einen wichtigen Punkt gemein, unabhängig von Ihrer Wahl von Sprache, Framework oder Plattform. In diesem besonderen Workflow entwickeln und testen Sie Docker-Container immer in keinen anderen Umgebungen, sondern lokal.

![Abbildung, die das Konzept einer Entwicklungsumgebung mit innerer Schleife zeigt.](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

**Abbildung 4-21:** Entwicklungskontext der inneren Schleife

Der Container oder die Instanz eines Docker-Images enthält diese Komponenten:

- Eine Betriebssystemauswahl (z.B. eine Linux-Distribution oder Windows)

- Vom Entwickler hinzugefügte Dateien (z.B. Anwendungsbinärdateien)

- Konfiguration (z.B. Umgebungseinstellungen und Abhängigkeiten)

- Anweisungen für die von Docker auszuführenden Prozesse

Sie können den Entwicklungsworkflow der inneren Schleife, dr Docker verwendet, als Prozess einrichten (im nächsten Abschnitt beschrieben). Beachten Sie, dass die anfänglichen Schritte zum Einrichten der Umgebung nicht enthalten sind, da sie nur einmal ausgeführt werden müssenC.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Erstellen einer einzelnen App innerhalb eines Docker-Containers mithilfe von Visual Studio Code und Docker CLI

Apps bestehen aus Ihren eigenen Diensten zuzüglich zusätzlicher Bibliotheken (Abhängigkeiten).

Abbildung 4–22 zeigt die grundlegenden Schritte, die Sie in der Regel beim Erstellen einer Docker-App ausführen müssen, gefolgt von ausführlichen Beschreibungen der einzelnen Schritte.

![Das Diagramm zeigt die erforderlichen sieben Schritte zum Erstellen einer Container-App.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

**Abbildung 4-22.** Allgemeiner Workflow für den Lebenszyklus von in Containern verpackten Docker-Anwendungen unter Verwendung der Docker CLI

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Schritt 1: Beginn der Codeerstellung in Visual Studio Code und Erstellen der anfänglichen App/Dienstbaseline

Die Art, wie Sie Ihre Anwendung entwickeln, ähnelt der Weise, wie Sie das ohne Docker erledigen würden. Der Unterschied besteht darin, dass Sie beim Entwickeln eine Anwendung oder Dienste bereitstellen und testen, die in Docker-Containern ausgeführt werden, die in Ihrer lokalen Umgebung (wie einer Linux-VM oder Windows) platziert sind.

**Einrichten Ihrer lokalen Umgebung**

Mit den neuesten Versionen von Docker Desktop für Mac und Windows ist es einfacher als je zuvor, Docker-Anwendungen zu entwickeln, und die Einrichtung ist unkompliziert.

> [!TIP]
> Anweisungen zum Einrichten von Docker Desktop für Windows finden Sie unter <https://docs.docker.com/docker-for-windows/>.
>
> Anweisungen zum Einrichten von Docker Desktop für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.

Darüber hinaus benötigen Sie einen Code-Editor, damit Sie Ihre Anwendung tatsächlich entwickeln können, während Sie die Docker CLI verwenden.

Microsoft stellt Visual Studio Code zur Verfügung, einen schlanken Code-Editor. Dieser wird unter Windows, Linux und macOS unterstützt und bietet IntelliSense-Funktionen mit [Unterstützung für viele Sprachen](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python und die meisten modernen Sprachen), [Debuggen](https://code.visualstudio.com/Docs/editor/debugging), [Integration in Git](https://code.visualstudio.com/Docs/editor/versioncontrol) und [Unterstützung für Erweiterungen](https://code.visualstudio.com/docs/extensions/overview). Dieser Editor eignet sich hervorragend für macOS- and Linux-Entwickler. Unter Windows können Sie auch Visual Studio verwenden.

> [!TIP]
> Anweisungen zum Installieren von Visual Studio Code für Windows, Linux oder macOS finden Sie unter <https://code.visualstudio.com/docs/setup/setup-overview/>.
>
> Anweisungen zum Einrichten von Docker für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.

Sie können mit Docker CLI arbeiten und Ihren Code mithilfe eines beliebigen Code-Editors erstellen, die Verwendung von Visual Studio Code mit der Docker-Erweiterung macht es aber einfacher, `Dockerfile` und `docker-compose.yml`-Dateien in Ihrem Arbeitsbereich zu erstellen. Sie können darüber hinaus Aufgaben und Skripts aus der Visual Studio Code IDE ausführen, um Docker-Befehle mithilfe der zugrunde liegenden Docker CLI auszuführen.

Die Docker-Erweiterung für VS Code bietet die folgenden Features:

- Automatische Erstellung von `Dockerfile` und `docker-compose.yml`-Dateien

- Syntaxhervorhebung und QuickInfo-Hinweise für `docker-compose.yml` und `Dockerfile`-Dateien

- IntelliSense (Vervollständigungen) für `Dockerfile` und `docker-compose.yml`-Dateien

- Linting (Fehler und Warnungen) für `Dockerfile`-Dateien

- Integration der Befehlspalette (F1) für die gängigsten Docker-Befehle

- Explorer-Integration für die Verwaltung von Images und Containern

- Bereitstellen von Images von DockerHub und Azure-Containerregistrierungen in Azure App Service

Drücken Sie zum Installieren der Docker-Erweiterung STRG+UMSCHALT+P, geben Sie `ext install` ein, und führen Sie den Befehl „Erweiterung installieren“ aus, um die Liste der Marketplace-Erweiterungen anzuzeigen. Geben Sie dann **Docker** ein, um die Ergebnisse zu filtern, und wählen Sie dann die Docker Support-Erweiterung aus, wie in Abbildung 4–23 dargestellt.

![Ansicht der Docker-Erweiterung für Visual Studio Code.](media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

**Abbildung 4-23.** Installieren der Docker-Erweiterung in Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-nodejs-and-ruby"></a>Schritt 2: Erstellen einer DockerFile-Datei zu einem vorhandenen Image (einfaches Betriebssystem oder Entwicklungsumgebungen wie .NET, Node.js und Ruby)

Sie benötigen ein `DockerFile` pro erstelltem benutzerdefiniertem Image und pro bereitzustellendem Container. Wenn Ihre App aus einem einzelnen benutzerdefinierten Dienst besteht, benötigen Sie eine einzelne `DockerFile`-Datei. Wenn Ihre App sich jedoch aus mehreren Diensten zusammensetzt (wie bei einer Microservices-Architektur), benötigen Sie ein `Dockerfile` pro Dienst.

Das `DockerFile` Dockerfile wird üblicherweise im Stammordner Ihrer App oder Ihres Dienstes platziert und enthält die erforderlichen Befehle, um Docker anzuweisen, wie der betreffende Dienst einzurichten und auszuführen ist. Sie können Ihre `DockerFile`-Datei erstellen und sie Ihrem Projekt zusammen mit Ihrem Code (Node.js, .NET usw.) hinzufügen, oder Sie lesen sich den folgenden Tipp durch, wenn Sie gerade erst in die Umgebung einsteigen.

> [!TIP]
> Sie können die Docker-Erweiterung zur Führung beim Verwenden der `Dockerfile`- und `docker-compose.yml`-Dateien zu Ihren Docker-Containern verwenden. Im Lauf der Zeit werden Sie diese Art von Dateien wahrscheinlich ohne dieses Tool schreiben, die Verwendung der Docker-Erweiterung bildet aber einen guten Ausgangspunkt, der Ihren Lernprozess beschleunigt.

In Abbildung 4-24 können Sie die Schritte zum Hinzufügen der Docker-Dateien zu einem Projekt sehen, indem die Docker-Erweiterung für VS Code verwendet wird:

1. Öffnen Sie die Befehlspalette, geben Sie **docker** ein, und wählen Sie **Add Docker Files to Workspace** (Docker-Dateien dem Arbeitsbereich hinzufügen) aus.
2. Auswählen der Anwendungsplattform (ASP.NET Core)
3. Auswählen des Betriebssystems (Linux)
4. Einbinden optionaler Docker Compose-Dateien
5. Eingeben von Ports zum Veröffentlichen (80, 443)
6. Auswählen des Projekts

![Schritte zum Hinzufügen von Docker-Dateien mit der Docker-Erweiterung](media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

**Abbildung 4-24.** Mithilfe des Befehls **Add Docker files to Workspace** (Docker-Dateien dem Arbeitsbereich hinzufügen) hinzugefügte Docker-Dateien

Wenn Sie eine Dockerfile-Datei hinzufügen, geben Sie an, welches Docker-Basisimage Sie verwenden (z. B. `FROM mcr.microsoft.com/dotnet/aspnet`). Normalerweise erstellen Sie Ihr benutzerdefiniertes Image auf der Grundlage eines Basisimage, das Sie aus einem beliebigen offiziellen Repository in der [Docker Hub-Registrierung](https://hub.docker.com/) beziehen (z. B. ein [Image für .NET](https://hub.docker.com/_/microsoft-dotnet/) oder [für Node.js](https://hub.docker.com/_/node/)).

> [!TIP]
> Sie müssen dieses Verfahren für jedes Projekt in Ihrer Anwendung wiederholen. Die Erweiterung fragt jedoch nach dem ersten Mal, ob die generierte docker-compose-Datei überschrieben werden soll. Sie sollten sie nicht überschreiben, sodass die Erweiterung separate docker-compose-Dateien erstellt, die Sie dann vor der Ausführung von Docker-Compose von Hand mergen können.

**_Verwenden eines vorhandenen offiziellen Docker-Images_**

Durch Verwendung eines offiziellen Repositorys eines Sprachstapels mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (Entwicklung, Test und Produktion) verfügbar sind.

Nachstehend finden Sie ein Beispiel für eine DockerFile-Datei für einen .NET-Container:

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /src
COPY ["src/WebApi/WebApi.csproj", "src/WebApi/"]
RUN dotnet restore "src/WebApi/WebApi.csproj"
COPY . .
WORKDIR "/src/src/WebApi"
RUN dotnet build "WebApi.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "WebApi.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "WebApi.dll"]
```

In diesem Fall basiert das Image, gemäß der Zeile `FROM mcr.microsoft.com/dotnet/aspnet:5.0`, auf Version 5.0 des offiziellen ASP.NET Core-Docker-Image (mehrere Architekturen für Linux und Windows). (Weitere Informationen zu diesem Thema finden Sie auf der Seite zum [ASP.NET Core-Docker-Image](https://hub.docker.com/_/microsoft-dotnet-aspnet/) und auf der Seite zum [.NET-Docker-Image](https://hub.docker.com/_/microsoft-dotnet/).)

In der DockerFile-Datei können Sie Docker außerdem anweisen, an dem TCP-Port zu lauschen, den Sie zur Laufzeit verwenden möchten (z. B. Port 80 oder 443).

Je nach Sprache und Framework, die Sie verwenden, können Sie zusätzliche Konfigurationseinstellungen in der Dockerfile angeben. Beispielsweise weist die `ENTRYPOINT`-Zeile mit `["dotnet", "WebMvcApplication.dll"]` Docker an, eine .NET-Anwendung auszuführen. Wenn Sie das SDK und die .NET-CLI (`dotnet CLI`) verwenden, um die .NET-Anwendung zu entwickeln und auszuführen, wird eine andere Einstellung verwendet. Entscheidend ist, dass die ENTRYPOINT-Zeile und andere Einstellungen von der Sprache und Plattform abhängen, die Sie für Ihre Anwendung auswählen.

> [!TIP]
> Weitere Informationen zum Erstellen von Docker-Images für .NET-Anwendungen finden Sie unter <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.
>
> Weitere Informationen über das Erstellen eigener Images finden Sie unter <https://docs.docker.com/engine/tutorials/dockerimages/>.

**Verwenden von Repositorys für Images für mehrere Architekturen**

Der Name eines einzelnen Images in einem Repository kann Plattformvarianten enthalten, wie z.B. ein Linux-Image und ein Windows-Image. Dieses Feature ermöglicht Anbietern wie Microsoft (Basisimageentwickler), ein Repository für mehrere Plattformen (Linux und Windows) zu entwickeln. Das in der Docker Hub-Registrierung verfügbare [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/)-Repository bietet beispielsweise Unterstützung für Linux und Windows Nano Server, indem der gleiche Imagename verwendet wird.

Beim Pullen des [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/)-Image von einem Windows-Host aus wird die Windows-Variante gepullt, während das Pullen des gleichen Imagenamens von einem Linux-Host aus ein Pullen der Linux-Variante bewirkt.

**_Erstellen eines Basisimages von Grund auf_**

Sie können Ihr eigenes Docker-Basisimage von Grund auf neu erstellen, wie in diesem [Artikel](https://docs.docker.com/engine/userguide/eng-image/baseimages/) von Docker erläutert. Dieses Szenario ist für Sie vermutlich nicht ideal, wenn Sie gerade erst in Docker einsteigen, aber wenn Sie die spezifischen Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Schritt 3: Erstellen eines angepassten Docker-Images durch Einbetten eines Diensts

Für jeden benutzerdefinierten Dienst, den Ihre App beinhaltet, müssen Sie ein zugehöriges Image erstellen. Wenn Ihre App aus einem einzelnen Dienst oder einer einzelnen Web-App besteht, benötigen Sie nur ein einzelnes Image.

> [!NOTE]
> Wenn Sie die „DevOps-Workflow der äußeren Schleife“ berücksichtigen, werden immer, wenn Sie Ihren Quellcode per Push in ein Git-Repository übertragen (Continuous Integration), die Images mithilfe eines automatisierten Buildprozesses erstellt, sodass die Images in der globalen Umgebung aus Ihrem Quellcode erstellt werden.
>
> Bevor Sie aber den Weg in die äußere Schleife in Betracht ziehen, müssen Sie sicherstellen, dass die Docker-Anwendung tatsächlich ordnungsgemäß arbeitet, sodass kein Code an das Quellcodeverwaltungssystem (Git usw.) übertragen wird, der möglicherweise nicht ordnungsgemäß funktioniert.
>
> Daher muss jeder Entwickler zuerst den gesamten Prozess der inneren Schleife absolvieren, um lokal zu testen und mit der Entwicklung fortzufahren, bis er eine vollständige Funktion oder Änderung an das Quellcodeverwaltungssystem übertragen möchte.

Um ein Image in Ihrer lokalen Umgebung und unter Verwendung der DockerFile-Datei zu erstellen, können Sie den Befehl „docker build“ verwenden, wie in Abbildung 4-25 gezeigt, da er das Image bereits für Sie mit Tags versieht und die Images für alle Dienste in der Anwendung mit einem einfachen Befehl erstellt.

![Der Screenshot zeigt die Konsolenausgabe des Befehls „docker-compose build“.](media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

**Abbildung 4-25.** Ausführen des Docker-Erstellungsbefehls

Statt `docker build` direkt aus dem Projektordner auszuführen, können Sie optional auch zuerst einen bereitstellbaren Ordner mit den erforderlichen .NET-Bibliotheken generieren, indem Sie den `dotnet publish`-Ausführungsbefehl verwenden und dann `docker build` ausführen.

Dieses Beispiel erstellt ein Docker-Image mit dem Namen `webapi:latest` (`:latest` ist ein Tag, wie eine spezifische Version). Sie können diesen Schritt für jedes benutzerdefinierte Image ausführen, das Sie für Ihre aus mehreren Containern zusammengesetzte Docker-Anwendung erstellen müssen. Im nächsten Abschnitt werden wir jedoch sehen, dass dies mit `docker-compose` einfacher zu bewerkstelligen ist.

Sie können die vorhandenen Images in Ihrem lokalen Repository (Ihrem Bereitstellungscomputer) suchen, indem Sie den Befehl `docker images` verwenden, wie in Abbildung 4–26 gezeigt.

![Konsolenausgabe des Befehls „docker images“, gezeigt werden vorhandene Images.](media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

**Abbildung 4-26.** Anzeigen vorhandener Images mithilfe des Befehls „docker images“

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Schritt 4: Definieren Ihrer Dienste in der Datei „docker-compose.yml“ beim Erstellen einer zusammengesetzten Docker-Anwendung mit mehreren Diensten

Mit der Datei `docker-compose.yml` können Sie einen Satz verwandter Dienste definieren, die mit den im nächsten Schritt beschriebenen Bereitstellungsbefehlen als zusammengesetzte Anwendung bereitgestellt werden sollen.

Erstellen Sie die betreffende Datei in Ihrem Haupt- oder Stamm-Projektmappenordner; seine Inhalte sollten ähnlich den in dieser `docker-compose.yml`-Datei dargestellten sein:

```yml
version: "3.4"

services:
  webapi:
    image: webapi
    build:
      context: .
      dockerfile: src/WebApi/Dockerfile
    ports:
      - 51080:80
    depends_on:
      - redis
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80

  webapp:
    image: webapp
    build:
      context: .
      dockerfile: src/WebApp/Dockerfile
    ports:
      - 50080:80
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80
      - WebApiBaseAddress=http://webapi

  redis:
    image: redis
```

In diesem speziellen Fall definiert diese Datei drei Dienste: den Web-API-Dienst (Ihren benutzerdefinierten Dienst), eine Webanwendung und den Redis-Dienst (einen beliebten Cachedienst). Jeder Dienst wird als Container bereitgestellt. Sie müssen also für jeden Dienst ein konkretes Docker-Image verwenden. Für diese spezielle Anwendung gilt:

- Der Web-API-Dienst wird aus der DockerFile-Datei im Verzeichnis „`src/WebApi/Dockerfile`“ erstellt.

- Der Hostport 51080 wird an den bereitgestellten Port 80 für den `webapi`-Container weitergeleitet.

- Der Web-API-Dienst hängt vom Redis-Dienst ab.

- Die Webanwendung greift über die interne Adresse auf den Web-API-Dienst zu: `http://webapi`.

- Der Redis-Dienst verwendet das [neueste öffentliche Redis-Image](https://hub.docker.com/_/redis/), das er aus der Docker Hub-Registrierung gepullt hat. [Redis](https://redis.io/) ist ein beliebtes Cachesystem für serverseitige Anwendungen.

### <a name="step-5-build-and-run-your-docker-app"></a>Schritt 5: Erstellen und Ausführen Ihrer Docker-App

Wenn Ihre App nur einen einzelnen Container aufweist, müssen Sie ihn lediglich ausführen, indem Sie ihn auf Ihrem Docker-Host (VM oder physischer Server) bereitstellen. Wenn sich Ihre App jedoch aus mehreren Diensten zusammensetzt, müssen Sie sie außerdem _zusammenstellen_. Betrachten wir die verschiedenen Optionen.

**_Option A: Ausführen eines einzelnen Containers oder Diensts_**

Sie können das Docker-Image mithilfe des Ausführen-Befehls von Docker ausführen, wie hier gezeigt:

```console
docker run -t -d -p 50080:80 webapp:latest
```

Für diese spezielle Bereitstellung leiten wir Anforderungen, die an Port 50080 auf dem Host gesendet werden, an den internen Port 80 um.

**_Option B: Zusammenstellen und Ausführen einer aus mehreren Containern bestehenden Anwendung_**

In den meisten Unternehmensszenarien ist eine Docker-Anwendung aus mehreren Diensten zusammengesetzt. In diesen Fällen können Sie den Befehl `docker-compose up` (Abbildung 4–27) ausführen, der die docker-compose.yml-Datei verwendet, die Sie zuvor erstellt haben. Durch Ausführen dieses Befehls werden alle benutzerdefinierten Images erstellt, und die zusammengesetzte Anwendung wird mit allen zugehörigen Containern bereitgestellt.

![Konsolenausgabe des Befehls „docker-compose up“.](media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

**Abbildung 4-27.** Ergebnisse der Ausführung des Befehls „docker-compose up“

Nach dem Ausführen von `docker-compose up` stellen Sie Ihre Anwendung und ihre zugehörigen Container auf Ihrem Docker-Host bereit, wie in Abbildung 4–28 in der VM-Darstellung abgebildet.

![VM, die Anwendungen aus mehreren Containern ausführt.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

**Abbildung 4-28.** VM mit bereitgestellten Docker-Containern

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Schritt 6: Testen der Docker-Anwendung (lokal, auf Ihrer lokalen CD-VM)

Dieser Schritt unterscheidet sich je nachdem, welche Aktionen Ihre App ausführt.

In einer einfachen .NET-Web-API „Hallo Welt“, die als einzelner Container oder Dienst bereitgestellt wird, müssen Sie lediglich auf den Dienst zugreifen, indem Sie den in der DockerFile-Datei angegebenen TCP-Port übergeben.

Öffnen Sie auf dem Docker-Host einen Browser, und navigieren Sie zu der betreffenden Website; Sie sollten Ihre aktiv ausgeführte App/Ihren ausgeführten Webdienst sehen, wie in Abbildung 4–29 dargestellt.

![Browseransicht der Antwort von „localhost/API/values“.](media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

**Abbildung 4-29.** Lokales Testen Ihrer Docker-Anwendung mithilfe des Browsers

Beachten Sie, dass die Anwendung Port 50080 verwendet, intern aber an Port 80 umgeleitet wird, weil die Bereitstellung mit `docker compose` erfolgt ist, wie bereits zuvor erläutert.

Sie können dies mithilfe des Browsers testen, indem Sie CURL über das Terminal verwenden, wie in Abbildung 4-30 gezeigt.

![Von http://localhost:51080/WeatherForecast abgerufenes CURL-Ergebnis](media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

**Abbildung 4-30.** Lokales Testen einer Docker-Anwendung mithilfe von CURL

**Debuggen eines in Docker ausgeführten Containers**

Visual Studio Code unterstützt das Debuggen von Docker, wenn Sie Node.js und andere Plattformen wie .NET-Container verwenden.

Sie können auch, wie im nächsten Abschnitt beschrieben, .NET- oder .NET Framework-Container in Docker debuggen, wenn Sie Visual Studio für Windows oder Mac verwenden.

> [!TIP]
> Weitere Informationen zum Debuggen von Node.js-Docker-Containern finden Sie unter <https://blog.docker.com/2016/07/live-debugging-docker/> und <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.

> [!div class="step-by-step"]
> [Zurück](docker-apps-development-environment.md)
> [Weiter](visual-studio-tools-for-docker.md)
