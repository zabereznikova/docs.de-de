---
title: "Exemplarische Vorgehensweisen und technische abrufen gestarteten (Übersicht)"
description: "Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Exemplarische Vorgehensweisen und technische abrufen gestarteten (Übersicht)"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: e78dd4a324ca9fc973f1aa0d8e6a9abe1341876c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Exemplarische Vorgehensweisen und technische abrufen gestarteten (Übersicht) 

Um die Größe dieser e-Book zu beschränken, haben wir zusätzliche technische Dokumentation und die vollständige Exemplarische Vorgehensweisen in ein GitHub-Repository zur Verfügung. Die online Reihe von exemplarischen Vorgehensweisen, die in diesem Kapitel beschriebenen behandelt schrittweise Setup von mehreren Umgebungen, die auf Windows-Containern und Bereitstellung in Azure basieren.

In den folgenden Abschnitten wird erläutert, was jeder exemplarischen Vorgehensweise zu seiner ist Ziele, die allgemeine Vision- und enthält ein Diagramm der Aufgaben, die beteiligt sind. Sie können die exemplarischen Vorgehensweisen selbst abrufen in der *eShopModernizing* apps GitHub-Repository Wiki am [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).

# <a name="technical-walkthrough-list"></a>Technische Anleitung-Liste

Die folgenden abrufen gestarteten exemplarischen Vorgehensweisen bieten konsistent und umfassende technische Anleitung für die Beispiel-apps, die Sie heben und verschieben Sie mithilfe von Containern und klicken Sie dann mit der mehrere Bereitstellungsoptionen haben in Azure verschieben.

Jede der folgenden exemplarischen Vorgehensweisen verwendet die neue eShopLegacy und eShopModernizing beispielapps, die auf GitHub unter zur Verfügung stehen [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).

-   **Tour durch Shopping legacy-apps**

-   **Containerize Ihre vorhandenen .NET Anwendungen mit Windows-Containern**

-   **Bereitstellen der Windows Container-basierten app in Azure-VMs**

-   **Bereitstellen Sie Windows-Container-basierte apps auf Kubernetes im Azure-Container-Dienst**

-   **Bereitstellen von Windows-Container-basierten apps Azure Service Fabric**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Exemplarische Vorgehensweise 1: Überblick Shopping legacy-apps

### <a name="technical-walkthrough-availability"></a>Technische Anleitung-Verfügbarkeit

Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/01.-Tour-On-eShopModernizing-Apps-Implementation-Code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a>Übersicht

