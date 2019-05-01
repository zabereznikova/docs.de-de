---
title: Inner-Loop-Entwicklungsworkflow für Docker-Apps
description: Erfahren Sie, die "innere Schleife"-Workflow für die Entwicklung von Docker-Anwendungen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 36fcf5769376375854c2a2631e26e8b136df0de6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050574"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Inner-Loop-Entwicklungsworkflow für Docker-Apps

Vor dem Auslösen des äußeren Schleife Workflows umfasst den gesamten DevOps-Zyklus, es beginnt alles auf dem Computer jedes Entwicklers, die app selbst zu codieren, verwenden ihren bevorzugten Sprachen oder Plattformen und diese lokal testen (Abbildung 4-21). In jedem Fall müssen Sie aber einen wichtigen Punkt gemeinsam, unabhängig davon, welche Sprache, Framework oder Plattformen, die Sie auswählen. In diesem bestimmten Workflow immer entwickeln und Testen des Docker-Containern, aber lokal.

![Schritt 1: Code, Ausführungs-und Debuggen](./media/image18.png)

**Abbildung 4-21:** Innere Schleife Development-Kontext

Der Container oder eine Instanz eines Docker-Images werden diese Komponenten enthalten:

-   Eine Betriebssystemauswahl (z.B. eine Linux-Distribution oder Windows)

- Dateien, die vom Entwickler (z.B. app-Binärdateien) hinzugefügt

-   Konfiguration (z. B. umgebungseinstellungen und Abhängigkeiten)

- Anweisungen für welche Aspekte Sie verarbeitet die Ausführung von Docker

Sie können die innere Schleife Entwicklungsworkflow einrichten, die Docker wie der Prozess (im nächsten Abschnitt beschrieben) verwendet. Erwägen Sie, dass die ersten Schritte zum Einrichten der Umgebung nicht eingeschlossen werden, da Sie nur einmal tun müssen.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Erstellen eine einzelne app in Docker-Container mit Visual Studio Code und Docker-CLI

Apps bestehen aus Ihren eigenen Diensten sowie zusätzlichen Bibliotheken (Abhängigkeiten).

Abbildung 4-22 zeigt die grundlegenden Schritte, die Sie in der Regel beim Erstellen einer Docker-app, gefolgt von ausführliche Beschreibungen der einzelnen Schritte ausführen müssen.

![Übersicht über Workflow –: Schritt 1: Code, Schritt2: Schreiben von dockerfile-Dateien, Schritt 3: Erstellen von Images mit docker-Dateien, Schritt 4 definiert – definieren Sie mit Schritt 5: Ausführen von Containern docker-Compose-Datei, Dienste oder zusammengesetzte Anwendungen, Schritt 6 – Test-apps, Schritt 7: per Push übertragen, um zu beginnen die äußere Schleife (CI/CD-Pipelines), oder de Veloping.](./media/image19.png)

**Abbildung 4-22.** Allgemeiner Workflow für die Lebenszyklus von Docker-containeranwendungen mit Docker CLI

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Schritt 1: Beginnen mit dem Programmieren in Visual Studio Code, und erstellen Sie Ihrer ersten app/des Diensts

Die Möglichkeit, die Sie bei der Entwicklung Ihrer Anwendung ist ähnlich wie Sie es ohne Docker. Der Unterschied besteht darin, dass beim Entwickeln, sind Sie bereitstellen und Testen Ihre Anwendung oder Dienste, die in Docker-Containern platziert, die in Ihrer lokalen Umgebung (z.B. eine Linux-VM oder Windows) ausgeführt.

**Das Einrichten Ihrer lokalen Umgebung**

Mit den neuesten Versionen von Docker für Mac und Windows es ist einfacher als je zuvor zu Docker-Anwendungen entwickeln, und das Setup ist einfach.

> [!INFORMATION]
>
> Anweisungen zum Einrichten von Docker für Windows finden Sie unter <https://docs.docker.com/docker-for-windows/>.
>
>Anweisungen zum Einrichten von Docker für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.

Darüber hinaus benötigen Sie einen Code-Editor, damit Sie Ihre Anwendung bei der Verwendung von Docker-CLI tatsächlich entwickeln können.

