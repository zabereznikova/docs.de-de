---
title: Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 1c23acc16698446bc07c0047b68186e21c2ceb2d
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372850"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)

Um die Größe der in diesem e-Book zu beschränken, wurden zusätzliche technische Dokumentation und die vollständigen exemplarischen Vorgehensweisen in einem GitHub-Repository verfügbar. Die online Reihe von exemplarischen Vorgehensweisen, die in diesem Kapitel beschrieben werden behandelt, die für ein schrittweises Setup mehrere Umgebungen, die auf Windows-Containern und Bereitstellung in Azure basieren.

In den folgenden Abschnitten wird erläutert, was jeder exemplarischen Vorgehensweise ist über, ihre Ziele und den allgemeinen Vision und bietet ein Diagramm der Aufgaben, die beteiligt sind. Sie können die exemplarischen Vorgehensweisen selbst abrufen, in der *eShopModernizing* apps GitHub-Repository-Wiki auf [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).

## <a name="technical-walkthrough-list"></a>Liste der technischen exemplarischen Vorgehensweisen

Die folgenden Get-started exemplarischen Vorgehensweisen bieten konsistente und umfassende technische Anleitungen, die für die Beispiel-apps, die Sie können übertragen und verschieben mithilfe von Containern, und klicken Sie dann unter Verwendung von mehreren Bereitstellungsoptionen in Azure verschieben.

Jede der folgenden exemplarischen Vorgehensweisen verwendet die neue Beispiel eShopLegacy und eShopModernizing-apps, die auf GitHub zur Verfügung stehen [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).

- **Überblick über die Shopping-legacy-apps (Baseline-apps zur Modernisierung von)**

- **Packen Sie Ihre vorhandenen ASP.NET Web-apps (Web Forms und MVC) mit Windows-Containern in Container**

- **Packen Sie Ihre vorhandenen WCF-Dienste (N-Tier-apps) mit Windows-Containern in Container**

- **Bereitstellen Sie Ihrer Windows-Containern basierenden-app für Azure-VMs**

- **Bereitstellen Sie die Windows-Containern basierende apps in Kubernetes in Azure Container Service**

- **Bereitstellen Sie Windows-Containern basierenden apps in Azure Service Fabric**


## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Exemplarische Vorgehensweise 1: Überblick über Shopping-legacy-apps

### <a name="technical-walkthrough-availability"></a>Technische Anleitung Verfügbarkeit

Die vollständige technische Exemplarische Vorgehensweise ist im eShopModernizing GitHub Repo Wiki verfügbar:

[Exemplarische Vorgehensweisen eShopModernizing-wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki)


### <a name="overview"></a>Übersicht

In dieser exemplarischen Vorgehensweise können Sie die ursprüngliche Implementierung von drei ältere Beispielanwendungen untersuchen. Die ersten zwei Beispiel-Web-apps eine monolithische Architektur verfügen und mithilfe der klassischen ASP.NET erstellt wurden. Eine Anwendung basiert auf ASP.NET 4.x MVC; die zweite Anwendung basiert auf ASP.NET 4.x-Web Forms. Die dritte app ist eine 3-Tier-app, bestehend aus einer Windows Forms-Client-app und ein serverseitiges [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) Service.

