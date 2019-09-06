---
title: Migrieren zu Hybridcloudszenarios
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Migration zu Hybrid Cloud Szenarios
ms.date: 04/30/2018
ms.openlocfilehash: 313608c41427b3833bbc873398595ceb37bd7c7d
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373944"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>Migrieren zu Hybridcloudszenarios

Einige Organisationen und Unternehmen können einige Ihrer Anwendungen aufgrund von Bestimmungen oder ihrer eigenen Richtlinien nicht in öffentliche Clouds wie Microsoft Azure oder andere Public Cloud migrieren. Es ist jedoch wahrscheinlich, dass alle Organisationen davon profitieren können, dass einige Ihrer Anwendungen in der Public Cloud und anderen Anwendungen lokal vorhanden sind. Eine gemischte Umgebung kann jedoch aufgrund verschiedener Plattformen und Technologien, die in öffentlichen Clouds und lokalen Umgebungen verwendet werden, zu einer übermäßigen Komplexität in Umgebungen führen.

Microsoft bietet die beste Hybrid Cloud Lösung, bei der Sie Ihre vorhandenen Ressourcen lokal und im Public Cloud optimieren können, während Sie die Konsistenz in einem Azure-Hybrid Cloud gewährleisten. Dank Azure Stack (lokal) und Azure (Public Cloud) können Sie vorhandene Fähigkeiten maximieren und einen flexiblen, einheitlichen Ansatz zum Entwickeln von Apps nutzen, die in der Cloud oder lokal ausgeführt werden können.

Wenn es um die Sicherheit geht, können Sie die Verwaltung und Sicherheit über ihre Hybrid Cloud hinweg zentralisieren. Sie können die Kontrolle über alle Assets von Ihrem Rechenzentrum in die Cloud erhalten, indem Sie Single Sign-on für lokale und Cloud-apps bereitstellen. Dies erreichen Sie, indem Sie Active Directory auf eine Hybrid Cloud erweitern und die Identitätsverwaltung verwenden.

Schließlich können Sie Daten nahtlos verteilen und analysieren, die gleichen Abfrage Sprachen für Cloud-und lokale Ressourcen verwenden und Analysen und Deep Learning in Azure anwenden, um Ihre Daten unabhängig von ihrer Quelle zu erweitern.

## <a name="azure-stack"></a>Azure Stack

Azure Stack ist eine Hybrid Cloud Plattform, mit der Sie Azure-Dienste aus dem Rechenzentrum Ihrer Organisation bereitstellen können. Azure Stack ist für die Unterstützung neuer Optionen für ihre modernen Anwendungen in wichtigen Szenarien konzipiert, z. b. bei Edge-und nicht verbundenen Umgebungen oder bei der Erfüllung spezifischer Sicherheits-und Konformitätsanforderungen.

Abbildung 4-13 zeigt eine Übersicht über die echte Hybrid Cloud Plattform, die Microsoft bietet.

![Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure](./media/image13.jpg)

**Abbildung 4-13.** Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure

Azure Stack wird in zwei Bereitstellungs Optionen angeboten, die Ihren Anforderungen entsprechen:

- Azure Stack integrierter Systeme

- Azure Stack Development Kit

### <a name="azure-stack-integrated-systems"></a>Azure Stack integrierter Systeme

Azure Stack integrierte Systeme werden über eine Partnerschaft von Microsoft und Hardwarepartnern angeboten. Mit der Partnerschaft wird eine Lösung erstellt, die Innovationen in der Cloud bietet, die mit der Einfachheit der Verwaltung ausgeglichen werden. Da Azure Stack als integriertes System von Hardware und Software angeboten wird, erhalten Sie die richtige Flexibilität und Kontrolle, während Sie trotzdem Innovationen aus der Cloud einführen. Azure Stack integrierte Systeme reichen von 4 bis 12 Knoten und werden vom Hardwarepartner und von Microsoft gemeinsam unterstützt. Verwenden Sie Azure Stack integrierte Systeme, um neue Szenarien für Ihre produktionsworkloads zu implementieren.

### <a name="azure-stack-development-kit"></a>Azure Stack Development Kit

Microsoft Azure Stack Development Kit ist eine Bereitstellung von Azure Stack mit einem einzelnen Knoten, die Sie zum Auswerten und Kennenlernen von Azure Stack verwenden können. Sie können auch Azure Stack Development Kit als Entwicklerumgebung verwenden, in der Sie mithilfe von APIs und Tools entwickeln können, die mit Azure konsistent sind. Azure Stack Development Kit ist nicht für die Verwendung als Produktionsumgebung vorgesehen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Azure-Hybrid Cloud**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

- **Active Directory-Dienst Konten für Windows-Container**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- **Erstellen eines Containers mit Active Directory-Unterstützung**

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- **Azure-Hybridvorteil Lizenzierung**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[Zurück](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Weiter](../walkthroughs-technical-get-started-overview.md)
