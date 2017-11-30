---
title: Erlernen von Grundlagen der Docker mit .NET Core
description: Ein Docker und .NET Core-Lernprogramm
keywords: .NET, .NET Core, Docker, Lernprogramm
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 5935f67d7e4ca9c9e8768373e2bcaa9febccfdc5
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
---
# <a name="learn-docker-basics-with-net-core"></a>Erlernen von Grundlagen der Docker mit .NET Core

Dieses Lernprogramm vermittelt die Docker Container erstellen und Bereitstellen von Aufgaben für eine Anwendung .NET Core. Im Verlauf dieses Lernprogramms erfahren Sie:

> [!div class="checklist"]
> * Vorgehensweise: Erstellen Sie eine dockerfile-Datei
> * Vorgehensweise: erstellen eine .NET Core-app.
> * Zum Bereitstellen Ihrer app in einem Docker-Container.

Die [die Plattform Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) verwendet die [Docker-Modul](https://docs.docker.com/engine/docker-overview/#docker-engine) schnell erstellen und die Paket-apps als [Docker Images](https://docs.docker.com/glossary/?term=image). Diese Abbilder werden geschrieben, der [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) Format bereitgestellt werden, und führen Sie in einer [Container in den Ebenen](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

## <a name="net-core-easiest-way-to-get-started"></a>.NET Core: Die einfachste Möglichkeit für den Einstieg

Vor der Erstellung der Docker-Abbilds, benötigen Sie eine Anwendung containerize. Sie können es unter Linux, Mac OS oder Windows erstellen. Die schnellste und einfachste Möglichkeit hierzu ist die Verwendung von .NET Core.

Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../tools/index.md).

