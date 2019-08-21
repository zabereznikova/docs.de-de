---
title: Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Exemplarische Vorgehensweisen und technische Übersicht über den Einstieg
ms.date: 04/28/2018
ms.openlocfilehash: 190b33c4307b09bab0543d481e66ac9328074a0d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660881"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)

Um die Größe dieses e-Books einzuschränken, wurden zusätzliche technische Dokumentation und die vollständigen exemplarischen Vorgehensweisen in einem GitHub-Repository zur Verfügung gestellt. In der Online Serie der exemplarischen Vorgehensweisen, die in diesem Kapitel beschrieben werden, wird erläutert, wie Sie die verschiedenen Umgebungen, die auf Windows-Containern basieren, und die Bereitstellung in Azure schrittweise einrichten.

In den folgenden Abschnitten wird erläutert, worum es sich bei jeder exemplarischen Vorgehensweise um die Ziele und die allgemeine Vision handelt, und es wird ein Diagramm der beteiligten Aufgaben bereitstellt. Die exemplarischen Vorgehensweisen können Sie auch im GitHub-Repository von *eshopmodernisierender* apps unter <https://github.com/dotnet-architecture/eShopModernizing/wiki>finden.

## <a name="technical-walkthrough-list"></a>Technische Exemplarische Vorgehensweise

In den folgenden exemplarischen Vorgehensweisen für die ersten Schritte finden Sie konsistente und umfassende technische Anleitungen für Beispiel-apps, die Sie mithilfe von Containern per Lift und Shift migrieren und dann mithilfe mehrerer Bereitstellungs Optionen in Azure verschieben können.

In jeder der folgenden exemplarischen Vorgehensweisen werden die neuen Sample eshoplegacy-und eshopmoderniup-Apps verwendet, die auf GitHub unter <https://github.com/dotnet-architecture/eShopModernizing>verfügbar sind.

- **Tour durch die Legacy-apps von eShop (Baseline-Apps für die Modernisierung)**

- **Containerisieren vorhandener ASP.net-Web-Apps (WebForms & MVC) mit Windows-Containern**

- **Containerisieren Ihrer vorhandenen WCF-Dienste (N-Tier-Apps) mit Windows-Containern**

- **Bereitstellen Ihrer Windows-Container-basierten App auf Azure-VMS**

- **Bereitstellen Ihrer Windows-Container-basierten apps in Kubernetes in Azure Container Service**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Exemplarische Vorgehensweise 1: Tour durch die Legacy-apps von eShop

### <a name="technical-walkthrough-availability"></a>Technische Exemplarische Vorgehensweise

Die vollständige technische Exemplarische Vorgehensweise finden Sie im wiki für das eshopmoderniup-GitHub-Repository:

