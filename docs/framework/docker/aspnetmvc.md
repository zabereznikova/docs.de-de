---
title: Migrieren von ASP.NET MVC-Anwendungen zu Windows-Containern
description: "Erfahren Sie, wie Sie eine vorhandene ASP.NET MVC-Anwendung in einem Windows Docker-Container ausführen können."
keywords: Windows-Container, Docker, ASP.NET MVC
author: BillWagner
manager: wpickett
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net-framework-4.6
ms.technology: dotnet-mvc
ms.devlang: dotnet
ms.assetid: c9f1d52c-b4bd-4b5d-b7f9-8f9ceaf778c4
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: 3e8a8a953cbb3dde6ddf386f8c3b3a1fd4c549f1

---

# <a name="migrating-aspnet-mvc-applications-to-windows-containers"></a>Migrieren von ASP.NET MVC-Anwendungen zu Windows-Containern

Voraussetzung für das Ausführen einer vorhandenen .NET Framework-basierten Anwendung in einem Windows-Container ist das Erstellen des Docker-Images, das Ihre Anwendung enthält, und Starten eines oder mehrerer Container, um das Image auszuführen. In diesem Thema werden die Aufgaben erläutert, die Sie ausführen müssen, um eine vorhandene [ASP.NET MVC-Anwendung](http://www.asp.net/mvc) in einem Windows-Container bereitzustellen.

Sie beginnen mit einer vorhandenen ASP.NET MVC-Anwendung. Anschließend erstellen Sie die veröffentlichten Objekte mit Visual Studio. Sie verwenden Docker, um das Image zu erstellen, das die Anwendung enthält, und die Anwendung ausführt, wenn sie gestartet wird. Wenn Sie dies abgeschlossen haben, können Sie einen Browser mit der Website verbinden, die in einem Windows-Container ausgeführt wird, und überprüfen, ob die Anwendung ausgeführt wird.

Dieser Artikel setzt Grundkenntnisse in Docker voraus. Wenn dieser Bereich für Sie neu ist, lesen Sie die Informationen zur Docker-Architektur auf der Docker-Website unter [Docker Overview](https://docs.docker.com/engine/understanding-docker/) (Übersicht zu Docker).

Die Anwendung, die Sie in einem Container ausführen, ist eine einfache Website, die Fragen nach dem Zufallsprinzip beantwortet. Diese Anwendung ist eine grundlegende MVC-Anwendung ohne Authentifizierungsunterstützung oder Datenbankspeicher, sodass Sie sich auf das Verschieben der Webebene in einen Container konzentrieren können. In zukünftigen Themen wird das Verschieben und Verwalten von beständigem Speicher in Containeranwendungen gezeigt.

Das Verschieben Ihrer Anwendung umfasst folgenden Schritte:

1. [Erstellen einer Veröffentlichungsaufgabe, um die Objekte für ein Image zu erstellen](#publish-script)
2. [Erstellen eines Docker-Images, das die Anwendung ausführt](#build-the-image)
3. [Starten eines Docker-Containers, der das Image ausführt](#start-a-container)
4. [Überprüfen der Anwendung mit Ihrem Browser](#verify-in-the-browser)

Die fertige Anwendung befindet sich im [Repository „dotnet/core-docs“ auf GitHub](https://github.com/dotnet/docs/tree/master/samples/framework/docker/MVCRandomAnswerGenerator).

## <a name="prerequisites"></a>Erforderliche Komponenten

Zumindest auf Ihrem Entwicklungscomputer muss [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) oder [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server) ausgeführt werden. 

Bevor Sie beginnen, müssen Sie [Docker für Windows](https://docs.docker.com/docker-for-windows/), Version 1.12 Beta 26 oder höher installieren. Unterstützung für Windows-Container ist zu diesem Zeitpunkt nur im Beta-Kanal verfügbar.

> [!IMPORTANT]
> Wenn Sie Windows Server 2016 verwenden, müssen Sie die Anweisungen unter [Containerhostbereitstellung: Windows Server](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/deployment/deployment) befolgen, bevor Sie Docker-Container ausführen können.

Nachdem Sie Docker installiert und gestartet haben, müssen Sie mit der rechten Maustaste auf das Taskleistensymbol klicken und **Switch to Windows containers** (Zu Windows-Containern wechseln) wählen, um Docker-Images auf Windows-Basis auszuführen. Die Ausführung dieses Befehls dauert ein paar Sekunden:

![Windows-Container][windows-container]

## <a name="publish-script"></a>Veröffentlichen des Skripts

Der erste Schritt besteht darin, alle Objekte abzurufen, die Sie an einem Ort in ein Docker-Image laden müssen. Glücklicherweise können Sie den Visual Studio-Befehl **Veröffentlichen** verwenden, um ein Veröffentlichungsprofil für Ihre Anwendung zu erstellen. In diesem Profil sind alle Objekte in einer einzigen Verzeichnisstruktur untergebracht, die Sie im weiteren Verlauf dieses Tutorials in Ihr Zielimage kopieren.

**Veröffentlichungsschritte**

1. Klicken Sie mit der rechten Maustaste in Visual Studio auf das Webprojekt, und wählen Sie **Veröffentlichen**.
2. Klicken Sie auf die **Schaltfläche „Benutzerdefiniertes Profil“, und wählen Sie **„Dateisystem“ als Methode.
3. Wählen Sie das Verzeichnis aus. Konventionsgemäß verwendet das heruntergeladene Beispiel `bin/PublishOutput`.

![Veröffentlichungsverbindung][publish-connection]

Öffnen Sie als Nächstes den Abschnitt **Dateiveröffentlichungsoptionen** der Registerkarte **Einstellungen**. Wählen Sie **Während der Veröffentlichung vorkompilieren**. Diese Optimierung bedeutet, dass Sie beim Kompilieren von Ansichten im Docker-Container die vorkompilierten Sichten kopieren.

![Veröffentlichungseinstellungen][publish-settings]

Klicken Sie auf **Veröffentlichen**, und Visual Studio kopiert alle erforderlichen Objekte in den Zielordner. 

## <a name="build-the-image"></a>Erstellen des Images

Sie definieren Ihr Docker-Image in einer Dockerfile-Datei, die Anweisungen für das Basisimage, ggf. zusätzliche Komponenten, die Anwendung, die Sie ausführen möchten und andere Konfigurationsimages enthält.  Die Dockerfile-Datei ist die Eingabe für den `docker build`-Befehl, der das Image erstellt.

Sie erstellen ein Image auf der Grundlage des `microsft/aspnet`-Images, das sich auf dem [Docker-Hub](https://hub.docker.com/r/microsoft/aspnet/) befindet.
Das Basisimage `microsoft/aspnet` ist ein Windows Server-Image. Ergänzend zu Windows Server Core sind dort IIS und ASP.NET 4.6.2 installiert und aktiviert. Beim Ausführen dieses Images in einem Container wird IIS automatisch gestartet, und alle installierten Websites sind aktiv.

Die Dockerfile-Datei, die das Image erstellt, sieht folgendermaßen aus:

```
# The `FROM` instruction specifies the base image. You are
# extending the `microsoft/aspnet` image.

FROM microsoft/aspnet

# Next, this Dockerfile creates a directory for your application
RUN mkdir C:\randomanswers

# configure the new site in IIS.
RUN powershell -NoProfile -Command \
    Import-module IISAdministration; \
    New-IISSite -Name "ASPNET" -PhysicalPath C:\randomanswers -BindingInformation "*:8000:"

# This instruction tells the container to listen on port 8000. 
EXPOSE 8000

# The final instruction copies the site you published earlier into the container.
ADD containerImage/ /randomanswers
```

Es gibt keinen `ENTRYPOINT`-Befehl in dieser Dockerfile-Datei. Sie benötigen ihn nicht.
Das Basisimage stellt sicher, dass IIS startet, wenn der Container startet. 

Als Nächstes müssen Sie einen Docker-Buildbefehl zum Erstellen des Images ausführen, das Ihre ASP.NET-Anwendung ausführt. Öffnen Sie zu diesem Zweck ein PowerShell-Fenster, und geben Sie den folgenden Befehl im Projektmappenverzeichnis ein:

```
docker build -t mvcrandomanswers .
```

Mit diesem Befehl wird das neue Image mithilfe der Anweisungen in Ihrer Dockerfile-Datei erstellt. Dies kann beinhalten, dass das Basisimage aus dem [Docker-Hub](http://hub.docker.com) gezogen wird. Dann wird Ihre Anwendung diesem Image hinzugefügt.

Nach Abschluss dieses Befehls können Sie den `docker images`-Befehl ausführen, um Informationen über das neue Image anzuzeigen:

```
REPOSITORY                    TAG                 IMAGE ID            CREATED             SIZE
mvcrandomanswers              latest              86838648aab6        2 minutes ago       8.104 GB
```

Die IMAGE-ID wird auf Ihrem Computer anders lauten. Jetzt führen wir die Anwendung aus.

## <a name="start-a-container"></a>Starten eines Containers

Sie starten einen Container mit folgendem `docker run`-Befehl:

```
docker run -d -p 8000:8000 --name randomanswers mvcrandomanswers
```

Das `-d`-Argument weist Docker an, das Image im getrennten Modus zu starten. Das bedeutet, dass das Docker-Image getrennt von der aktuellen Shell ausgeführt wird.

Das `-p 8000:8000`-Argument teilt Docker mit, wie die eingehenden Ports zuzuordnen sind. In diesem Beispiel verwenden wir sowohl auf dem Host als auch dem Container Port 8000.

`--name randomanswers` gibt dem ausgeführten Container einen Namen. Sie können diesen Namen in den meisten Befehlen anstelle der Container-ID verwenden.

`mvcrandomanswers` ist der Name des zu startenden Images.

## <a name="verify-in-the-browser"></a>Überprüfen im Browser

> [!NOTE]
> Bei der aktuellen Version können Sie `http://localhost` nicht verwenden, um zu Ihrer Website zu wechseln. Dies liegt an einem bekannten Verhalten in WinNAT und wird in Zukunft gelöst werden. Bis zur Behebung dieses Fehlers müssen Sie die IP-Adresse des Containers verwenden.

Nach dem Start des Containers müssen Sie seine IP-Adresse ermitteln, damit Sie über einen Browser eine Verbindung mit dem ausgeführten Container herstellen können:

```
docker inspect -f "{{ .NetworkSettings.Networks.nat.IPAddress }}" randomanswers
172.31.194.61
```

Sie können mit der IPv4-Adresse und dem konfigurierten Port (8000) eine Verbindung mit dem ausgeführten Container herstellen, im gezeigten Beispiel `http://172.31.194.61:8000`. Wenn Sie diese URL in Ihren Browser eingeben, sollte die ausgeführte Website angezeigt werden.

> [!NOTE]
> Manche VPN- oder Proxysoftware könnte Ihren Wechsel zu Ihrer Website verhindern.
> Sie können diese Software vorübergehend deaktivieren, um sicherzustellen, dass der Container ausgeführt wird.

Das Beispielverzeichnis auf GitHub enthält ein [PowerShell-Skript](https://github.com/dotnet/docs/tree/master/samples/framework/docker/MVCRandomAnswerGenerator/run.ps1), das diese Befehle für Sie ausführt. Öffnen Sie ein PowerShell-Fenster, wechseln Sie in das Projektmappenverzeichnis, und geben Sie ein:

```
./run.ps1
```

Dieser Befehl erstellt das Image, zeigt die Liste der Images auf dem Computer an, startet einen Container und zeigt die IP-Adresse für diesen Container an. 

Wenn Sie dies abgeschlossen haben und den Container stoppen möchten, geben Sie einen `docker
stop`-Befehl ein:

```
docker stop randomanswers
```

Um den Container zu entfernen, geben Sie einen `docker rm`-Befehl ein:

```
docker rm randomanswers
```

## <a name="summary"></a>Zusammenfassung

In diesem Thema haben Sie die Schritte zum Verschieben einer vorhandenen ASP.NET MVC-Anwendung in einen Windows Server-Container und zum dortigen Ausführen kennen gelernt. Das Ausführen einer vorhandenen Anwendung erfordert keine Änderungen Ihrer Anwendung. Sie müssen die Aufgaben zum Veröffentlichen der Anwendung, Erstellen eines Docker-Images und Starten des Images in einem neuen Container ausführen. Die Nutzung von Windows Server-Containern ist der einfachste Weg, um Ihre vorhandenen Anwendungen zu dieser Umgebung zu migrieren.

[Windows-Container]: media/aspnetmvc/SwitchContainer.png "Wechseln zum Windows-Container"
[publish-connection]: media/aspnetmvc/PublishConnection.png "Veröffentlichen im Dateisystem"
[publish-settings]: media/aspnetmvc/PublishSettings.png "Veröffentlichungseinstellungen"



<!--HONumber=Nov16_HO3-->


