---
title: Bereitstellen einer App im Container mit Docker
description: Dieses Tutorial zeigt das Erstellen einer einfachen .NET Core-Anwendung und ihr Bereitstellen im Container mit Docker.
ms.date: 10/11/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: addaabb41e57e03a5cf4ec5b2fa3b8b4f3089b32
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372918"
---
# <a name="how-to-containerize-a-net-core-application"></a>Bereitstellen einer .NET Core-Anwendung im Container

In diesem Tutorial werden die Aufgaben für das Erstellen und Bereitstellen von Docker-Containern für eine .NET Core-Anwendung erläutert. Die [Docker-Plattform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) verwendet die [Docker-Engine](https://docs.docker.com/engine/docker-overview/#docker-engine), um Pakete schnell als [Docker-Images](https://docs.docker.com/glossary/?term=image) zu erstellen und zu packen. Diese Images werden im [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile)-Format geschrieben, um in einem [mehrstufigen Container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers) bereitgestellt und ausgeführt zu werden.

Im Verlauf dieses Tutorials lernen Sie Folgendes:

> [!div class="checklist"]
> * das Erstellen einer Dockerfile-Datei
> * das Erstellen einer .NET Core-App
> * das Bereitstellen Ihrer App in einem Docker-Container

## <a name="net-core-easiest-way-to-get-started"></a>.NET Core: Einfacher Einstieg

Bevor Sie ein Docker-Image erstellen, benötigen Sie eine Anwendung, die containerisiert werden kann. Diese können Sie unter Linux, macOS oder Windows erstellen. Die schnellste und einfachste Methode hierfür ist die Verwendung von .NET Core.

Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../tools/index.md).

