---
title: Migrieren zu Hybridcloudszenarios
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Migrieren zu Hybridcloudszenarios
ms.date: 04/30/2018
ms.openlocfilehash: dcbb799a45609f8bb811866c4041951abf1fda8b
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937364"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>Migrieren zu Hybridcloudszenarios

Manche Organisationen und Unternehmen können einige Ihrer Anwendungen aufgrund von Bestimmungen oder ihrer eigenen Richtlinien nicht in öffentliche Clouds wie Microsoft Azure oder eine andere öffentliche Cloud migrieren. Es ist jedoch wahrscheinlich, dass alle Organisationen davon profitieren können, dass sich einige Ihrer Anwendungen in der öffentlichen Cloud befinden und andere Anwendungen lokal vorhanden sind. Eine gemischte Umgebung kann jedoch aufgrund verschiedener Plattformen und Technologien, die in öffentlichen Clouds im Gegensatz zu lokalen Umgebungen verwendet werden, zu übermäßiger Komplexität in Umgebungen führen.

Microsoft bietet die beste Hybrid Cloud-Lösung, bei der Sie Ihre vorhandenen Ressourcen lokal und in der öffentlichen Cloud optimieren können, während Sie die Konsistenz in einer Azure Hybrid Cloud gewährleisten. Dank Azure Stack (lokal) und Azure (Public Cloud) können Sie vorhandene Fähigkeiten maximieren und einen flexiblen, einheitlichen Ansatz zum Entwickeln von Apps nutzen, die in der Cloud oder lokal ausgeführt werden können.

Hinsichtlich Sicherheit können Sie die Verwaltung und Sicherheit in der gesamten Hybrid Cloud zentralisieren. Sie können die Kontrolle über alle Ressourcen erhalten, von Ihrem Rechenzentrum bis in die Cloud, indem Sie einmaliges Anmelden für lokale und Cloud-Apps bereitstellen. Dies erreichen Sie, indem Sie Active Directory in eine Hybrid Cloud erweitern und Identitätsverwaltung verwenden.

Schließlich können Sie Daten nahtlos verteilen und analysieren, dieselben Abfragesprachen für Cloud- und lokale Ressourcen verwenden sowie Analysen und Deep Learning in Azure anwenden, um Ihre Daten unabhängig von deren Quelle anzureichern.

## <a name="azure-stack"></a>Azure Stack

Azure Stack ist eine Hybrid Cloud-Plattform, mit der Sie Azure-Dienste über das Rechenzentrum Ihrer Organisation bereitstellen können. Azure Stack soll in wichtigen Szenarien (etwa in Edge-Umgebungen und nicht verbundenen Umgebungen) neue Möglichkeiten für Ihre modernen Anwendungen unterstützen und zur Erfüllung spezifischer Sicherheits- und Konformitätsanforderungen beitragen.

Abbildung 4-13 zeigt eine Übersicht über die echte Hybrid Cloud-Plattform, die Microsoft bietet.

![Diagramm der Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

**Abbildung 4-13.** Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure

Azure Stack wird in zwei auf Ihre Anforderungen abgestimmten Bereitstellungsoptionen angeboten:

- Integrierte Azure Stack-Systeme

- Azure Stack Development Kit

### <a name="azure-stack-integrated-systems"></a>Integrierte Azure Stack-Systeme

Integrierte Azure Stack-Systeme werden im Rahmen einer Partnerschaft zwischen Microsoft und Hardwarepartnern angeboten. Durch diese Partnerschaft entsteht eine Lösung mit cloudbasierten Innovationen und komfortabler Computeverwaltung. Da Azure Stack als integriertes System aus Hardware und Software angeboten wird, erhalten Sie genau das richtige Maß an Flexibilität und Kontrolle und können dennoch Innovationen aus der Cloud übernehmen. Integrierte Azure Stack-Systeme haben eine Größe von 4 bis 12 Knoten, und der Support wird vom Hardwarepartner und von Microsoft gemeinsam bereitgestellt. Mit integrierten Azure Stack-Systemen ermöglichen Sie die Implementierung neuer Szenarien für Ihre Produktionsworkloads.

### <a name="azure-stack-development-kit"></a>Azure Stack Development Kit

Microsoft Azure Stack Development Kit ist eine Einzelknotenbereitstellung von Azure Stack, die Sie verwenden können, um Azure Stack kennenzulernen und zu testen. Sie können auch Azure Stack Development Kit als Entwicklerumgebung verwenden, in der Sie anhand von mit Azure konsistenten APIs und Tools Entwicklungsarbeiten durchführen können. Azure Stack Development Kit ist nicht zur Verwendung als Produktionsumgebung vorgesehen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Azure Hybrid Cloud**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

- **Active Directory-Dienstkonten für Windows-Container**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- **Erstellen eines Containers mit Active Directory-Unterstützung**

    <https://docs.microsoft.com/archive/blogs/containerstuff/create-a-container-with-active-directory-support>

- **Azure-Hybridvorteil – Lizenzierung**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[Zurück](life-cycle-ci-cd-pipelines-devops-tools.md)
>[Weiter](../walkthroughs-technical-get-started-overview.md)
