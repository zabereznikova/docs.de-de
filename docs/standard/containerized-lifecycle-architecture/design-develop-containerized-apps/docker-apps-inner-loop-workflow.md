---
title: Innere Schleife Entwicklungsworkflow für Docker-apps
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: f7acb60e6136c0250d18bdce23ac21fb6aa80b34
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148860"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Innere Schleife Entwicklungsworkflow für Docker-apps

Vor dem Auslösen des äußeren Schleife Workflows umfasst den gesamten DevOps-Zyklus, es beginnt alles auf dem Computer jedes Entwicklers, die app selbst zu codieren, verwenden ihren bevorzugten Sprachen oder Plattformen und diese lokal testen (Abbildung 4-14). In jedem Fall, müssen aber einen sehr wichtigen Punkt gemeinsam, unabhängig davon, welche Sprache, Framework oder Plattformen, die Sie auswählen. In diesem bestimmten Workflow immer entwickeln und Testen des Docker-Containern, aber lokal.

![](./media/image18.png)

Abbildung 4-14: Innere Schleife Development-Kontext

Der Container oder eine Instanz eines Docker-Images werden diese Komponenten enthalten:

-   Eine Betriebssystemauswahl (z.B. eine Linux-Distribution oder Windows)

-   Dateien, die vom Entwickler (z.B. app-Binärdateien) hinzugefügt

-   Konfiguration (z. B. umgebungseinstellungen und Abhängigkeiten)

-   Anweisungen für welche Aspekte Sie verarbeitet die Ausführung von Docker

Sie können die innere Schleife Entwicklungsworkflow einrichten, die Docker wie der Prozess (im nächsten Abschnitt beschrieben) verwendet. Berücksichtigen Sie, dass die ersten Schritte zum Einrichten der Umgebung ist nicht eingeschlossen werden, da Sie nur einmal durchführen müssen.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Erstellen eine einzelne app in Docker-Container mit Visual Studio Code und Docker-CLI

Apps bestehen aus Ihren eigenen Diensten sowie zusätzlichen Bibliotheken (Abhängigkeiten).

Abbildung 4-15 zeigt die grundlegenden Schritte, die Sie in der Regel beim Erstellen einer Docker-app, gefolgt von ausführliche Beschreibungen der einzelnen Schritte ausführen müssen.

![](./media/image19.png)

Abbildung 4-15: Allgemeiner Workflow für die Lebenszyklus von Docker-containeranwendungen mit Docker CLI

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Schritt 1: Beginnen mit dem Programmieren in Visual Studio Code, und erstellen Sie Ihrer ersten app/des Diensts

Die Möglichkeit, die Sie bei der Entwicklung Ihrer Anwendung ist ganz ähnlich wie Sie es ohne Docker. Der Unterschied ist, die beim Entwickeln, bereitstellen und Testen Ihre Anwendung oder Dienste, die in Docker-Containern platziert, die in Ihrer lokalen Umgebung (z.B. eine Linux-VM oder Windows) ausgeführt.

**Das Einrichten Ihrer lokalen Umgebung**

Mit den neuesten Versionen von Docker für Mac und Windows es ist einfacher als je zuvor zu Docker-Anwendungen entwickeln, und das Setup ist einfach.

**Weitere Informationen** Anweisungen zum Einrichten von Docker für Windows finden Sie unter [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).

Anweisungen zum Einrichten von Docker für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.

Darüber hinaus benötigen Sie einen Code-Editor, damit Sie Ihre Anwendung bei der Verwendung von Docker-CLI tatsächlich entwickeln können.