Sie können Windows- und Linux-Container mit [Tags, die auf mehreren Architekturen basieren](https://github.com/dotnet/announcements/issues/14), erstellen.

## <a name="your-first-net-core-docker-app"></a>Ihre erste Docker-App mit .NET Core

### <a name="prerequisites"></a>Erforderliche Komponenten

Zum Abschließen dieses Tutorials benötigen Sie Folgendes:

#### <a name="net-core-sdk"></a>.NET Core SDK

* Installieren Sie [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) oder höher.

Unter [.NET Core 2.1.x Supported OS Versions (Von .NET Core 2.1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.1 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

* Installieren Sie Ihren bevorzugten Code-Editor, wenn Sie dies nicht bereits erledigt haben.

> [!TIP]
> Benötigen Sie einen Code-Editor? Probieren Sie [Visual Studio Code](https://code.visualstudio.com/download) aus!

#### <a name="installing-docker-client"></a>Installieren des Docker-Clients

Installieren Sie den Docker-Client [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) oder höher.

Der Docker-Client kann unter folgenden Betriebssystemen installiert werden:

* Linux-Verteilungen

   * [CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [Debian](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [Fedora](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [macOS](https://docs.docker.com/docker-for-mac/install/)

* [Windows](https://docs.docker.com/docker-for-windows/install/)

### <a name="create-a-net-core-21-console-app-for-dockerization"></a>Erstellen einer .NET Core 2.1-Konsolen-App für das Bereitstellen in Docker

Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *Hello*. Navigieren Sie zum erstellten Ordner, und geben Sie folgende Befehle ein:

```console
dotnet new console
dotnet run
```

Hier eine kurze Beschreibung der Schritte:

1. `$ dotnet new console`

   Mit [`dotnet new`](../tools/dotnet-new.md) wird eine aktuelle Projektdatei `Hello.csproj` mit den Abhängigkeiten erstellt, die zum Erstellen einer Konsolen-App benötigt werden.  Zudem wird `Program.cs` erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.

   `Hello.csproj`:

   Die Projektdatei gibt alle Elemente an, die zum Wiederherstellen von Abhängigkeiten und erstellen des Programms erforderlich sind.

   * Das Tag `OutputType` gibt an, dass wir eine ausführbare Datei, also eine Konsolenanwendung, erstellen.
   * Das Tag `TargetFramework` gibt an, welche .NET-Implementierung verwendet werden soll. In einem komplexen Szenario können Sie mehrere Zielframeworks angeben und die Erstellung für die angegebenen Frameworks in einem einzigen Vorgang vornehmen. In diesem Tutorial werden Projekte für .NET Core 2.1 erstellt.

   `Program.cs`:

   Das Programm wird durch `using System` gestartet. Diese Anweisung bedeutet: „Alle Elemente im `System`-Namespace müssen in den Bereich dieser Datei gebracht werden.“ Der Namespace `System` enthält grundlegende Konstrukte, wie z.B. `string`, oder numerische Typen.

   Wir definieren dann einen Namespace namens `Hello`. Sie können den Namespace beliebig ändern. Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen als Argument verwendet. Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das kompilierte Programm aufgerufen wird. In diesem Beispiel gibt das Programm lediglich „Hallo Welt!“ auf der Konsole aus.

   **dotnet new** führt den [`dotnet restore`](../tools/dotnet-restore.md)-Befehl aus. Durch **dotnet restore** wird die Struktur der Abhängigkeiten durch einen Aufruf von [NuGet](https://www.nuget.org/) (.NET-Paket-Manager) wiederhergestellt.
   NuGet führt folgende Ausgaben aus:
   * Analyse der *Hello.csproj*-Datei.
   * Download der Abhängigkeiten der Datei (oder Abrufen aus dem Cache des Computers).
   * Schreiben der *obj/project.assets.json*-Datei.

   Die Datei *project.assets.json* stellt einen vollständigen Satz von App-Metadaten (z.B. Diagramme, Bindungsauflösungen usw.) für NuGet-Abhängigkeiten dar. Diese Datei wird von anderen Tools wie [`dotnet build`](../tools/dotnet-build.md) und [`dotnet run`](../tools/dotnet-run.md) verwendet, um den Quellcode ordnungsgemäß zu verarbeiten.

2. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) ruft [`dotnet build`](../tools/dotnet-build.md) auf, um einen erfolgreichen Build zu bestätigen. Anschließend wird `dotnet <assembly.dll>` aufgerufen, um die Anwendung zu starten.

    ```console
    $ dotnet run

    Hello World!
    ```

    Weitere Informationen zu erweiterten Szenarios finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).

## <a name="dockerize-the-net-core-application"></a>Bereitstellen der .NET Core-Anwendung in Docker

Die Konsolen-App „Hello .NET Core“ wird erfolgreich lokal ausgeführt. Im nächsten Schritt wird die App in Docker erstellt und ausgeführt.

### <a name="your-first-dockerfile"></a>Ihre erste Dockerfile-Datei

Öffnen Sie Ihren Text-Editor, um zu beginnen. Sie arbeiten weiterhin mit dem Hello-Verzeichnis, in dem die App erstellt wurde.

Fügen Sie folgende Docker-Anweisungen für Linux- oder [Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/) zu einer neuen Datei hinzu. Wenn dieser Vorgang abgeschlossen ist, speichern Sie die Datei ohne Erweiterung im Stammverzeichnis Ihres Hello-Verzeichnisses als **Dockerfile**. Sie müssen den Dateityp möglicherweise auf `All types (*.*)` (oder etwas ähnliches) festlegen.

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Die Dockerfile-Datei enthält die Buildanweisungen für Docker, die nacheinander ausgeführt werden.

Die erste Anweisung muss [**FROM**](https://docs.docker.com/engine/reference/builder/#from) sein. Diese Anweisung initialisiert eine neue Stufe des Builds und legt das Basisimage für die übrigen Anweisungen fest. Die Tags für mehrere Architekturen pullen abhängig vom [Containermodus](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) von Docker für Windows entweder Windows- oder Linux-Container. Das Basisimage für dieses Beispiel ist das 2.1-sdk-Image aus dem Repository „microsoft/dotnet“.

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

Die [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir)-Anweisung legt das Arbeitsverzeichnis für die übrigen Dockerfile-Anweisungen RUN, CMD, ENTRYPOINT, COPY und ADD fest. Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt. In diesem Fall ist WORKDIR auf das App-Verzeichnis festgelegt.

```Dockerfile
WORKDIR /app
```

Die [**COPY**](https://docs.docker.com/engine/reference/builder/#copy)-Anweisung kopiert neue Dateien oder Verzeichnisse aus dem Quellpfad und fügt diese dem Zieldateisystem des Containers hinzu. Mit dieser Anweisung wird die C#-Projektdatei in den Container kopiert.

```Dockerfile
COPY *.csproj ./
```

Die [**RUN**](https://docs.docker.com/engine/reference/builder/#run)-Anweisung führt jeden Befehl in einer neuen Ebene über dem aktuellen Image aus und committet die Ergebnisse. Das resultierende committete Image wird im nächsten Schritt in der Dockerdatei verwendet. Führen Sie **dotnet restore** aus, um die erforderlichen Abhängigkeiten der C#-Projektdatei abzurufen.

```Dockerfile
RUN dotnet restore
```

Diese **COPY**-Anweisung kopiert die restlichen Dateien in neue [Ebenen](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) des Containers.

```Dockerfile
COPY . ./
```

Veröffentlichen Sie die App mit der **RUN**-Anweisung. Der Befehl [**dotnet publish**](../tools/dotnet-publish.md) kompiliert die Anwendung, liest die Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis. Die App wird mit einer **Releasekonfiguration** und einer Ausgabe in das Standardverzeichnis veröffentlicht.

```Dockerfile
RUN dotnet publish -c Release -o out
```

Die [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint)-Anweisung ermöglicht die Ausführung des Containers als ausführbare Datei.

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Sie verfügen nun über eine Dockerfile-Datei, die:

* Ihre App in das Image kopiert
* die Abhängigkeiten Ihrer App in das Image kopiert
* die App für die Ausführung als ausführbare Datei erstellt

### <a name="build-and-run-the-hello-net-core-app"></a>Erstellen und Ausführen der Hello-.NET Core-App

#### <a name="essential-docker-commands"></a>Grundlegende Docker-Befehle

Diese Docker-Befehle sind grundlegend:

* [docker build](https://docs.docker.com/engine/reference/commandline/build/)
* [docker run](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [docker image](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>Erstellen und Ausführen

Nachdem Sie die Dockerfile-Datei geschrieben haben, erstellt Docker Ihre App und führt anschließend den Container aus.

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

Die Ausgabe des `docker build`-Befehls sollte folgender Konsolenausgabe ähneln:

```console
Sending build context to Docker daemon   173.1kB
Step 1/7 : FROM microsoft/dotnet:2.1-sdk
 ---> 288f8c45f7c2
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 46db075bd98d
Successfully tagged dotnetapp-dev:latest
```

Wie Sie an der Ausgabe erkennen können, verwendet die Docker-Engine die Dockerfile-Datei, um Ihren Container zu erstellen.

Die Ausgabe des `docker run`-Befehls sollte folgender Konsolenausgabe ähneln:

```console
Hello World!
```

Herzlichen Glückwunsch! Sie haben gerade:
> [!div class="checklist"]
> * eine lokale .NET Core-App erstellt
> * eine Dockerfile-Datei erstellt, um Ihren ersten Container zu erstellen
> * die in Docker bereitgestellte App erstellt und ausgeführt

## <a name="next-steps"></a>Nächste Schritte

Im Folgenden finden Sie weiterführende Schritte:

* [Introduction to .NET Docker Images Video(Video: Einführung in .NET-Docker-Images)](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Visual Studio, Docker & Azure Container Instances better together! (Wie sich Visual Studio, Docker und Azure Container Instances ergänzen)](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae)
* [Docker for Azure Quickstarts (Docker für Azure-Schnellstarts)](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Deploy your app on Docker for Azure (Bereitstellen Ihrer App in Docker für Azure)](https://docs.docker.com/docker-for-azure/deploy/)

> [!NOTE]
> Wenn Sie kein Azure-Abonnement besitzen, [registrieren Sie sich noch heute für ein kostenloses 30-Tage-Konto](https://azure.microsoft.com/free/?b=16.48), und erhalten Sie ein Azure-Guthaben in Höhe von 200 US-Dollar, um eine beliebige Kombination von Azure-Diensten zu testen.

## <a name="docker-images-used-in-this-sample"></a>In diesem Beispiel verwendete Docker-Images

Folgende Docker-Images werden in diesem Beispiel verwendet:

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>Weitere Informationen

* [.NET Core Docker samples (Docker-Beispiele für .NET Core)](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* [Dockerfile-Datei in Windows-Containern](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [.NET Framework Docker samples (Docker-Beispiele für .NET Framework)](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [ASP.NET Core auf DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/)
* [Dockerize a .NET Core application - Docker Tutorial (Docker-Tutorial: Bereitstellen einer .NET Core-Anwendung in Docker)](https://docs.docker.com/engine/examples/dotnetcore/)
* [Arbeiten mit Visual Studio-Tools für Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances (Bereitstellen von Docker-Images aus Azure Container Registry für Azure Container Instances)](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)