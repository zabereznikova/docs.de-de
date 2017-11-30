---
title: "Einführung in .NET und Docker"
description: Grundlegendes zu Docker und .NET Core
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
manager: wpickett
ms.custom: mvc
ms.openlocfilehash: 1c9ce7a008c86d1c245ce8b7d616e05fcb3d4bbc
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="introduction-to-net-and-docker"></a>Einführung in .NET und Docker

 Dieser Artikel bietet eine Einführung und konzeptionelle Hintergrund für die Arbeit mit .NET auf Docker. 

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker: Verpacken Ihrer apps zur bereitstellen und Ausführen von überall

[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) ist eine offene Plattform, die Entwicklern und Administratoren erstellen [Bilder](https://docs.docker.com/glossary/?term=image), liefern, und führen Sie verteilte Anwendungen in einer lose netzwerkisolierte Umgebung bezeichnet eine [Container](https://www.docker.com/what-container). Dieser Ansatz ermöglicht eine effiziente Anwendungslebenszyklus-Verwaltung zwischen Entwicklung, QA und produktionsumgebungen.
 
Die [die Plattform Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) verwendet die [Docker-Modul](https://docs.docker.com/engine/docker-overview/#docker-engine) schnell erstellen und die Paket-apps als [Docker Images](https://docs.docker.com/glossary/?term=image) mit Dateien in erstellt die [dockerfile-Datei ](https://docs.docker.com/glossary/?term=Dockerfile) Format, das dann bereitgestellt und ausgeführt wird, einem [Container in den Ebenen](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

Sie können entweder Erstellen eigener [Bilder in den Ebenen](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) als dockerfile-Dateien, oder verwenden Sie existierende aus eine [Registrierung](https://docs.docker.com/glossary/?term=registry), z. B. [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).

Die [Beziehung zwischen Docker-Containern, Bilder und Registrierungen](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) ist ein wichtiges Konzept bei [Entwurf und Erstellen von Containern, Anwendungen oder Microservices](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/). Dieser Ansatz wird erheblich verkürzt die Zeit zwischen Entwicklung und Bereitstellung.

### <a name="further-reading-and-watching"></a>Weitere Informationen (und beobachten von)

* [Windows-basierte Container: moderne app-Entwicklung mit dem Enterprise-Grade Control.](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [Docker-Übersicht](https://docs.docker.com/engine/docker-overview/)
* [Dockerfile unter Windows-Containern](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Bewährte Methoden zum Schreiben von dockerfile-Dateien](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [Erstellen von Docker-Images für .NET Core-Anwendungen](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>Abrufen von Docker-Images für .NET

Die offizielle .NET Docker-Images erstellt und optimiert, die von Microsoft. Sie sind in den Microsoft-Repositorys auf Docker Hub öffentlich verfügbar. Jedes Repository kann mehrere Abbilder, je nach Version und auf Betriebssystemversionen enthalten. Die meisten Image-Repositorys bieten umfassende kennzeichnen, damit Sie eine spezifische Framework-Version und Betriebssystem (Linux-Distribution oder Windows-Version) auswählen können.

## <a name="scenario-based-guidance"></a>Szenario Basis, Anleitung

Microsofts beabsichtigte für .NET-Repositorys ist präzise und konzentriert sich-Repositorys, die ein bestimmtes Szenario oder eine arbeitsauslastung darstellen.

Die `microsoft/aspnetcore` Images sind für ASP.NET Core-apps in Docker optimiert, sodass Container schneller gestartet werden können.

Die .NET Core-Bilder (`microsoft/dotnet`) sind für die Konsolen-apps, die basierend auf .NET Core vorgesehen. Beispielsweise sollten Batchprozessen Azure WebJobs und Weitere Szenarien Konsole optimierte .NET Core-Images verwenden.

Der offensichtlichste horizontale Szenario für die Verwendung von Docker und .NET Applications ist für die produktionsbereitstellung und hosting. Es stellt sich heraus, dass die Produktion ist nur ein Szenario und die anderen werden gleichermaßen eignen. Diese Szenarien sind nicht spezifisch für .NET allerdings gelten für die meisten Entwickler-Plattformen.

* **Installieren mit niedriger Unstimmigkeiten** – .NET auszuprobieren, ohne eine lokale Installation. Laden Sie einfach ein Docker Bild mit .NET darin herunter.

* **Entwickeln Sie in einem Container** – können Sie entwickeln in eine konsistente Umgebung vornehmen Entwicklungs-und produktionsumgebungen ähnliche (z. B. globale Zustand auf Entwicklercomputern Probleme zu vermeiden). Visual Studio-Tools für Docker aktivieren Sie auch direkt in Visual Studio einen Container zu starten.

* **Testen in einem Container** – Sie können testen, in einem Container Verringerung von Fehlern aufgrund von falsch konfigurierten Umgebungen oder andere Änderungen aus dem letzten Testlauf hinterlassen.

* **Erstellen Sie in einem Container** – Sie können Code in einem Container erstellen entfällt die Notwendigkeit für Umgebungen mit mehreren freigegebenen Buildcomputern nicht ordnungsgemäß konfiguriert, jedoch stattdessen in einer "BYOC" verschieben (bring eigene Container) Ansatz.

* **Bereitstellung in sämtlichen Umgebungen** – Sie können ein Bild über alle Ihre Umgebungen bereitstellen. Dieser Ansatz reduziert Fehler aufgrund von Konfigurationsunterschiede, in der Regel die Image-Verhalten über externe Konfiguration (z. B. eingefügten Umgebungsvariablen) ändern.

[Allgemeine Richtlinien](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) bei der Entscheidung zwischen .NET Core und .NET Framework für die Entwicklung der Docker-Container.

### <a name="common-docker-development-scenarios"></a>Allgemeine Docker-Entwicklungsszenarien

#### <a name="net-core"></a>.NET Core

**.NET Core-Ressourcen**

 Wählen Sie die .NET Core-Beispiele, in denen Ihre Szenarien von Interesse sind geeignet. Alle Beispiel Anweisungen wird beschrieben, wie Windows oder Linux-Docker-Images von Windows, Linux oder MacOS Hosts als Ziel.

Die Beispiele verwenden die .NET Core 2.0. Verwenden Sie Docker [mehrstufiger Build](https://github.com/dotnet/announcements/issues/18) und [mit mehreren arch Tags](https://github.com/dotnet/announcements/issues/14) , sofern zutreffend.

* [.NET Core-Images auf DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [Dockerize einer .NET Core-Anwendung](https://docs.docker.com/engine/examples/dotnetcore/)

* Diese .NET Core Docker-Beispiel wird veranschaulicht, wie [Docker im Entwicklungsprozess .NET Core verwenden](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev). Das Beispiel funktioniert mit Linux und Windows-Containern.

* Diese .NET Core Docker demonstriert eine best Practice-Muster für [Docker-Images für .NET Core-apps für die Produktion zu erstellen.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod) Das Beispiel funktioniert mit Linux und Windows-Containern.

* Dies [.NET Core Docker Beispiel](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) veranschaulicht eine best Practice-Muster zum Erstellen von Images von Docker für [eigenständige .NET Core-Anwendungen](https://docs.microsoft.com/dotnet/core/deploying/). Verwendet für den kleinsten Produktions-Container ohne einen Vorteil von [Basisimages zwischen Containern freigeben](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/). Jedoch werden niedrigere Ebenen der Docker gemeinsam genutzt.

#### <a name="arm32--raspberry-pi"></a>ARM32 / Brombeere Pi

* [.NET Core-Laufzeit ARM32 Builds Ankündigung](https://github.com/dotnet/announcements/issues/29)

* [ARM32 / Brombeere Pi .NET Core auf DockerHub Bilder](https://hub.docker.com/r/microsoft/dotnet/)

* [ARM32 / Brombeere Pi .NET Core Docker Samples auf GitHub](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a>.NET Framework

* [.NET Framework-Images auf DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/) diesem Repository enthalten Beispiele für die verschiedenen .NET Framework Docker-Konfigurationen. Sie können diese Abbilder als Grundlage für eigene Docker-Images verwenden.

**.NET Framework 4.7**

[Die [Dotnet-Framework: 4.7 Beispiel](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) veranschaulicht die einfache "hello World" Verwendung von der [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47). Hier erfahren Sie, wie Sie erstellen und Bereitstellen der Anwendung der vertrauenden Seite auf die [.NET Framework 4.7 Docker Bild](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).

**.NET Framework 4.6.2**

Die [Dotnet-Framework 4.6.2: Beispiel](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) veranschaulicht die einfache "hello World" Verwendung von der [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462). Hier erfahren Sie, wie Sie erstellen und Bereitstellen der Anwendung der vertrauenden Seite auf die [.NET Framework 4.6.2 Docker Bild](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).

**.NET Framework 3.5**

 Die [Dotnet-Framework 3.5: Beispiel](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) veranschaulicht die einfache "hello World" Verwendung von [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5). Hier erfahren Sie, das Erstellen und Bereitstellen eines Projekts auf .NET Framework 3.5 in Docker zurückzugreifen.

#### <a name="aspnet-core"></a>ASP.NET Core

* [In diesem Beispiel ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) veranschaulicht ein best Practice-Muster für die Erstellung von Docker-Abbilder für ASP.NET Core apps für die Produktion. Das Beispiel funktioniert mit Linux und Windows-Containern.

* [ASP.NET Core Bilder auf DockerHub](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [ASP.NET Core Bilder auf GitHub](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a>ASP.NET Framework 

* [ASP.NET-Framework Bilder auf DockerHub](https://hub.docker.com/r/microsoft/aspnet/)

* [ASP.NET Web Forms-Anwendung auf .NET Framework 4.6.2-Beispiel](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a>Windows Communication Framework (WCF)

* [Windows Communication Framework (WCF)-Images auf DockerHub](https://hub.docker.com/r/microsoft/wcf/)

* [Windows Communication Framework (WCF)-Images auf GitHub](https://github.com/microsoft/iis-docker)

* [Verwenden die vollständige .NET Framework 4.6.2 Windows Communication Framework (WCF)-Docker-Beispiele](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a>Internet Information Server (IIS)

* [Internet Information Server (IIS)-Images auf DockerHub](https://hub.docker.com/r/microsoft/iis/)

* [Internet Information Server (IIS)-Images auf GitHub](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a>Interaktion mit anderen Microsoft-Stack-containerimages

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [Führen Sie die Microsoft SQL Server für Linux 2017 Container-Image mit Docker-Schnellstart](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [Microsoft SQL Server für Linux-Images auf DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [Microsoft SQL Server für Windows-Container Bilder auf DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [Microsoft SQL Server Express Edition-Images für Windows-Container unter DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [Microsoft SQL Server Developer Edition-Images für Windows-Container unter DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a>Visual Studio Team Services (VSTS)-agent

* [Visual Studio Team Services (VSTS)-Agent-Images auf DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/)

* [Visual Studio Team Services (VSTS)-Agent-Images auf GitHub](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>Operations Management Suite (OMS) Linux-agent

* [Übersicht über die Operations Management Suite (OMS) Linux-agent](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [Operations Management Suite (OMS) Bilder auf DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/) 

* [Operations Management Suite (OMS) Bilder auf GitHub](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Microsoft Azure-Befehlszeilenschnittstelle (CLI)

* [Microsoft Azure-Befehlszeilenschnittstelle (CLI) Bilder auf DockerHub](Docker image for Microsoft Azure Command Line Interface) 

* [Microsoft Azure-Befehlszeilenschnittstelle (CLI) Bilder auf GitHub](https://github.com/Microsoft/OMS-docker)

> [!Note]
> Wenn Sie nicht über ein Azure-Abonnement verfügen [registrieren Sie sich noch heute](https://azure.microsoft.com/free/?b=16.48) für eine kostenlose 30-Tage-Konto verhindern und $200 Azure-Guthaben auf eine beliebige Kombination von Azure-Dienste zu testen.
>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Microsoft Azure-Cosmos-DB-Emulator (nur Windows-Container)

* [Microsoft Azure-Cosmos-DB-Emulator Bilder auf DockerHub](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [Verwenden der Azure-Cosmos-DB-Speicheremulator für lokale Entwicklung und Tests](https://docs.microsoft.com/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>Untersuchen das umfangreiche Docker-Ökosystem Entwicklung

Nun, dass Sie über die Plattform Docker und verschiedene Docker-Images gelernt haben, besteht der nächste Schritt der Docker-Ökosystems zu durchsuchen. Die folgenden Links zeigen, wie die Microsoft-Tools für Container Entwicklung ergänzen.

* [Die gemeinsame Verwendung von .NET und Docker](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) 
* [Entwerfen und Entwickeln von Anwendungen mit mehreren Container und Microservice basierende .NET](../standard/microservices-architecture/multi-container-microservice-net-applications)
* [Visual Studio Code Docker-Erweiterung](https://code.visualstudio.com/docs/languages/dockerfile) 
* [Informationen Sie zum Verwenden von Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/) 
* [Service Fabric-erste Schritte – Beispiel](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [Vorteile von Windows-Containern](https://docs.microsoft.com/virtualization/windowscontainers/about/index#video-overview)
* [Arbeiten mit Docker-Tools für Visual Studio](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Bereitstellen von Docker-Images aus der Registrierung des Azure-Container für Instanzen von Azure-Container](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Debuggen mit Visual Studio-Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Beim Abrufen der Hände für mit Visual Studio für Mac, Container und serverlose Code in der cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Erste Schritte mit Docker und Visual Studio für Mac-Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a>Nächste Schritte

* [Erlernen von Grundlagen der Docker mit .NET Core](../docker/docker-basics-dotnet-core.md)
* [Erstellen von .NET Core Docker-Images](../docker/building-net-docker-images)