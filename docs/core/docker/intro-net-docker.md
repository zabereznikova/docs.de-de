---
title: Einführung zu .NET und Docker
description: Grundlegendes zu Docker und .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.custom: mvc
ms.openlocfilehash: bc652a375abd03bbc70f055b34d6ecea4d9fc374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33219166"
---
# <a name="introduction-to-net-and-docker"></a>Einführung zu .NET und Docker

Dieser Artikel enthält eine Einführung und einen Überblick über den konzeptionellen Hintergrund für die Arbeit mit .NET in Docker.

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker: Packen Ihrer Apps für die Bereitstellung und Ausführung von einem beliebigen Ort aus

[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) ist eine offene Plattform, die es Entwicklern und Administratoren ermöglicht, in einer isolierten Umgebung, einem sogenannten [Container](https://www.docker.com/what-container), [Images](https://docs.docker.com/glossary/?term=image) zu erstellen, zu versenden und verteilte Anwendungen auszuführen. Diese Vorgehensweise ermöglicht ein effizientes Application Lifecycle Management zwischen Entwicklungs-, QA- und Produktionsumgebungen.
 
Die [Docker-Plattform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) verwendet die [Docker-Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) zum schnellen Erstellen und Packen von Apps als [Docker-Images](https://docs.docker.com/glossary/?term=image), die mit Dateien erstellt wurden, die im [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile)-Format geschrieben und dann in einem [mehrstufigen Container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers) bereitgestellt und ausgeführt werden.

Sie können entweder eigene [mehrstufige Images](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) als Dockerfile-Dateien erstellen oder vorhandene aus einer [Registry](https://docs.docker.com/glossary/?term=registry) wie [Docker-Hub](https://docs.docker.com/glossary/?term=Docker%20Hub) verwenden.

Die [Beziehung zwischen Docker-Containern, -Images und -Registrys](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md) ist ein wichtiges Konzept beim [Entwurf und Aufbau von Containeranwendungen oder Microservices](../../standard/microservices-architecture/architect-microservice-container-applications/index.md). Durch diese Vorgehensweise wird die Zeit zwischen Entwicklung und Bereitstellung deutlich verkürzt.

### <a name="further-reading-and-watching"></a>Weitere Ressourcen

* [Windows-based containers: Modern app development with enterprise-grade control (Windows-basierte Container: Entwicklung moderner Apps mit Steuerung auf Unternehmensniveau)](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [Docker overview (Docker – Übersicht)](https://docs.docker.com/engine/docker-overview/)
* [Dockerfile-Datei in Windows-Containern](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Best practices for writing Dockerfiles (Bewährte Methoden zum Schreiben von Docker-Dateien)](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [Erstellen von Docker-Images für .NET Core-Anwendungen](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>Abrufen von .NET Docker-Images

Die offiziellen .NET-Docker-Images werden von Microsoft erstellt und optimiert. Sie sind öffentlich in den Microsoft-Repositorys im Docker-Hub verfügbar. Jedes Repository kann abhängig von den .NET-Versionen und den Betriebssystemversionen mehrere Images enthalten. Die meisten Imagerepositorys bieten umfangreiche Taggingfunktionen, die Sie bei der Auswahl einer bestimmten Frameworkversion sowie eines Betriebssystems (Linux-Distribution oder Windows-Version) unterstützen.

## <a name="scenario-based-guidance"></a>Szenariobasierter Leitfaden

Das Ziel von Microsoft besteht darin, granulare und fokussierte .NET-Repositorys bereitzustellen, die ein bestimmtes Szenario oder eine bestimmte Workload darstellen.

Die `microsoft/aspnetcore`-Images sind für ASP.NET Core-Apps in Docker optimiert, sodass Container schneller gestartet werden können.

Die .NET Core-Images (`microsoft/dotnet`) sind für Konsolen-Apps konzipiert, die auf .NET Core basieren. Beispielsweise sollten Batchbewertungsprozesse, Azure WebJobs und andere Konsolenszenarien optimierte .NET Core-Images verwenden.

Das naheliegendste horizontale Szenario für die Verwendung von Docker- und .NET-Anwendungen ist die Bereitstellung und das Hosting in der Produktion. Die Produktion stellt jedoch nur ein Szenario dar, und sie erweisen sich in anderen Szenarien gleichermaßen als nützlich. Diese Szenarien gelten nicht speziell für .NET, sollten jedoch auf die meisten Entwicklerplattformen anwendbar sein.

* **Reibungslose Installation** – Sie können .NET ohne lokale Installation testen. Laden Sie einfach ein Docker-Image mit .NET herunter.

* **Entwicklung in einem Container** – Sie können Entwicklungsarbeiten in einer konsistenten Umgebung durchführen, bei der Entwicklungs- und Produktionsumgebungen ähnlich sind (so werden Probleme wie globale Zustände auf Entwicklungscomputern vermieden). Mit Visual Studio-Tools für Docker können Sie sogar einen Container direkt über Visual Studio starten.

* **Testen in einem Container** – Sie können in einem Container Tests durchführen, wodurch Ausfälle aufgrund von falsch konfigurierten Umgebungen oder sonstigen Änderungen, die durch den letzten Test verursacht wurden, reduziert werden.

* **Erstellung in einem Container** – Sie können Codes in einem Container erstellen, ohne gemeinsam genutzte Buildcomputer für unterschiedliche Umgebungen ordnungsgemäß konfigurieren zu müssen, und stattdessen einen BYOC-Ansatz (Bring Your Own Container) implementieren.

* **Bereitstellung in sämtlichen Umgebungen** – Sie können ein Image in all Ihren Umgebungen bereitstellen. Durch diese Vorgehensweise werden Ausfälle aufgrund von Konfigurationsdifferenzen reduziert, wodurch sich in der Regel das Imageverhalten über externe Konfigurationen (z.B. injizierte Umgebungsvariablen) ändert.

Lesen Sie die [allgemeinen Leitfäden](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md), um eine Entscheidung zwischen .NET Core und dem .NET Framework für die Entwicklung von Docker-Containern zu treffen.

### <a name="common-docker-development-scenarios"></a>Allgemeine Docker-Entwicklungsszenarien

#### <a name="net-core"></a>.NET Core

**.NET Core-Ressourcen**

 Wählen Sie die .NET Core-Beispiele aus, die am besten zu den von Ihnen gewünschten Szenarien passen. Alle Beispielanweisungen beschreiben, wie Windows- oder Linux-Docker-Images von Windows-, Linux- oder macOS-Hosts als Zielimages festgelegt werden.

Die Beispiele basieren auf .NET Core 2.0. Sie verwenden ggf. [mehrstufige Builds](https://github.com/dotnet/announcements/issues/18) und [Multi-Arch-Tags](https://github.com/dotnet/announcements/issues/14) von Docker.

* [.NET Core-Images auf DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [Bereitstellen einer .NET Core-Anwendung in Docker](https://docs.docker.com/engine/examples/dotnetcore/)

* In diesem Beispiel zum .NET Core-Docker wird gezeigt, wie [Docker in Ihrem .NET Core-Entwicklungsprozess verwendet wird](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev). Das Beispiel funktioniert sowohl mit Linux- als auch mit Windows-Containern.

* In diesem Beispiel für .NET Core-Docker wird ein bewährtes Muster für die [Erstellung von Docker-Images für .NET Core-Apps für die Produktion](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod) vorgestellt. Das Beispiel funktioniert sowohl mit Linux- als auch mit Windows-Containern.

* Dieses [Beispiel für .NET Core-Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) stellt ein bewährtes Muster für die Erstellung von Docker-Images für [eigenständige .NET Core-Anwendungen](../deploying/index.md) vor. Diese werden für den kleinsten Produktionscontainer verwendet, wobei der Vorteil einer [gemeinsamen Nutzung von Basisimages zwischen Containern](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/) hier entfällt. Es können jedoch auch niedrigere Docker-Ebenen gemeinsam genutzt werden.

#### <a name="arm32--raspberry-pi"></a>ARM32/Raspberry Pi

* [Ankündigung zu .NET Core Runtime ARM32-Builds](https://github.com/dotnet/announcements/issues/29)

* [ARM32/Raspberry Pi-.NET Core-Images auf DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [Beispiele für ARM32/Raspberry Pi-.NET Core-Docker auf GitHub](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a>.NET Framework

* [.NET Framework-Images auf DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/)

Dieses Repository enthält Beispiele, die verschiedene .NET Framework-Docker-Konfigurationen zeigen. Sie können diese Images als Grundlage für Ihre eigenen Docker-Images verwenden.

**.NET Framework 4.7**

Das [Beispiel für dotnet-framework:4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) zeigt die grundsätzliche „Hallo Welt“-Nutzung von [.NET Framework 4.7](../../framework/whats-new/index.md#v47). Es zeigt, wie Sie die App auf Grundlage des [.NET Framework 4.7-Docker-Images](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.7/Dockerfile) erstellen und bereitstellen können.

**.NET Framework 4.6.2**

Das [Beispiel für dotnet-framework:4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) zeigt die grundsätzliche „Hello World“-Nutzung von [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462). Es zeigt, wie Sie die App auf Grundlage des [.NET Framework 4.6.2-Docker-Images](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.6.2/Dockerfile) erstellen und bereitstellen können.

**.NET Framework 3.5**

 Das [Beispiel für dotnet-framework:3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) zeigt die grundsätzliche „Hello World“-Nutzung von [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-3.5/dotnetapp-3.5/Dockerfile). Es zeigt, wie Sie die App auf Grundlage des .NET Framework 3.5-Docker-Images erstellen und bereitstellen können.

#### <a name="aspnet-core"></a>ASP.NET Core

* Dieses [Beispiel zum ASP.NET Core-Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) stellt ein bewährtes Muster für die Erstellung von Docker-Images für ASP.NET Core-Apps für die Produktion vor. Das Beispiel funktioniert sowohl mit Linux- als auch mit Windows-Containern.

* [ASP.NET Core-Images auf DockerHub](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [ASP.NET Core-Images auf GitHub](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a>ASP.NET Framework

* [ASP.NET Framework-Images auf DockerHub](https://hub.docker.com/r/microsoft/aspnet/)

* [Beispiel für eine ASP.NET Web Forms-App basierend auf .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a>Windows Communication Framework (WCF)

* [Windows Communication Framework-Images (WCF) auf DockerHub](https://hub.docker.com/r/microsoft/wcf/)

* [Windows Communication Framework-Images (WCF) auf GitHub](https://github.com/microsoft/wcf-docker)

* [Beispiele für Windows Communication Framework-Docker (WCF) mit dem vollständigen .NET Framework 4.6.2](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a>Internet Information Server (IIS)

* [Internet Information Server-Images (IIS) auf DockerHub](https://hub.docker.com/r/microsoft/iis/)

* [Internet Information Server-Images (IIS) auf GitHub](https://github.com/microsoft/iis-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a>Interaktion mit anderen Microsoft-Stack-Containerimages

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [Schnellstart zum Ausführen des Microsoft SQL Server für Linux 2017-Containerimages mit Docker](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [Microsoft SQL Server für Linux-Images auf DockerHub](https://hub.docker.com/r/microsoft/mssql-server-linux/)

* [Microsoft SQL Server Express Edition-Images für Windows-Container auf DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [Microsoft SQL Server Developer Edition-Images für Windows-Container auf DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a>Visual Studio Team Services-Agent (VSTS)

* [Visual Studio Team Services-Agent-Images (VSTS) auf DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/)

* [Visual Studio Team Services-Agent-Images (VSTS) auf GitHub](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>Operations Management Suite-Linux-Agent (OMS)

* [Operations Management Suite-Linux-Agent (OMS) – Übersicht](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md)

* [Operations Management Suite-Images (OMS) auf DockerHub](https://hub.docker.com/r/microsoft/oms/)

* [Operations Management Suite-Images (OMS) auf GitHub](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Microsoft Azure-Befehlszeilenschnittstelle (CLI)

* [Microsoft Azure CLI-Images (Befehlszeilenschnittstelle) auf DockerHub](https://hub.docker.com/r/microsoft/azure-cli/) 

* [Microsoft Azure CLI-Images (Befehlszeilenschnittstelle) auf GitHub](https://github.com/Azure/azure-cli#Docker)

> [!NOTE]
> Wenn Sie kein Azure-Abonnement besitzen, [registrieren Sie sich noch heute für ein kostenloses 30-Tage-Konto](https://azure.microsoft.com/free/?b=16.48), und erhalten Sie ein Azure-Guthaben in Höhe von 200 US-Dollar, um eine beliebige Kombination von Azure-Diensten zu testen.

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Microsoft Azure Cosmos DB-Emulator (nur Windows-Container)

* [Microsoft Azure Cosmos DB-Emulatorimages auf DockerHub](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [Verwenden des Azure Cosmos DB-Emulators für lokale Entwicklungsarbeiten und Tests](/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>Erkunden des umfangreichen Docker-Entwicklungsökosystems

Nachdem Sie nun die Docker-Plattform und verschiedene Docker-Images kennengelernt haben, ist der nächste Schritt die Erkundung des umfangreichen Docker-Ökosystems. Über die folgenden Links erfahren Sie, wie die Microsoft-Tools die Containerentwicklung unterstützen.

* [Using .NET and Docker together (Gemeinsame Verwendung von .NET und Docker)](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/)
* [Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservices basieren](../../standard/microservices-architecture/multi-container-microservice-net-applications/index.md)
* [Visual Studio Code-Docker-Erweiterung](https://code.visualstudio.com/docs/languages/dockerfile)
* [Informationen zum Verwenden von Azure Service Fabric](/azure/service-fabric/index)
* [Service Fabric Getting Started Sample (Erste Schritte mit Service Fabric – Beispiel)](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [Vorteile von Windows-Containern](/virtualization/windowscontainers/about/index#video-overview)
* [Arbeiten mit Visual Studio-Tools für Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances (Bereitstellen von Docker-Images aus Azure Container Registry für Azure Container Instances)](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Debuggen mit Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)
* [Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud (Erste Schritte mit Visual Studio für Mac, Container und serverlose Code in der Cloud)](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Erste Schritte mit Docker und Visual Studio für Mac – Übung](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a>Nächste Schritte

* [Erlernen der Docker-Grundlagen mit .NET Core](docker-basics-dotnet-core.md)
* [Erstellen von .NET Core Docker-Images](building-net-docker-images.md)
