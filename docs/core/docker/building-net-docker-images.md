---
title: Übersicht zu Docker-Images – .NET Core
description: Erfahren Sie, wie Sie veröffentlichte .NET Core-Docker-Images aus der Docker-Registrierung verwenden können. Außerdem lernen Sie, wie Sie Pull für Images ausführen und Ihre eigenen Images erstellen.
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 34ff6ce7d990412fa0ac4896d1e2e39b307681f0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145831"
---
# <a name="learn-about-docker-images-for-net-core"></a>Informationen zu Docker-Images für .NET Core

In diesem Tutorial liegt der Schwerpunkt auf der Verwendung von .NET Core in Docker. Zunächst werden die unterschiedlichen Docker-Images erläutert, die von Microsoft angeboten und verwaltet werden, sowie einige Anwendungsfälle. Sie erfahren, wie eine ASP.NET Core-App erstellt und in Docker bereitgestellt wird.

Im Verlauf dieses Tutorials lernen Sie Folgendes:
> [!div class="checklist"]
> * Allgemeines zu Docker-Images in Microsoft .NET Core 
> * das Abrufen einer ASP.NET Core-Beispiel-App für die Bereitstellung in Docker
> * das lokale Ausführen der ASP.NET-Beispiel-App
> * das Erstellen und Ausführen des Beispiels mit Docker für Linux-Container
> * das Erstellen und Ausführen des Beispiels mit Docker für Windows-Container

## <a name="docker-image-optimizations"></a>Docker-Image-Optimierungen

Beim Erstellen von Docker-Images für Entwickler standen drei wichtige Szenarios im Mittelpunkt:

* Images zum Entwickeln von .NET Core-Apps
* Images zum Erstellen von .NET Core-Apps
* Images zum Ausführen von .NET Core-Apps

Warum drei Images?
Beim Entwickeln, Erstellen und Ausführen von Containeranwendungen gibt es unterschiedliche Prioritäten.

* **Entwicklung:** Die Priorität liegt hierbei auf dem schnellen Durchführen von Änderungen sowie auf dem Debuggen der Änderungen. Die Größe des Images ist nicht entscheidend, sondern ob Änderungen am Code vorgenommen und schnell angezeigt werden können.

* **Build:** Dieses Image enthält alle Bestandteile, die zum Kompilieren Ihrer App erforderlich sind. Dazu zählen der Compiler und alle anderen Abhängigkeiten, die zum Optimieren der Binärdateien verwendet werden.  Sie verwenden das Buildimage zum Erstellen der Objekte, die Sie in einem Produktionsimage platzieren. Dieses Image wird für die Continuous Integration oder in einer Buildumgebung verwendet. Dieser Ansatz ermöglicht einem Build-Agent das Kompilieren und Erstellen der Anwendung (mit allen erforderlichen Abhängigkeiten) in einer Instanz des Buildimages. Der Build-Agent muss nur wissen, wie dieses Docker-Image ausgeführt wird.

* **Produktion:** Wie schnell kann das Image bereitgestellt und gestartet werden? Da dieses Image klein ist, ist die Netzwerkleistung von Ihrer Docker-Registrierung zu Ihren Docker-Hosts ideal. Die Inhalte sind bereit zur Ausführung und ermöglichen in kürzester Zeit nach dem Dockerlauf das Verarbeiten von Ergebnissen. Die dynamische Codekompilierung ist im Docker-Modell nicht erforderlich. Die Inhalte, die Sie in diesem Image platzieren, sind auf die Binärdateien und Inhalte beschränkt, die zum Ausführen der Anwendung erforderlich sind.

    Die `dotnet publish`-Ausgabe enthält beispielsweise:

    * die kompilierten Binärdateien
    * JS- und CSS-Dateien


Sie sollten die `dotnet publish`-Befehlsausgabe Ihrem Produktionsimage hinzufügen, um die Größe so gering wie möglich zu halten.

Einige .NET Core-Images geben die Ebenen zwischen verschiedenen Tags frei, sodass es sich beim Herunterladen der aktuellen Tags um einen einfachen Vorgang handelt. Wenn Sie bereits über eine ältere Version auf Ihrem Computer verfügen, verringert diese Architektur den erforderlichen Speicherplatz.

