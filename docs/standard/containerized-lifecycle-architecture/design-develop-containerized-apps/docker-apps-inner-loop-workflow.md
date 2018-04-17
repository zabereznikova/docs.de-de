---
title: Innere Schleife Entwicklungsworkflow für Docker-apps
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7f49b19b0836636bf7656dc618ef2f181a0d7fff
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Innere Schleife Entwicklungsworkflow für Docker-apps

Vor dem Auslösen des äußeren Schleife Workflows umfasst die gesamte DevOps durchlaufen, Ausgangspunkt für alle weiteren auf jeder Entwickler-Computer, codieren die app selbst, ihren bevorzugten Sprachen oder Plattformen verwenden und lokal testen (Abbildung 4-14). In jedem Fall, müssen aber einen sehr wichtigen Punkt gemeinsam, unabhängig davon, welche Sprache, Framework oder Plattformen, die Sie auswählen. In diesem bestimmten Workflow immer entwickeln und Testen des Docker-Containern lokal.

![](./media/image18.png)

Abbildung 4 – 14: innere Schleife Entwicklung Kontext

Der Container oder eine Instanz des Docker-Images werden diese Komponenten enthalten:

-   Eine Auswahl des Betriebssystems (z. B. eine Linux-Distribution oder Windows)

-   Dateien vom Entwickler (z. B. app Binärdateien) hinzugefügt

-   Konfiguration (z. B. umgebungseinstellungen und Abhängigkeiten)

-   Anweisungen für welche Prozesse für die Ausführung von Docker

Sie können die innere Schleife Entwicklungsworkflow einrichten, auf dem Docker wie der Prozess (im nächsten Abschnitt beschrieben) ausgeführt. Berücksichtigen Sie, dass die ersten Schritte zum Einrichten der Umgebung ist nicht enthalten, da die, die nur einmal durchführen müssen.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Erstellen eine einzelne app in einem Docker-Container mithilfe von Visual Studio Code und Docker-Befehlszeilenschnittstelle

Apps bestehen aus Ihrer eigenen Services plus zusätzliche Bibliotheken (Abhängigkeiten).

Abbildung 4-15 zeigt die grundlegenden Schritte, die Sie in der Regel beim Erstellen einer app Docker ein, gefolgt von detaillierten Beschreibungen der einzelnen Schritte ausführen müssen.

![](./media/image19.png)

Abbildung 4 – 15: Allgemeine Workflow für den Lebenszyklus Anwendungsmöglichkeiten Docker-Containern mit Docker-Befehlszeilenschnittstelle

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Schritt 1: Beginnen Sie in Visual Studio-Code codieren, und erstellen Sie Ihre erste Anwendungsdienst

Die Möglichkeit, die Entwicklung der Anwendung ist ziemlich ähnlich wie bei, die Sie dies, ohne Docker tun. Der Unterschied besteht darin, dass beim Entwickeln, sind Sie bereitstellen und Testen Ihrer Anwendung oder ausgeführte dateiserverdienste Docker-Containern, die in Ihrer lokalen Umgebung (z. B. ein Linux-VM oder -Windows) platziert.

**Das Einrichten der lokalen Umgebung**

Mit den neuesten Versionen von Docker für Macintosh und Windows es ist einfacher als je, Docker-Anwendungen entwickeln, und das Setup ist einfach.

**Weitere Informationen** finden Sie eine Anleitung zum Einrichten von Docker für Windows [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).

Anweisungen zum Einrichten von Docker für Mac, wechseln Sie zu <https://docs.docker.com/docker-for-mac/>.

Darüber hinaus benötigen Sie einen Code-Editor, damit Sie Ihre Anwendung bei der Verwendung von Docker-Befehlszeilenschnittstelle tatsächlich entwickeln können.