Microsoft bietet Visual Studio Code, einem einfachen Code-Editor, die unter Mac, Windows und Linux unterstützt, und bietet IntelliSense mit [Unterstützung für viele Sprachen](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python und die meisten Moderne Sprachen), [Debuggen](https://code.visualstudio.com/Docs/editor/debugging), [-Integration mit Git](https://code.visualstudio.com/Docs/editor/versioncontrol) und [unterstützen](https://code.visualstudio.com/docs/extensions/overview). Dieser Editor ist ideal für Mac und Linux-Entwickler. In Windows können Sie auch die vollständige Visual Studio-Anwendung verwenden.

**Weitere Informationen** finden Sie Anweisungen zum Installieren von Visual Studio für Windows, Mac oder Linux <https://code.visualstudio.com/docs/setup/setup-overview/>.

Sie arbeiten mit Docker-CLI und Schreiben Sie Ihren Code ein Code-Editor verwenden können, aber wenn Sie Visual Studio Code verwenden, macht es einfach, Autor dockerfile-Datei und Docker-compose.yml-Dateien in Ihrem Arbeitsbereich. Darüber hinaus können Sie Aufgaben für Visual Studio Code aus der IDE ausführen, die Skripts aufgefordert, die ausführliche Vorgänge, die mit Docker-CLI unter ausgeführt werden können.

Visual Studio Code wird von einer Erweiterung bereitgestellt, die Sie installieren müssen. Drücken Sie STRG + UMSCHALT + P, dazu geben **Ext installieren**, und führen Sie dann auf die Erweiterungen: Installieren Sie die Erweiterung-Befehl, um die Liste der Marketplace-Erweiterungen anzuzeigen. Geben Sie als Nächstes **Docker** zum Filtern der Ergebnisse, und wählen Sie dann die Dockerfile und Docker Compose-Datei (Yml) Erweiterung "Support" aus, wie in Abbildung 4-16 dargestellt.

![](./media/image20.png)

Abbildung 4 – 16: Installieren der Docker-Erweiterungs in Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Schritt 2: Erstellen Sie eine dockerfile-Datei im Zusammenhang mit einem vorhandenen Image (einfaches Betriebssystem oder entwicklungsumgebungen wie .NET Core, Node.js und Ruby)

Sie benötigen eine dockerfile-Datei pro benutzerdefiniertes Image erstellt werden und Container bereitgestellt werden, daher, wenn Ihre app aus einen benutzerdefinierten Dienst besteht, benötigen Sie eine einzelne dockerfile-Datei. Aber wenn Ihre app aus mehreren Diensten (wie in einer Microservices-Architektur) besteht, benötigen Sie eine dockerfile-Datei pro Dienst.

Die dockerfile-Datei befindet sich in der Regel im Stammordner Ihrer app oder Ihres Diensts und enthält die erforderlichen Befehle aus, damit Docker weiß, wie einrichten und Ausführen dieser app oder Ihres Diensts. Sie können die dockerfile-Datei zu erstellen und zu Ihrem Projekt zusammen mit Ihrem Code hinzufügen (.NET Core, node.js usw.), oder, wenn Sie in der Umgebung vertraut sind, sehen Sie sich den folgenden Tipp.

> [!TIP]
> Sie können ein Befehlszeilentool namens [yo Docker](https://github.com/Microsoft/generator-docker), der erstellt das Gerüst für die Dateien aus Ihrem Projekt in der Sprache Ihrer Wahl, und fügt die erforderlichen Docker-Konfigurationsdateien. Im Grunde genommen, um Entwicklern die ersten Schritte zu unterstützen, erstellt der entsprechenden dockerfile-Datei "Docker-Compose.yml", und die anderen zugehörigen Skripts zum Erstellen und Ausführen der Docker-Container. Diese Yeoman-Generators werden mit ein paar Fragen, Fragen Ihren ausgewählten Entwicklung Sprache und das Ziel der containerhost aufgefordert.

![yo Docker](./media/image21.png)

Beispielsweise zeigt die beiden Screenshots aus den Terminals Abbildung 4-17, in Windows und auf einem Mac in beiden Fällen "yo" denen Docker ausgeführt wird, die den Code Beispielprojekte (derzeit .NET Core, Golang und Node.js als unterstützten Sprachen) bereits so konfiguriert, dass die arbeiten generiert wird obere von Docker.

![](./media/image22.PNG)  ![](./media/image23.png)

Abbildung 4-17: yo Docker Befehlstool in Windows (links) und auf einem Mac

Abbildung 4-18 zeigt ein Beispiel mit yo Docker nachdem man von einem vorhandenen .NET Core-Projekt einrichten, um das Gerüst erstellt werden.

![](./media/image24.PNG)

Abbildung 4-18: yo Docker mit einem vorhandenen .NET Core vorgesehenes Projekt

Geben Sie aus der dockerfile-Datei welche Docker-Basisimage Sie verwenden möchten (z. B. mit "von microsoft/dotnet:1.0.0-core") an. In der Regel erstellen Sie Ihr benutzerdefinierte Image auf einem Basisimage, das Sie über alle offiziellen-Repository in abrufen können die [Docker Hub-Registrierung](https://hub.docker.com/) (z. B. eine [Images für .NET Core](https://hub.docker.com/r/microsoft/dotnet/) oder einem [für Node.js](https://hub.docker.com/_/node/)).

***Option A: Verwenden Sie ein vorhandenes offizielles dockerimage***

Mit einem offiziellen-Repository eines Stapels Sprache mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (einschließlich Entwicklung, Tests und Produktion) verfügbar sind.

Es folgt eine DockerFile-Beispieldatei für eine .NET Core-Container:

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

In diesem Fall ist es die Version 1.0.1 des offiziellen ASP.NET Core-Docker-Image für Linux mit dem Namen microsoft/aspnetcore:1.0.1 verwenden. Weitere Informationen finden Sie in der [ASP.NET Core-Docker-Image-Seite](https://hub.docker.com/r/microsoft/aspnetcore/) und [.NET Core-Docker-Image-Seite](https://hub.docker.com/r/microsoft/dotnet/). Außerdem können verwenden Sie einen anderen vergleichbares Bild wie Knoten: 4-Onbuild für Node.js oder vielen anderen vorkonfigurierten Images für Entwicklungssprachen erhältlich sind [Docker Hub](https://hub.docker.com/explore/).

In der dockerfile-Datei müssen Sie auch angeben, dass Docker zum TCP-Port zu lauschen, die Sie zur Laufzeit (z. B. Port 80) verwenden.

Es gibt andere Zeilen in der Konfiguration, die Sie in der dockerfile-Datei je nach Sprachen/Frameworks, die Sie verwenden, hinzufügen können, damit Docker weiß, wie Sie die app ausführen. Beispielsweise benötigen Sie die ENTRYPOINT-Zeile mit \["Dotnet", "MyCustomMicroservice.dll"\] eine .NET Core-app ausgeführt wird, obwohl Sie mehrere Varianten je nach den Ansatz zum Erstellen und Ausführen Ihres Diensts haben können. Wenn Sie verwenden das SDK und die Dotnet-CLI zum Erstellen und führen Sie die app .NET, wäre es etwas anders. Das Fazit ist, dass die ENTRYPOINT-Zeile sowie weitere Zeilen je nach Sprache/Plattform unterscheiden, die Sie für Ihre Anwendung auswählen.

**Weitere Informationen** Informationen über das Erstellen von Docker-Images für .NET Core-Anwendungen finden Sie unter <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.

Wechseln Sie zu, um weitere Informationen zum Erstellen Ihrer eigenen Images [ https://docs.docker.com/engine/\ Tutorials/Dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).

**Für mehrere Plattformen Image-Repositorys**

Wie Windows-Containern immer häufiger verwendet, kann ein einzelnes Repository Plattformvarianten, z. B. ein Linux- und Windows-Image enthalten. Dies ist ein neues Feature in Docker, das für die softwareaktualisierung ein einziges Repository für die verwenden mehrere Plattformen wie z. B. ermöglicht [Microsoft/Aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) -Repository, das an DockerHub-Registrierung verfügbar ist. Wie die Funktion aktiv ist, wird dieses Image von einem Windows-Host ziehen die Windows-Variante, rufen Sie während der gleiche ImageName von einem Linux-Host ziehen die Linux-Variante abruft.

***Option B: Ihr Basisimage von Grund auf neu erstellen***

Sie können Ihre eigenen Docker-Basisimage von Grund auf neu erstellen, wie dies unter [Artikel](https://docs.docker.com/engine/userguide/eng-image/baseimages/) von Docker. Dies ist ein Szenario, das ist wahrscheinlich nicht für Sie am besten, wenn Sie nur mit Docker beginnen, aber wenn Sie die bestimmten Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Schritt 3: Erstellen Sie Ihre benutzerdefinierten Docker-Images, die Ihrem Dienst darin einbetten

Für jeden benutzerdefinierten Dienst, die Ihre app umfasst, müssen Sie ein zugehöriges Image erstellen. Wenn Ihre app aus einem einzelnen Dienst oder Web-app besteht, benötigen Sie ein einziges Bild.

> [!NOTE]
> Wenn die "outer-Loop-DevOps-Workflow" berücksichtigen, die Bilder erstellt durch einen automatisierten Buildprozess zu, wenn Sie Ihren Quellcode in einem Git-Repository (Continuous Integration) übertragen, sodass die Bilder in der globalen Umgebung erstellt werden von Ihrem im Quellcode.

Aber bevor wir auf die äußere Schleife Route in Betracht ziehen, müssen wir sicherstellen, dass die Docker-Anwendung ordnungsgemäß funktioniert, damit sie Code nicht die Warteschlange übertragen, die auf das Quellcodeverwaltungssystem (Git, usw.) möglicherweise nicht ordnungsgemäß funktioniert.

Jeder Entwickler muss daher zuerst führen Sie den gesamten Entwicklungsworkflow Prozess zum Testen lokal und weiterentwickeln, bis eine vollständige Funktion mithilfe von Push übertragen, oder ändern Sie in das Quellcodeverwaltungssystem werden soll.

Um ein Image in Ihrer lokalen Umgebung und verwenden die dockerfile-Datei zu erstellen, können Sie die Docker-Erstellungsbefehl aus, wie in Abbildung 4-19 (Sie können auch ausführen Docker-compose up--build für Anwendungen besteht aus mehreren Containern/Diensten).

![](./media/image25.png)

Abbildung 4-19: Docker-Build ausgeführt wird

Anstatt direkt mit Docker erstellen Sie optional aus dem Ordner des Projekts, Sie können zuerst einen bereitstellbaren Ordner mit den .NET-Bibliotheken erforderlich sind, mit der Ausführung Dotnet-publish-Befehl aus, und führen Sie Docker Build generieren.

In diesem Beispiel ist dies ein Docker-Image erstellt, mit dem Namen Cesardl/Netcore-Webapi-Microservice-Docker: First (: zuerst wird ein Tag, wie eine bestimmte Version). Sie können diesen Schritt für jedes benutzerdefinierte Image nutzen, die Sie für Ihre zusammengesetzte Docker-Anwendung mit mehreren Containern erstellen müssen.

Die vorhandenen Images finden in Ihrem lokalen Repository (Entwicklungscomputer) Sie unter Verwendung von Docker Images-Befehl, wie in Abbildung 4-20 dargestellt.

![](./media/image26.png)

Abbildung 4-20: Anzeigen vorhandener Images, die mithilfe von Docker-images

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Schritt 4: (Optional) Definieren Sie Ihre Dienste im Docker-compose.yml beim Erstellen einer zusammengesetzten Docker-app mit mehreren Diensten

Mit der Docker-compose.yml-Datei können Sie eine Reihe von verknüpften Diensten als zusammengesetzte Anwendung bereitgestellt werden, mit den Bereitstellungsbefehlen im nächsten Schritt Abschnitt erläutert definieren.

Sie müssen diese Datei in Ihrem Haupt- oder stammlösungsordner erstellen; Sie müssen einen vergleichbaren Artikel in der folgenden Docker-compose.yml-Datei:

```yml
version: '2'
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

-   Aus der dockerfile-Datei im aktuellen Verzeichnis erstellen

-   Weiterleiten von den verfügbar gemachten Port 80 im Container Port 81 auf dem Hostcomputer

-   Bereitstellen Sie Verzeichnis des Projekts, auf dem Host /code innerhalb des Containers, und es ermöglicht, dass Sie den Code ändern, ohne das Abbild neu erstellen

-   Verknüpfen Sie den Webdienst mit Redis-Diensts

Der Redis-Dienst verwendet die [neueste öffentliche Redis-Image](https://hub.docker.com/_/redis/) mithilfe von Pull aus Docker Hub-Registrierung. [redis](https://redis.io/) ist ein sehr beliebtes Cache-System für serverseitige Anwendungen.

### <a name="step-5-build-and-run-your-docker-app"></a>Schritt 5: Erstellen und Ausführen der Docker-app

Wenn Ihre Anwendung nur einen einzelnen Container verfügt, müssen Sie nur ausführen, indem sie in Ihrem Docker-Host (VM oder physischer Server) bereitstellen. Wenn Ihre app aus mehreren Diensten besteht, müssen Sie jedoch *erstellen Sie sie*ebenfalls. Sehen Sie die verschiedenen Optionen an.

***Option A: Führen Sie ein einzelner Container oder Dienst***

Sie können das Docker-Image ausführen, mithilfe von "Docker run" Befehl aus, wie hier gezeigt:

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

Beachten Sie, dass für diese bestimmte Bereitstellung, wir an Port 80 für den internen Port 5000 gesendete Anforderungen umgeleitet werden. Nun wird die Anwendung den externen Port 80 auf der Hostebene überwacht.

***Option B: Erstellen und Ausführen einer Anwendung von mehreren Containern***

In den meisten unternehmensumgebungen wird eine Docker-Anwendung aus mehreren Diensten bestehen. In diesen Fällen können Sie den Befehl ausführen Docker-compose-einrichten (Abbildung 4-21), die verwenden der Docker-compose.yml-Datei, die Sie zuvor erstellt haben. Mit diesem Befehl wird die zusammengesetzte Anwendung mit allen ihre zugehörigen Container bereitgestellt.

![](./media/image27.png)

Abbildung 4-21: Ergebnisse der Ausführung des Befehls "Docker-compose up"

Nach dem Ausführen von Docker-compose-einrichten, Sie bereitstellen Ihrer Anwendung und die zugehörigen Container in Ihrem Docker-Host, wie in Abbildung 4-22, in der VM-Darstellung dargestellt.

![](./media/image28.png)

Abbildung 4-22: VM mit bereitgestellten Docker-Containern

Hinweis Docker-compose-einrichten und "Docker run" möglicherweise für Ihre Container in Ihrer Entwicklungsumgebung testen ausreichend, aber Sie möglicherweise verwenden sie überhaupt nicht, wenn Sie erwarten, arbeiten mit Docker-Cluster und orchestratoren wie Docker Swarm, Mesosphere DC/OS oder Kubernetes Damit Sie zentral hochskalieren können. Wenn Sie einen Cluster wie verwenden [Docker Swarm-Modus](https://docs.docker.com/engine/swarm/) (verfügbar in Docker für Windows und Mac ab Version 1.12), müssen Sie zum Bereitstellen und Testen mit zusätzlichen Befehlen, z. B. Docker-Dienst für einzelne Dienste erstellen, oder wenn Sie sich befinden Bereitstellen einer app, bestehend aus mehreren Containern mit Docker compose-Paket und Docker bereitstellen MyBundleFile, als Stapel, das Bereitstellen von der app aus, wie in diesem Artikel erläutert [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) von Docker.

Für [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) und [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) verwenden Sie unterschiedliche Bereitstellungsbefehle und Skripts, als auch.

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Schritt 6: Testen Sie Ihre Docker-Anwendung (lokal, in Ihre lokale CD-VM)

Dieser Schritt hängen davon ab, was den Status Ihrer app.

In einer einfachen .NET Core Web-API "Hello World" als ein einzelner Container oder der Dienst bereitgestellt müssten Sie nur Zugriff auf den Dienst durch die Bereitstellung des TCP-Ports in der dockerfile-Datei angegeben.

Wenn Sie "localhost" nicht aktiviert ist, navigieren Sie zu dem Dienst finden Sie die IP-Adresse für den Computer mit diesem Befehl:

Docker-Machine-Ip *Container Name-Ihrer-*

Öffnen Sie einen Browser, und navigieren Sie zu dieser Website, auf dem Docker-Host; Ihre app/des Diensts ausgeführt wird, sollte angezeigt werden, wie in Abbildung 4-23 veranschaulicht.

![](./media/image29.png)

Abbildung 4-23: Testen der Docker-Anwendung, die lokal mithilfe von "localhost"

Beachten Sie, dass Port 80 verwendet wird, aber er intern wird, an Port 5000 umgeleitet wurde, denn das ist wie mit "Docker run", bereitgestellt wurde wie weiter oben erläutert.

Sie können dies testen, über das Terminal mithilfe von CURL. In einer Docker-Installation unter Windows ist die Standard-IP 10.0.75.1, an, wie in Abbildung 4-24 dargestellt.

![](./media/image30.png)

Abbildung 4-24: Testen eine Docker-Anwendung lokal mithilfe von CURL

**Debuggen eines Containers ausführen unter Docker**

Visual Studio Code unterstützt Debuggen Docker an, wenn Sie Node.js und anderen Plattformen wie .NET Core-Container verwenden.

Sie können auch .NET Core in Docker-Container Debuggen bei Verwendung von Visual Studio, wie im nächsten Abschnitt beschrieben.

**Weitere Informationen:** wechseln Sie zu, um weitere Informationen zum Debuggen von Node.js-Docker-Containern <https://blog.docker.com/2016/07/live-debugging-docker/> und [ https://blogs.msdn.microsoft.com/\ Benutzer\_Ed/2016/02/27 / Visual-Studio-Code-New-Features-13-Big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-Mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).

>[!div class="step-by-step"]
>[Zurück](docker-apps-development-environment.md)
>[Weiter](visual-studio-tools-for-docker.md)