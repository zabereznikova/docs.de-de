---
title: Microsoft-Technologien in die Cloud optimierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Microsoft-Technologien in die Cloud optimierte Anwendungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 874eeffe77d7f5e459be4d1a93cc2c45e8f8711a
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46481961"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Microsoft-Technologien in die Cloud optimierte Anwendungen

Die folgende Liste beschreibt die Tools, Technologien und Lösungen, die als Voraussetzung für die Cloud optimierte apps erkannt werden. Sie können Elemente Cloudoptimierte selektiv oder nacheinander, je nach Prioritäten übernehmen.

-   **Cloud-Infrastruktur**: die Infrastruktur, die computeplattform, Betriebssystem, Netzwerk und Speicher bereitstellt. Microsoft Azure ist auf dieser Ebene positioniert.

-   **Common Language Runtime**: Diese Ebene bietet die Umgebung für die Ausführung der Anwendung. Wenn Sie Container verwenden, diese Ebene in der Regel basiert auf [Docker-Engine](https://docs.docker.com/engine/), ausgeführt auf Linux-Hosts oder auf Windows-Hosts. ([Windows-Containern](https://docs.microsoft.com/virtualization/windowscontainers/about/) werden ab Windows Server 2016 unterstützt. Windows-Containern ist die beste Wahl für vorhandene .NET Framework-Anwendungen, die unter Windows ausgeführt.)

-   **Verwaltete Cloud**: Wenn Sie eine verwaltete Cloud-Option auswählen, können Sie vermeiden, die Kosten und Komplexität der Verwaltung und Unterstützung der zugrunde liegenden Infrastruktur, virtuelle Computer, Betriebssystem-Patches und Netzwerks. Falls gewünscht, für die Migration mithilfe von IaaS, sind Sie verantwortlich, alle diese Aufgaben und damit verbundenen Kosten. In einer verwalteten Cloud-Option verwalten Sie die Anwendungen und Dienste, die Sie entwickeln. Cloud-Dienstanbieter verwaltet in der Regel alles andere. Beispiele für verwaltete Cloud-Dienste in Azure [Azure SQL-Datenbank](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [, Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [, Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), und Compute Services wie verwaltet [VM-skalierungsgruppen Legt](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), und [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

-   **Anwendungsentwicklung**: Sie können aus vielen Sprachen auswählen, bei der Erstellung von Anwendungen, die in Containern ausgeführt werden. Dieser Leitfaden konzentriert sich auf [.NET](https://www.microsoft.com/net), aber Sie können Container basierende apps entwickeln, indem Sie mit anderen Sprachen wie Java/Node.js, Python, Spring, oder wechseln Sie.

-   **Überwachung, Protokollierung und Überwachung Telemetriedaten**: die Möglichkeit zum Überwachen von Anwendungen und Container, die in der Cloud ausgeführt werden für jede Cloud optimierte Anwendung von entscheidender Bedeutung ist. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) und [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) sind die wichtigsten Microsoft-Tools, Überwachung und Überprüfung für die Cloud optimierte apps bereitstellen.

-   **Bereitstellung**: Automation-Tools helfen Ihnen bei die Infrastruktur einrichten und Bereitstellen einer Anwendung in mehreren Umgebungen (Produktion, Tests, staging). Sie können Tools wie Chef und Puppet verwenden, um Konfigurations- und Umgebungsdaten einer Anwendung zu verwalten. Diese Ebene kann auch mithilfe einfachere und direktere Methoden implementiert werden. Beispielsweise können direkt mithilfe von Azure-Befehlszeilenschnittstelle (Azure CLI)-Tools, bereitstellen und anschließend verwenden Sie den continuous Deployment und release Management-Pipelines in [Azure DevOps-Dienste](https://visualstudio.microsoft.com/team-services/).

-   **Anwendungslebenszyklus**: [Azure DevOps-Dienste](https://visualstudio.microsoft.com/team-services/) und andere Tools wie Jenkins, sind integrierte Automatisierungsserver, mit denen Sie implementieren Sie CI/CD-Pipelines, einschließlich der releaseverwaltung.

In den nächsten Abschnitten dieses Kapitels und verwandten exemplarischen Vorgehensweisen an, den schwerpunktmäßig Informationen zu der Ebene der Common Language Runtime (Windows Container). Die Anleitung wird beschrieben, wie Sie Windows-Containern unter Windows Server 2016 (und höher)-VMs und Azure Container Instances bereitstellen können. Hierin sind auch erweiterte PaaS-Plattformen wie Azure App Service und Orchestrator wie Azure Service Fabric und Azure Kubernetes Service.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Monolithische Anwendungen *können* werden Cloudoptimiert

Es ist wichtig, hervorzuheben, monolithischer Anwendungen (Anwendungen, die nicht auf Microservices basieren) *können* Cloudoptimierte Anwendungen sein. Sie können erstellen und betreiben monolithische Anwendungen, die von der Cloud computing-Modell mithilfe einer Kombination von Containern, continuous Delivery und DevOps nutzen. Ob eine vorhandene monolithische Anwendung für Ihre geschäftlichen Ziele geeignet ist, können Sie modernisiere diese, und machen es Cloud optimiert.

Auf ähnliche Weise monolithische Anwendungen Cloudoptimierte Anwendungen werden, können andere, komplexere Architekturen wie N-Tier-Anwendungen auch als Cloudoptimierte Anwendungen modernisiert werden.

>[!div class="step-by-step"]
[Zurück](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[Weiter](what-about-cloud-native-applications.md)