Alle diese Anwendungen finden Sie unter den [eShopModernizing GitHub-Repository](https://github.com/dotnet-architecture/eShopModernizing).

### <a name="goals"></a>Ziele

Das Hauptziel der in dieser exemplarischen Vorgehensweise ist einfach, vertraut, dass mit diesen apps, und klicken Sie mit ihren Code und die Konfiguration zu. Sie können die apps, damit sie generieren und verwenden ohne Verwendung von SQL-Datenbank, zu Testzwecken simulierte Daten konfigurieren. Diese optionale Konfiguration basiert auf Abhängigkeitsinjektion, entkoppelt.

### <a name="scenario-1-aspnet-web-apps"></a>Szenario 1: ASP.NET Web-apps

Die folgende Abbildung zeigt das einfache Szenario die ursprünglichen älteren Webanwendungen in ASP.NET.

> ![Einfache Architektur Szenario der ursprünglichen legacy ASP.NET-Webanwendungen](./media/image5-1.png)
>

Aus einer geschäftsperspektive für die Domäne bieten beide apps den gleichen Katalog Verwaltungsfunktionen. Mitglieder des Teams Enterprise eShop werden mithilfe der app anzeigen und bearbeiten den Produktkatalog durchsuchen. 

Die folgende Abbildung zeigt die Screenshots der ersten app.

![ASP.NET MVC und ASP.NET Web Forms-Anwendungen (vorhandenen und ältere Technologien)](./media/image5-2.png)

Abhängigkeiten ASP.NET 4.x oder früheren Versionen (entweder für MVC oder Web Forms) bedeutet, dass diese Anwendungen in .NET Core ausgeführt wird nicht, es sei denn, der Code vollständig neu geschrieben wird, mithilfe von ASP.NET Core MVC. 

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>Szenario 2: WCF-Dienst und WinForms-Client-app (3-Tier-app)

Die folgende Abbildung zeigt das einfache Szenario die ursprünglichen ältere 3-Tier-Anwendung.

> ![Einfache Architektur Szenario der ursprünglichen legacy 3-Tier-app mit einem WCF-Dienst und einer WinForms-Client-app](./media/image5-1.5.png)
>

### <a name="benefits"></a>Vorteile

Die Vorteile der in dieser exemplarischen Vorgehensweise sind einfach: nur mit dem Code und die ersten apps vertraut machen.

### <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki:

  - [Tour auf der Basislinie ASP.NET MVC und "legacy" Web Forms-apps](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
  - [Tour auf die Baseline-WCF-Dienst und WinForms (3-Ebenen) "legacy"-app](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)


## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Exemplarische Vorgehensweise 2: Packen Ihrer vorhandenen .NET-Anwendungen verwenden können mit Windows-Containern in Container.

### <a name="overview"></a>Übersicht

Verwenden Sie Windows-Container, um die Bereitstellung von vorhandenen .NET-Anwendungen verwenden können, wie basierend auf MVC, Web Forms- oder WCF, zu der Produktion, Entwicklungs- und testumgebungen zu verbessern.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise werden Sie mehrere Optionen für das containerisieren einer vorhandenen .NET Framework-Anwendung anzuzeigen. Sie haben folgende Möglichkeiten:

- Packen Sie Ihre Anwendung in Container, mit [Visual Studio 2017-Tools für Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 oder höher).

- Packen Sie Ihre Anwendung in Container, manuell hinzufügen eine [dockerfile-Datei](https://docs.docker.com/engine/reference/builder/), und klicken Sie dann mit der [Docker-CLI](https://docs.docker.com/engine/reference/commandline/cli/).

- Packen Sie Ihre Anwendung in Container, mit der [Img2Docker](https://github.com/docker/communitytools-image2docker-win) Tools an (ein Open-Source-Tool von Docker).

In dieser exemplarischen Vorgehensweise liegt der Schwerpunkt auf Visual Studio 2017-Tools für Docker-Ansatz, aber die anderen beiden Ansätze sind ziemlich ähnlich hinsichtlich der dockerfile-Dateien verwenden.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>Szenario 1: Containerbasierte ASP.NET Web-apps

Die folgende Abbildung zeigt das Szenario für Container eShop ältere apps Webanwendungen.

> ![Vereinfachte Architekturdiagramm von containeranwendungen auf ASP.NET in einer Entwicklungsumgebung](./media/image5-3.png)
>


### <a name="scenario-2-containerized-wcf-service"></a>Szenario 2: Container-WCF-Dienst

Die folgende Abbildung zeigt das Szenario für eine 3-Tier-app mit WCF-Dienst in einem Container. 

> ![Architekturdiagramm eines WCF-Dienst in einer Entwicklungsumgebung in Containern vereinfacht](./media/image5-3.5.png)
>

### <a name="benefits"></a>Vorteile

Es gibt Vorteile zum Ausführen der monolithischen Anwendung in einem Container. Erstellen Sie zunächst ein Image für die Anwendung. Ab diesem Punkt führt jede Bereitstellung in der gleichen Umgebung. Alle Container verwendet die gleiche Version des Betriebssystems, hat die gleiche Version von Abhängigkeiten installiert, verwendet die gleiche Version von .NET Framework und wird unter Verwendung des gleichen Prozesses erstellt. Im Grunde genommen, steuern Sie die Abhängigkeiten Ihrer Anwendung mithilfe eines Docker-Images. Die Abhängigkeiten mit der Anwendung übertragen werden, wenn Sie die Container bereitstellen.

Ein weiterer Vorteil ist, dass Entwickler die Anwendung in den konsistenten Umgebung ausführen können, die von Windows-Containern bereitgestellt wird. Probleme, die nur in bestimmten Versionen angezeigt werden können sofort in einer Staging- oder produktionsumgebung Umgebung behebt, anstatt entdeckt werden. Unterschiede in entwicklungsumgebungen verwendet, die von Mitgliedern des Entwicklungsteams sind weniger wichtig, wenn Anwendungen in Containern ausgeführt werden.

Containerbasierte Anwendungen müssen auch eine flachere horizontale skalierungskurve. Container-apps können Sie mehrere Anwendungs- und Dienstinstanzen, die (auf der Grundlage der Container) verfügen, in einem virtuellen Computer oder physischen Computer, die im Vergleich zu regulären anwendungsbereitstellungen pro Computer. Dies führt zu höhere Dichte und weniger erforderliche Ressourcen, insbesondere wenn Sie orchestratoren wie Kubernetes oder Service Fabric verwenden.

Containerisierung, im Idealfall erfordert keine Änderungen an den Anwendungscode (C\#). In den meisten Fällen benötigen Sie nur die Docker-Bereitstellung-Metadatendateien (dockerfile-Dateien und Docker Compose-Dateien).

### <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki:

  - [Packen Sie die .NET Framework-Web-apps mit Windows-Containern und Docker in Container](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
  - [Hinzufügen von Docker-Unterstützung für einen WCF-Dienst](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)



## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Exemplarische Vorgehensweise 3: Bereitstellen Sie Ihrer Windows-Container-basierten app in Azure-VMs

### <a name="technical-walkthrough-availability"></a>Technische Anleitung Verfügbarkeit

Die vollständige technische Exemplarische Vorgehensweise ist im eShopModernizing GitHub Repo Wiki verfügbar: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>Übersicht

Bereitstellung in einem Docker-Host auf einem Windows Server 2016 Virtual Machine (VM) in Azure können Sie schnell Entwicklungs-/Test-/stagingphase Umgebungen einrichten. Außerdem erhalten Sie einen allgemeinen Speicherort für Tester oder Benutzer in Unternehmen, um die app zu überprüfen. Virtuelle Computer können auch gültige Infrastuktur als eine produktionsumgebungen Service (IaaS) sein.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise ist die mehrere alternativen beschrieben, die Ihnen beim Bereitstellen von Windows-Container für Azure-VMs, die auf Windows Server 2016 oder höher basieren.

### <a name="scenarios"></a>Szenarien

In dieser exemplarischen Vorgehensweise werden verschiedene Szenarien behandelt.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Szenario A:-Bereitstellung in einer Azure-VM aus ein Entwickler-PC über Docker-Engine-Verbindung

![Bereitstellen Sie in einer Azure-VM aus ein Entwickler-PCs über eine Docker-Engine-Verbindung](./media/image5-4.png)

> **Abbildung 5-4.** Bereitstellen Sie in einer Azure-VM aus ein Entwickler-PCs über eine Docker-Engine-Verbindung

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Szenario B: Bereitstellen Sie für eine Azure-VM über eine Docker-Registrierung

![Bereitstellen Sie in einer Azure-VM über eine Docker-Registrierung](./media/image5-5.png)

> **Abbildung 5-5.** Bereitstellen Sie in einer Azure-VM über eine Docker-Registrierung

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>Szenario "c:" Bereitstellen in einer Azure-VM über CI/CD-Pipelines in Azure DevOps-Dienste

![Bereitstellen Sie in einer Azure-VM über CI/CD-Pipelines in Azure DevOps-Dienste](./media/image5-6.png)

> **Abbildung 5-6.** Bereitstellen Sie in einer Azure-VM über CI/CD-Pipelines in Azure DevOps-Dienste

### <a name="azure-vms-for-windows-containers"></a>Azure-VMs für Windows-Container

Azure-VMs für die Windows-Container werden VMs basierend auf Windows Server 2016, Windows 10 oder höher, mit der Docker-Engine einrichten. In den meisten Fällen wird die Windows Server 2016 in die Azure-VMs verwendet.

Azure bietet derzeit einen virtuellen Computer namens **Windows Server 2016 mit Containern**. Dieser virtuelle Computer können Sie um das neue Windows Server-Container-Feature, mit Windows Server Core oder Windows Nano Server zu testen. Containerbetriebssystem-Images werden installiert, und klicken Sie dann die VM mit Docker verwendet wird.

### <a name="benefits"></a>Vorteile

Obwohl Windows-Container bei der Bereitstellung in Azure zu lokalen Windows Server 2016-VMs bereitgestellt werden können, erhalten Sie eine einfachere Möglichkeit, sofort zu verwendende Windows Server-Container-VMs Einstieg. Sie können auch eine allgemeine Onlinespeicherort, die für Tester und automatische Skalierbarkeit durch Azure VM Scale Sets-Instanzen zugänglich ist.

### <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Exemplarische Vorgehensweise 4: Bereitstellen Sie Ihrer Windows-Containern basierende apps in Azure Container Instances (ACI)

### <a name="technical-walkthrough-availability"></a>Technische Anleitung Verfügbarkeit

Die vollständige technische Exemplarische Vorgehensweise ist im eShopModernizing GitHub Repo Wiki verfügbar:

[Bereitstellen der Apps für ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>Übersicht

[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) ist die schnellste Möglichkeit, eine Container-Dev/Test/Staging-Umgebung verfügen, in dem Sie einzelne Instanzen von Containern bereitstellen können.

### <a name="goals"></a>Ziele

In dieser exemplarischen Vorgehensweise erfahren Sie die wichtigsten Szenarien, bei der Bereitstellung von Windows-Container für Azure Container Instances (ACI) und wie Sie in ACI eShopModernizing Apps bereitstellen können.

### <a name="scenarios"></a>Szenarien

Unterschiede können zum Bereitstellen von apps eShopModernizing in ACI z. B. nur eine oder alle apps (MVC-app, WebForms-app oder WCF-Dienst) bereitstellen vorhanden sein. Im folgenden Szenario unten sehen Sie die ASP.NET MVC-app sowie SQL Server-Container, die beide bereitgestellt als Container in ACI (Azure Container Instances).

![Bereitstellung für ACI aus einer Entwicklungsumgebung](./media/image5-3.5.6.png)

### <a name="benefits"></a>Vorteile

Mit Azure Container Instances erleichtert das Erstellen und Verwalten von Docker-Containern in Azure, ohne dass virtuelle Computer bereitstellen oder einen übergeordneten Dienst einführen müssen. Mit ACI können Sie direkt bereitstellen einen Windows-Container in Azure und machen es über einen vollständig qualifizierten Domänennamen (FQDN) im Internet in wenigen Sekunden (vorausgesetzt, dass Sie das Windows-Container-Image bereit in einer Docker-Registrierung, wie Docker Hub oder Azure Container verfügen Die Registrierung).

### <a name="considerations"></a>Weitere Überlegungen

Bereitstellen von Windows-Containern mit entweder vollständige .NET Framework / ASP.NET oder SQL Server in Azure Container Instances (ACI) ist nicht ganz so schnell wie die Bereitstellung auf eine reguläre Docker-Host (z. B. Windows Server 2016 mit Containern für Windows), da das Docker-Image muss herunterladen (Pull aus der Docker-Registrierung) jedes Mal, und die Größe der SQL-Container-Abbild (15.1 GB) und das containerimage für ASP.NET (13.9 GB) sind sehr groß ist, jedoch sehr viel kostengünstiger als die Beibehaltung von Ihren eigenen Docker-Host (dauerhaft Online ist WindowsServer 2016 mit Windows-Container-VM in Azure) ganz zu schweigen davon eine gesamte Orchestrator wie Kubernetes in Azure (AKS/ACS) oder Azure Service Fabric, die auf der anderen Seite das sind gute Optionen für Bereitstellungen in der Produktion.

Als wichtigsten Schlussfolgerung: ist mit Azure Container Instances eine sehr bestechende Option für Entwicklungs-/Testszenarios vorgesehen und für CI/CD-Pipelines aus.

## <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki: 

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)


## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Exemplarische Vorgehensweise 5: Bereitstellen Sie Ihrer Windows-Containern basierende apps in Kubernetes in Azure Container Service

### <a name="technical-walkthrough-availability"></a>Technische Anleitung Verfügbarkeit

Die vollständige technische Exemplarische Vorgehensweise ist im eShopModernizing GitHub Repo Wiki verfügbar:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a>Übersicht

Eine Anwendung, die basierend auf Windows-Container müssen schnell Plattformen Umzug entfernt noch einen Schritt weiter von IaaS-VMs verwenden. Dies ist erforderlich, um hohe Skalierbarkeit nur schwer erzielen besser automatisierte Skalierbarkeit und für eine erhebliche Verbesserung in automatisierten Bereitstellungen und der versionsverwaltung. Sie können diese Ziele erreichen, indem Sie mit der Orchestrator [Kubernetes](https://kubernetes.io/), in der verfügbaren [Azure Container Services](https://azure.microsoft.com/services/container-service/).

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise erfahren, wie zum Bereitstellen einer Windows-Container-basierte Anwendung in Kubernetes ist (so genannte *K8s*) in Azure Container Service. Bereitstellen in Kubernetes von Grund auf neu ist ein zweistufiger Prozess:

1.  Bereitstellen eines Kubernetes-Clusters in Azure Container Service.

2.  Stellen Sie die Anwendung und die zugehörigen Ressourcen mit dem Kubernetes-Cluster bereit.

### <a name="scenarios"></a>Szenarien

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Szenario A: direkt in einem Kubernetes-Cluster aus einer Entwicklungsumgebung bereitstellen

![Direkt in einem Kubernetes-Cluster bereitgestellt wird, aus einer Entwicklungsumgebung](./media/image5-7.png)

> **Abbildung 5-7.** Direkt in einem Kubernetes-Cluster bereitgestellt wird, aus einer Entwicklungsumgebung

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Szenario B: in einem Kubernetes-Cluster bereitstellen, von CI/CD-pipelines in Azure DevOps-Dienste

![Bereitstellen Sie in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps-Dienste](./media/image5-8.png)

> **Abbildung 5-8.** Bereitstellen Sie in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps-Dienste

### <a name="benefits"></a>Vorteile

Es gibt viele Vorteile, die in einem Kubernetes-Cluster bereitstellen. Der größte Vorteil ist, dass Sie eine produktionsbereiten Umgebung erhalten, in der Sie die Anwendung basierend auf der Anzahl von containerinstanzen, die Sie (Inner-Skalierbarkeit in den vorhandenen Knoten) verwenden möchten, die und basierend auf der Anzahl von Knoten oder virtuellen Computern in den Cluster (horizontal skalieren können Globale Skalierbarkeit des Clusters).

Azure Container Service optimiert die beliebte Open-Source-Tools und Technologien, speziell für Azure. Sie erhalten eine offene Lösung, die Portabilität für Ihre Container sowohl für die Anwendungskonfiguration bietet. Wählen Sie die Größe, die Anzahl der Hosts, und der Orchestrator-Tools-Container Service übernimmt den Rest.

Mit Kubernetes können Entwickler Gedanken über physische und virtuelle Computer, Status, zum Planen einer Container ausgerichtete Infrastruktur, die die folgenden Funktionen, unter anderem ermöglicht:

- Auf mehreren Containern basierenden Anwendungen

- Replizieren von Container Instances und automatische horizontale Skalierung

- Benennen und zu ermitteln (z. B. interne DNS)

- Lädt Lastenausgleich

- Parallele updates

- Verteilen von Geheimnissen

- Integritätsprüfungen für Anwendung

## <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>Exemplarische Vorgehensweise 6: Bereitstellen Sie Ihrer Windows-Containern basierende apps in Azure Service Fabric

### <a name="technical-walkthrough-availability"></a>Technische Anleitung Verfügbarkeit

Die vollständige technische Exemplarische Vorgehensweise ist im eShopModernizing GitHub Repo Wiki verfügbar:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>Übersicht

Eine Anwendung schnell auf Windows-Containern basierenden muss Plattformen Umzug entfernt noch einen Schritt weiter von IaaS-VMs verwenden. Dies ist erforderlich, um hohe Skalierbarkeit nur schwer erzielen besser automatisierte Skalierbarkeit und für eine erhebliche Verbesserung in automatisierten Bereitstellungen und der versionsverwaltung. Sie können diese Ziele erreichen, mit der Orchestrator-Azure Service Fabric, die in der Azure-Cloud verfügbar, aber auch lokalen Verwendung verfügbar ist, oder sogar in eine andere öffentlichen Cloud.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise ist, wie Sie eine Windows-Container-basierte Anwendung auf einem Service Fabric-Cluster in Azure bereitzustellen. In Service Fabric bereitstellen, von Grund auf neu ist ein zweistufiger Prozess:

1.  Bereitstellen von Service Fabric-Cluster in Azure (oder zu einer anderen Umgebung).

2.  Stellen Sie die Anwendung und die zugehörigen Ressourcen mit dem Service Fabric-Cluster bereit.

### <a name="scenarios"></a>Szenarien

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>Szenario A: direkt in Service Fabric-Cluster aus einer Entwicklungsumgebung bereitstellen

![Direkt in Service Fabric-Cluster bereitgestellt wird, aus einer Entwicklungsumgebung](./media/image5-9.png)

> **Abbildung 5-9.** Direkt in Service Fabric-Cluster bereitgestellt wird, aus einer Entwicklungsumgebung

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Szenario B: in einem Service Fabric-Cluster bereitstellen, von CI/CD-pipelines in Azure DevOps-Dienste

![Bereitstellen Sie in Service Fabric-Cluster über CI/CD-Pipelines in Azure DevOps-Dienste](./media/image5-10.png)

> **Abbildung 5-10.** Bereitstellen Sie in Service Fabric-Cluster über CI/CD-Pipelines in Azure DevOps-Dienste

## <a name="benefits"></a>Vorteile

Die Vorteile einer Bereitstellung in einem Service Fabric-Cluster sind die Vorteile der Verwendung von Kubernetes mit. Ein Unterschied, allerdings besteht darin, dass Service Fabric ist eine ausgereiftere produktionsumgebung für Windows-Anwendungen, die im Vergleich zu Kubernetes in der eine Betaphase für Windows-Container in Kubernetes-Version 1.9 (Dezember 2017). Kubernetes ist eine ausgereiftere Umgebung für Linux.

Der Hauptvorteil der Verwendung von Azure Service Fabric ist, erhalten Sie in der Sie die Anwendung basierend auf der Anzahl von containerinstanzen, die Sie (Inner-Skalierbarkeit in den vorhandenen Knoten) verwenden möchten, die und basierend auf der Anzahl der, horizontal skalieren können eine produktionsbereiten Umgebung Knoten oder virtuellen Computern im Cluster (globale Skalierbarkeit des Clusters).

Azure Service Fabric bietet die Portabilität für Ihre Container sowohl für die Anwendungskonfiguration. Sie können ein Service Fabric-cluster in Azure, oder installieren Sie sie lokal in Ihrem eigenen Datencenter verwenden. Sie können Service Fabric-Cluster in einer anderen Cloud auch wie installieren [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).

Bei Service Fabric können Entwickler Gedanken über physische und virtuelle Computer fortgesetzt, zum Planen einer Container ausgerichtete Infrastruktur, die die folgenden Funktionen, unter anderem ermöglicht:

- Auf mehreren Containern basierenden Anwendungen.

- Replizieren von Container Instances und automatische horizontale Skalierung.

- Benennen und ermitteln (z. B. interne DNS).

- Ausgleichen von lädt.

- Parallele Updates an.

- Verteilen von Geheimnissen aus.

- Integrität der Anwendung überprüft.

Die folgenden Funktionen sind exklusiv in Service Fabric (im Vergleich zu anderen orchestratoren):

- Zustandsbehaftete Dienste die Möglichkeit, über das Reliable Services-Anwendungsmodell.

- Actors-Muster, über das Reliable Actors-Anwendungsmodell.

- Bereitstellen von bare-Knochenarbeit Prozesse, zusätzlich zu Windows oder Linux-Container.

- Erweiterte Rollierende Updates und integritätsprüfungen beobachtet werden.

### <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
[Zurück](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Weiter](conclusions.md)