[Exemplarische Vorgehensweisen für das eshopmodernisierende wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a>Übersicht

In dieser exemplarischen Vorgehensweise können Sie die anfängliche Implementierung von drei veralteten Beispielanwendungen untersuchen. Die ersten beiden Beispiel-Web-Apps verfügen über eine monolithische Architektur und wurden mit klassischem ASP.NET erstellt. Eine Anwendung basiert auf ASP.NET 4. x MVC; die zweite Anwendung basiert auf ASP.NET 4. x Web Forms.
Die dritte APP ist eine 3-Ebenen-APP, die sich aus einer WinForms-Client-App und einem serverseitigen [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) -Dienst zusammensetzt.

Alle diese Anwendungen sind im [eshopmodernisierenden GitHub](https://github.com/dotnet-architecture/eShopModernizing)-Repository verfügbar.

### <a name="goals"></a>Ziele

Das Hauptziel dieser exemplarischen Vorgehensweise besteht darin, sich mit diesen apps und Ihrem Code und ihrer Konfiguration vertraut zu machen. Sie können die apps so konfigurieren, dass Sie mockdaten generieren und verwenden, ohne die SQL-Datenbank zu Testzwecken zu verwenden. Diese optionale Konfiguration basiert auf einer entkoppelten Abhängigkeit von der Abhängigkeitsinjektion.

### <a name="scenario-1-aspnet-web-apps"></a>Szenario 1: ASP.net Web-Apps

Die folgende Abbildung zeigt das einfache Szenario der ursprünglichen ASP.NET-Webanwendungen.

![Einfaches Architektur Szenario der ursprünglichen Legacy ASP.NET Webanwendungen](./media/image5-1.png)

Aus Sicht der Geschäftsdomäne bieten beide apps die gleichen Katalog Verwaltungsfunktionen. Mitglieder des eShop Enterprise-Teams verwenden die APP zum Anzeigen und Bearbeiten des Produktkatalogs.

Die nächste Abbildung zeigt die ersten App-Screenshots.

![ASP.NET MVC-und ASP.net-Web Forms Anwendungen (vorhandene/ältere Technologien)](./media/image5-2.png)

Abhängigkeiten in ASP.NET 4. x oder früheren Versionen (entweder für MVC oder für Web Forms) bedeutet, dass diese Anwendungen nicht unter .net Core ausgeführt werden, es sei denn, der Code wird mit ASP.net Core MVC vollständig umgeschrieben.

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>Szenario 2: WCF-Dienst und WinForms-Client-app (3-Ebenen-APP)

Die folgende Abbildung zeigt das einfache Szenario der ursprünglichen 3-Ebenen-Legacy Anwendung.

![Einfaches Architektur Szenario der ursprünglichen veralteten 3-Ebenen-App mit einem WCF-Dienst und einer WinForms-Client-App](./media/image5-1.5.png)

### <a name="benefits"></a>Vorteile

Die Vorteile dieser exemplarischen Vorgehensweise sind einfach: Machen Sie sich mit dem Code und den ersten apps vertraut.

### <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:

- [Tour durch die Baseline ASP.NET MVC und Web Forms "Legacy"-Apps](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [Tour durch den WCF-Basis Dienst und die Windows-Legacy-app (3 Ebenen)](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Exemplarische Vorgehensweise 2: Containerisieren vorhandener .NET-Anwendungen mit Windows-Containern

### <a name="overview"></a>Übersicht

Verwenden Sie Windows-Container, um die Bereitstellung vorhandener .NET-Anwendungen, wie z. b. der auf MVC, Web Forms oder WCF, in Produktions-, Entwicklungs-und Testumgebungen zu verbessern.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise besteht darin, Ihnen mehrere Optionen für das containerialisieren einer vorhandenen .NET Framework Anwendung anzuzeigen. Sie haben folgende Möglichkeiten:

- Containerisieren Ihrer Anwendung mithilfe von [Visual Studio 2017-Tools für docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 oder höhere Versionen).

- Containerisieren Sie Ihre Anwendung, indem Sie manuell eine [dockerfile-Datei](https://docs.docker.com/engine/reference/builder/)hinzufügen und dann die [docker-CLI](https://docs.docker.com/engine/reference/commandline/cli/)verwenden.

- Containerisieren Sie Ihre Anwendung mithilfe des [Img2Docker](https://github.com/docker/communitytools-image2docker-win) -Tools (Open Source-Tool von Docker).

Diese exemplarische Vorgehensweise konzentriert sich auf den Visual Studio 2017-Tools für docker-Ansatz, aber die anderen beiden Ansätze sind hinsichtlich der Verwendung von dockerfiles ziemlich ähnlich.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>Szenario 1: Containerisiert ASP.net Web-Apps

In der folgenden Abbildung ist das Szenario für ältere Web-Apps-Anwendungen in einem Container im Container dargestellt.

![Vereinfachtes Architektur Diagramm von containerisierten ASP.NET-Anwendungen in einer Entwicklungsumgebung](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a>Szenario 2: Containerisierter WCF-Dienst

Die folgende Abbildung zeigt das Szenario für eine APP mit drei Ebenen und einem containerisierten WCF-Dienst.

![Vereinfachtes Architektur Diagramm des containerisierten WCF-Dienstanbieter in einer Entwicklungsumgebung](./media/image5-3.5.png)

### <a name="benefits"></a>Vorteile

Die Ausführung einer monolithischen Anwendung in einem Container hat einige Vorteile. Zuerst erstellen Sie ein Image für die Anwendung. Ab diesem Zeitpunkt wird jede Bereitstellung in derselben Umgebung ausgeführt. Jeder Container verwendet die gleiche Betriebssystemversion, die gleiche Version der Abhängigkeiten ist installiert, verwendet dieselbe .NET Framework-Version und wird mit demselben Prozess erstellt. Im Grunde steuern Sie die Abhängigkeiten Ihrer Anwendung mithilfe eines docker-Images. Die Abhängigkeiten werden bei der Bereitstellung der Container mit der Anwendung übertragen.

Ein zusätzlicher Vorteil besteht darin, dass Entwickler die Anwendung in der konsistenten Umgebung ausführen können, die von Windows-Containern bereitgestellt wird. Probleme, die nur mit bestimmten Versionen auftreten, können sofort erkannt werden, anstatt in einer Staging-oder Produktionsumgebung verfügbar zu sein. Unterschiede in Entwicklungsumgebungen, die von Mitgliedern des Entwicklungsteams verwendet werden, sind weniger wichtig, wenn Anwendungen in Containern ausgeführt werden.

Containerisierte Anwendungen verfügen auch über eine Flatter Scale-Out-Kurve. Container-apps ermöglichen es Ihnen, mehr Anwendungs-und Dienst Instanzen (basierend auf Containern) auf einem virtuellen Computer oder physischen Computer auf einem virtuellen Computer oder physischen Computer zu haben, verglichen mit regulären Anwendungs Bereitstellungen pro Computer. Dies bedeutet eine höhere Dichte und weniger erforderliche Ressourcen, insbesondere dann, wenn Sie orchestratoren wie Kubernetes verwenden.

Die Containerisierung erfordert in idealen Situationen keine Änderungen am Anwendungscode (C\#). In den meisten Szenarien benötigen Sie lediglich die Docker-bereitstellungsmetadatendateien (dockerfiles und docker Compose Dateien).

### <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:

- [Containerisieren der .NET Framework-Web-Apps mit Windows-Containern und docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [Docker-Unterstützung zu einem WCF-Dienst hinzufügen](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Exemplarische Vorgehensweise 3: Bereitstellen Ihrer Windows-Container-basierten App auf Azure-VMS

### <a name="technical-walkthrough-availability"></a>Technische Exemplarische Vorgehensweise

Die vollständige technische Exemplarische Vorgehensweise finden Sie im wiki für das eshopmoderniup-GitHub-Repository:<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

### <a name="overview"></a>Übersicht

Durch die Bereitstellung auf einem docker-Host auf einem virtuellen Windows Server 2016-Computer (Virtual Machine, VM) in Azure können Sie schnell Entwicklungs-/Test-/Stagingumgebungen einrichten. Außerdem gibt es einen allgemeinen Ort für Tester oder geschäftliche Benutzer, um die APP zu validieren. VMs können auch gültige IaaS-Produktionsumgebungen (Infrastructure-as-a-Service) sein.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise besteht darin, Ihnen die verschiedenen Alternativen aufzuzeigen, die Sie bei der Bereitstellung von Windows-Containern auf virtuellen Azure-Computern haben, die auf Windows Server 2016 oder höheren Versionen basieren.

### <a name="scenarios"></a>Szenarien

In dieser exemplarischen Vorgehensweise werden verschiedene Szenarien behandelt.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Szenario A: Bereitstellen auf einem virtuellen Azure-Computer über einen Entwickler über die Docker-Engine-Verbindung

![Bereitstellen auf einem virtuellen Azure-Computer über einen dev-PC über eine docker-Engine-Verbindung](./media/image5-4.png)

**Abbildung 5-4.** Bereitstellen auf einem virtuellen Azure-Computer über einen dev-PC über eine docker-Engine-Verbindung

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Szenario B: Bereitstellen für eine Azure-VM über eine docker-Registrierung

![Bereitstellen für eine Azure-VM über eine docker-Registrierung](./media/image5-5.png)

**Abbildung 5-5.** Bereitstellen für eine Azure-VM über eine docker-Registrierung

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>Szenario C: Bereitstellen auf einem virtuellen Azure-Computer über CI/CD-Pipelines in Azure DevOps Services

![Bereitstellen auf einem virtuellen Azure-Computer über CI/CD-Pipelines in Azure DevOps Services](./media/image5-6.png)

**Abbildung 5-6.** Bereitstellen auf einem virtuellen Azure-Computer über CI/CD-Pipelines in Azure DevOps Services

### <a name="azure-vms-for-windows-containers"></a>Azure-VMs für Windows-Container

Azure-VMs für Windows-Container sind virtuelle Computer, die auf Windows Server 2016, Windows 10 oder höheren Versionen basieren und beide mit der Docker-Engine eingerichtet sind. In den meisten Fällen wird Windows Server 2016 auf den Azure-VMS verwendet.

Azure stellt derzeit einen virtuellen Computer namens **Windows Server 2016 mit Containern**bereit. Mit diesem virtuellen Computer können Sie die neue Windows Server-Container Funktion mit Windows Server Core oder Windows Nano Server testen. Container Betriebssystem-Images werden installiert, und der virtuelle Computer ist für die Verwendung mit docker bereit.

### <a name="benefits"></a>Vorteile

Obwohl Windows-Container auf lokalen Windows Server 2016-VMS bereitgestellt werden können, erhalten Sie bei der Bereitstellung in Azure eine einfachere Möglichkeit, mit sofort einsatzbereiten Windows Server-Container-VMs zu beginnen. Außerdem erhalten Sie einen gemeinsamen Online Speicherort, der für Tester verfügbar ist, und die automatische Skalierbarkeit über Azure-VM-Skalierungs Gruppen.

### <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Exemplarische Vorgehensweise 4: Bereitstellen Ihrer Windows-Container-basierten apps in Azure Container Instances (ACI)

### <a name="technical-walkthrough-availability"></a>Technische Exemplarische Vorgehensweise

Die vollständige technische Exemplarische Vorgehensweise finden Sie im wiki für das eshopmoderniup-GitHub-Repository:

[Bereitstellen der apps in ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>Übersicht

[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) ist die schnellste Möglichkeit, eine Container Entwicklungs-/Test-/Stagingumgebung zu erhalten, in der Sie einzelne Instanzen von Containern bereitstellen können.

### <a name="goals"></a>Ziele

Diese exemplarische Vorgehensweise zeigt Ihnen die wichtigsten Szenarien für die Bereitstellung von Windows-Containern für Azure Container Instances (ACI) und wie Sie eshopmodernisierungsapps in ACI bereitstellen können.

### <a name="scenarios"></a>Szenarien

Es können Variationen in Bezug auf die Bereitstellung der eshopmoderniup-apps in ACI auftreten, z. b. das Bereitstellen von nur einer oder aller apps (MVC-APP, WebForms-APP oder WCF-Dienst). Im folgenden Szenario sehen Sie die ASP.NET MVC-APP und den SQL Server-Container, die beide als Container in ACI (Azure Container Instances) bereitgestellt werden.

![Bereitstellen in ACI aus einer Entwicklungsumgebung](./media/image5-3.5.6.png)

### <a name="benefits"></a>Vorteile

Azure Container Instances erleichtert das Erstellen und Verwalten von Docker-Containern in Azure, ohne dass Sie virtuelle Computer bereitstellen oder einen übergeordneten Dienst einführen müssen. Mit ACI können Sie einen Windows-Container in Azure direkt bereitstellen und im Internet mit einem vollständig qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) innerhalb weniger Sekunden verfügbar machen (vorausgesetzt, dass das Windows-Container Image in einer docker-Registrierung wie docker Hub oder Azure Container bereit steht). Registrierung).

### <a name="considerations"></a>Weitere Überlegungen

Das Bereitstellen von Windows-Containern mit voll .NET Framework/ASP.net oder SQL Server in Azure Container Instances (ACI) ist nicht ganz so schnell wie die Bereitstellung auf einem regulären docker-Host (z. b. Windows Server 2016 mit Windows-Containern), da das docker-Image wird jedes mal heruntergeladen (aus der Docker-Registrierung abgerufen), und die Größe des SQL-Container Images (15,1 GB) und des ASP.NET-Container Images (13,9 GB) sind sehr groß, aber es ist viel günstiger als die Beibehaltung ihres eigenen docker-Hosts (dauerhaft Online). Windows Server 2016 mit Windows-Container-VM in Azure), um einen vollständigen Orchestrator wie Kubernetes in Azure (AKS) zu erwähnen, was andererseits eine gute Wahl für Produktions Bereitstellungen ist.

Als Hauptergebnis ist die Verwendung von Azure Container Instances eine sehr überzeugende Option für Entwicklungs-/Testszenarien und für CI/CD-Pipelines.

## <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Exemplarische Vorgehensweise 5: Bereitstellen Ihrer Windows-Container-basierten apps in Kubernetes in Azure Container Service

### <a name="technical-walkthrough-availability"></a>Technische Exemplarische Vorgehensweise

Die vollständige technische Exemplarische Vorgehensweise finden Sie im wiki für das eshopmoderniup-GitHub-Repository:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a>Übersicht

Eine Anwendung, die auf Windows-Containern basiert, muss schnell Plattformen verwenden und sich noch weiter von virtuellen IaaS-Computern verlagern. Dies ist erforderlich, um auf einfache Weise eine hohe Skalierbarkeit und eine bessere automatisierte Skalierbarkeit zu erreichen und eine bedeutende Verbesserung bei automatisierten bereit Stellungen und Versionsverwaltung zu erzielen. Diese Ziele können Sie mithilfe der Orchestrator- [Kubernetes](https://kubernetes.io/)erreichen, die in [Azure Container Services](https://azure.microsoft.com/services/container-service/)verfügbar ist.

### <a name="goals"></a>Ziele

In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie in Azure Container Service eine Windows-Container – basierte Anwendung in Kubernetes (auch als *K8s*bezeichnet) bereitstellen. Die Bereitstellung von Grund auf Kubernetes ist ein zweistufiger Prozess:

1. Stellen Sie einen Kubernetes-Cluster für die Azure Container Service bereit.

2. Stellen Sie die Anwendung und zugehörige Ressourcen für den Kubernetes-Cluster bereit.

### <a name="scenarios"></a>Szenarien

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Szenario A: Direktes bereitstellen in einem Kubernetes-Cluster aus einer Entwicklungsumgebung

![Direktes bereitstellen in einem Kubernetes-Cluster aus einer Entwicklungsumgebung](./media/image5-7.png)

**Abbildung 5-7.** Direktes bereitstellen in einem Kubernetes-Cluster aus einer Entwicklungsumgebung

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Szenario B: Bereitstellen in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps Services

![Bereitstellen in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps Services](./media/image5-8.png)

**Abbildung 5-8.** Bereitstellen in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps Services

### <a name="benefits"></a>Vorteile

Die Bereitstellung in einem Cluster in Kubernetes bietet viele Vorteile. Der größte Vorteil besteht darin, dass Sie eine Produktions bereite Umgebung erhalten, in der Sie die Anwendung basierend auf der Anzahl der zu verwendenden Container Instanzen (innere Skalierbarkeit in den vorhandenen Knoten) und basierend auf der Anzahl der Knoten oder VMS im Cluster horizontal hochskalieren können. Globale Skalierbarkeit des Clusters).

Azure Container Service optimiert beliebte Open Source-Tools und-Technologien speziell für Azure. Sie erhalten eine offene Lösung, die Portabilität sowohl für Ihre Container als auch für Ihre Anwendungskonfiguration bietet. Sie wählen die Größe, die Anzahl der Hosts und Orchestrator-Tools aus. der Container Dienst verarbeitet alles andere.

Mit Kubernetes können sich Entwickler über physische und virtuelle Computer nachdenken und eine Container zentrierte Infrastruktur planen, die die folgenden Funktionen unter anderem ermöglicht:

- Anwendungen, die auf mehreren Containern basieren

- Replizieren von Container Instanzen und horizontaler automatischer Skalierung

- Benennen und ermitteln (z. b. internes DNS)

- Lastenausgleich

- Parallele Updates

- Verteilen von Geheimnissen

- Anwendungs Integritätsprüfungen

## <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a>Exemplarische Vorgehensweise 6: Bereitstellen von Windows-Container-basierten Apps für die Azure App Service für Container

### <a name="technical-walkthrough-availability"></a>Technische Exemplarische Vorgehensweise

Die vollständige technische Exemplarische Vorgehensweise finden Sie im wiki für das eshopmoderniup-GitHub-Repository:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a>Übersicht

Eine einfache containerisierte Anwendung, die Windows-Container verwendet Azure App Service, kann problemlos für Container bereitgestellt werden. Dies ist die empfohlene Vorgehensweise für die meisten Windows-Container basierten Anwendungen.

### <a name="goals"></a>Ziele

In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie eine Windows Container – basierte Anwendung für die Azure App Service für Container aus einer Registrierung (docker Hub oder Azure Container Registry) bereitstellen.

### <a name="scenario"></a>Szenario

![Bereitstellen einer Windows Container-basierten App für Azure App Service für Container](./media/image5-11.png)

### <a name="benefits"></a>Vorteile

Die Bereitstellung in Azure App Service für Container bietet die Vorteile von Containern in Kombination mit den PaaS-Vorteilen von Azure App Service. Der APP Service kann problemlos vertikal und horizontal skaliert werden und kann so konfiguriert werden, dass er eine automatische Skalierung durch findet, um geänderte Anforderungen zu erfüllen. Updates können ohne Ausfallzeiten ausgeführt werden, und die Konfiguration von Continuous Deployment aus einer Registrierung ist ebenfalls leicht zu konfigurieren.

## <a name="next-steps"></a>Nächste Schritte

Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

> [!div class="step-by-step"]
> [Zurück](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [Weiter](conclusions.md) <!-- Next Chapter -->
