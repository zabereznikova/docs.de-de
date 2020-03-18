---
title: Inner-Loop-Entwicklungsworkflow für Docker-Apps
description: Lernen Sie den Workflow der „inneren Schleife“ bei der Entwicklung von Docker-Anwendungen kennen.
ms.date: 02/15/2019
ms.openlocfilehash: 3d2fc889d22dbf02acccfbf9231ad98fca224cff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936813"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Inner-Loop-Entwicklungsworkflow für Docker-Apps

Bevor der Workflow der äußeren Schleife ausgelöst wird, der den gesamten DevOps-Zyklus umspannt, beginnt alle auf den Computern der einzelnen Entwickler, die den eigentlichen Code für die App in den bevorzugten Sprachen oder auf den bevorzugten Plattformen erstellen und ihn lokal testen (Abbildung 4–21). In jedem Fall haben Sie aber einen wichtigen Punkt gemein, unabhängig von Ihrer Wahl von Sprache, Framework oder Plattform. In diesem besonderen Workflow entwickeln und testen Sie stets Docker-Container, das aber lokal.

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

Mit den neuesten Versionen von Docker für Mac und Windows ist es einfacher denn je, Docker-Anwendungen zu entwickeln, und die Einrichtung ist geradlinig.

> [!TIP]
> Anweisungen zum Einrichten von Docker für Windows finden Sie unter <https://docs.docker.com/docker-for-windows/>.
>
>Anweisungen zum Einrichten von Docker für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.

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