Wenn mehrere Anwendungen gemeinsame Images auf demselben Computer verwenden, wird der Arbeitsspeicher zwischen den gemeinsamen Images aufgeteilt. Hierzu müssen die Images identisch sein.

## <a name="docker-image-variations"></a>Docker-Image-Varianten

Zum Erreichen der oben genannten Ziele werden unter [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/) Imagevarianten bereitgestellt.

* `microsoft/dotnet:<version>-sdk` (`microsoft/dotnet:2.1-sdk`) Dieses Image enthält das .NET Core SDK, das die .NET Core- und CLI-Tools (Command Line Interface) enthält. Dieses Image ist dem **Entwicklungsszenario** zugeordnet. Dieses Image wird für die lokale Entwicklung sowie für das Debuggen und für Komponententests verwendet. Dieses Image kann auch für **Build**-Szenarios verwendet werden. Mithilfe von `microsoft/dotnet:sdk` können Sie jederzeit die aktuelle Version abrufen.

> [!TIP]
> Bei Unsicherheiten bezüglich Ihrer Anforderungen sollten Sie das `microsoft/dotnet:<version>-sdk`-Image verwenden. Es wurde als allgemeines Image entwickelt, um als Basiscontainer (zum Einbinden Ihres Quellcodes und Starten des Containers, um die App zu starten) und als Basisimage zum Erstellen von anderen Images verwendet zu werden.

* `microsoft/dotnet:<version>-runtime`: Dieses Image enthält die .NET Core-Runtime und -Bibliotheken und wurde für das Ausführen von .NET Core-Apps in der **Produktion** optimiert.

## <a name="alternative-images"></a>Alternative Images

Zusätzliche Images zu den optimierten Szenarios für Entwicklung, Erstellung und Produktion:

* `microsoft/dotnet:<version>-runtime-deps`: Das Image **runtime-deps** enthält das Betriebssystem und alle für .NET Core erforderlichen nativen Abhängigkeiten. Dieses Image ist für [eigenständige Anwendungen](../deploying/index.md) vorgesehen.

Aktuelle Versionen jeder Variante:

* `microsoft/dotnet` oder `microsoft/dotnet:latest` (Alias für das SDK-Image)
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>Hilfreiche Beispiele

* Dieses [Beispiel zum ASP.NET Core-Docker](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) stellt ein bewährtes Muster für die Erstellung von Docker-Images für ASP.NET Core-Apps für die Produktion vor. Das Beispiel funktioniert sowohl mit Linux- als auch mit Windows-Containern.

* In diesem Beispiel für .NET Core-Docker wird ein bewährtes Muster für die [Erstellung von Docker-Images für .NET Core-Apps für die Produktion](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp) vorgestellt.

## <a name="forward-the-request-scheme-and-original-ip-address"></a>Weiterleiten des Anforderungsschemas und der ursprünglichen IP-Adresse

Proxyserver, Lastenausgleichsmodule und anderen Netzwerkgeräte verdecken häufig Informationen zu einer Anforderung, bevor diese die Container-App erreicht:

* Wenn HTTPS-Anforderungen über HTTP-Proxy ausgeführt werden, geht das ursprüngliche Schema (HTTPS) verloren und muss in einem Header weitergeleitet werden.
* Da eine App eine Anforderung über den Proxy empfängt und nicht über ihre echte Quelle im Internet oder Unternehmensnetzwerk, muss die ursprüngliche Client-IP-Adresse ebenfalls in einem Header weitergeleitet werden.

Diese Informationen können im Anforderungsprozess, z.B. in Umleitungen, bei der Authentifizierung, der Linkgenerierung, der Richtlinienauswertung und der Client-Geolocation wichtig sein.

Verwenden Sie Middleware für weitergeleitete Header, um das Schema und die ursprüngliche IP-Adresse an eine ASP.NET Core-Container-App weiterzuleiten. Weitere Informationen hierzu feinden Sie unter [Konfigurieren von ASP.NET Core zur Verwendung mit Proxyservern und Lastenausgleich](/aspnet/core/host-and-deploy/proxy-load-balancer).

