---
title: "Microsoft-Technologien in Cloud Devops einsatzfähige Anwendungen"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Microsoft-Technologien in Cloud DevOps einsatzfähige Anwendungen"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3212bf1e938b789d68ca76dd06ce53a2788244b6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="microsoft-technologies-in-cloud-devops-ready-applications"></a>Microsoft-Technologien in Cloud Devops einsatzfähige Anwendungen

Die folgende Liste beschreibt die Tools, Technologien und Lösungen, die als Anforderungen für die Cloud DevOps-fähige apps erkannt werden. Sie können Cloud DevOps-fähige apps selektiv oder allmählich, je nach Ihrer Aufgaben ausführen.

-   **Cloud-Infrastruktur**: die Infrastruktur, die die Compute-Plattform, Betriebssystem, Netzwerk und Speicher bereitstellt. Microsoft Azure wird auf dieser Ebene positioniert.

-   **Common Language Runtime**: Diese Ebene bietet die Umgebung für die Anwendung ausgeführt. Bei Verwendung von Containern dieser Ebene in der Regel basiert auf [Docker-Modul](https://docs.docker.com/engine/)ausführen, entweder auf Linux-Hosts oder auf Windows-Hosts. ([Windows-Containern](https://docs.microsoft.com/virtualization/windowscontainers/about/) werden beginnend mit Windows Server 2016 unterstützt. Windows-Containern ist die beste Wahl für vorhandene .NET Framework-Clientanwendungen, die unter Windows ausgeführt.)

-   **Verwaltete Cloud**: Wenn Sie eine verwaltete Cloud-Option auswählen, können Sie vermeiden, die kostspielige und komplexe verwalten und unterstützen die zugrunde liegende Infrastruktur VMs, Betriebssystempatches und Netzwerks. Falls gewünscht, um die Migration mit IaaS, sind Sie verantwortlich für alle diese Aufgaben und damit verbundenen Kosten. In einer verwalteten Cloud-Option verwalten Sie nur die Anwendungen und Dienste, die Sie entwickeln. Cloud-Dienstanbieter verwaltet in der Regel alles andere. Beispiele für verwaltete Cloud-Dienste in Azure [Azure SQL-Datenbank](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos-DB](https://azure.microsoft.com/services/cosmos-db/), [Azure-Speicher](https://azure.microsoft.com/services/storage/), [Azure-Datenbank für MySQL](https://azure.microsoft.com/services/mysql/), [Azure-Datenbank für PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), und verwaltet die Compute-Dienste wie [VM Scale Legt](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), und [Azure Containerdienst](https://azure.microsoft.com/services/container-service/).

-   **Anwendungsentwicklung**: Sie können aus vielen Sprachen auswählen, wenn Sie Anwendungen erstellen, die in Containern ausgeführt. In diesem Handbuch konzentrieren wir uns auf [.NET](https://www.microsoft.com/net), aber Sie können die Container-basierte apps entwickeln, mit anderen Sprachen, z. B. Node.js, Python, für die Steifheit/Java oder GoLang.

-   **Überwachen von Telemetriedaten, die Protokollierung und Überwachung**: die Möglichkeit zum Überwachen von Anwendungen und Container, die in der Cloud ausgeführt werden für jede Cloud DevOps-fähige Anwendung von entscheidender Bedeutung ist. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) und [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sind die wichtigsten Microsoft-Tools, Überwachung und Überprüfung für die Cloud DevOps-fähige apps bereitstellen.

-   **Bereitstellung**: Automatisierungstools helfen Ihnen beim Bereitstellen der Infrastruktur und Bereitstellen einer Anwendung in mehreren Umgebungen (Produktion, testen, staging). Tools wie Chef oder Puppet können Sie die Konfiguration einer Anwendungsverzeichnis und die Umgebung verwalten. Diese Ebene kann auch mithilfe einfacher und eine direktere Ansätze implementiert werden. Z. B. Sie können direkt mithilfe von Azure-Befehlszeilenschnittstelle (CLI zu Azure) Tools, bereitstellen und verwenden Sie die dauerhafte Bereitstellung und release Management-Pipelines in [Visual Studio Team Services](https://www.visualstudio.com/team-services/).

-   **Anwendungslebenszyklus**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/) und andere Tools, wie Jenkins, Build-Server, mit denen Sie implementieren, CI-CD-Pipelines, einschließlich der releaseverwaltung.

In den nächsten Abschnitten dieses Kapitels und der verwandten exemplarischen Vorgehensweisen schwerpunktmäßig das Details zu der Ebene der Common Language Runtime (Windows-Containern). Die Anweisungen wird beschrieben, wie Sie Windows-Container unter Windows Server 2016 (und Folgeversionen) virtuelle Computer bereitstellen können. Es werden auch erweiterte Orchestrator-Ebenen, wie Azure Service Fabric, Kubernetes und Azure Containerdienst behandelt. Einrichten von Orchestrator-Ebenen ist eine zentrale Anforderung Modernisierung vorhandene .NET Framework-Anwendungen auf (Windows-basierten) als DevOps Cloudfähige Anwendungen.

## <a name="monolithic-applications-can-be-cloud-devops-ready"></a>Aufgrund eines monolithischen Anwendungen *können* werden Cloud DevOps bereit

Es ist wichtig, markieren Sie diese monolithischen Anwendungen (Anwendungen, die nicht auf Microservices basieren) *können* DevOps Cloudfähige Anwendungen werden. Sie können erstellen und betreiben monolithische Anwendungen, die von der Cloud computing-Modell mithilfe einer Kombination von Containern, fortlaufende Übermittlung und DevOps nutzen. Wenn eine vorhandene monolithische Anwendung für Ihre geschäftlichen Ziele geeignet ist, können es modernisieren und DevOps Cloudfähige unbedingt.

Wenn aufgrund eines monolithischen DevOps Cloudfähige Anwendungen werden können, können auf ähnliche Weise anderen und komplexe Architekturen wie N-Tier-Anwendungen auch als DevOps Cloudfähige Anwendungen modernisiert.

>[!div class="step-by-step"]
[Zurück](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)
[Weiter](what-about-cloud-optimized-applications.md)