![Ansicht der Docker-Erweiterung für Visual Studio Code.](./media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

**Abbildung 4-23.** Installieren der Docker-Erweiterung in Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Schritt 2: Erstellen eines DockerFile zu einem vorhandenen Image (einfaches Betriebssystem oder Entwicklungsumgebungen wie .NET Core, Node.js und Ruby)

Sie benötigen ein `DockerFile` pro erstelltem benutzerdefiniertem Image und pro bereitzustellendem Container. Wenn Ihre App aus einem einzelnen benutzerdefinierten Dienst besteht, benötigen Sie ein einzelnes `DockerFile`. Wenn Ihre App sich jedoch aus mehreren Diensten zusammensetzt (wie bei einer Microservices-Architektur), benötigen Sie ein `Dockerfile` pro Dienst.

Das `DockerFile` Dockerfile wird üblicherweise im Stammordner Ihrer App oder Ihres Dienstes platziert und enthält die erforderlichen Befehle, um Docker anzuweisen, wie der betreffende Dienst einzurichten und auszuführen ist. Sie können Ihr `DockerFile` erstellen und es Ihrem Projekt zusammen mit Ihrem Code (node.js, .NET Core usw.) hinzufügen, oder sich den folgenden Tipp ansehen, wenn Sie gerade erst in die Umgebung einsteigen.

> [!TIP]
> Sie können die Docker-Erweiterung zur Führung beim Verwenden der `Dockerfile`- und `docker-compose.yml`-Dateien zu Ihren Docker-Containern verwenden. Im Lauf der Zeit werden Sie diese Art von Dateien wahrscheinlich ohne dieses Tool schreiben, die Verwendung der Docker-Erweiterung bildet aber einen guten Ausgangspunkt, der Ihren Lernprozess beschleunigt.

In Abbildung 4–24 können Sie sehen, wie eine docker-compose-Datei mithilfe der Docker-Erweiterung für VS Code hinzugefügt wird.

![Konsolenansicht der Docker-Erweiterung für VS Code.](./media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

**Abbildung 4-24.** Mithilfe des Befehls **Add Docker files to Workspace** (Docker-Dateien zu Arbeitsbereich hinzufügen) hinzugefügte Docker-Dateien

Wenn Sie ein DockerFile hinzufügen, geben Sie an, welches Docker-Basisimage Sie verwenden (wie bei der Verwendung von `FROM mcr.microsoft.com/dotnet/core/aspnet`). Normalerweise erstellen Sie Ihr benutzerdefiniertes Image auf der Grundlage einem Basisimage, das Sie aus einem beliebigen offiziellen Repository in der [Docker Hub-Registrierung](https://hub.docker.com/) beziehen (wie ein [Image für .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) oder das Image [für Node.js](https://hub.docker.com/_/node/)).

***Verwenden eines vorhandenen offiziellen Docker-Images***

Durch Verwendung eines offiziellen Repositorys eines Sprachstapels mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (Entwicklung, Test und Produktion) verfügbar sind.

Das Folgende ist ein Beispiel-DockerFile für einen .NET Core-Container:

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

In diesem Fall basiert das Image auf Version 2.2 des offiziellen ASP.NET Core-Docker-Images (mehrere Architekturen für Linux und Windows), gemäß der Zeile `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`. (Weitere Informationen zu diesem Thema finden Sie unter [ASP.NET Core Docker Image (ASP.NET Core-Docker-Image)](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) und [.NET Core Docker Image (.NET Core-Docker-Image)](https://hub.docker.com/_/microsoft-dotnet-core/).)

In dem DockerFile können Sie Docker außerdem anweisen, an dem TCP-Port zu lauschen, den Sie zur Laufzeit verwenden möchten (z.B. Port 80).

Je nach Sprache und Framework, die Sie verwenden, können Sie zusätzliche Konfigurationseinstellungen in der Dockerfile angeben. Beispielsweise weist die `ENTRYPOINT`-Zeile mit `["dotnet", "MySingleContainerWebApp.dll"]` Docker an, eine .NET Core-Anwendung auszuführen. Wenn Sie das SDK und die .NET Core-CLI (`dotnet CLI`) verwenden, um die .NET-Anwendung zu entwickeln und auszuführen, wird eine andere Einstellung verwendet. Entscheidend ist, dass die ENTRYPOINT-Zeile und andere Einstellungen von der Sprache und Plattform abhängen, die Sie für Ihre Anwendung auswählen.

> [!TIP]
> Weitere Informationen zum Erstellen von Docker-Images für .NET Core-Anwendungen finden Sie unter <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.
>
> Weitere Informationen über das Erstellen eigener Images finden Sie unter <https://docs.docker.com/engine/tutorials/dockerimages/>.

**Verwenden von Repositorys für Images für mehrere Architekturen**

Der Name eines einzelnen Images in einem Repository kann Plattformvarianten enthalten, wie z.B. ein Linux-Image und ein Windows-Image. Dieses Feature ermöglicht Anbietern wie Microsoft (Basisimageentwickler), ein Repository für mehrere Plattformen (Linux und Windows) zu entwickeln. Das in der Docker Hub-Registrierung verfügbare [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)-Repository bietet beispielsweise Unterstützung für Linux und Windows Nano Server dadurch, dass der gleiche Imagename verwendet wird.

Beim Pullen des [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)-Images von einem Windows-Host wird die Windows-Variante gepullt, während das Pullen des gleichen Imagenamens von einem Linux-Host ein Pullen der Linux-Variante bewirkt.

***Erstellen eines Basisimages von Grund auf***

Sie können Ihr eigenes Docker-Basisimage von Grund auf neu erstellen, wie in diesem [Artikel](https://docs.docker.com/engine/userguide/eng-image/baseimages/) von Docker erläutert. Dieses Szenario ist für Sie vermutlich nicht ideal, wenn Sie gerade erst in Docker einsteigen, aber wenn Sie die spezifischen Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Schritt 3: Erstellen eines angepassten Docker-Images durch Einbetten eines Diensts

Für jeden benutzerdefinierten Dienst, den Ihre App beinhaltet, müssen Sie ein zugehöriges Image erstellen. Wenn Ihre App aus einem einzelnen Dienst oder einer einzelnen Web-App besteht, benötigen Sie nur ein einzelnes Image.

> [!NOTE]
> Wenn Sie die „DevOps-Workflow der äußeren Schleife“ berücksichtigen, werden immer, wenn Sie Ihren Quellcode per Push in ein Git-Repository übertragen (Continuous Integration), die Images mithilfe eines automatisierten Buildprozesses erstellt, sodass die Images in der globalen Umgebung aus Ihrem Quellcode erstellt werden.
>
> Bevor wir aber den Weg in die äußere Schleife in Betracht ziehen, müssen wir sicherstellen, dass die Docker-Anwendung tatsächlich ordnungsgemäß arbeitet, sodass kein Code an das Quellcodeverwaltungssystem (Git usw.) übertragen wird, der möglicherweise nicht ordnungsgemäß funktioniert.
>
> Daher muss jeder Entwickler zuerst den gesamten Prozess der inneren Schleife absolvieren, um lokal zu testen und mit der Entwicklung fortzufahren, bis er eine vollständige Funktion oder Änderung an das Quellcodeverwaltungssystem übertragen möchte.

Um ein Image in Ihrer lokalen Umgebung zu erstellen und das DockerFile zu verwenden, können Sie den Docker-Erstellungsbefehl verwenden, wie in Abbildung 4–25 veranschaulicht (Sie können auch `docker-compose up --build` für Anwendungen ausführen, die aus mehreren Containern/Diensten zusammengesetzt sind).

![Der Screenshot zeigt die Konsolenausgabe des Befehls „docker build“.](./media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

**Abbildung 4-25.** Ausführen des Docker-Erstellungsbefehls

Statt `docker build` direkt aus dem Projektordner auszuführen, können Sie optional auch zuerst einen bereitstellbaren Ordner mit den erforderlichen .NET-Bibliotheken generieren, indem Sie den `dotnet publish`-Ausführungsbefehl verwenden und dann `docker build` ausführen.

Dieses Beispiel erstellt ein Docker-Image mit dem Namen `cesardl/netcore-webapi-microservice-docker:first` (`:first` ist ein Tag, wie eine spezifische Version). Sie können diesen Schritt für jedes benutzerdefinierte Image ausführen, das Sie für Ihre aus mehreren Containern zusammengesetzte Docker-Anwendung erstellen müssen.

Sie können die vorhandenen Images in Ihrem lokalen Repository (Ihrem Bereitstellungscomputer) suchen, indem Sie den „docker images“-Befehl verwenden, wie in Abbildung 4–26 dargestellt.

![Konsolenausgabe des Befehls „docker images“, gezeigt werden vorhandene Images.](./media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

**Abbildung 4-26.** Anzeigen vorhandener Images mithilfe des Befehls „docker images“

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Schritt 4: Definieren Ihrer Dienste in der Datei „docker-compose.yml“ beim Erstellen einer zusammengesetzten Docker-Anwendung mit mehreren Diensten

Mit der Datei `docker-compose.yml` können Sie einen Satz verwandter Dienste definieren, die mit den im nächsten Schritt beschriebenen Bereitstellungsbefehlen als zusammengesetzte Anwendung bereitgestellt werden sollen.

Erstellen Sie die betreffende Datei in Ihrem Haupt- oder Stamm-Projektmappenordner; seine Inhalte sollten ähnlich den in dieser `docker-compose.yml`-Datei dargestellten sein:

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

In diesem speziellen Fall definiert diese Datei zwei Dienste: den Webdienst (Ihren benutzerdefinierten Dienst) und den Redis-Dienst (einen beliebten Cachedienst). Jeder Dienst wird als Container bereitgestellt, wir müssen also für jeden ein konkretes Docker-Image verwenden. Für diesen speziellen Webdienst muss das Image Folgendes leisten:

- Einen Build aus dem DockerFile im aktuellen Verzeichnis erstellen

- Den verfügbar gemachten Port 80 des Containers an Port 81 auf dem Hostcomputer weiterleiten

- Das Projektverzeichnis auf dem Host für „/code“ innerhalb des Containers einzubinden, was es Ihnen ermöglicht, den Code zu ändern, ohne das Image neu erstellen zu müssen

- Den Webdienst mit dem Redis-Dienst verknüpfen

Der Redis-Dienst verwendet die [neuesten öffentliche Redis-Image](https://hub.docker.com/_/redis/), die er mithilfe von Pull aus Docker Hub-Registrierung abruft. [Redis](https://redis.io/) ist ein beliebtes Cachesystem für serverseitige Anwendungen.

### <a name="step-5-build-and-run-your-docker-app"></a>Schritt 5: Erstellen und Ausführen Ihrer Docker-App

Wenn Ihre App nur einen einzelnen Container aufweist, müssen Sie ihn lediglich ausführen, indem Sie ihn auf Ihrem Docker-Host (VM oder physischer Server) bereitstellen. Wenn sich Ihre App jedoch aus mehreren Diensten zusammensetzt, müssen Sie sie außerdem *zusammenstellen*. Betrachten wir die verschiedenen Optionen.

***Option A: Ausführen eines einzelnen Containers oder Diensts***

Sie können das Docker-Image mithilfe des Ausführen-Befehls von Docker ausführen, wie hier gezeigt:

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

Für diese spezielle Bereitstellung leiten wir Anforderungen, die an Port 80 gesendet werden, an den internen Port 5000 um. Jetzt lauscht die Anwendung am externen Port 80 auf der Hostebene.

***Option B: Zusammenstellen und Ausführen einer aus mehreren Containern bestehenden Anwendung***

In den meisten Unternehmensszenarien ist eine Docker-Anwendung aus mehreren Diensten zusammengesetzt. In diesen Fällen können Sie den `docker-compose up`-Befehl (Abbildung 4–27) ausführen, der die docker-compose.yml-Datei verwendet, die Sie möglicherweise bereits zuvor erstellt haben. Durch Ausführen dieses Befehls wird eine zusammengesetzte Anwendung mit allen zugehörigen Containern bereitgestellt.

![Konsolenausgabe des Befehls „docker-compose up“.](./media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

**Abbildung 4-27.** Ergebnisse der Ausführung des Befehls „docker-compose up“

Nach dem Ausführen von `docker-compose up` stellen Sie Ihre Anwendung und ihre zugehörigen Container auf Ihrem Docker-Host bereit, wie in Abbildung 4–28 in der VM-Darstellung abgebildet.

![VM, die Anwendungen aus mehreren Containern ausführt.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

**Abbildung 4-28.** VM mit bereitgestellten Docker-Containern

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Schritt 6: Testen der Docker-Anwendung (lokal, auf Ihrer lokalen CD-VM)

Dieser Schritt unterscheidet sich je nachdem, welche Aktionen Ihre App ausführt.

In einer einfachen .NET Core-Web-API „Hallo Welt“, die als einzelner Container oder Dienst bereitgestellt wird, müssen Sie lediglich auf den Dienst zugreifen, indem Sie den im DockerFile angegebenen TCP-Port übergeben.

Wenn localhost nicht aktiviert ist, navigieren Sie zu Ihrem Dienst, indem Sie die IP-Adresse für den Computer mithilfe dieses Befehls ermitteln:

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

Öffnen Sie auf dem Docker-Host einen Browser, und navigieren Sie zu der betreffenden Website; Sie sollten Ihre aktiv ausgeführte App/Ihren ausgeführten Webdienst sehen, wie in Abbildung 4–29 dargestellt.

![Browseransicht der Antwort von „localhost/API/values“.](./media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

**Abbildung 4-29.** Lokales Testen Ihrer Docker-Anwendung mithilfe von localhost

Beachten Sie, dass sie Port 80 verwendet, der aber intern an Port 5000 umgeleitet wird, weil es in dieser Weise mit `docker run` bereitgestellt wurde, wie bereits zuvor erläutert.

Sie können dies mithilfe von CURL am Terminal testen. In einer Docker-Installation unter Windows ist die Standard-IP-Adresse 10.0.75.1, wie in Abbildung 4–30 dargestellt.

![Konsolenausgabe beim Abrufen von http://10.0.75.1/API/values mit curl](./media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

**Abbildung 4-30.** Lokales Testen einer Docker-Anwendung mithilfe von CURL

**Debuggen eines in Docker ausgeführten Containers**

Visual Studio Code unterstützt das Debuggen von Docker, wenn Sie Node.js und andere Plattformen wie .NET Core-Container verwenden.

Wenn Sie Visual Studio für Windows oder Mac verwenden, können Sie darüber hinaus .NET Core- oder .NET Framework-Container in Docker debuggen, wie im nächsten Abschnitt beschrieben.

> [!TIP]
> Weitere Informationen zum Debuggen von Node.js-Docker-Containern finden Sie unter <https://blog.docker.com/2016/07/live-debugging-docker/> und <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.

>[!div class="step-by-step"]
>[Zurück](docker-apps-development-environment.md)
>[Weiter](visual-studio-tools-for-docker.md)
