---
title: "Visual Studio-Tools für Docker"
description: "Verwenden von Visual Studio-Tools für Docker"
keywords: .NET, .NET Core, Docker, ASP.NET Core, Visual Studio
author: spboyer
ms.author: shboyer
ms.date: 04/27/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 1f3b9a68-4dea-4b60-8cb3-f46164eedbbf
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 113d470a55fd92704de0e6def392a6e0a1a3a118
ms.contentlocale: de-de
ms.lasthandoff: 08/25/2017

---

# <a name="visual-studio-tools-for-docker"></a>Visual Studio-Tools für Docker

[Microsoft Visual Studio 2017](https://www.visualstudio.com/) mit [Docker für Windows](https://docs.docker.com/docker-for-windows/install/) unterstützt das Erstellen, Debuggen und Ausführen von .NET Framework und .NET Core-Web- und Konsolenanwendungen mithilfe von Windows- und Linux-Containern.

## <a name="prerequisites"></a>Erforderliche Komponenten

- [Microsoft Visual Studio 2017](https://www.visualstudio.com/) mit der .NET Core-Workload
- [Docker für Windows](https://docs.docker.com/docker-for-windows/install/)

## <a name="installation-and-setup"></a>Installation und Einrichtung

Installieren Sie [Microsoft Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio) mit der .NET Core-Arbeitsauslastung.

Informationen zur Docker-Installation entnehmen Sie dem Artikel [Docker for Windows: What to know before you install (Docker für Windows: Was Sie vor der Installation wissen müssen)](https://docs.docker.com/docker-for-windows/install/#what-to-know-before-you-install), und installieren Sie [Docker für Windows](https://docs.docker.com/docker-for-windows/install/).

Es ist erforderlich, dass Sie in Docker für Windows **[freigegebene Laufwerke](https://docs.docker.com/docker-for-windows/#shared-drives)** einrichten. Die Einstellung ist für die Volumezuordnung und die Debugunterstützung erforderlich.

Klicken Sie in der Taskleiste mit der rechten Maustaste auf das Docker-Symbol. Klicken Sie auf **Einstellungen**, und wählen Sie **Freigegebene Laufwerke**. Wählen Sie das Laufwerk aus, in dem Docker Ihre Dateien speichern soll, und übernehmen Sie die Änderungen.

![Freigegebene Laufwerke](./media/visual-studio-tools-for-docker/settings-shared-drives-win.png)

## <a name="create-an-aspnet-web-application-and-add-docker-support"></a>Erstellen einer ASP.NET-Webanwendung und Hinzufügen der Docker-Unterstützung

Erstellen Sie mithilfe von Visual Studio eine neue ASP.NET Core-Webanwendung. Wählen Sie beim Laden der Anwendung die Option **Add Docker Support** (Docker-Unterstützung hinzufügen) im Menü **Projekt**, oder klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Docker Support** (Docker-Unterstützung).

Menü „Projekt“

![Projekt > Add Docker Support (Docker-Unterstützung hinzufügen)](./media/visual-studio-tools-for-docker/project-add-docker-support.png)

Kontextmenü „Projekt“

![Rechtsklick auf „Add Docker Support“ (Docker-Unterstützung hinzufügen)](./media/visual-studio-tools-for-docker/right-click-add-docker-support.png)

Wenn Sie Docker-Unterstützung zu Ihrem Projekt hinzufügen, können Sie zwischen Windows- und Linux-Containern wählen. (Der Docker-Host muss den gleichen Containertyp ausführen. Wenn Sie den Containertyp in der ausgeführten Docker-Instanz ändern müssen, klicken Sie mit der rechten Maustaste auf das **Docker**-System in der Taskleiste, und wählen Sie **Zu Windows-Containern wechseln** oder **Zu Linux-Containern wechseln**.) 

Die folgenden Dateien werden zum Projekt hinzugefügt.

- **Dockerfile**: Die Docker-Datei für ASP.NET Core-Anwendungen basiert auf dem [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore)-Image. Dieses Image enthält die ASP.NET Core NuGet-Pakete, die zur Verbesserung der Leistung beim Starten vorab mit JIT kompiliert wurden. Beim Erstellen von .NET Core-Konsolenanwendungen verweist die Docker-Datei auf das aktuellste [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet)-Image.   
- **docker-compose.yml**: Docker Compose-Basisdatei zum Definieren der Sammlung von Images, die mit „docker-compose build/run“ erstellt und ausgeführt werden soll.   
- **docker-compose.dev.debug.yml**: zusätzliche „docker-compose“-Datei für iterative Änderungen, wenn die Konfiguration zum Debuggen festgelegt wurde. Visual Studio ruft „-f docker-compose.yml“ und „-f docker-compose.dev.debug.yml“ auf und führt beide zusammen. Diese compose-Datei wird von den Visual Studio-Entwicklungstools verwendet.   
- **docker-compose.dev.release.yml**: zusätzliche Docker Compose-Datei zum Debuggen der Releasedefinition. Sie dient der Volumebereitstellung für den Debugger, sodass der Inhalt des Produktionsimages nicht verändert wird.  

Die Datei „docker-compose.yml“ enthält den Namen des Images, das beim Ausführen des Projekts erstellt wird. 

```
version '2'

services:
  hellodockertools:
    image:  user/hellodockertools${TAG}
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "80"
``` 

In diesem Beispiel erstellt `image: user/hellodockertools${TAG}` das Image `user/hellodockertools:dev`, wenn die Anwendung im **Debugmodus** und `user/hellodockertools:latest` im **Releasemodus** ausgeführt wird. 

Sie sollten für `user` den Benutzernamen Ihres Docker-Hubs angeben, wenn Sie das Image in die Registrierung verschieben möchten. Beispiel: `spboyer/hellodockertools`. Oder geben Sie je nach Konfiguration Ihre private Registrierungs-URL `privateregistry.domain.com/` an.

### <a name="debugging"></a>Debuggen

Wählen Sie in der Symbolleiste im Dropdownmenü „Debuggen“ die Option **Docker** aus, und drücke Sie die Taste „F5“, um mit dem Debuggen der Anwendung zu beginnen. 

- Das „microsoft/aspnetcore“-Image wird geladen (falls es sich nicht bereits im Cache befindet).
- ASPNETCORE_ENVIRONMENT wird im Container auf „Development“ festgelegt.
- PORT 80 wird VERFÜGBAR GEMACHT und einem dynamisch zugewiesenen Port für localhost zugeordnet. Der Port wird vom Docker-Host bestimmt und kann mit „docker ps“ abgefragt werden. 
- Ihre Anwendung wird in den Container kopiert.
- Der Standardbrowser wird mit dem dynamisch zugewiesenen Port gestartet, wobei der Debugger an den Container angehängt wurde. 

Das resultierende Docker-Image ist das `dev`-Image Ihrer Anwendung mit den `microsoft/aspnetcore`-Images als Basisimage.
Hinweis: Das „dev“-Image enthält keine Anwendungsinhalte, da Debugkonfigurationen mittels Volumebereitstellung die iterative Erfahrung bereitstellen. Verwenden Sie zum Verschieben eines Images die Releasekonfiguration.

```console
REPOSITORY                  TAG         IMAGE ID            CREATED         SIZE
spboyer/hellodockertools    dev         0b6e2e44b3df        4 minutes ago   268.9 MB
microsoft/aspnetcore        1.0.1       189ad4312ce7        5 days ago      268.9 MB
```

Die Anwendung wird mit dem Container ausgeführt, der angezeigt wird, wenn der Befehl `docker ps` ausgeführt wird.

```console
CONTAINER ID        IMAGE                          COMMAND               CREATED             STATUS              PORTS                   NAMES
3f240cf686c9        spboyer/hellodockertools:dev   "tail -f /dev/null"   4 minutes ago       Up 4 minutes        0.0.0.0:32769->80/tcp   hellodockertools_hellodockertools_1
```

### <a name="edit-and-continue"></a>Bearbeiten und Fortfahren

Änderungen an statischen Dateien und/oder Razor-Vorlagendateien (.cshtml) werden ohne Kompilierungsschritt automatisch aktualisiert. Nehmen Sie die Änderung vor, speichern Sie die Datei, und aktualisieren Sie die Browseransicht, um die Aktualisierung anzuzeigen.  

Wenn Sie Änderungen an Codedateien vornehmen, müssen Sie die Dateien kompilieren und Kestrel im Container neu starten. Nachdem Sie die Änderung vorgenommen haben, drücken Sie die Tastenkombination STRG + F5, um den Prozess durchzuführen und die Anwendung im Container zu starten. Der Docker-Container wird nicht neu erstellt oder beendet. Wenn Sie `docker ps` in die Befehlszeile eingeben, können Sie sehen, dass der ursprüngliche Container seit 10 Minuten ausgeführt wird. 

```console
CONTAINER ID        IMAGE                          COMMAND               CREATED             STATUS              PORTS                   NAMES
3f240cf686c9        spboyer/hellodockertools:dev   "tail -f /dev/null"   10 minutes ago      Up 10 minutes       0.0.0.0:32769->80/tcp   hellodockertools_hellodockertools_1
```

### <a name="publishing-docker-images"></a>Veröffentlichen von Docker-Images

Nachdem Sie den Entwicklungs- und Debug-Zyklus für Ihre Anwendung abgeschlossen haben, können Sie mit den Visual Studio-Tools für Docker das Produktionsimage Ihrer Anwendung erstellen. Wählen Sie im Dropdownmenü „Debuggen“ die Option **Release**, und erstellen Sie die Anwendung. Das Tool erstellt das Image mit dem Tag `:latest`, das Sie mittels Push an Ihre private Registrierung oder den Docker-Hub übertragen können. 

Mit den `docker images` können Sie die Liste mit Images anzeigen.

```console
REPOSITORY                 TAG                 IMAGE ID            CREATED             SIZE
spboyer/hellodockertools   latest              8184ae38ba91        5 seconds ago       278.4 MB
spboyer/hellodockertools   dev                 0b6e2e44b3df        About an hour ago   268.9 MB
microsoft/aspnetcore       1.0.1               189ad4312ce7        5 days ago          268.9 MB
```

Man würde möglicherweise erwarten, dass das Produktions- oder Release-Image aufgrund der Volumezuordnung im Vergleich zum **Entwicklungsimage** kleiner ist. Debugger und Anwendung werden jedoch auf dem lokalen Computer und nicht im Container ausgeführt. Beim **neuesten** Image wurde der gesamte Anwendungscode, der zum Ausführen der Anwendung auf einem Hostcomputer benötigt wird, gepackt. Daher entspricht die Größe der Deltaversion der Größe des Anwendungscodes.