Microsoft bietet Visual Studio Code, einem einfachen Code-Editor, die unter Mac, Windows und Linux unterstützt, und bietet IntelliSense mit [Unterstützung für viele Sprachen](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python und die meisten Moderne Sprachen), [Debuggen](https://code.visualstudio.com/Docs/editor/debugging), [-Integration mit Git](https://code.visualstudio.com/Docs/editor/versioncontrol) und [unterstützen](https://code.visualstudio.com/docs/extensions/overview). Dieser Editor ist ideal für Mac und Linux-Entwickler. In Windows können Sie auch die vollständige Visual Studio-Anwendung verwenden.

> [!INFORMATION]
>
> Anweisungen zum Installieren von Visual Studio Code für Windows, Mac oder Linux finden Sie unter <https://code.visualstudio.com/docs/setup/setup-overview/>.
>
> Anweisungen zum Einrichten von Docker für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.

Sie können Arbeit mit Docker-CLI und Schreiben Sie Ihren Code mit jedem Code-Editor, aber mit Visual Studio Code mit der Docker-Erweiterung vereinfacht Autor `Dockerfile` und `docker-compose.yml` Dateien in Ihrem Arbeitsbereich. Sie können auch Aufgaben und Skripts aus Visual Studio Code-IDE zum Ausführen von Docker-Befehlen, die mit der Docker CLI unter ausführen.

Die Docker-Erweiterung für Visual Studio Code bietet die folgenden Features:

- Automatische `Dockerfile` und `docker-compose.yml` Datei generieren

- Hervorhebung und zeigen Sie Tipps zur Syntax für `docker-compose.yml` und `Dockerfile` Dateien

- IntelliSense (vervollständigungen) für `Dockerfile` und `docker-compose.yml` Dateien

- Linting (Fehler und Warnungen) für `Dockerfile` Dateien

- Befehl Palette (F1)-Integration für die am häufigsten verwendeten Docker-Befehle

- Explorer-Integration für die Verwaltung von Images und Containern

- Bereitstellen von Images von DockerHub und Azure-Containerregistrierungen in Azure App Service

Zum Installieren der Docker-Erweiterung, drücken Sie STRG + UMSCHALT + P, geben `ext install`, und führen Sie den Befehl "Erweiterung installieren", um die Liste der Marketplace-Erweiterungen anzuzeigen. Geben Sie als Nächstes **Docker** zum Filtern der Ergebnisse, und wählen Sie dann die Erweiterung für Docker-Unterstützung, wie in Abbildung 4-23 dargestellt.

![Ansicht der Docker-Erweiterung für Visual Studio Code.](./media/image20.png)

**Abbildung 4-23.** Installieren der Docker-Erweiterungs in Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Schritt 2: Erstellen Sie eine dockerfile-Datei im Zusammenhang mit einem vorhandenen Image (einfaches Betriebssystem oder entwicklungsumgebungen wie .NET Core, Node.js und Ruby)

Sie müssen eine `DockerFile` pro benutzerdefiniertes Image erstellt werden und Container bereitgestellt werden. Wenn Ihre app aus einen benutzerdefinierten Dienst besteht, benötigen Sie ein einzelnes `DockerFile`. Aber wenn Ihre app aus mehreren Diensten (wie in einer Microservices-Architektur) besteht, benötigen Sie ein `Dockerfile` pro Dienst.

Die `DockerFile` wird häufig im Stammordner Ihrer app oder Ihres Diensts und enthält die erforderlichen Befehle aus, damit Docker weiß, wie einrichten und Ausführen dieser app oder Ihres Diensts. Sie erstellen Ihre `DockerFile` und fügen sie dem Projekt zusammen mit Ihrem Code hinzu (.NET Core, node.js usw.), oder, wenn Sie in der Umgebung vertraut sind, sehen Sie sich den folgenden Tipp.

> [!TIP]
>
> Können Sie die Docker-Erweiterung Anleitung für die Verwendung der `Dockerfile` und `docker-compose.yml` Dateien im Zusammenhang mit der Docker-Container. Schließlich schreiben Sie wahrscheinlich diese Arten von Dateien ohne dieses Tool, aber mit der Docker-Erweiterung ist ein guter Ausgangspunkt, der mit der Lernprozess beschleunigt wird.

In Abbildung 4-24, können Sie sehen, wie ein Docker-compose-Datei wird mithilfe der Docker-Erweiterung für Visual Studio Code hinzugefügt.

![Die Konsolenansicht der Docker-Erweiterung für Visual Studio Code.](./media/image24.png)

**Abbildung 4-24.** Docker-Dateien hinzugefügt, mit der **Hinzufügen von Docker-Dateien auf Workspace-Befehl**

Wenn Sie eine dockerfile-Datei hinzufügen, geben Sie welche Docker-Basisimage Sie verwenden (wie die Verwendung von `FROM mcr.microsoft.com/dotnet/core/aspnet`). Erstellen Sie in der Regel Ihr benutzerdefinierte Image auf einem Basisimage, die Sie aus einem offiziellen-Repository auf erhalten die [Docker Hub-Registrierung](https://hub.docker.com/) (z. B. eine [Images für .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) oder der [für Node.js](https://hub.docker.com/_/node/)).

***Verwenden Sie ein vorhandenes offizielles dockerimage***

Mit einem offiziellen-Repository eines Stapels Sprache mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (einschließlich Entwicklung, Tests und Produktion) verfügbar sind.

Im folgenden finden eine DockerFile-Beispieldatei für eine .NET Core-Container:

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.1
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

Das Bild in diesem Fall basiert auf Version 2.1 von der offiziellen ASP.NET Core-Docker-Image (Multi-Arch für Linux und Windows), gemäß der Zeile `FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`. (Weitere Informationen zu diesem Thema finden Sie unter den [ASP.NET Core-Docker-Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Seite und die [.NET Core-Docker-Image](https://hub.docker.com/_/microsoft-dotnet-core/) Seite).

In der dockerfile-Datei können Sie auch weisen Docker an zum TCP-Port zu lauschen, die Sie zur Laufzeit (z. B. Port 80) verwenden.

Je nach Sprache und Framework, die Sie verwenden, können Sie zusätzliche Konfigurationseinstellungen in der Dockerfile angeben. Z. B. die `ENTRYPOINT` Linie mit `["dotnet", "MySingleContainerWebApp.dll"]` teilt Docker zum Ausführen einer .NET Core-Anwendung. Wenn Sie das SDK und .NET Core-CLI nutzen (`dotnet CLI`) zum Erstellen, und führen Sie die Anwendung .NET, diese Einstellung wären unterschiedlich. Der ausschlaggebende Punkt hierbei ist, dass die ENTRYPOINT-Zeile und andere Einstellungen hängen von der Sprache und Plattform, die Sie für Ihre Anwendung auswählen.

> [!INFORMATION]
>
> Weitere Informationen zum Erstellen von Docker-Images für .NET Core-Anwendungen finden Sie unter <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.
>
> Wechseln Sie zu, um weitere Informationen zum Erstellen Ihrer eigenen Images <https://docs.docker.com/engine/tutorials/dockerimages/>.

**Verwenden Sie die Repositorys für Images für mehrere Architekturen**

Ein einzelnes Image-Name in einem Repository kann Plattformvarianten, z. B. ein Linux-Image und ein Windows-Image enthalten. Dieses Feature ermöglicht Anbietern wie Microsoft (basisimageentwickler), um ein Repository für mehrere Plattformen (d. h., Linux und Windows) zu erstellen. Z. B. die [Dotnet/Core/Aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Repository zur Verfügung, in der Docker-Hub-Registrierung bietet Unterstützung für Linux und Windows Nano Server mit denselben imagenamen ein.

Abrufen der [Dotnet/Core/Aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Image von einem Windows-Host Ruft die Windows-Variante, während der gleiche ImageName von einem Linux-Host ziehen die Linux-Variante abruft.

***Ihr Basisimage von Grund auf neu erstellen***

Sie können Ihre eigenen Docker-Basisimage von Grund auf neu erstellen, wie dies unter [Artikel](https://docs.docker.com/engine/userguide/eng-image/baseimages/) von Docker. Dieses Szenario ist wahrscheinlich nicht für Sie am besten geeignet, wenn Sie gerade mit Docker beginnen, aber wenn Sie die bestimmten Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Schritt 3: Erstellen Sie Ihre benutzerdefinierten Docker-Images, die Ihrem Dienst darin einbetten

Für jeden benutzerdefinierten Dienst, die Ihre app umfasst, müssen Sie ein zugehöriges Image erstellen. Wenn Ihre app aus einem einzelnen Dienst oder Web-app besteht, benötigen Sie ein einziges Bild.

> [!NOTE]
>
> Wenn die "outer-Loop-DevOps-Workflow" berücksichtigen, die Bilder erstellt durch einen automatisierten Buildprozess zu, wenn Sie mithilfe von Push Ihren Quellcode in einem Git-Repository (Continuous Integration), übertragen sodass die Bilder in der globalen Umgebung erstellt werden von Ihrem im Quellcode.
>
> Aber bevor wir auf die äußere Schleife Route in Betracht ziehen, müssen wir sicherstellen, dass die Docker-Anwendung ordnungsgemäß funktioniert, damit sie Code nicht die Warteschlange übertragen, die auf das Quellcodeverwaltungssystem (Git, usw.) möglicherweise nicht ordnungsgemäß funktioniert.
>
> Jeder Entwickler muss daher zuerst führen Sie den gesamten Entwicklungsworkflow Prozess zum Testen lokal und weiterentwickeln, bis eine vollständige Funktion mithilfe von Push übertragen, oder ändern Sie in das Quellcodeverwaltungssystem werden soll.

Um ein Image in Ihrer lokalen Umgebung und verwenden die dockerfile-Datei zu erstellen, können Sie die Docker-Erstellungsbefehl aus, wie in Abbildung 4-25 dargestellt (Sie können auch ausführen `docker-compose up --build` für Anwendungen besteht aus mehreren Containern/Diensten).

![Die Konsolenausgabe von der docker-Compose Build, zeigt die Bilder Fortschritt herunterladen.](./media/image25.png)

**Abbildung 4-25.** Docker-Build ausgeführt wird

Optional, anstatt direkt `docker build` aus dem Projektordner, Sie zuerst können generieren einen bereitstellbaren Ordner mit den mithilfe der erforderlichen .NET-Bibliotheken `dotnet publish` Befehl aus, und führen Sie `docker build`.

In diesem Beispiel erstellt ein Docker-Image mit dem Namen `cesardl/netcore-webapi-microservice-docker:first` (`:first` ist ein Tag, wie eine bestimmte Version). Sie können diesen Schritt für jedes benutzerdefinierte Image nutzen, die Sie für Ihre zusammengesetzte Docker-Anwendung mit mehreren Containern erstellen müssen.

Die vorhandenen Images finden in Ihrem lokalen Repository (Entwicklungscomputer) Sie unter Verwendung von der Docker Images-Befehl, wie in Abbildung 4-26 veranschaulicht.

![Konsolenausgabe Befehl Docker-Images, mit der vorhandenen Bilder.](./media/image26.png)

**Abbildung 4-26.** Anzeigen vorhandener Images, die mithilfe von Docker-images

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Schritt 4: Definieren Sie Ihre Dienste im Docker-compose.yml beim Erstellen einer zusammengesetzten Docker-app mit mehreren Diensten

Mit der `docker-compose.yml` -Datei, Sie können definieren eine Gruppe von verwandten Diensten als zusammengesetzte Anwendung mit den Bereitstellungsbefehlen im nächsten Schritt Abschnitt beschrieben bereitgestellt werden.

Erstellen Sie diese Datei in Ihrem Haupt- oder stammlösungsordner; Er sollte ähnlichen Inhalt wie in diesem angezeigten haben `docker-compose.yml` Datei:

```yml
version: '3.4'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

In diesem speziellen Fall diese Datei definiert zwei Dienste: der Webdienst (Ihr benutzerdefinierter Dienst) und der Redis-Dienst (ein beliebten Cache-Dienst). Jeder Dienst wird als Container bereitgestellt werden, daher wir ein konkretes Docker-Image für die einzelnen zu verwenden müssen. Für diesen bestimmten Webdienst muss das Image die folgenden Schritte ausführen:

- Aus der dockerfile-Datei im aktuellen Verzeichnis erstellen

- Weiterleiten von den verfügbar gemachten Port 80 im Container Port 81 auf dem Hostcomputer

- Bereitstellen Sie Verzeichnis des Projekts, auf dem Host /code innerhalb des Containers, und es ermöglicht, dass Sie den Code ändern, ohne das Abbild neu erstellen

- Verknüpfen Sie den Webdienst mit Redis-Diensts

Der Redis-Dienst verwendet die [neueste öffentliche Redis-Image](https://hub.docker.com/_/redis/) mithilfe von Pull aus Docker Hub-Registrierung. [redis](https://redis.io/) ist ein beliebter Cache-System für serverseitige Anwendungen.

### <a name="step-5-build-and-run-your-docker-app"></a>Schritt 5: Erstellen und Ausführen der Docker-app

Wenn Ihre Anwendung nur einen einzelnen Container verfügt, müssen Sie nur ausführen, indem sie in Ihrem Docker-Host (VM oder physischer Server) bereitstellen. Wenn Ihre app aus mehreren Diensten besteht, müssen Sie jedoch *erstellen Sie sie*ebenfalls. Sehen Sie die verschiedenen Optionen an.

***Option A: Führen Sie ein einzelner Container oder Dienst***

Sie können das Docker-Image ausführen, mithilfe von "Docker run" Befehl aus, wie hier gezeigt:

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

Für diese bestimmte Bereitstellung müssen wir Umleiten von Anforderungen an Port 80 für den internen Port 5000 gesendet werden. Jetzt wird die Anwendung den externen Port 80 auf der Hostebene überwacht.

***Option B: Erstellen und Ausführen einer Anwendung von mehreren Containern***

In den meisten unternehmensumgebungen wird eine Docker-Anwendung aus mehreren Diensten bestehen. Sie können in diesen Fällen Ausführen der `docker-compose up` Befehl (Abbildung 4-27), der die Docker-compose.yml-Datei verwendet wird, die Sie zuvor erstellt haben. Mit diesem Befehl wird die zusammengesetzte Anwendung mit allen ihre zugehörigen Container bereitgestellt.

![Konsolenausgabe aus dem Docker-compose-Befehl.](./media/image27.png)

**Abbildung 4-27.** Ergebnisse der Ausführung des Befehls "Docker-compose up"

Nach der Ausführung `docker-compose up`, Sie bereitstellen Ihrer Anwendung und die zugehörigen Container in Ihrem Docker-Host, wie in Abbildung 4-28, in der VM-Darstellung dargestellt.

![VM, die Anwendungen mit mehreren Containern ausgeführt werden.](./media/image28.png)

**Abbildung 4-28.** VM mit bereitgestellten Docker-Containern

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Schritt 6: Testen Sie Ihre Docker-Anwendung (lokal, in Ihre lokale CD-VM)

Dieser Schritt hängen davon ab, was den Status Ihrer app.

In einer einfachen .NET Core-Web-API "Hello World" als ein einzelner Container oder der Dienst bereitgestellt müssten Sie nur Zugriff auf den Dienst durch die Bereitstellung des TCP-Ports in der dockerfile-Datei angegeben.

Wenn Sie "localhost" nicht aktiviert ist, navigieren Sie zu dem Dienst finden Sie die IP-Adresse für den Computer mit diesem Befehl:

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

Öffnen Sie einen Browser, und navigieren Sie zu dieser Website, auf dem Docker-Host; Ihre app/des Diensts ausgeführt wird, sollte angezeigt werden, wie in Abbildung 4-29 dargestellt.

![Browseransicht der Antwort von "localhost" / API/Values.](./media/image29.png)

**Abbildung 4-29.** Testen der Docker-Anwendung, die lokal mithilfe von "localhost"

Beachten Sie, dass Port 80 verwendet wird, aber intern zu Port 5000 umgeleitet werden wird, da es sich handelt, wie er bereitgestellt wurde, mit `docker run`, wie weiter oben erläutert.

Sie können dies testen, über das Terminal mithilfe von CURL. In einer Docker-Installation unter Windows ist die Standard-IP 10.0.75.1, an, wie in Abbildung 4-30 dargestellt.

![Konsolenausgabe an der Erledigung der http://10.0.75.1/API/values mit Curl](./media/image30.png)

**Abbildung 4-30.** Testen eine Docker-Anwendung lokal mithilfe von CURL

**Debuggen eines Containers ausführen unter Docker**

Visual Studio Code unterstützt Debuggen Docker an, wenn Sie Node.js und anderen Plattformen wie .NET Core-Container verwenden.

Sie können auch .NET Core oder .NET Framework-Containern in Docker Debuggen bei Verwendung von Visual Studio für Windows oder Mac zu erstellen, wie im nächsten Abschnitt beschrieben.

> [!INFORMATION]
>
> Wechseln Sie zu, um weitere Informationen zum Debuggen von Node.js-Docker-Containern <https://blog.docker.com/2016/07/live-debugging-docker/> und <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.

>[!div class="step-by-step"]
>[Zurück](docker-apps-development-environment.md)
>[Weiter](visual-studio-tools-for-docker.md)
