---
title: Erlernen der Docker-Grundlagen mit .NET Core
description: Ein Tutorial für die Grundlagen von Docker und .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: dotnet-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.custom: mvc
manager: wpickett
ms.workload:
- dotnetcore
ms.openlocfilehash: 085ddb58aae78737fae642e7334e7f0139f0cfec
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="learn-docker-basics-with-net-core"></a>Erlernen der Docker-Grundlagen mit .NET Core

In diesem Tutorial werden die Aufgaben für das Erstellen und Bereitstellen von Docker-Containern für eine .NET Core-Anwendung erläutert. Im Verlauf dieses Tutorials lernen Sie Folgendes:

> [!div class="checklist"]
> * das Erstellen einer Dockerfile-Datei
> * das Erstellen einer .NET Core-App
> * das Bereitstellen Ihrer App in einem Docker-Container

Die [Docker-Plattform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) verwendet die [Docker-Engine](https://docs.docker.com/engine/docker-overview/#docker-engine), um Pakete schnell als [Docker-Images](https://docs.docker.com/glossary/?term=image) zu erstellen und zu packen. Diese Images werden im [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile)-Format geschrieben, um in einem [mehrstufigen Container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers) bereitgestellt und ausgeführt zu werden.

## <a name="net-core-easiest-way-to-get-started"></a>Einfacher Einstieg in .NET Core

Bevor Sie ein Docker-Image erstellen, benötigen Sie eine Anwendung, die containerisiert werden kann. Diese können Sie unter Linux, macOS oder Windows erstellen. Die schnellste und einfachste Methode hierfür ist die Verwendung von .NET Core.

Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../tools/index.md).

Sie können Windows- und Linux-Container mit [Tags, die auf mehreren Architekturen basieren](https://github.com/dotnet/announcements/issues/14), erstellen.

## <a name="your-first-net-core-docker-app"></a>Ihre erste Docker-App mit .NET Core

### <a name="prerequisites"></a>Erforderliche Komponenten

Zum Abschließen dieses Tutorials benötigen Sie Folgendes:

#### <a name="net-core-20-sdk"></a>.NET Core 2.0 SDK

* Installieren Sie das [.NET Core SDK 2.0](https://www.microsoft.com/net/core).

Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

* Installieren Sie Ihren bevorzugten Code-Editor, wenn Sie dies nicht bereits erledigt haben.

> [!TIP]
> Benötigen Sie einen Code-Editor? Testen Sie [Visual Studio](https://visualstudio.com/downloads).

#### <a name="installing-docker-client"></a>Installieren des Docker-Clients

Installieren Sie den Docker-Client [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) oder höher.

Der Docker-Client kann unter folgenden Betriebssystemen installiert werden:

* Linux-Verteilungen

   * [CentOS](https://www.docker.com/docker-centos-distribution)

   * [Debian](https://www.docker.com/docker-debian)

   * [Fedora](https://www.docker.com/docker-fedora)

   * [Ubuntu](https://www.docker.com/docker-ubuntu)

* [macOS](https://docs.docker.com/docker-for-mac/)

* [Windows](https://docs.docker.com/docker-for-windows/)

### <a name="create-a-net-core-20-console-app-for-dockerization"></a>Erstellen einer .NET Core 2.0-Konsolen-App für das Bereitstellen in Docker

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
   * Das Tag `TargetFramework` gibt an, welche .NET-Implementierung verwendet werden soll. In einem komplexen Szenario können Sie mehrere Zielframeworks angeben und die Erstellung für die angegebenen Frameworks in einem einzigen Vorgang vornehmen. In diesem Tutorial werden Projekte für .NET Core 2.0 erstellt.

   `Program.cs`:

   Das Programm wird durch `using System` gestartet. Diese Anweisung bedeutet: „Alle Elemente im `System`-Namespace müssen in den Bereich dieser Datei gebracht werden.“ Der Namespace `System` enthält grundlegende Konstrukte, wie z.B. `string`, oder numerische Typen.

   Wir definieren dann einen Namespace namens `Hello`. Sie können den Namespace beliebig ändern. Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen als Argument verwendet. Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das kompilierte Programm aufgerufen wird. In diesem Beispiel gibt das Programm lediglich „Hallo Welt!“ auf der Konsole aus.

2. `$ dotnet restore`

   In .NET Core 2.x wird der [`dotnet restore`](../tools/dotnet-restore.md)-Befehl durch **dotnet new** ausgeführt. Durch **dotnet restore** wird die Struktur der Abhängigkeiten durch einen Aufruf von [NuGet](https://www.nuget.org/) (.NET-Paket-Manager) wiederhergestellt.
   NuGet führt folgende Ausgaben aus:
   * Analyse der *Hello.csproj*-Datei 
   * Download der Abhängigkeiten der Datei (oder Abrufen aus dem Cache des Computers)
   * Schreiben der *obj/project.assets.json*-Datei

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   Die Datei *project.assets.json* stellt einen vollständigen Satz von App-Metadaten (z.B. Diagramme, Bindungsauflösungen usw.) für NuGet-Abhängigkeiten dar. Diese Datei wird von anderen Tools wie [`dotnet build`](../tools/dotnet-build.md) und [`dotnet run`](../tools/dotnet-run.md) verwendet, um den Quellcode ordnungsgemäß zu verarbeiten.
   
3. `$ dotnet run`

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
FROM microsoft/dotnet:2.0-sdk
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

Die erste Anweisung muss [**FROM**](https://docs.docker.com/engine/reference/builder/#from) sein. Diese Anweisung initialisiert eine neue Stufe des Builds und legt das Basisimage für die übrigen Anweisungen fest. Die Tags für mehrere Architekturen pullen abhängig vom [Containermodus](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) von Docker für Windows entweder Windows- oder Linux-Container. Das Basisimage für dieses Beispiel ist „2.0-sdk image“ aus dem Repository „microsoft/dotnet“.

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
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

### <a name="build-and-run-the-hello-net-core-20-app"></a>Erstellen und Ausführen der Hello .NET Core 2.0-App

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
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
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
Successfully built 53c337887e18
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
* [Visual Studio, Docker & Azure Container Instances better together! (Wie sich Visual Studio, Docker und Azure Container Instances ergänzen)](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [Docker for Azure Quickstarts (Docker für Azure-Schnellstarts)](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Deploy your app on Docker for Azure (Bereitstellen Ihrer App in Docker für Azure)](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> Wenn Sie kein Azure-Abonnement besitzen, [registrieren Sie sich noch heute für ein kostenloses 30-Tage-Konto](https://azure.microsoft.com/free/?b=16.48), und erhalten Sie ein Azure-Guthaben in Höhe von 200 US-Dollar, um eine beliebige Kombination von Azure-Diensten zu testen.

## <a name="docker-images-used-in-this-sample"></a>In diesem Beispiel verwendete Docker-Images

Folgende Docker-Images werden in diesem Beispiel verwendet:

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>Verwandte Ressourcen

* [.NET Core Docker samples (Docker-Beispiele für .NET Core)](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [Dockerfile-Datei in Windows-Containern](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [.NET Framework Docker samples (Docker-Beispiele für .NET Framework)](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [ASP.NET Core auf DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/)
* [Dockerize a .NET Core application - Docker Tutorial (Docker-Tutorial: Bereitstellen einer .NET Core-Anwendung in Docker)](https://docs.docker.com/engine/examples/dotnetcore/)
* [Arbeiten mit Visual Studio-Tools für Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances (Bereitstellen von Docker-Images aus Azure Container Registry für Azure Container Instances)](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)