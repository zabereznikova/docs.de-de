---
title: Migrieren zu Hybridcloudszenarios
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Migrieren Sie zu hybridcloudszenarien
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b04c6edecf5b63f191cb2e0f808fb1d0f801d0a3
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612575"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>Migrieren zu Hybridcloudszenarios

Einige Organisationen und Unternehmen können nicht einige seiner Anwendungen in öffentlichen Clouds wie Microsoft Azure oder jede andere öffentliche Cloud, die aufgrund von Bestimmungen oder ihre eigenen Richtlinien migriert. Allerdings ist es wahrscheinlich, dass jedes Unternehmen davon profitieren kann, dass einige seiner Anwendungen in der öffentlichen Cloud und andere Anwendungen vor Ort. Eine gemischte Umgebung kann jedoch zu führen Übermäßige Komplexität in Umgebungen, die aufgrund von verschiedenen Plattformen und Technologien, die in öffentlichen Clouds und lokale Umgebungen.

Microsoft bietet die beste Hybrid Cloud-Lösung, eine in der Sie Ihre vorhandenen Assets optimieren können lokal und in der öffentlichen Cloud, während Sie Konsistenz in einer Azure hybridcloud zu gewährleisten. Sie können vorhandene Fähigkeiten zu maximieren und erhalten einen flexibel und einheitlichen Ansatz zum Erstellen von apps, die in der Cloud oder lokal, Dank der Azure Stack (lokal) und Azure (öffentliche Cloud) ausgeführt werden können.

Wenn es um Sicherheit geht, können Sie die Verwaltung und Sicherheit in Ihre hybridcloud zentralisieren. Sie können gewinnen, Kontrolle über alle Ressourcen aus Ihrem Datencenter in die Cloud, indem einmaligen Anmeldung mit lokalen und cloud-apps. Sie erreichen dies durch das Erweitern des Active Directory in einer hybridcloud, und mit der identitätsverwaltung.

Sie können schließlich verteilen und analysieren Sie Daten nahtlos, verwenden dieselben Abfragesprachen für Cloud- und lokalen Ressourcen und Anwenden von Analytics und Deep learning in Azure, um Ihre Daten unabhängig von der Quelle zu erweitern.

## <a name="azure-stack"></a>Azure Stack

Azure Stack ist eine Hybrid Cloud-Plattform, die Sie Azure-Dienste über das Rechenzentrum Ihrer Organisation bereitstellen kann. Azure Stack dient zur Unterstützung von neuer Options für Ihre modernen Anwendungen in gängigen Szenarien, z. B. Rand, und nicht verbundenen Umgebungen oder bestimmte Sicherheits- und Compliance-Anforderungen erfüllen.

Abbildung 4-13 zeigt eine Übersicht über die hybride Cloud-Plattform, die Microsoft anbietet.

![Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure](./media/image13.jpg)

> **Abbildung 4-13.** Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure

Azure Stack wird in zwei Bereitstellungsoptionen zur Erfüllung Ihrer Anforderungen angeboten:

-   Azure Stack integrierte Systeme

-   Azure Stack Development Kits

### <a name="azure-stack-integrated-systems"></a>Azure Stack integrierte Systeme

Azure Stack integrierte Systeme werden im Rahmen einer Partnerschaft zwischen Microsoft und Hardwarepartnern angeboten. Die Partnerschaft erstellt eine Lösung, die von cloudbasierten Innovationen und komfortabler bietet, die Verwaltung ausgeglichen ist. Da es sich bei Azure Stack als integriertes System von Hardware und Software angeboten wird, erhalten Sie das richtige Maß an Flexibilität und Kontrolle bei der Einführung von Innovationen in der Cloud weiterhin. Azure Stack integrierte Systeme Größe von 4 bis zu 12 Knoten liegen, und Support wird vom Hardwarepartner und von Microsoft. Verwenden Sie Azure Stack integrierte Systeme, um neue Szenarien für Ihre produktionsworkloads zu implementieren.

### <a name="azure-stack-development-kit"></a>Azure Stack Development Kits

Microsoft Azure Stack Development Kit ist eine einzelknotenbereitstellung von Azure Stack, die Sie zum Evaluieren und Kennenlernen von Azure Stack verwenden können. Sie können auch Azure Stack Development Kit als entwicklerumgebung verwenden, verwenden, wobei können Sie entwickeln, mithilfe von APIs und Tools, die mit Azure konsistent sind. Azure Stack Development Kit ist nicht als produktionsumgebung verwendet werden soll.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Azure hybridcloud**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

-   **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

-   **Active Directory-Dienstkonten für Windows-Container**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

-   **Erstellen Sie einen Container mit Active Directory-Unterstützung**

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

-   **Lizenzieren von Azure-Hybridvorteil**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[Zurück](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Weiter](../walkthroughs-technical-get-started-overview.md)