Microsoft bietet Visual Studio-Code, der eine einfache Code-Editor, die auf Windows, Mac und Linux unterstützt wird ist, und bietet IntelliSense mit [für viele Sprachen unterstützen](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET Go, Java, Ruby, Python, und die meisten modernen Sprachen), [Debuggen](https://code.visualstudio.com/Docs/editor/debugging), [Integration mit Git](https://code.visualstudio.com/Docs/editor/versioncontrol) und [unterstützen](https://code.visualstudio.com/docs/extensions/overview). Dieser Editor ist hervorragend für Mac und Linux-Entwickler. In Windows können Sie auch die vollständige Visual Studio-Anwendung.

**Weitere Informationen** finden Sie Anweisungen zum Installieren von Visual Studio für Windows, Mac und Linux [ http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/ ](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).

Sie können mit Docker-Befehlszeilenschnittstelle arbeiten und Ihren Code mit einem beliebigen Codeeditor schreiben, aber bei Verwendung von Visual Studio Code macht es einfach, zum Erstellen von dockerfile-Datei und Docker-compose.yml-Dateien in Ihrem Arbeitsbereich. Darüber hinaus können Sie Aufgaben für Visual Studio-Code aus der IDE ausführen, die Skripts aufgefordert, die ausführlichen mit Docker-Befehlszeilenschnittstelle, darunter Vorgänge ausgeführt werden können.

Visual Studio-Code ist durch eine Erweiterung bereitgestellt, die Sie installieren müssen. Drücken Sie STRG + UMSCHALT + P dazu geben **Ext installieren**, und führen Sie die Erweiterungen: Erweiterung installieren-Befehl, um die Liste der Marketplace-Erweiterung zu öffnen. Geben Sie als Nächstes **Docker** zum Filtern der Ergebnisse, und wählen Sie die dockerfile-Datei und Docker verfassen Datei (Yml) Support-Erweiterung, wie in Abbildung 4-16 dargestellt.

![](./media/image20.png)

Abbildung 4 – 16: die Docker-Erweiterung in Visual Studio Code installieren

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Schritt 2: Erstellen einer dockerfile-Datei im Zusammenhang mit einem vorhandenen Image (plain OS oder Dev Umgebungen wie .NET Core, Node.js und Ruby)

Sie benötigen eine dockerfile-Datei pro benutzerdefiniertes Bild erstellt werden sollen und Container bereitgestellt werden, daher, wenn Ihre app aus einem einzelnen benutzerdefinierten Dienst besteht, benötigen Sie eine einzelne dockerfile-Datei. Aber wenn Ihre app aus mehreren Diensten (wie eine Microservices-Architektur) besteht, benötigen Sie eine dockerfile-Datei pro Dienst.

Die dockerfile-Datei befindet sich im Stammordner der Ihrer app oder Ihrem Dienst in der Regel und die erforderlichen Befehle enthält, damit diese Docker weiß, wie einrichten und Ausführen dieser app oder einen Dienst. Sie können Ihr dockerfile-Datei erstellen und dem Projekt zusammen mit Ihrem Code hinzufügen (.NET Core, node.js usw.), oder wenn Sie mit der Umgebung vertraut sind, sehen Sie sich die folgenden Tipps.

> [!TIP]
> Können Sie ein Befehlszeilentool namens [Handelsversion Docker](https://github.com/Microsoft/generator-docker), dem Gerüste Dateien aus Ihrem Projekt in der Sprache, die Sie auswählen, und fügt die erforderlichen Dateien der Docker-Konfiguration. Im Grunde um Entwicklern die ersten Schritte zu unterstützen, erstellt er die entsprechenden dockerfile-Datei Docker-compose.yml und anderen zugehörigen Skripts zum Erstellen und Ausführen von Docker-Containern. Dieses Yeoman-Generators werden einige Fragen, Fragen die ausgewählte Sprache und Ziel Container Entwicklungshost aufgefordert.

![Handelsversion Docker](./media/image21.png)

Beispielsweise zeigt Abbildung 4 – 17 zwei Screenshots aus der Terminals in Windows und auf einem Mac, in beiden Fällen zu ausgeführt Handelsversion Docker, die den Code Beispielprojekte (derzeit .NET Core, Golang und Node.js als unterstützten Sprachen) bereits so konfiguriert, dass arbeiten generieren wird Anfang Docker.

![](./media/image22.PNG)  ![](./media/image23.png)

Abbildung 4 – 17: Handelsversion Docker Befehl Tool in Windows (links) und auf einem Mac

Abbildung 4 – 18 zeigt ein Beispiel für verwendet werden, können Docker Nachdem Sie ein vorhandenes Projekt für .NET Core zu Gerüstbau werden verfügen.

![](./media/image24.PNG)

Abbildung 4 – 18: Handelsversion Docker mit einer vorhandenen .NET Core Projekt vorhanden

Geben Sie aus der dockerfile-Datei welche Basis Docker-Image, das Sie verwenden (z. B. mit "von microsoft/dotnet:1.0.0-core") an. In der Regel erstellen Sie Ihr benutzerdefinierte Bild eine Basis-Image, die Sie aus jeder offizielle Repository auf der [Docker Hub-Registrierung](https://hub.docker.com/) (z. B. ein [Bild für .NET Core](https://hub.docker.com/r/microsoft/dotnet/) oder einem [für Node.js](https://hub.docker.com/_/node/)).

***Option A: Verwenden eines vorhandenen offizielle Docker-Images***

Mit einem offiziellen Repository Sprache Stapel mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (einschließlich Entwicklungs-, Test- und Produktionszwecke) verfügbar sind.

Es folgt ein Beispiel für dockerfile-Datei für einen .NET Core-Container:

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

In diesem Fall wird die Version 1.0.1 des offiziellen ASP.NET Core Docker-Images für Linux mit dem Namen microsoft/aspnetcore:1.0.1 verwendet. Weitere Informationen finden Sie in der [ASP.NET Core Docker-Image-Seite](https://hub.docker.com/r/microsoft/aspnetcore/) und [.NET Core Docker-Image-Seite](https://hub.docker.com/r/microsoft/dotnet/). Auch konnten verwenden Sie ein anderes vergleichbare Bild wie Knoten: 4-Onbuild für Node.js oder viele andere vorkonfigurierter Images für die Entwicklungssprachen, von denen in verfügbaren [Docker Hub](https://hub.docker.com/explore/).

In der dockerfile-Datei müssen Sie auch weisen Docker an, den TCP-Port zu überwachen, die zur Laufzeit (z. B. Port 80) verwendet werden.

Es gibt andere Zeilen Konfiguration, die Sie in die dockerfile-Datei je nach Sprache/Framework, die Sie verwenden, die hinzufügen können, damit Docker weiß, wie die app ausgeführt werden kann. Sie benötigen beispielsweise die ENTRYPOINT-Zeile mit \["Dotnet", "MyCustomMicroservice.dll"\] eine app .NET Core ausgeführt wird, obwohl Sie mehrere Varianten abhängig von der Ansatz zum Erstellen und führen Sie den Dienst verwenden können. Wenn Sie verwenden das SDK und Dotnet CLI erstellen und Ausführen der app .NET, wäre es etwas anders. Entscheidend ist, dass die ENTRYPOINT-Zeile plus zusätzliche Zeilen je nach der Sprachplattform unterschiedlich sind, die Sie für Ihre Anwendung auswählen.

**Weitere Informationen** finden Sie Informationen zum Erstellen von Docker-Images für .NET Core-Anwendungen, <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.

Wechseln Sie zu, um weitere Informationen zur Erstellung Ihrer eigenen Abbilder [ https://docs.docker.com/engine/\Lernprogramme/Dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).

**Multiplattform-Image-Repositorys**

Windows-Containern häufiger verwendet, kann ein einzelnes Repository Plattform Varianten, z. B. ein Linux- und Windows-Image enthält. Dies ist ein neues Feature eingehen, die Anbieter auf ein einzelnes Repository verwenden, z. B. mehrere Plattformen abdecken kann Docker [Microsoft/Aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) Repository, die am DockerHub Registrierung verfügbar ist. Sobald die Funktion aktiv ist, wird dieses Bild für das Ausführen von Pull aus einem Windows-Host die Windows-Variante einziehen während der gleiche Name für das Ausführen von Pull aus einem Linux-Host die Linux-Variante pull.

***Option B: Erstellen des Basis-Image von Grund auf neu***

Sie können eigene Docker-Basis-Image von Grund auf neu erstellen, wie in diesem erläutert [Artikel](https://docs.docker.com/engine/userguide/eng-image/baseimages/) von Docker. Dies ist ein Szenario, das ist wahrscheinlich nicht für Sie am besten geeignet, wenn Sie gerade mit Docker gestartet werden, aber wenn Sie die bestimmte Bits des eigene Basisimage festlegen möchten, können Sie dies tun.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Schritt 3: Erstellen Sie Ihre benutzerdefinierten Docker-Images, die Ihr Dienst darin einbetten

Für jeden benutzerdefinierten Dienst, der Ihrer app ausmacht, müssen Sie eine verwandte Image zu erstellen. Wenn Ihre app von einem Einzelgerät oder Web-app vorgenommen wird, benötigen Sie nur ein einziges Bild.

> [!NOTE]
> Der Workflow"DevOps äußere Schleife" modellbasiert, die Bilder erstellt werden durch einen automatisierten Erstellungsprozess Wenn Quellcode in einem Git-Repository (Continuous Integration) übertragen, sodass die Bilder in der globalen Umgebung erstellt werden von Ihrem Quellcode.

Aber bevor wir diese Route für die äußere Schleife hörmal betrachten, müssen wir sicherstellen, dass die Docker-Anwendung, damit sie Code mithilfe von Push übertragen nicht, die unter Umständen nicht ordnungsgemäß auf dem Quellcodeverwaltungssystem (Git, usw.) funktionieren tatsächlich ordnungsgemäß funktioniert.

Daher muss jeder Entwickler zunächst müssen den gesamten Prozess der inneren Schleife um lokal testen und entwickeln, bis eine vollständige Funktion push oder ändern Sie in das Quellcodeverwaltungssystem werden soll.

Um ein Bild in Ihrer lokalen Umgebung und verwenden die dockerfile-Datei zu erstellen, können Sie den Befehl "Docker Build", wie in Abbildung 4-19 gezeigt (Sie können auch ausführen Docker verfassen – erstellen Sie für die Anwendungen aus, das mehrere Container/Dienste).

![](./media/image25.png)

Abbildung 4 – 19: Ausführen von Docker build

Optional, statt direkt Docker "erstellen" aus dem Ordner des Projekts, Sie können einen bereitstellbaren Ordner zuerst generieren, mit der .NET-Bibliotheken, die erforderlich sind, veröffentlichen mithilfe der Laufzeit Dotnet Befehl, und führen Sie Docker Build.

In diesem Beispiel wird dies ein Docker Bild erstellt, mit dem Namen Cesardl/Netcore-Webapi-Microservice-Docker: erste (: zuerst wird ein Tag, wie eine bestimmte Version). Sie können diesen Schritt für jeden benutzerdefinierten Abbilds nutzen, die Sie für die zusammengesetzte Docker-Anwendung mit mehreren Containern erstellen müssen.

Sie können vorhandenen Images in Ihr lokales Repository (Entwicklungscomputer) Suchbefehl mit Docker Images, wie in Abbildung 4-20 veranschaulicht.

![](./media/image26.png)

Abbildung 4-20: Anzeigen von vorhandenen Images mit Docker-images

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Schritt 4: (Optional) definieren Ihre Dienste in Docker-compose.yml beim Erstellen einer zusammengesetzten Docker-app mit mehreren Diensten

Mit der Docker-compose.yml-Datei können Sie einen Satz verwandter Dienste als einer zusammengesetzten Anwendung bereitgestellt werden, mit den Bereitstellungsbefehlen im nächsten Schritt Abschnitt erläuterten definieren.

Sie müssen diese Datei im Hauptfenster oder Stammordner für die Projektmappe zu erstellen. Sie müssen einen vergleichbaren Artikel in der folgenden Docker-compose.yml-Datei:

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

In diesem speziellen Fall diese Datei definiert zwei Dienste: der Webdienst (Ihr benutzerdefinierter Dienst) und den Redis-Dienst (eine beliebte Cachedienst). Jeder Dienst wird als Container bereitgestellt werden, daher muss eine konkrete Docker Bild für jede zu verwenden. Für diesen bestimmten Webdienst müssen das Abbild wie folgt vorgehen:

-   Aus der dockerfile-Datei im aktuellen Verzeichnis erstellen

-   Weiterleiten Sie die verfügbar gemachten Port 80 für den Container an Port 81 auf dem Hostcomputer

-   Laden Sie das Projektverzeichnis auf dem Host /code innerhalb des Containers, wodurch Sie zum Ändern des Codes, ohne das Bild neu erstellen

-   Verknüpfen Sie den Webdienst für den Redis-Dienst

Der Redis-Dienst verwendet die [neueste öffentliche Redis-Image](https://hub.docker.com/_/redis/) von Docker Hub-Registrierung abgerufen. [redis](http://redis.io/) ist eine sehr beliebte Cache-System für die serverseitigen Anwendungen.

### <a name="step-5-build-and-run-your-docker-app"></a>Schritt 5: Erstellen und Ausführen der Docker-app

Wenn Ihre app nur einen einzelnen Container verfügt, müssen Sie nur ausführen, indem sie in der Docker-Host (VM oder physischer Server) bereitstellen. Wenn Ihre app aus mehreren Diensten besteht, Sie müssen jedoch *Verfassen sie*ebenfalls. Sehen Sie die verschiedenen Optionen an.

***Option A: Führen Sie einen einzelnen Container oder Dienst***

Sie können das Docker-Image ausführen, mithilfe von "Docker run" Befehl, wie hier gezeigt:

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

Beachten Sie, dass für diese bestimmte Bereitstellung wir Anforderungen an Port 80 mit den internen Port 5000 gesendet umgeleitet werden. Nun wird die Anwendung den externen Port 80 auf der Hostebene überwacht.

***Option B: verfassen und Ausführen einer Anwendung mehrere container***

In den meisten Enterprise-Szenarios wird eine Docker-Anwendung mehrere Dienste erstellt werden. In diesen Fällen können Sie den Befehl ausführen Docker verfassen einrichten (Abbildung 4 – 21), verwenden die Docker-compose.yml-Datei, die Sie zuvor erstellt haben. Mit diesem Befehl wird eine zusammengesetzte Anwendung mit allen seine zugehörige Container bereitgestellt.

![](./media/image27.png)

Abbildung 4 – 21: Ergebnisse mit dem Befehl "Docker-verfassen einrichten"

Nach dem Ausführen des Docker-verfassen einrichten, die Bereitstellung der Anwendung und ihre zugehörigen Container in Ihrem Docker-Host, wie in Abbildung 4-22, in der VM-Darstellung dargestellt.

![](./media/image28.png)

Abbildung 4 – 22: VM mit Docker-Containern bereitgestellt

Hinweis Docker verfassen einrichten und "Docker run" möglicherweise hoch genug für die Container in der Entwicklungsumgebung testen, aber Sie möglicherweise verwenden sie überhaupt nicht, wenn Sie zur Arbeit mit Clustern Docker erwarten und Orchestrators wie Docker Containerhostclustern, Mesosphere DC/OS oder Kubernetes Damit skaliert werden. Bei Verwendung ein Clusters wie [Docker Containerhostclustern Modus](https://docs.docker.com/engine/swarm/) (verfügbar in Docker für Windows und Mac seit Version 1.12), müssen Sie zum Bereitstellen und Testen mit zusätzlichen Befehlen, z. B. Docker-Dienst für einzelne Dienste erstellen, oder Sie sind Bereitstellen einer app besteht aus mehreren Containern mit Docker Bundle verfassen und Docker bereitstellen MyBundleFile, durch die zusammengesetzte app als Stapel, bereitstellen, wie im Artikel erläutert [verteilte Anwendung Bündel](https://blog.docker.com/2016/06/docker-app-bundle/) von Docker.

Für [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) und [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) verwenden Sie unterschiedliche Bereitstellungsbefehlen und-Skripts sind auch.

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Schritt 6: Testen der Docker-Anwendung (lokal, in Ihrer lokalen CD-VM)

Dieser Schritt hängen davon ab, welche Vorgänge die app ausführt.

In eine sehr einfache .NET Core Web-API "Hello World" als eine einzelne Container oder einen Dienst bereitgestellt haben müssten Sie einfach auf den Dienst zuzugreifen, durch die Bereitstellung des TCP-Ports in der dockerfile-Datei angegeben.

Wenn Sie "localhost" nicht aktiviert ist, navigieren Sie zu dem Dienst finden Sie die IP-Adresse für den Computer mit diesem Befehl ein:

Docker-Computer-IP- *your Containername*

Öffnen Sie einen Browser, und navigieren Sie zu diesem Standort, auf dem Docker-Host; Ihre app/-Dienst ausgeführt wird, sollte angezeigt werden, wie in Abbildung 4 – 23 veranschaulicht.

![](./media/image29.png)

Abbildung 4 – 23: Testen der Docker-Anwendung, die lokal mithilfe von "localhost"

Beachten Sie, dass Port 80 verwendet wird, jedoch intern an Port 5000, umgeleitet wird wurde, da, wie mit "Docker run", bereitgestellt wurde wie zuvor beschrieben ist.

Sie können dies mithilfe von CURL aus der Terminaldienste testen. Bei einer Installation Docker unter Windows ist die Standard-IP-10.0.75.1, wie in Abbildung 4 – 24 dargestellt.

![](./media/image30.png)

Abbildung 4 – 24: Testen einer Docker-Anwendung lokal mithilfe von CURL

**Debuggen eines Containers, ausgeführt auf Docker**

Visual Studio-Code unterstützt Debuggen Docker, wenn Sie Node.js und anderen Plattformen wie .NET Core-Container verwenden.

Sie können auch .NET Core-Container in Docker Debuggen bei Verwendung von Visual Studio, wie im nächsten Abschnitt beschrieben.

**Weitere Informationen:** wechseln Sie zu, um weitere Informationen zum Debuggen von Node.js-Docker-Containern <https://blog.docker.com/2016/07/live-debugging-docker/> und [ https://blogs.msdn.microsoft.com/\ Benutzer\_Ed/2016/02/27 / Visual-Studio-Code-New-Features-13-Big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-Mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).


>[!div class="step-by-step"]
[Vorherigen] (Docker-apps-Development-environment.md) [weiter] (Visual-Studio-Tools-für-docker.md)
