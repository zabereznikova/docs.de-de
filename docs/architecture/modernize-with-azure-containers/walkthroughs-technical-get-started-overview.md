---
title: Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)
ms.date: 04/28/2018
ms.openlocfilehash: 190b33c4307b09bab0543d481e66ac9328074a0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69660881"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)

Um die Größe dieses e-Books zu begrenzen, wurden zusätzliche technische Dokumentation und die vollständigen exemplarischen Vorgehensweisen in einem GitHub-Repository zur Verfügung gestellt. In der Onlineserie der exemplarischen Vorgehensweisen, die in diesem Kapitel beschrieben werden, wird schrittweise Einrichtung der verschiedenen Umgebungen behandelt, die auf Windows-Containern basieren, sowie die Bereitstellung in Azure.

In den folgenden Abschnitten wird erläutert, worum es sich bei jeder exemplarischen Vorgehensweise handelt, ihre Ziele und die allgemeine Vision, und es wird ein Diagramm der beteiligten Aufgaben bereitstellt. Die exemplarischen Vorgehensweisen selbst können Sie im GitHub-Repository-Wiki mit den *eShopModernizing*-Apps unter <https://github.com/dotnet-architecture/eShopModernizing/wiki> herunterladen.

## <a name="technical-walkthrough-list"></a>Liste der technischen exemplarischen Vorgehensweisen

In den folgenden exemplarischen Vorgehensweisen für die ersten Schritte finden Sie konsistente und umfassende technische Anleitungen für Beispiel-Apps, die Sie mithilfe von Containern übertragen und verschieben und dann mithilfe mehrerer Bereitstellungsoptionen in Azure verschieben können.

In jeder der folgenden exemplarischen Vorgehensweisen werden die neuen Beispiel-Apps „eShopLegacy“ und „eShopModernizing“ verwendet, die auf GitHub unter <https://github.com/dotnet-architecture/eShopModernizing> verfügbar sind.

- **Tour durch die eShop-Legacy-Apps (zu modernisierende Baseline-Apps)**

- **Containerisieren Ihrer vorhandenen ASP.NET-Web-Apps (WebForms & MVC) mit Windows-Containern**

- **Containerisieren Ihrer vorhandenen WCF-Dienste (N-schichtige Apps) mit Windows-Containern**

- **Bereitstellen Ihrer Windows-Containerbasierten App auf virtuellen Azure-Computern**

- **Bereitstellen Ihrer Windows-Containerbasierten Apps in Kubernetes in Azure Container Service**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Exemplarische Vorgehensweise 1: Tour durch die eShop-Legacy-Apps

### <a name="technical-walkthrough-availability"></a>Verfügbarkeit der technischen exemplarischen Vorgehensweise

Die vollständige technische exemplarische Vorgehensweise finden Sie im GitHub-Repository-Wiki für eShopModernizing:

[Exemplarische Vorgehensweisen im eShopModernizing-Wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a>Übersicht

In dieser exemplarischen Vorgehensweise können Sie die anfängliche Implementierung von drei Legacy-Beispielanwendungen untersuchen. Die ersten beiden Beispiel-Web-Apps verfügen über eine monolithische Architektur und wurden mit klassischem ASP.NET erstellt. Eine Anwendung basiert auf ASP.NET 4. x MVC, die zweite Anwendung basiert auf ASP.NET 4. x Web Forms.
Die dritte App ist eine 3-schichtige APP, die sich aus einer WinForms-Client-App und einem serverseitigen [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md)-Dienst zusammensetzt.

Alle diese Anwendungen sind im [eShopModernizing-GitHub-Repository](https://github.com/dotnet-architecture/eShopModernizing) verfügbar.

### <a name="goals"></a>Ziele

Das Hauptziel dieser exemplarischen Vorgehensweise besteht darin, sich mit diesen Apps sowie Ihrem Code und ihrer Konfiguration vertraut zu machen. Sie können die Apps so konfigurieren, dass sie zu Testzwecken Pseudodaten generieren und verwenden, ohne die SQL-Datenbank zu verwenden. Diese optionale Konfiguration basiert auf einer Abhängigkeitsinjektion in entkoppelter Weise.

### <a name="scenario-1-aspnet-web-apps"></a>Szenario 1: ASP.NET-Web-Apps

Die folgende Abbildung zeigt das einfache Szenario der ursprünglichen ASP.NET-Legacy-Webanwendungen.

![Einfaches Architekturszenario der ursprünglichen ASP.NET-Legacy-Webanwendungen](./media/image5-1.png)

Aus der geschäftlichen Sicht bieten beide Apps dieselben Katalogverwaltungsfunktionen. Mitglieder des eShop-Unternehmensteams würden die App verwenden, um den Produktkatalog anzuzeigen und zu bearbeiten.

Die nächste Abbildung zeigt die ersten App-Screenshots.

![ASP.NET MVC- und ASP.NET Web Forms-Anwendungen (vorhandene/Legacy-Technologien)](./media/image5-2.png)

Abhängigkeiten in ASP.NET 4. x oder früheren Versionen (entweder für MVC oder für Web Forms) bedeuten, dass diese Anwendungen nur unter .NET Core ausgeführt werden können, wenn der Code vollständig mit ASP.NET Core MVC umgeschrieben wird.

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>Szenario 2: WCF-Dienst und WinForms-Client-App (3-schichtige App)

Die folgende Abbildung zeigt das einfache Szenario der ursprünglichen 3-schichtigen Legacy-Anwendung.

![Einfaches Architekturszenario der ursprünglichen 3-schichtigen Legacy-App mit einem WCF-Dienst und einer WinForms-Client-App](./media/image5-1.5.png)

### <a name="benefits"></a>Vorteile

Die Vorteile dieser exemplarischen Vorgehensweise sind einfach: Sie machen sich mit dem Code und den ersten Apps vertraut.

### <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-Wiki:

- [Tour durch die Baseline-Legacy-Apps von ASP.NET MVC und Web Forms](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [Tour durch die Baseline-Legacy-Apps von WCF-Dienst- und WinForms (3-schichtig)](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Exemplarische Vorgehensweise 2: Containerisieren Ihrer vorhandenen .NET-Anwendungen mit Windows-Containern

### <a name="overview"></a>Übersicht

Verwenden Sie Windows-Container, um die Bereitstellung vorhandener .NET-Anwendungen, wie z. B. der auf MVC, Web Forms oder WCF basierenden, in Produktions-, Entwicklungs- und Testumgebungen zu verbessern.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise besteht darin, Ihnen mehrere Optionen für das Containerisieren einer vorhandenen .NET Framework-Anwendung zu zeigen. Sie haben folgende Möglichkeiten:

- Containerisieren Ihrer Anwendung mithilfe der [Visual Studio 2017-Tools für Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 oder höhere Versionen).

- Containerisieren Ihrer Anwendung durch manuelles Hinzufügen einer [Dockerfile](https://docs.docker.com/engine/reference/builder/) und anschließende Verwendung der [Docker-CLI](https://docs.docker.com/engine/reference/commandline/cli/).

- Containerisieren Ihrer Anwendung mithilfe des [Img2Docker](https://github.com/docker/communitytools-image2docker-win)-Tools (einem Open-Source-Tool von Docker).

Diese exemplarische Vorgehensweise konzentriert sich auf den Ansatz mit den Visual Studio 2017-Tools für Docker, doch die anderen beiden Ansätze sind hinsichtlich der Verwendung von Dockerfiles ziemlich ähnlich.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>Szenario 1: Containerisierte ASP.NET-Web-Apps

In der folgenden Abbildung ist das Szenario für containerisierte eShop-Legacy-Web-Apps dargestellt.

![Vereinfachtes Architekturdiagramm der containerisierten ASP.NET-Anwendungen in einer Entwicklungsumgebung](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a>Szenario 2: Containerisierter WCF-Dienst

In der folgenden Abbildung ist das Szenario für eine 3-schichtige App mit einem containerisierten WCF-Dienst dargestellt.

![Vereinfachtes Architekturdiagramm des containerisierten WCF-Diensts in einer Entwicklungsumgebung](./media/image5-3.5.png)

### <a name="benefits"></a>Vorteile

Es gibt Vorteile bei der Ausführung Ihrer monolithischen Anwendung in einem Container. Zunächst erstellen Sie ein Image für die Anwendung. Ab diesem Punkt wird jede Bereitstellung in derselben Umgebung ausgeführt. Auf jedem Container wird die gleiche Version des Betriebssystems verwendet, sind dieselben Abhängigkeiten installiert und wird dieselbe Version des .NET Frameworks verwendet. Außerdem wird jeder Container mithilfe desselben Prozesses erstellt. Im Grunde steuern Sie die Abhängigkeiten Ihrer Anwendung mithilfe eines Docker-Images. Die Abhängigkeiten begleiten die Anwendung, wenn Sie die Container bereitstellen.

Ein zusätzlicher Vorteil besteht darin, dass Entwickler die Anwendung in der konsistenten Umgebung ausführen können, die von Windows-Containern bereitgestellt wird. Probleme, die nur in bestimmten Versionen auftreten, lassen sich sofort feststellen, statt in einer Staging- oder Produktionsumgebung aufzutauchen. Unterschiede zwischen den Entwicklungsumgebungen, die von Mitgliedern des Entwicklungsteams verwendet werden, sind von geringerer Bedeutung, wenn Anwendungen in Containern ausgeführt werden.

Zudem verfügen containerisierte Anwendungen über eine flachere horizontale Skalierungskurve. Containerisierte Apps ermöglichen es Ihnen, mehr Anwendungs- und Dienstinstanzen (basierend auf Containern) auf einem virtuellen oder physischen Computer zu haben, verglichen mit regulären Anwendungsbereitstellungen pro Computer. Daraus ergeben sich eine höhere Dichte und weniger erforderliche Ressourcen, insbesondere wenn Sie Orchestratoren wie Kubernetes verwenden.

Containerisierung erfordert im Idealfall keine Änderungen am Anwendungscode (C\#). In den meisten Szenarien benötigen Sie lediglich die Docker-Bereitstellungsmetadatendateien (Dockerfiles und Docker Compose Dateien).

### <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-Wiki:

- [Containerisieren der .NET Framework-Web-Apps mit Windows-Containern und Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [Hinzufügen von Docker-Unterstützung zu einem WCF-Dienst](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Exemplarische Vorgehensweise 3: Bereitstellen Ihrer Windows-Containerbasierten App auf virtuellen Azure-Computern

### <a name="technical-walkthrough-availability"></a>Verfügbarkeit der technischen exemplarischen Vorgehensweise

Die vollständige technische exemplarische Vorgehensweise finden Sie im GitHub-Repository-Wiki für eShopModernizing: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

### <a name="overview"></a>Übersicht

Durch die Bereitstellung auf einem Docker-Host auf einem virtuellen Windows Server 2016-Computer (VM) in Azure können Sie schnell Entwicklungs-/Test-/Stagingumgebungen einrichten. Es verschafft Ihnen außerdem einen allgemeinen Ort für Tester oder geschäftliche Benutzer, um die App zu validieren. VMs können auch gültige IaaS-Produktionsumgebungen (Infrastructure-as-a-Service) sein.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise besteht darin, Ihnen die verschiedenen Alternativen aufzuzeigen, die Sie bei der Bereitstellung von Windows-Containern auf virtuellen Azure-Computern haben, die auf Windows Server 2016 oder höheren Versionen basieren.

### <a name="scenarios"></a>Szenarien

Es werden mehrere Szenarien in dieser exemplarischen Vorgehensweise behandelt.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Szenario A: Bereitstellen auf einem virtuellen Azure-Computer von einem Entwickler-PC aus über die Docker-Engine-Verbindung

![Bereitstellen auf einem virtuellen Azure-Computer von einem Entwickler-PC aus über eine Docker-Engine-Verbindung](./media/image5-4.png)

**Abbildung 5-4.** Bereitstellen auf einem virtuellen Azure-Computer von einem Entwickler-PC aus über eine Docker-Engine-Verbindung

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Szenario B: Bereitstellen auf einem virtuellen Azure-Computer über eine Docker-Registrierung

![Bereitstellen auf einem virtuellen Azure-Computer über eine Docker-Registrierung](./media/image5-5.png)

**Abbildung 5-5.** Bereitstellen auf einem virtuellen Azure-Computer über eine Docker-Registrierung

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>Szenario C: Bereitstellen auf einem virtuellen Azure-Computer aus CI/CD-Pipelines in Azure DevOps Services

![Bereitstellen auf einem virtuellen Azure-Computer aus CI/CD-Pipelines in Azure DevOps Services](./media/image5-6.png)

**Abbildung 5-6.** Bereitstellen auf einem virtuellen Azure-Computer aus CI/CD-Pipelines in Azure DevOps Services

### <a name="azure-vms-for-windows-containers"></a>Azure-VMs für Windows-Container

Azure-VMs für Windows-Container sind virtuelle Computer, die auf Windows Server 2016, Windows 10 oder höheren Versionen basieren und auf denen die Docker-Engine eingerichtet ist. In den meisten Fällen wird Windows Server 2016 auf den Azure-VMs verwendet.

Azure stellt derzeit einen virtuellen Computer mit dem Namen **Windows Server 2016 mit Containern** bereit. Mit diesem virtuellen Computer können Sie die neue Windows Server-Containerfunktion mit Windows Server Core oder mit Windows Nano Server testen. Container-Betriebssystemimages werden installiert, woraufhin dann der virtuelle Computer für die Verwendung mit Docker bereit ist.

### <a name="benefits"></a>Vorteile

Obwohl Windows-Container auf lokalen Windows Server 2016-VMs bereitgestellt werden können, erhalten Sie bei der Bereitstellung in Azure eine einfachere Möglichkeit, um mit sofort einsatzbereiten Windows Server-Container-VMs zu beginnen. Sie erhalten außerdem einen gemeinsamen Onlinespeicherort, auf den Tester zugreifen können, sowie automatische Skalierbarkeit über Azure-VM-Skalierungsgruppen.

### <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-Wiki:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Exemplarische Vorgehensweise 4: Bereitstellen von Windows-Containerbasierten Apps in Azure Container Instances (ACI)

### <a name="technical-walkthrough-availability"></a>Verfügbarkeit der technischen exemplarischen Vorgehensweise

Die vollständige technische exemplarische Vorgehensweise finden Sie im GitHub-Repository-Wiki für eShopModernizing:

[Bereitstellen der Apps auf ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>Übersicht

[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) ist die schnellste Methode zum Einrichten einer Entwicklungs-/Test-/Stagingumgebung für Container, in der Sie einzelne Instanzen von Containern bereitstellen können.

### <a name="goals"></a>Ziele

Diese exemplarische Vorgehensweise zeigt Ihnen die wichtigsten Szenarien für die Bereitstellung von Windows-Containern in Azure Container Instances (ACI) und wie Sie eShopModernizing-Apps in ACI bereitstellen können.

### <a name="scenarios"></a>Szenarien

Es können Variationen bei der Bereitstellung der eShopModernizing-Apps in ACI auftreten, z. B. das Bereitstellen von nur einer oder allen Apps (MVC-App, WebForms-App oder WCF-Dienst). Im folgenden, unten dargestellten Szenario sehen Sie die ASP.NET MVC-App sowie den SQL Server-Container, die beide als Container in ACI (Azure Container Instances) bereitgestellt sind.

![Bereitstellen in ACI aus einer Entwicklungsumgebung](./media/image5-3.5.6.png)

### <a name="benefits"></a>Vorteile

Azure Container Instances erleichtert die Erstellung und Verwaltung von Docker-Containern in Azure, ohne dass Sie virtuelle Computer bereitstellen oder einen übergeordneten Dienst einführen müssen. Mit ACI können Sie einen Windows-Container direkt in Azure bereitstellen und im Internet mit einem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) innerhalb weniger Sekunden verfügbar machen (vorausgesetzt, dass das Windows-Containerimage in einer Docker-Registrierung wie Docker Hub oder Azure Container bereit steht).

### <a name="considerations"></a>Weitere Überlegungen

Das Bereitstellen von Windows-Containern mit vollständigem .NET Framework/ASP.NET oder SQL Server in Azure Container Instances (ACI) ist nicht ganz so schnell wie die Bereitstellung auf einem regulären Docker-Host (wie einem Windows Server 2016 mit Windows-Containern), da das Docker-Image jedes Mal heruntergeladen werden muss (aus der Docker-Registrierung abgerufen) und das SQL-Containerimage (15,1 GB) und das ASP.NET-Containerimage (13,9 GB) eine erhebliche Größen aufweisen. Es ist jedoch viel billiger, als Ihren eigenen Docker-Host zu unterhalten (Windows Server 2016 mit Windows-Container-VM in Azure, dauerhaft online), ganz zu schweigen von einem vollständigen Orchestrator wie Kubernetes in Azure (AKS), der andererseits eine gute Wahl für Produktionsbereitstellungen ist.

Als Hauptschluss ergibt sich hieraus, dass die Verwendung von Azure Container Instances eine sehr überzeugende Option für Entwicklungs-/Testszenarien und für CI/CD-Pipelines ist.

## <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-Wiki:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Exemplarische Vorgehensweise 5: Bereitstellen Ihrer Windows-Containerbasierten Apps in Kubernetes in Azure Container Service

### <a name="technical-walkthrough-availability"></a>Verfügbarkeit der technischen exemplarischen Vorgehensweise

Die vollständige technische exemplarische Vorgehensweise finden Sie im GitHub-Repository-Wiki für eShopModernizing:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a>Übersicht

Eine Anwendung, die auf Windows-Containern basiert, muss schnell Plattformen verwenden, wodurch sie sich noch weiter von virtuellen IaaS-Computern verlagert. Dies ist erforderlich, um auf einfache Weise eine hohe Skalierbarkeit und eine besser automatisierte Skalierbarkeit zu erreichen sowie eine bedeutende Verbesserung bei automatisierten Bereitstellungen und der Versionsverwaltung. Diese Ziele können Sie mithilfe des Orchestrators [Kubernetes](https://kubernetes.io/) erreichen, der in [Azure Container Services-](https://azure.microsoft.com/services/container-service/) verfügbar ist.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise ist, Ihnen zu zeigen, wie Sie eine Windows-Containerbasierte Anwendung in Kubernetes (auch als *K8s* bezeichnet) bereitstellen. Die Bereitstellung in Kubernetes von Grund auf ist ein zweistufiger Prozess:

1. Bereitstellen eines Kubernetes-Clusters in Azure Container Service.

2. Bereitstellen der Anwendung und zugehöriger Ressourcen im Kubernetes-Cluster.

### <a name="scenarios"></a>Szenarien

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Szenario A: Direktes Bereitstellen in einem Kubernetes-Cluster aus einer Entwicklungsumgebung

![Direktes Bereitstellen in einem Kubernetes-Cluster aus einer Entwicklungsumgebung](./media/image5-7.png)

**Abbildung 5-7.** Direktes Bereitstellen in einem Kubernetes-Cluster aus einer Entwicklungsumgebung

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Szenario B: Bereitstellen in einem Kubernetes-Cluster aus CI/CD-Pipelines in Azure DevOps Services

![Bereitstellen in einem Kubernetes-Cluster aus CI/CD-Pipelines in Azure DevOps Services](./media/image5-8.png)

**Abbildung 5-8.** Bereitstellen in einem Kubernetes-Cluster aus CI/CD-Pipelines in Azure DevOps Services

### <a name="benefits"></a>Vorteile

Die Bereitstellung in einem Cluster in Kubernetes kann viele Vorteile bieten. Der größte Vorteil besteht darin, dass Sie eine produktionsbereite Umgebung erhalten, in der Sie die Anwendung basierend auf der Anzahl der zu verwendenden Containerinstanzen (innere Skalierbarkeit in den vorhandenen Knoten) und basierend auf der Anzahl der Knoten oder VMs im Cluster (globale Skalierbarkeit des Clusters) horizontal hochskalieren können.

Azure Container Service optimiert beliebte Open Source-Tools und -Technologien speziell für Azure. Dadurch erhalten Sie eine offene Lösung, die die Portabilität Ihrer Container und Ihrer Anwendungskonfiguration garantiert. Erforderlich ist nur die Angabe der Größe, Anzahl der Hosts und Orchestratortools. Alles Weitere erledigt ACS.

Mit Kubernetes können Entwickler von Überlegungen zu physischen und virtuellen Computern zur Planung einer containerzentrierten Infrastruktur fortschreiten, die unter anderem die folgenden Funktionen ermöglicht:

- Anwendungen, die auf mehreren Containern basieren

- Replizieren von Containerinstanzen und automatische horizontale Skalierung

- Benennen und Ermitteln (z. B. internes DNS)

- Ausgleichen von Lasten

- Parallele Updates

- Verteilen von Geheimnissen

- Überprüfung der Anwendungsintegrität

## <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-Wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a>Exemplarische Vorgehensweise 6: Bereitstellen Ihrer Windows-Containerbasierten Apps in Azure App Service für Container

### <a name="technical-walkthrough-availability"></a>Verfügbarkeit der technischen exemplarischen Vorgehensweise

Die vollständige technische exemplarische Vorgehensweise finden Sie im GitHub-Repository-Wiki für eShopModernizing:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a>Übersicht

Eine einfache containerisierte Anwendung, die Windows-Container verwendet, lässt sich einfach in Azure App Service für Container bereitstellen. Dies ist die empfohlene Vorgehensweise für die meisten Windows-Containerbasierten Anwendungen.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise ist, Ihnen zu zeigen, wie Sie eine Windows-Containerbasierte Anwendung in Azure App Service für Container aus einer Registrierung (Docker Hub oder Azure Container Registry) bereitstellen.

### <a name="scenario"></a>Szenario

![Bereitstellen der Windows-Containerbasierten App in Azure App Service für Container](./media/image5-11.png)

### <a name="benefits"></a>Vorteile

Die Bereitstellung in Azure App Service für Container bietet die Vorteile von Containern in Kombination mit den PaaS-Vorteilen von Azure App Service. Der App-Dienst kann problemlos vertikal und horizontal skaliert werden und lässt sich für eine automatische Skalierung konfigurieren, um sich an geänderte Anforderungen anzupassen und diese zu erfüllen. Updates können ohne Ausfallzeiten ausgeführt werden, und die Konfiguration von Continuous Deployment aus einer Registrierung heraus lässt sich ebenfalls leicht konfigurieren.

## <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-Wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

> [!div class="step-by-step"]
> [Zurück](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [Weiter](conclusions.md) <!-- Next Chapter -->
