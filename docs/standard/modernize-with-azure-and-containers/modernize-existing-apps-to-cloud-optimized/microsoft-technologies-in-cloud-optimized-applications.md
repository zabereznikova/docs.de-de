---
title: Microsoft-Technologien in Cloud-optimierte Anwendungen
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Microsoft-Technologien in Cloud-optimierte Anwendungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: ece366ee3918124bb60e367d3c7447c1d4555c72
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957940"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Microsoft-Technologien in Cloud-optimierte Anwendungen

Die folgende Liste beschreibt die Tools, Technologien und Lösungen, die als Anforderungen für die Cloud optimierten apps erkannt werden. Sie können Elemente Cloudoptimiertes selektiv oder schrittweise, je nach Ihrer Aufgaben ausführen.

-   **Cloud-Infrastruktur**: die Infrastruktur, die die Compute-Plattform, Betriebssystem, Netzwerk und Speicher bereitstellt. Microsoft Azure wird auf dieser Ebene positioniert.

-   **Common Language Runtime**: Diese Ebene bietet die Umgebung für die Anwendung ausgeführt. Bei Verwendung von Containern dieser Ebene in der Regel basiert auf [Docker-Modul](https://docs.docker.com/engine/)ausführen, entweder auf Linux-Hosts oder auf Windows-Hosts. ([Windows-Containern](https://docs.microsoft.com/virtualization/windowscontainers/about/) werden beginnend mit Windows Server 2016 unterstützt. Windows-Containern ist die beste Wahl für vorhandene .NET Framework-Clientanwendungen, die unter Windows ausgeführt.)

-   **Verwaltete Cloud**: Wenn Sie eine verwaltete Cloud-Option auswählen, können Sie vermeiden, die kostspielige und komplexe verwalten und unterstützen die zugrunde liegende Infrastruktur VMs, Betriebssystempatches und Netzwerks. Falls gewünscht, um die Migration mit IaaS, sind Sie verantwortlich für alle diese Aufgaben und damit verbundenen Kosten. In einer verwalteten Cloud-Option verwalten Sie nur die Anwendungen und Dienste, die Sie entwickeln. Cloud-Dienstanbieter verwaltet in der Regel alles andere. Beispiele für verwaltete Cloud-Dienste in Azure [Azure SQL-Datenbank](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos-DB](https://azure.microsoft.com/services/cosmos-db/), [Azure-Speicher](https://azure.microsoft.com/services/storage/), [Azure-Datenbank für MySQL](https://azure.microsoft.com/services/mysql/), [Azure-Datenbank für PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), und verwaltet die Compute-Dienste wie [VM Scale Legt](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), und [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

-   **Anwendungsentwicklung**: Sie können aus vielen Sprachen auswählen, wenn Sie Anwendungen erstellen, die in Containern ausgeführt. Dieses Handbuch konzentriert sich auf [.NET](https://www.microsoft.com/net), aber Container-basierten apps zu entwickeln, mit anderen Sprachen wie Java/Node.js, Python, für die Steifheit, oder wechseln Sie zu können.

-   **Überwachen von Telemetriedaten, die Protokollierung und Überwachung**: die Möglichkeit zum Überwachen von Anwendungen und Container, die in der Cloud ausgeführt werden für jede Cloud-optimierten Anwendung von entscheidender Bedeutung ist. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) und [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sind die wichtigsten Microsoft-Tools, Überwachung und Überprüfung für die Cloud optimierten apps bereitstellen.

-   **Bereitstellung**: Automatisierungstools helfen Ihnen beim Bereitstellen der Infrastruktur und Bereitstellen einer Anwendung in mehreren Umgebungen (Produktion, testen, staging). Tools wie Chef oder Puppet können Sie die Konfiguration einer Anwendungsverzeichnis und die Umgebung verwalten. Diese Ebene kann auch mithilfe einfacher und eine direktere Ansätze implementiert werden. Z. B. Sie können direkt mithilfe von Azure-Befehlszeilenschnittstelle (CLI zu Azure) Tools, bereitstellen und verwenden Sie die dauerhafte Bereitstellung und release Management-Pipelines in [Visual Studio Team Services](https://www.visualstudio.com/team-services/).

-   **Anwendungslebenszyklus**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/) und andere Tools, wie Jenkins sind integrierte Automatisierungsserver, mit denen Sie implementieren CI-CD-Pipelines, einschließlich der releaseverwaltung.

In den nächsten Abschnitten dieses Kapitels und der verwandten exemplarischen Vorgehensweisen schwerpunktmäßig das Details zu der Ebene der Common Language Runtime (Windows-Containern). Die Anweisungen wird beschrieben, wie Sie Windows-Container unter Windows Server 2016 (und Folgeversionen) virtuelle Computer und Azure-Container-Instanzen bereitstellen können. Es werden auch erweiterte PaaS-Plattformen wie Azure App Service und Orchestrator wie Azure Service Fabric und Azure Kubernetes Dienst behandelt.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Aufgrund eines monolithischen Anwendungen *können* werden Cloudoptimiertes

Es ist wichtig, markieren Sie diese monolithischen Anwendungen (Anwendungen, die nicht auf Microservices basieren) *können* Anwendungen Cloud optimiert werden. Sie können erstellen und betreiben monolithische Anwendungen, die von der Cloud computing-Modell mithilfe einer Kombination von Containern, fortlaufende Übermittlung und DevOps nutzen. Wenn eine vorhandene monolithische Anwendung für Ihre geschäftlichen Ziele geeignet ist, können Sie es zu aktualisieren und machen Cloudoptimiertes.

Wenn aufgrund eines monolithischen Anwendungen Cloud optimiert werden können, können auf ähnliche Weise anderen und komplexe Architekturen wie N-Tier-Anwendungen auch als Cloud-optimierte Anwendungen modernisiert.

>[!div class="step-by-step"]
[Zurück](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[Weiter](what-about-cloud-native-applications.md)