## <a name="your-first-aspnet-core-docker-app"></a>Ihre erste Docker-App mit ASP.NET Core

In diesem Beispiel wird eine Docker-Beispielanwendung für ASP.NET-Core für die App verwendet, die in Docker bereitgestellt werden soll. Diese Docker-Beispielanwendung für ASP.NET Core veranschaulicht eine bewährte Methode zum Erstellen von Docker-Images für ASP.NET Core-Apps für die Produktion. Das Beispiel funktioniert sowohl mit Linux- als auch mit Windows-Containern.

Die Dockerfile-Beispieldatei erstellt ein Docker-Image einer ASP.NET Core-Anwendung, das auf dem Docker-Basisimage der ASP.NET Core-Runtime basiert.

Dieses verwendet das [Docker-Feature für mehrstufige Builds](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) für:

* das Erstellen des Beispiels in einem Container, der auf dem **größeren** Docker-Basisimage für ASP.NET Core-Builds basiert 
* das Kopieren der finalen Buildergebnisse in ein Docker-Image, das auf dem **kleineren** Docker-Basisimage der ASP.NET Core-Runtime basiert

> [!NOTE]
> Das Buildimage enthält im Gegensatz zum Runtimeimage die erforderlichen Tools zum Erstellen von Anwendungen.

### <a name="prerequisites"></a>Erforderliche Komponenten

Installieren Sie zum Erstellen und Ausführen folgende Elemente:

#### <a name="net-core-21-sdk"></a>.NET Core 2.1 SDK