In dieser exemplarischen Vorgehensweise können Sie die ursprüngliche Implementierung von zwei Beispiel Legacyanwendungen untersuchen. Beide Beispiel-apps haben eine monolithische Architektur und mithilfe des klassischen ASP.NET erstellt wurden. Eine Anwendung basiert auf ASP.NET 4.x MVC; die zweite Anwendung basiert auf ASP.NET 4.x Web Forms. Beide Anwendungen sind der [eShopModernizing GitHub-Repository](https://github.com/dotnet-architecture/eShopModernizing).

Sie können beide beispielapps containerize, ähnlich wie die können die Klassisches containerize [Windows Communication Foundation](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) (WCF)-Anwendung als eine desktop-Anwendung verwendet wird. Ein Beispiel finden Sie unter [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).

### <a name="goals"></a>Ziele

Das wichtigste Ziel dieser exemplarischen Vorgehensweise besteht darin, mit diesen apps und mit ihren Code und Konfiguration vertraut. Sie können die apps konfigurieren, sodass sie generieren und Verwenden von simulierten Daten ohne Verwendung der SQL-Datenbank für Testzwecke verwenden. Diese optionale Konfiguration basiert auf Abhängigkeitsinjektion, in einer entkoppelten Weise.

### <a name="scenario"></a>Szenario

Abbildung 5 – 1 zeigt die einfachen Szenarios, die ursprüngliche Legacyanwendungen.

> ![Einfache Architektur-Szenario für die ursprüngliche Legacyanwendungen](./media/image5-1.png)
>
> **Abbildung 5 – 1.** Einfache Architektur-Szenario für die ursprüngliche Legacyanwendungen

Aus Sicht der Business-Domäne bieten beide apps den gleichen Katalog Verwaltungsfunktionen. Mitglieder des Teams Enterprise Shopping würde die app anzeigen und Bearbeiten des Produktkatalogs verwenden. Abbildung 5 – 2 zeigt die anfänglichen app Screenshots.

![ASP.NET MVC und ASP.NET Web Forms-Anwendungen (vorhandene/Legacy-Technologien)](./media/image5-2.png)

> **Abbildung 5-2.** ASP.NET MVC und ASP.NET Web Forms-Anwendungen (vorhandene/Legacy-Technologien)

Hierbei handelt es sich um Webanwendungen, die zum Suchen und Ändern von Katalogeinträge verwendet werden. Die Tatsache, dass beide apps die gleichen Business/funktionale Funktionen bieten ist einfach für Vergleichszwecke. Sie können einem ähnlichen Modernisierung-Prozess für apps, die mithilfe von ASP.NET MVC und ASP.NET Web Forms-Frameworks erstellt wurden, finden Sie unter.

Abhängigkeiten ASP.NET 4.x oder früheren Versionen (entweder für MVC oder Web Forms) bedeutet, dass diese Anwendungen keine auf .NET Core ausgeführt werden, wenn der Code vollständig neu geschrieben wird, mithilfe von ASP.NET Core MVC. Dies beweist dann, wenn Sie nicht möchten Umgestalten oder Schreiben Sie Code, können Sie vorhandene Anwendungen containerize und weiterhin die gleichen Technologien für .NET und denselben Code verwenden. Sie können sehen, wie Sie Anwendungen, wie diese in Containern, ohne Änderungen für legacy-Code ausführen können.

### <a name="benefits"></a>Vorteile

Die Vorteile der in dieser exemplarischen Vorgehensweise sind einfach: nur den Code und Anwendungskonfiguration in, basierend auf Abhängigkeitsinjektion vertraut machen. Anschließend können Sie bei diesem Ansatz experimentieren, beim containerize und in Zukunft in mehreren Umgebungen bereitstellen.

### <a name="next-steps"></a>Nächste Schritte

Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/01.-Tour-On-eShopModernizing-Apps-Implementation-Code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Exemplarische Vorgehensweise 2: Containerize, Ihre vorhandenen .NET Anwendungen mit Windows-Containern

### <a name="technical-walkthrough-availability"></a>Technische Anleitung-Verfügbarkeit

Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/02.-How-to-containerized-the-.NET-Framework-Web-Apps-with-Windows-Containers-and-Docker](https://https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerized-the-.NET-Framework-web-apps-with-Windows-Containers-and-DockerTBD)

### <a name="overview"></a>Übersicht

Mithilfe von Windows-Containern um Bereitstellung der vorhandenen .NET-Anwendungen, wie die Grundlage von MVC oder Web Forms, WCF, Produktions-, Entwicklungs- und testumgebungen zu verbessern.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise werden Ihnen mehrere Optionen für eine vorhandene .NET Framework-Anwendung containerizing anzeigen. Sie haben folgende Möglichkeiten:

-   Containerize Ihrer Anwendung mit [Visual Studio 2017-Tools für Docker](https://docs.microsoft.com/dotnet/core/docker/visual-studio-tools-for-docker) (Visual Studio-2017 oder höhere Versionen).

-   Containerize Ihrer Anwendung durch manuelles Hinzufügen von einer [dockerfile-Datei](https://docs.docker.com/engine/reference/builder/), und klicken Sie dann mit der [Docker-Befehlszeilenschnittstelle](https://docs.docker.com/engine/reference/commandline/cli/).

-   Containerize Ihrer Anwendung mithilfe der [Img2Docker](https://github.com/docker/communitytools-image2docker-win) -Tool (eine Open-Source-Tool von Docker).

In dieser exemplarischen Vorgehensweise konzentriert sich auf Visual Studio 2017-Tools für Docker-Ansatz, aber die anderen beiden Methoden im Hinblick auf die dockerfile-Dateien mit ähnlich sind.

### <a name="scenario"></a>Szenario

Abbildung 5-3 wird das Szenario für Legacyanwendungen Datenvolumes Shopping.

> ![Vereinfachte Sammelartikeleinheit in einer Entwicklungsumgebung-Architekturdiagramm](./media/image5-3.png)
>
> **Abbildung 5-3.** Vereinfachte Sammelartikeleinheit in einer Entwicklungsumgebung-Architekturdiagramm

### <a name="benefits"></a>Vorteile

Es sind Vorteile, die aufgrund eines monolithischen Anwendung in einem Container ausgeführt. Zunächst erstellen Sie ein Bild für die Anwendung. Ab diesem Zeitpunkt wird Sie jede Bereitstellung in der gleichen Umgebung ausgeführt. Jeder Container verwendet die gleiche Version des Betriebssystems, die gleiche Version von Abhängigkeiten installiert wurde, verwendet die gleiche Version von .NET Framework und wird erstellt, indem Sie mit der gleichen. Grundsätzlich können Sie die Abhängigkeiten der Anwendung mithilfe eines Images von Docker steuern. Die Abhängigkeiten Reisen mit der Anwendung während der Bereitstellung auf den Container.

Ein zusätzlicher Vorteil besteht darin, dass Entwickler die Anwendung in die konsistente Umgebung ausführen können, die von Windows-Container bereitgestellt wird. Probleme, die nur mit bestimmten Versionen angezeigt werden können sofort entdeckt werden, statt in einer Staging- oder Produktionsserver Umgebung einbringen. Unterschiede in entwicklungsumgebungen verwendet, die von Mitgliedern des Entwicklungsteams unerheblich kleiner, wenn Anwendungen in Containern ausgeführt.

Sammelartikeleinheit haben auch eine flachere mit horizontaler Skalierung Kurve. Datenvolumes apps können Sie weitere Anwendung und Dienstinstanzen (basierend auf den Container) verfügen, in einem virtuellen Computer oder physischen Computer im Vergleich zu normalen anwendungsbereitstellungen pro Computer. Dies bedeutet höhere Dichte und weniger erforderlichen Ressourcen, insbesondere wenn Sie Orchestrators wie Kubernetes oder Service Fabric verwenden.

Containerization, im Idealfall, erfordert keine Änderungen am Anwendungscode (C\#). In den meisten Fällen benötigen Sie nur die Docker-Bereitstellung-Metadatendateien (dockerfile-Dateien und Docker Compose-Dateien).

### <a name="next-steps"></a>Nächste Schritte

Dieser Inhalt ausführlicheren im GitHub-Wiki durchsuchen: [Https://https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerized-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerized-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Exemplarische Vorgehensweise 3: Bereitstellen der Windows-Container-basierten Anwendung auf Azure VMs

### <a name="technical-walkthrough-availability"></a>Technische Anleitung-Verfügbarkeit

Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/03.-How-to-Deploy-Your-Windows-Containers-based-App-INTO-Azure-VMs-(including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>Übersicht

Bereitstellung auf einem Docker-Host auf einem Windows Server 2016-VM in Azure können Sie die Dev/Test/Stagingumgebungen schnell einzurichten. Darüber hinaus haben Sie einen allgemeinen Platz für Tester oder Geschäftsbenutzer, um die app zu überprüfen. Virtuelle Computer können auch mit gültigen IaaS-produktionsumgebungen sein.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise werden Sie mehrere Alternativen an, die Ihnen beim Bereitstellen von Windows-Container für Azure-VMs, die auf Windows Server 2016 oder höher basieren.

### <a name="scenarios"></a>Szenarien

In dieser exemplarischen Vorgehensweise werden mehrere Szenarien behandelt.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Szenario A: Bereitstellen in einer Azure-VM aus einer Dev PC über Docker-Modul-Verbindung

![Über eine Dev PC über eine Verbindung Docker-Modul in einer Azure-VM bereitstellen](./media/image5-4.png)

> **Abbildung 5-4.** Über eine Dev PC über eine Verbindung Docker-Modul in einer Azure-VM bereitstellen

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Szenario B: Bereitstellen Sie in einer Azure-VM über einen Docker-Registrierung

![Bereitstellen Sie in einer Azure-VM über einen Docker-Registrierung](./media/image5-5.png)

> **Abbildung 5 bis 5.** Bereitstellen Sie in einer Azure-VM über einen Docker-Registrierung

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a>Szenario "c:" in einer Azure-VM bereitstellen, von CI-CD-Pipelines in Visual Studio Team Services

![Bereitstellen Sie in einer Azure-VM von CI-CD-Pipelines in Visual Studio Team Services](./media/image5-6.png)

> **Abbildung 5 bis 6.** Bereitstellen Sie in einer Azure-VM von CI-CD-Pipelines in Visual Studio Team Services

### <a name="azure-vms-for-windows-containers"></a>Azure-VMs für Windows-Container

Azure-VMs für Windows-Containern einfach VMs von Windows 10, Windows Server 2016 abhängig oder höher, sowohl mit Docker-Modul einrichten. In den meisten Fällen verwenden Sie Windows Server 2016 in den Azure-VMs.

Azure bietet zurzeit einen virtuellen Computer mit dem Namen **Windows Server 2016 mit Containern**. Dieser virtuelle Computer können Sie das neue Windows Server-Container-Feature, mit Windows Server Core oder Windows Nano Server versuchen. Containerbetriebssystem-Images werden installiert, und klicken Sie dann der virtuellen Computer ist einsatzbereit mit Docker.

### <a name="benefits"></a>Vorteile

Obwohl Windows-Container bei der Bereitstellung in Azure zu einer lokalen Windows Server 2016-VMs bereitgestellt werden kann, erhalten Sie eine einfachere Möglichkeit, sofort zu verwendende Windows Server-Container-VMs Einstieg. Sie erhalten auch einen allgemeinen online Speicherort, der den Testern und automatische Skalierbarkeit durch die Azure-VM-skalierungsgruppen zugegriffen werden.

### <a name="next-steps"></a>Nächste Schritte

Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/03.-How-to-Deploy-Your-Windows-Containers-based-App-INTO-Azure-VMs-(including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Exemplarische Vorgehensweise 4: Bereitstellen der Windows-Container-basierte apps für Kubernetes im Azure-Container-Dienst

### <a name="technical-walkthrough-availability"></a>Technische Anleitung-Verfügbarkeit

Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/04.-How-to-Deploy-Your-Windows-Containers-based-Apps-INTO-Kubernetes-in-Azure-Container-Service-(including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a>Übersicht

Eine Anwendung, die basierend auf Windows-Containern müssen schnell verschieben unterwegs noch weiter von IaaS-VMs-Plattformen verwenden. Dies ist erforderlich, um problemlos hohe Skalierbarkeit zu erzielen eine bessere Leistung automatisierte Skalierbarkeit und für eine deutliche leistungsverbesserung automatische Bereitstellungen und versionsverwaltung. Sie können diese Ziele erreichen, indem Sie mit der Orchestrator [Kubernetes](https://kubernetes.io/), verfügbar im [Dienste der Azure-Container](https://azure.microsoft.com/services/container-service/).

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise erfahren, wie in einer Windows-Container-basierte Anwendung Kubernetes bereitstellen ist (so genannte *K8s*) im Azure-Container-Dienst. Bereitstellen für Kubernetes von Grund auf neu ist ein zweistufiger Prozess:

1.  Bereitstellen eines Clusters Kubernetes Azure-Container-Dienst an.

2.  Stellen Sie die Anwendung und die zugehörigen Ressourcen für den Cluster Kubernetes bereit.

### <a name="scenarios"></a>Szenarien

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Szenario A: Bereitstellen direkt zu einem Cluster Kubernetes aus einer Developer-Umgebung

![Direkt auf einem Cluster Kubernetes aus einer Entwicklungsumgebung bereitstellen](./media/image5-7.png)

> **Abbildung 5-7.** Direkt auf einem Cluster Kubernetes aus einer Entwicklungsumgebung bereitstellen

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a>Szenario B: zu einem Cluster Kubernetes bereitstellen, von CI-CD pipelines im Team Services

![Bereitstellen Sie für einen Cluster Kubernetes CI-CD-Pipelines in Team Services](./media/image5-8.png)

> **Abbildung 5 bis 8.** Bereitstellen Sie für einen Cluster Kubernetes CI-CD-Pipelines in Team Services

### <a name="benefits"></a>Vorteile

Es gibt viele Vorteile für eine Bereitstellung auf einem Cluster in Kubernetes. Der größte Vorteil ist, dass eine produktionsbereite Umgebung Sie in der Sie mit horizontaler Skalierung können die Anwendung basierend auf der Anzahl der containerinstanzen, die Sie erhalten (Inner-Skalierbarkeit in den vorhandenen Knoten) verwenden möchten, die und basierend auf der Anzahl von Knoten oder virtuellen Computern in den Cluster ( Globale Skalierbarkeit des Clusters).

Azure Containerdienst wird die beliebte Open Source-Tools und Technologien speziell für Azure optimiert. Sie erhalten eine geöffnete Projektmappe, die Portabilität, die sowohl für die Container als auch für Ihre Anwendungskonfiguration bietet. Wählen Sie die Größe der Anzahl der Hosts, und der Orchestrator-Tools-Container-Dienst verarbeitet alle anderen.

Mit Kubernetes können Entwickler Gedanken über physische und virtuelle Computer, Status, für die Planung einer Container anwendungsorientierte-Infrastruktur, die die folgenden Funktionen, u. a. erleichtert:

-   Anwendungen, die basierend auf mehrere Container

-   Replizieren von containerinstanzen und automatische horizontale Skalierung

-   Benennen und ermitteln (z. B. internes DNS)

-   Lastenausgleich Lasten

-   Parallele updates

-   Verteilen von geheimen Schlüsseln

-   Integritätsprüfungen für die Anwendung

## <a name="next-steps"></a>Nächste Schritte

Dieser Inhalt ausführlicheren im GitHub-Wiki durchsuchen: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-() Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>Exemplarische Vorgehensweise 5: Bereitstellen von Windows-Container-basierte apps Azure Service Fabric

### <a name="technical-walkthrough-availability"></a>Technische Anleitung-Verfügbarkeit

Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/05.-How-to-Deploy-Your-Windows-Containers-based-Apps-INTO-Azure-Service-Fabric-(including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>Übersicht

Eine Anwendung, die basierend auf Windows-Containern müssen schnell verschieben unterwegs noch weiter von IaaS-VMs-Plattformen verwenden. Dies ist erforderlich, um problemlos hohe Skalierbarkeit zu erzielen eine bessere Leistung automatisierte Skalierbarkeit und für eine deutliche leistungsverbesserung automatische Bereitstellungen und versionsverwaltung. Sie können diese Ziele erreichen, mit dem Orchestrator Azure Service Fabric, das in der Azure-Cloud verfügbar, aber auch zur Verwendung von lokalen verfügbar ist, oder sogar in einer anderen öffentlichen Cloud.

### <a name="goals"></a>Ziele

Das Ziel dieser exemplarischen Vorgehensweise ist, wie Sie eine Windows-Container-basierte Anwendung zu einem Service Fabric-Cluster in Azure bereitzustellen. Bereitstellen von Service Fabric von Grund auf neu ist ein zweistufiger Prozess:

1.  Bereitstellen von Service Fabric-Cluster in Azure (oder auf eine andere Umgebung).

2.  Stellen Sie die Anwendung und die zugehörigen Ressourcen für Service Fabric-Cluster bereit.

### <a name="scenarios"></a>Szenarien

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>Szenario A: Bereitstellen direkt zu einem Service Fabric-Cluster aus einer Developer-Umgebung

![Direkt auf einem Service Fabric-Cluster aus einer Entwicklungsumgebung bereitstellen](./media/image5-9.png)

> **Abbildung 5 bis 9.** Direkt auf einem Service Fabric-Cluster aus einer Entwicklungsumgebung bereitstellen

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a>Szenario B: zu einem Service Fabric-Cluster bereitstellen, von CI-CD pipelines im Team Services

![Bereitstellen Sie für Service Fabric-Cluster CI-CD-Pipelines in Visual Studio Team Services](./media/image5-10.png)

> **Abbildung 5 bis 10.** Bereitstellen Sie für Service Fabric-Cluster CI-CD-Pipelines in Visual Studio Team Services

## <a name="benefits"></a>Vorteile

Die Vorteile der Bereitstellung auf einem Service Fabric-Cluster sind die Vorteile der Verwendung von Kubernetes ähnlich. Ein Unterschied ist jedoch, dass Service Fabric ist eine sehr ausgereifte produktionsumgebung für Windows-Anwendungen im Vergleich zu Kubernetes, die in der Vorschau für Windows-Container bis zu einem frühen Zeitpunkt des 2017 fallen wurde. (Kubernetes ist eine ausgereiftere Umgebung für Linux). 

Der wichtigste Vorteil der Verwendung von Azure Service Fabric ist, dass eine produktionsbereite Umgebung Sie in der Sie mit horizontaler Skalierung können basierte auf der Anzahl der containerinstanzen, die Sie erhalten (Inner-Skalierbarkeit in den vorhandenen Knoten) verwenden möchten, die und basierend auf der Anzahl der Anwendung Knoten oder virtuellen Computern im Cluster (globale Skalierbarkeit des Clusters).

Azure Service Fabric bietet Portabilität sowohl für die Container als auch für die Anwendungskonfiguration. Sie können einen Service Fabric-cluster in Azure oder lokal in Ihrem eigenen Datacenter installieren. Sie können Service Fabric-Cluster in einer anderen Cloud geht auch wie installieren [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).

Mit Service Fabric können Entwickler Gedanken über physische und virtuelle Computer ausgeführt, für die Planung einer Container anwendungsorientierte-Infrastruktur, die die folgenden Funktionen, u. a. erleichtert:

-   Anwendungen, die basierend auf mehrere Container.

-   Das Replizieren von containerinstanzen und automatische horizontale Skalierung.

-   Benennen und ermitteln (z. B. internes DNS).

-   Lastenausgleich lädt.

-   Parallele Updates an.

-   Verteilen von geheimen Schlüssel ein.

-   Anwendungsintegrität überprüft.

Die folgenden Funktionen sind exklusiv in Service Fabric (verglichen mit anderen Orchestrators):

-   Zustandsbehaftete Dienste-Funktion, über das Anwendungsmodell zuverlässige Dienste.

-   Akteure-Muster, über das Anwendungsmodell für Reliable Actors.

-   Bereitstellen von bare Bone Prozesse, zusätzlich zu den Windows- oder Linux-Container.

-   Erweiterte parallelen Updates und Systemdiagnosen.

### <a name="next-steps"></a>Nächste Schritte

Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/05.-How-to-Deploy-Your-Windows-Containers-based-Apps-INTO-Azure-Service-Fabric-(including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
[Zurück](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Weiter](conclusions.md)
