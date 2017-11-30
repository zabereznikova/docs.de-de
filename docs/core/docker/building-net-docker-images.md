---
title: Erstellen von .NET Core Docker-Images
description: Grundlegendes zu Docker-Images und .NET Core
keywords: .NET, .NET Core, Docker
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
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a>Erstellen von Docker-Images für .NET Core-Anwendungen

 In diesem Lernprogramm liegt der Schwerpunkt auf wie .NET Core in Docker verwendet. Zunächst untersuchen wir die verschiedenen Docker-Images bereitgestellt und verwaltet von Microsoft und Anwendungsfälle. Wir Informationen klicken Sie dann zum Erstellen und dockerize eine ASP.NET Core-app.

Im Verlauf dieses Lernprogramms erfahren Sie:
> [!div class="checklist"]
> * Erfahren Sie mehr über Microsoft .NET Core Docker-images 
> * Abrufen einer ASP.NET Core Beispiel-app zu Dockerize
> * Der ASP.NET-beispielanwendung lokal ausführen
> * Erstellen Sie und führen Sie das Beispiel für Linux-Containern mit Docker
> * Erstellen Sie und führen Sie das Beispiel mit Docker für Windows-Containern

## <a name="docker-image-optimizations"></a>Docker-Image-Optimierungen

Beim Erstellen von Docker-Images für Entwickler standen drei wichtige Szenarios im Mittelpunkt:

* Images zum Entwickeln von .NET Core-Apps
* Images zum Erstellen von .NET Core-Apps
* Images zum Ausführen von .NET Core-Apps

Warum drei Images?
Beim Entwickeln, erstellen und Ausführen von Sammelartikeleinheit, haben wir die unterschiedliche Prioritäten.

* **Entwicklung:** der Priorität konzentriert sich auf Änderungen und die Fähigkeit zum Debuggen der Änderungen schnell zu durchlaufen. Nicht die Größe des Bilds wird so wichtig ist, sondern können Sie Änderungen am Code vornehmen und schnell?

* **Build:** dieses Image enthält alles, was zum Kompilieren der app, die der Compiler und alle anderen Abhängigkeiten zur Optimierung der Binärdateien umfasst benötigen.  Sie verwenden das Build-Image, um Objekte zu erstellen, die Sie in einer Produktions-Bild platzieren. Das Image Build würde für die fortlaufende Integration oder in einer Buildumgebung verwendet werden. Dieser Ansatz ermöglicht, einen Build-Agent zum Kompilieren und erstellen Sie die Anwendung (mit allen erforderlichen Abhängigkeiten) in einem Build bildinstanz. Der Build-Agent muss nur wissen, wie dieses Docker-Image ausgeführt wird.

* **Produktion:** wie schnell Sie bereitstellen und starten Sie das Abbild? Dieses Image ist klein, damit die Leistung des Netzwerks aus der Docker-Registrierung für die Docker-Hosts optimiert ist. Die Inhalte sind bereit zur Ausführung und ermöglichen in kürzester Zeit nach dem Dockerlauf das Verarbeiten von Ergebnissen. Dynamischen Codekompilierung ist nicht in der Docker-Modell erforderlich. Die Inhalte, die Sie in diesem Image platzieren, sind auf die Binärdateien und Inhalte beschränkt, die zum Ausführen der Anwendung erforderlich sind.

    Z. B. die `dotnet publish` Ausgabe enthält:

    * die kompilierten Binärdateien
    * js und CSS-Dateien


Der Grund für das Schließen der `dotnet publish` Ausgabe des Befehls in die Produktion Abbildung ist die Beibehaltung seiner "Größe auf ein Minimum.

Einige .NET Core-Abbilder freigeben Ebenen zwischen verschiedenen Tags damit Herunterladen der neuesten Tags eine relativ einfache Prozess ist. Wenn Sie bereits über eine ältere Version auf dem Computer verfügen, verringert diese Architektur des erforderlichen Speicherplatzes.

Wenn mehrere Anwendungen allgemeine Images auf dem gleichen Computer verwenden, ist die allgemeine Bilder Arbeitsspeicher freigegeben. Die Bilder müssen die weiterzuleitenden identisch sein.

## <a name="docker-image-variations"></a>Docker-Image-Varianten

Um die oben aufgeführten Ziele zu erreichen, bieten wir Image Varianten unter [ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/).