Sie können die Windows- und Linux-Containern mit erstellen [mit mehreren Arch basierend Tags](https://github.com/dotnet/announcements/issues/14).

## <a name="your-first-net-core-docker-app"></a>Die erste .NET Core Docker-app

### <a name="prerequisites"></a>Erforderliche Komponenten

Um dieses Lernprogramm abzuschließen:

#### <a name="net-core-20-sdk"></a>.NET core SDK 2.0

* Installieren Sie [.NET Core SDK 2.0](https://www.microsoft.com/net/core).

Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

* Installieren Sie Ihre bevorzugten Code-Editor, sofern Sie noch nicht geschehen.

> [!TIP]
> Zum Installieren von eines Code-Editors erforderlich? Wiederholen Sie den [Visual Studio](https://visualstudio.com/downloads)!

#### <a name="installing-docker-client"></a>Installieren von Docker-Client

Installieren Sie [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) oder höher des Docker-Clients.

In kann der Docker-Client installiert werden:

* Linux-Distributionen

   * [CentOS](https://www.docker.com/docker-centos-distribution)

   * [Debian](https://www.docker.com/docker-debian)

   * [Fedora](https://www.docker.com/docker-fedora)

   * [Ubuntu](https://www.docker.com/docker-ubuntu)

* [macOS](https://docs.docker.com/docker-for-mac/)

* [Windows](https://docs.docker.com/docker-for-windows/).

### <a name="create-a-net-core-20-console-app-for-dockerization"></a>Erstellen einer Konsolen-app von .NET Core 2.0 für Dockerization

Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *Hello*. Navigieren Sie zu dem Ordner, den Sie erstellt haben, und geben Sie die folgenden Befehle:

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
   * Das Tag `TargetFramework` gibt an, welche .NET-Implementierung verwendet werden soll. In einem erweiterten Szenario können Sie mehrere Zielframeworks angeben und auf den angegebenen Frameworks in einem einzigen Vorgang erstellen. In diesem Lernprogramm erstellen wir für .NET Core 2.0.

   `Program.cs`:

   Das Programm gestartet wird, indem Sie `using System`. Diese Aussage beinhaltet, "schalten Sie alle Elemente in der `System` Namespace in den Bereich für diese Datei." Der Namespace `System` enthält grundlegende Konstrukte, wie z.B. `string`, oder numerische Typen.

   Wir definieren dann einen Namespace namens `Hello`. Sie können auf einen gewünschten, Namespace ändern. Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen als Argument verwendet. Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das kompilierte Programm aufgerufen wird. In unserem Beispiel schreibt das Programm nur "Hello World!" auf der Konsole aus.

2. `$ dotnet restore`

   In .NET Core 2.x, **Dotnet neue** führt die [ `dotnet restore` ](../tools/dotnet-restore.md) Befehl. **Dotnet Wiederherstellung** stellt die Struktur von Abhängigkeiten mit einer [NuGet](https://www.nuget.org/)Aufruf (.NET Paket-Manager).
   NuGet führt die folgenden Aufgaben:
   * analysiert die *Hello.csproj* Datei 
   * Download der Datei Abhängigkeiten (oder holt aus Ihrem Computer-Cache)
   * Schreibt die *obj/project.assets.json* Datei

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   Die *project.assets.json* Datei ist, einen vollständigen Satz von NuGet Abhängigkeiten Diagramm, Bindung Lösungen und andere app-Metadaten. Diese Datei wird von anderen Tools verwendet, z. B. erforderlichen [ `dotnet build` ](../tools/dotnet-build.md) und [ `dotnet run` ](../tools/dotnet-run.md), um den Quellcode ordnungsgemäß zu verarbeiten.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md)Aufrufe [ `dotnet build` ](../tools/dotnet-build.md) zu einem erfolgreichen Build und ruft dann bestätigen `dotnet <assembly.dll>` um die Anwendung auszuführen.
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    Erweiterte Szenarien finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md) Details.

## <a name="dockerize-the-net-core-application"></a>Die .NET Core-Anwendung dockerize

Die Hello .NET Core-Konsolen-app wird erfolgreich lokal ausgeführt. Jetzt sehen wir führen, dass er einen Schritt weiter und erstellen und Ausführen der app in Docker.

### <a name="your-first-dockerfile"></a>Die erste dockerfile-Datei

Öffnen Sie einen Text-Editor, und los geht! Wir arbeiten weiterhin aus dem Hello-Verzeichnis, die wir die app in aufbauen.

Fügen Sie die folgenden Docker-Anweisungen für entweder Linux oder [Windows-Containern](https://docs.microsoft.com/virtualization/windowscontainers/about/) in eine neue Datei. Wenn Sie fertig sind, speichern Sie sie im Stammverzeichnis Ihres Verzeichnisses Hello als **Dockerfile**, ohne Erweiterung (müssen Sie möglicherweise auf dem Dateityp festgelegt `All types (*.*)` oder einer ähnlichen).

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

Die dockerfile-Datei enthält Docker Build-Anweisungen, die sequenziell ausgeführt.

Die erste Anweisung muss [ **FROM**](https://docs.docker.com/engine/reference/builder/#from). Diese Anweisung initialisiert eine neue Stufe für den Build und legt die Basis-Image für die übrigen Anweisungen. Die mit mehreren arch Tags pull Windows- oder Linux-Container abhängig von der Docker für Windows [containermodus](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers). Die Basis-Image für unser Beispiel ist die 2.0-Sdk-Image aus dem Microsoft/Dotnet-Repository,

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

Die [ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir) Anweisung legt das Arbeitsverzeichnis für alle verbleibenden ausführen, CMD ENTRYPOINT, kopieren und hinzufügen Dockerfile Anweisungen. Wenn das Verzeichnis nicht vorhanden ist, wird es erstellt. In diesem Fall wird das app-Verzeichnis WORKDIR fest.

```Dockerfile
WORKDIR /app
```

Die [ **Kopie** ](https://docs.docker.com/engine/reference/builder/#copy) -Anweisung neue Dateien oder Verzeichnisse aus dem Quellpfad kopiert und in das Dateisystem der Ziel-Container hinzugefügt. Mit dieser Anweisung werden wir die C#-Projektdatei für den Container kopiert.

```Dockerfile
COPY *.csproj ./
```

Die [ **ausführen** ](https://docs.docker.com/engine/reference/builder/#run) Anweisung führt alle Befehle in eine neue Schicht über das aktuelle Bild und übernehmen Sie die Ergebnisse. Das resultierende Image für die ein Commit ausgeführt wurde, wird für den nächsten Schritt in die dockerfile-Datei verwendet. Wir arbeiten **Dotnet-Wiederherstellung** zum Abrufen der erforderlichen Abhängigkeiten der C#-Projektdatei. 

```Dockerfile
RUN dotnet restore
```

Dies **Kopie** -Anweisung kopiert die restlichen Dateien in unsere Container in neue [Ebenen](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).

```Dockerfile
COPY . ./
```

Wir Veröffentlichen der app mit dieser **ausführen** Anweisung. Die [ **Dotnet veröffentlichen** ](../tools/dotnet-publish.md) Befehl wird die Anwendung kompiliert, über dessen Abhängigkeiten in der Projektdatei angegebenen liest und die resultierende Menge der Dateien in einem Verzeichnis veröffentlicht. Dieser app wird veröffentlicht, mit einem **Version** Konfiguration und die Ausgabe in das Standardverzeichnis.

```Dockerfile
RUN dotnet publish -c Release -o out
```

Die [ **ENTRYPOINT** ](https://docs.docker.com/engine/reference/builder/#entrypoint) Anweisung ermöglicht dem Container als ausführbare Datei ausgeführt.

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Nachdem Sie eine dockerfile-Datei verfügen, die:

* Ihre app kopiert auf das Bild
* Ihre app-Abhängigkeiten auf das Abbild
* erstellt die app als ausführbare Datei ausgeführt.

### <a name="build-and-run-the-hello-net-core-20-app"></a>Erstellen und Ausführen der app Hello .NET Core 2.0

#### <a name="essential-docker-commands"></a>Wichtige Docker-Befehle

Diese Befehle Docker sind wichtig:

* [Docker build](https://docs.docker.com/engine/reference/commandline/build/)
* ["Docker run"](https://docs.docker.com/engine/reference/commandline/run/)
* [Docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [Docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [Docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [Docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [Image von docker](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>Erstellen und ausführen

Sie wurde der dockerfile-Datei geschrieben; jetzt Docker Ihrer app erstellt und führt dann den Container.

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

Die Ausgabe der `docker build` Befehl sollte ähnlich der folgenden Konsolenausgabe sein:

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

Wie Sie aus der Ausgabe sehen können, verwendet das Docker-Modul die dockerfile-Datei um unsere Container zu erstellen.

Die Ausgabe der `docker run` Befehl sollte ähnlich der folgenden Konsolenausgabe sein:

```console
Hello World!
```

Herzlichen Glückwunsch! Sie haben soeben:
> [!div class="checklist"]
> * Erstellt eine lokale .NET Core-app
> * Erstellt eine dockerfile-Datei zum Erstellen Ihres ersten Containers
> * Erstellt und ausgeführt haben Ihre app Dockerized



## <a name="next-steps"></a>Nächste Schritte

Hier sind die nächsten Schritte, die Sie ergreifen können:

* [Einführung in .NET Docker Images Video](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Visual Studio, Docker & Azure-Container-Instanzen besser gemeinsam!](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [Docker für Azure-Quickstarts](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Bereitstellen der app auf Docker für Azure](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> Wenn Sie nicht über ein Azure-Abonnement verfügen [registrieren Sie sich noch heute](https://azure.microsoft.com/free/?b=16.48) für eine kostenlose 30-Tage-Konto verhindern und $200 Azure-Guthaben auf eine beliebige Kombination von Azure-Dienste zu testen.

## <a name="docker-images-used-in-this-sample"></a>In diesem Beispiel verwendete Docker-Images

In diesem Beispiel werden die folgenden Docker-Images verwendet.

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>Verwandte Ressourcen

* [.NET Core Docker-Beispiele](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [Dockerfile unter Windows-Containern](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Docker für .NET Framework-Beispiele](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [ASP.NET Core unter DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/)
* [Eine Anwendung für .NET Core - Docker-Lernprogramm dockerize](https://docs.docker.com/engine/examples/dotnetcore/)
* [Arbeiten mit Docker-Tools für Visual Studio](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Bereitstellen von Docker-Images aus der Registrierung des Azure-Container für Instanzen von Azure-Container](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)