* Installieren Sie [.NET Core SDK 2.1](https://www.microsoft.com/net/core).

* Installieren Sie Ihren bevorzugten Code-Editor, wenn Sie dies nicht bereits erledigt haben.

> [!TIP]
> Benötigen Sie einen Code-Editor? Testen Sie [Visual Studio](https://visualstudio.com/downloads).

#### <a name="installing-docker-client"></a>Installieren des Docker-Clients

Installieren Sie den Docker-Client [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) oder höher.

Der Docker-Client kann unter folgenden Betriebssystemen installiert werden:

* Linux-Verteilungen

   * [CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [Debian](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [Fedora](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [macOS](https://docs.docker.com/docker-for-mac/install/)

* [Windows](https://docs.docker.com/docker-for-windows/install/)

#### <a name="installing-git-for-sample-repository"></a>Installieren von Git für Beispielrepositorys

* Installieren Sie [Git](https://git-scm.com/download), wenn Sie das Repository klonen möchten.

### <a name="getting-the-sample-application"></a>Abrufen der Beispielanwendung

Sie können das Beispiel am einfachsten abrufen, indem Sie mithilfe der folgenden Anweisungen das [.NET Core Docker-Repository](https://github.com/dotnet/dotnet-docker) mit Git klonen: 

```console
git clone https://github.com/dotnet/dotnet-docker
```

Sie können das Repository ebenfalls als ZIP-Datei (die Datei ist klein) vom Docker-Repository für .NET Core herunterladen.

### <a name="run-the-aspnet-app-locally"></a>Lokales Ausführen der ASP.NET-App

Als Bezugspunkt, bevor die Anwendung containerisiert wird, führen Sie die Anwendung zunächst lokal aus.

Sie können die Anwendung mithilfe des .NET Core 2.1 SDK lokal erstellen und ausführen, indem Sie folgende Befehle verwenden (die Anweisungen gehen vom Stamm des Repositorys aus):

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located
cd aspnetapp // project scope

dotnet run
```

Rufen Sie nach dem Starten der Anwendung **http://localhost:5000** im Webbrowser auf.

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>das Erstellen und Ausführen des Beispiels mit Docker für Linux-Container

Sie können das Beispiel in Docker mit Linux-Containern erstellen und ausführen, indem Sie folgende Befehle verwenden (die Anweisungen gehen vom Stamm des Repositorys aus):

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> Das `docker run`-Argument „-p“ ordnet Port 5000 auf Ihrem lokalen Computer zu Port 80 im Container zu (das Format für die Zuordnung von Ports lautet `host:container`). Weitere Informationen finden Sie unter den Befehlszeilenparametern in der Referenz zu [docker run](https://docs.docker.com/engine/reference/commandline/exec/).

Rufen Sie nach dem Starten der Anwendung **http://localhost:5000** im Webbrowser auf.

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>das Erstellen und Ausführen des Beispiels mit Docker für Windows-Container

Sie können das Beispiel in Docker mit Windows-Containern erstellen und ausführen, indem Sie folgende Befehle verwenden (die Anweisungen gehen vom Stamm des Repositorys aus):

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> Sie müssen direkt in Ihrem Browser zur **IP-Adresse des Containers** navigieren (im Gegensatz zu `http://localhost`), wenn Sie Windows-Container verwenden. Sie können die IP-Adresse Ihres Containers abrufen, indem Sie folgende Schritte ausführen:

* Öffnen Sie eine weitere Eingabeaufforderung.
* Führen Sie `docker ps` aus, um Ihre ausgeführten Container anzuzeigen. Der Container „aspnetcore_sample“ sollte angezeigt werden.
* Führen Sie aus `docker exec aspnetcore_sample ipconfig`.
* Kopieren Sie die IP-Adresse des Containers (z.B. 172.29.245.43), und fügen Sie diese in Ihrem Browser ein.

> [!NOTE]
> „docker exec“ identifiziert Container per Name oder Hash. In diesem Beispiel wird der Name (aspnetcore_sample) verwendet.

Im folgenden Beispiel wird dargestellt, wie Sie die IP-Adresse eines ausgeführten Windows-Containers abrufen können.

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

> [!NOTE]
> „docker exec“ führt einen neuen Befehl in einem ausgeführten Container aus. Weitere Informationen finden Sie unter den Befehlszeilenparametern in der [Referenz zu docker exec](https://docs.docker.com/engine/reference/commandline/exec/).

Sie können eine Anwendung, die für die Produktion bereitgestellt werden kann, lokal mithilfe des Befehls [dotnet publish](../tools/dotnet-publish.md) erstellen.

```console
dotnet publish -c Release -o published
```

> [!NOTE]
> Das Argument „-c Release“ erstellt die Anwendung im Releasemodus (der Standardwert ist der Debugmodus). Weitere Informationen finden Sie unter den Befehlszeilenparametern in der [Referenz zu dotnet run](../tools/dotnet-run.md).

Sie können die Anwendung mithilfe des folgenden Befehls unter **Windows** ausführen.

```console
dotnet published\aspnetapp.dll
```

Sie können die Anwendung mithilfe des folgenden Befehls unter **Linux** oder **macOS** ausführen.

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>In diesem Beispiel verwendete Docker-Images

Folgende Docker-Images werden in der Dockerfile-Datei dieses Beispiels verwendet.

* `microsoft/dotnet:2.1-sdk`
* `microsoft/dotnet:2.1-aspnetcore-runtime`

Herzlichen Glückwunsch! Sie haben gerade:
> [!div class="checklist"]
> * Allgemeines zu Docker-Images in Microsoft .NET Core erfahren
> * eine ASP.NET Core-Beispiel-App für die Bereitstellung in Docker abgerufen
> * die ASP.NET-Beispiel-App lokal ausgeführt
> * das Beispiel mit Docker für Linux-Container erstellt und ausgeführt
> * das Beispiel mit Docker für Windows-Container erstellt und ausgeführt

**Nächste Schritte**

Im Folgenden finden Sie weiterführende Schritte:

* [Arbeiten mit Visual Studio-Tools für Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances (Bereitstellen von Docker-Images aus Azure Container Registry für Azure Container Instances)](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Debuggen mit Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud (Erste Schritte mit Visual Studio für Mac, Container und serverlose Code in der Cloud)](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Erste Schritte mit Docker und Visual Studio für Mac – Übung](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!NOTE]
> Wenn Sie kein Azure-Abonnement besitzen, [registrieren Sie sich noch heute für ein kostenloses 30-Tage-Konto](https://azure.microsoft.com/free/?b=16.48), und erhalten Sie ein Azure-Guthaben in Höhe von 200 US-Dollar, um eine beliebige Kombination von Azure-Diensten zu testen.