* `microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) Dieses Image enthält .NET Core SDK, das die .NET Core und über die Befehlszeile Tools (CLI) enthält. Dieses Image ist dem **Entwicklungsszenario** zugeordnet. Verwenden Sie dieses Image für lokale Entwicklung, Debuggen und Komponententests. Dieses Image kann auch für **Build**-Szenarios verwendet werden. Mithilfe von `microsoft/dotnet:sdk` erhalten Sie immer die neueste Version.

> [!TIP]
> Wenn Sie über Ihren Anforderungen nicht sicher sind, möchten Sie verwenden die `microsoft/dotnet:<version>-sdk` Bild. Als "de facto"-Image, es wurde entwickelt, als ein Throw verwendet werden soll beseitigen Container (Quellcode bereitgestellt, und starten Sie den Container aus, um die app zu starten), und als Basis-Image zum Erstellen von anderen Bildern aus.

* `microsoft/dotnet:<version>-runtime`: Dieses Image enthält die .NET Core (Common Language Runtime und Bibliotheken) und ist optimiert für die Ausführung von .NET Core-apps in **Produktion**.

## <a name="alternative-images"></a>Alternative Images

Zusätzliche Images zu den optimierten Szenarios für Entwicklung, Erstellung und Produktion:

* `microsoft/dotnet:<version>-runtime-deps`: Der **Runtime Einzahlgn** Abbild enthält das Betriebssystem mit alle systemeigenen Abhängigkeiten von .NET Core benötigt werden. Dieses Image ist für [eigenständige Anwendungen](https://docs.microsoft.com/dotnet/core/deploying/index).

Aktuelle Versionen jeder Variante:

* `microsoft/dotnet`oder `microsoft/dotnet:latest` (Alias für das SDK-Image)
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>Beispiele zum Durchsuchen

* [In diesem Beispiel ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) veranschaulicht ein best Practice-Muster für die Erstellung von Docker-Abbilder für ASP.NET Core apps für die Produktion. Das Beispiel funktioniert mit Linux und Windows-Containern.

* Diese .NET Core Docker demonstriert eine best Practice-Muster für [Docker-Images für .NET Core-apps für die Produktion zu erstellen.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)

## <a name="your-first-aspnet-core-docker-app"></a>Ihre erste ASP.NET Core Docker-app

Für dieses Lernprogramm können eine ASP.NET Core Docker-beispielanwendung für die app verwenden wir dockerize möchten. Diese beispielanwendung für ASP.NET Core Docker veranschaulicht ein best Practice-Muster für die Erstellung von Docker-Abbilder für ASP.NET Core apps für die Produktion. Das Beispiel funktioniert mit Linux und Windows-Containern.

Im Beispiel dockerfile-Datei wird ein ASP.NET Core Docker anwendungsimage basierend auf ASP.NET Core Runtime Docker-Basis-Image erstellt.

Er verwendet die [mehrstufiger Docker build Funktion](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) an:

* Erstellen Sie das Beispiel in einem Container auf Grundlage der **größere** ASP.NET Core erstellen Docker-Basis-Image 
* kopiert das Ergebnis des letzten Builds in ein Docker Bild auf der Grundlage der **kleinere** ASP.NET Core Docker-Laufzeit-Basis-Image

> [!Note]
> Der Build-Image enthält erforderlichen Tools zum Erstellen von Anwendungen, während der Laufzeit-Image nicht der Fall ist.

### <a name="prerequisites"></a>Erforderliche Komponenten

Zum Erstellen und ausführen, installieren Sie die folgenden Elemente:

#### <a name="net-core-20-sdk"></a>.NET core SDK 2.0

* Installieren Sie [.NET Core SDK 2.0](https://www.microsoft.com/net/core).

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

#### <a name="installing-git-for-sample-repository"></a>Installieren Git für die beispielrepository

* Installieren Sie [Git](https://git-scm.com/download) Wenn Sie das Repository klonen möchten.

### <a name="getting-the-sample-application"></a>Abrufen der beispielanwendung

Die einfachste Möglichkeit zum Abrufen des Beispiels wird durch das Klonen der [beispielrepository](https://github.com/dotnet/dotnet-docker-samples) mit Git, verwenden Sie die folgenden Anweisungen: 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

Sie können auch das Repository (er ist klein) herunterladen, als eine ZIP-Datei aus dem beispielrepository .NET Core Docker.

### <a name="run-the-aspnet-app-locally"></a>Die ASP.NET app lokal ausführen

Als Bezugspunkt, bevor die Anwendung containerisiert wird, führen Sie die Anwendung zunächst lokal aus.

Sie können erstellen und führen Sie die Anwendung lokal mit dem .NET Core 2.0 SDK mit den folgenden Befehlen (die Anweisungen gehen davon aus den Stamm des Repositorys):

```console
cd aspnetapp
dotnet run
```

Nachdem die Anwendung gestartet wird, besuchen Sie **http://localhost: 5000** in Ihrem Webbrowser.

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>Erstellen Sie und führen Sie das Beispiel für Linux-Containern mit Docker

Sie können erstellen und führen Sie das Beispiel in Docker mithilfe von Linux-Container mit den folgenden Befehlen (die Anweisungen gehen davon aus den Stamm des Repositorys):

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] Die `docker run` "-p"-Argument Maps port 5000 auf dem lokalen Computer an Port 80 im Container (Port Zuordnung ist `host:container`). Weitere Informationen finden Sie unter der ["Docker run"](https://docs.docker.com/engine/reference/commandline/exec/) Verweis auf Befehlszeilenparameter.

Nachdem die Anwendung gestartet wird, besuchen Sie **http://localhost: 5000** in Ihrem Webbrowser.

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>Erstellen Sie und führen Sie das Beispiel mit Docker für Windows-Containern

Sie können erstellen und führen Sie das Beispiel in Docker mithilfe von Windows-Container mit den folgenden Befehlen (die Anweisungen gehen davon aus den Stamm des Repositorys):

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> Sie müssen zu navigieren, die **Container IP-Adresse** (im Gegensatz zu http://localhost) in Ihrem Browser direkt bei Verwendung der Windows-Containern. Sie erhalten die IP-Adresse des Containers mit den folgenden Schritten:

* Öffnen Sie eine andere Befehlszeile.
* Führen Sie `docker ps` auf Ihre ausgeführten Container angezeigt. Der Container "Aspnetcore_sample" sollte angezeigt werden.
* Führen Sie `docker exec aspnetcore_sample ipconfig` aus.
* Kopieren Sie die Container-IP-Adresse ein, und fügen Sie in Ihrem Browser (z. B. 172.29.245.43).

> [!Note]
> Docker Exec unterstützt identifizierende Container mit dem Namen "oder" Hash. In unserem Beispiel wird der Name (Aspnetcore_sample) verwendet.

Sehen Sie im folgenden Beispiel des Abrufs der IP-Adresse von ausgeführten Windows-Container.

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!Note]
> Docker Exec führt einen neuen Befehl in einem ausgeführten Container. Weitere Informationen finden Sie unter der [Referenz zu Docker Exec](https://docs.docker.com/engine/reference/commandline/exec/) auf Befehlszeilenparameter.

Sie können eine Anwendung, die bereit für die Bereitstellung bis hin zur Produktion, die lokal mithilfe von erzeugen die [Dotnet veröffentlichen](../tools/dotnet-publish.md) Befehl.

```console
dotnet publish -c release -o published
```

> [!Note]
> Arguments - C Release wird die Anwendung im Releasemodus (der Standardwert ist Debug-Modus). Weitere Informationen finden Sie unter der [Dotnet Referenz run](../tools/dotnet-run.md) auf Befehlszeilenparameter.

Führen Sie die Anwendung auf **Windows** mithilfe des folgenden Befehls.

```console
dotnet published\aspnetapp.dll
```

Führen Sie die Anwendung auf **Linux** oder **MacOS** mithilfe des folgenden Befehls.

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>In diesem Beispiel verwendete Docker-Images

In diesem Beispiel werden die folgenden Docker-Images verwendet.

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

Herzlichen Glückwunsch! Sie haben soeben:
> [!div class="checklist"]
> * Microsoft .NET Core Docker Images gelernt
> * Erhalten eine ASP.NET Core Beispiel-app zu Dockerize
> * Wurde der ASP.NET-beispielanwendung lokal ausgeführt
> * Erstellt und die Ausführung des Beispiels mit Docker für Linux-Container
> * Erstellt und im Beispiel mit Docker für Windows-Container ausgeführt haben.


**Nächste Schritte**

Hier sind die nächsten Schritte, die Sie ergreifen können:

* [Arbeiten mit Docker-Tools für Visual Studio](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Bereitstellen von Docker-Images aus der Registrierung des Azure-Container für Instanzen von Azure-Container](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Debuggen mit Visual Studio-Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Beim Abrufen der Hände für mit Visual Studio für Mac, Container und serverlose Code in der cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Erste Schritte mit Docker und Visual Studio für Mac-Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> Wenn Sie nicht über ein Azure-Abonnement verfügen [registrieren Sie sich noch heute](https://azure.microsoft.com/free/?b=16.48) für eine kostenlose 30-Tage-Konto verhindern und $200 Azure-Guthaben auf eine beliebige Kombination von Azure-Dienste zu testen.
