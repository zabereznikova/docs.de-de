---
title: Migrieren zu Hybridcloudszenarios
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Migration zu Hybrid Cloud Szenarios
ms.date: 04/30/2018
ms.openlocfilehash: 4348a9b538042fee7ebd9c08f480491f17425937
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394543"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="4ca3d-103">Migrieren zu Hybridcloudszenarios</span><span class="sxs-lookup"><span data-stu-id="4ca3d-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="4ca3d-104">Einige Organisationen und Unternehmen können einige Ihrer Anwendungen aufgrund von Bestimmungen oder ihrer eigenen Richtlinien nicht in öffentliche Clouds wie Microsoft Azure oder andere Public Cloud migrieren.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="4ca3d-105">Es ist jedoch wahrscheinlich, dass alle Organisationen davon profitieren können, dass einige Ihrer Anwendungen in der Public Cloud und anderen Anwendungen lokal vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="4ca3d-106">Eine gemischte Umgebung kann jedoch aufgrund verschiedener Plattformen und Technologien, die in öffentlichen Clouds und lokalen Umgebungen verwendet werden, zu einer übermäßigen Komplexität in Umgebungen führen.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="4ca3d-107">Microsoft bietet die beste Hybrid Cloud Lösung, bei der Sie Ihre vorhandenen Ressourcen lokal und im Public Cloud optimieren können, während Sie die Konsistenz in einem Azure-Hybrid Cloud gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="4ca3d-108">Dank Azure Stack (lokal) und Azure (Public Cloud) können Sie vorhandene Fähigkeiten maximieren und einen flexiblen, einheitlichen Ansatz zum Entwickeln von Apps nutzen, die in der Cloud oder lokal ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="4ca3d-109">Wenn es um die Sicherheit geht, können Sie die Verwaltung und Sicherheit über ihre Hybrid Cloud hinweg zentralisieren.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="4ca3d-110">Sie können die Kontrolle über alle Assets von Ihrem Rechenzentrum in die Cloud erhalten, indem Sie Single Sign-on für lokale und Cloud-apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="4ca3d-111">Dies erreichen Sie, indem Sie Active Directory auf eine Hybrid Cloud erweitern und die Identitätsverwaltung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="4ca3d-112">Schließlich können Sie Daten nahtlos verteilen und analysieren, die gleichen Abfrage Sprachen für Cloud-und lokale Ressourcen verwenden und Analysen und Deep Learning in Azure anwenden, um Ihre Daten unabhängig von ihrer Quelle zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="4ca3d-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="4ca3d-113">Azure Stack</span></span>

<span data-ttu-id="4ca3d-114">Azure Stack ist eine Hybrid Cloud Plattform, mit der Sie Azure-Dienste aus dem Rechenzentrum Ihrer Organisation bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="4ca3d-115">Azure Stack ist für die Unterstützung neuer Optionen für ihre modernen Anwendungen in wichtigen Szenarien konzipiert, z. b. bei Edge-und nicht verbundenen Umgebungen oder bei der Erfüllung spezifischer Sicherheits-und Konformitätsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="4ca3d-116">Abbildung 4-13 zeigt eine Übersicht über die echte Hybrid Cloud Plattform, die Microsoft bietet.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Diagramm der Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="4ca3d-118">**Abbildung 4-13.**</span><span class="sxs-lookup"><span data-stu-id="4ca3d-118">**Figure 4-13.**</span></span> <span data-ttu-id="4ca3d-119">Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure</span><span class="sxs-lookup"><span data-stu-id="4ca3d-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="4ca3d-120">Azure Stack wird in zwei Bereitstellungs Optionen angeboten, die Ihren Anforderungen entsprechen:</span><span class="sxs-lookup"><span data-stu-id="4ca3d-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="4ca3d-121">Azure Stack integrierter Systeme</span><span class="sxs-lookup"><span data-stu-id="4ca3d-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="4ca3d-122">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="4ca3d-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="4ca3d-123">Azure Stack integrierter Systeme</span><span class="sxs-lookup"><span data-stu-id="4ca3d-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="4ca3d-124">Azure Stack integrierte Systeme werden über eine Partnerschaft von Microsoft und Hardwarepartnern angeboten.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="4ca3d-125">Mit der Partnerschaft wird eine Lösung erstellt, die Innovationen in der Cloud bietet, die mit der Einfachheit der Verwaltung ausgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="4ca3d-126">Da Azure Stack als integriertes System von Hardware und Software angeboten wird, erhalten Sie die richtige Flexibilität und Kontrolle, während Sie trotzdem Innovationen aus der Cloud einführen.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="4ca3d-127">Azure Stack integrierte Systeme reichen von 4 bis 12 Knoten und werden vom Hardwarepartner und von Microsoft gemeinsam unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="4ca3d-128">Verwenden Sie Azure Stack integrierte Systeme, um neue Szenarien für Ihre produktionsworkloads zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="4ca3d-129">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="4ca3d-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="4ca3d-130">Microsoft Azure Stack Development Kit ist eine Bereitstellung von Azure Stack mit einem einzelnen Knoten, die Sie zum Auswerten und Kennenlernen von Azure Stack verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="4ca3d-131">Sie können auch Azure Stack Development Kit als Entwicklerumgebung verwenden, in der Sie mithilfe von APIs und Tools entwickeln können, die mit Azure konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="4ca3d-132">Azure Stack Development Kit ist nicht für die Verwendung als Produktionsumgebung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4ca3d-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4ca3d-133">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4ca3d-133">Additional resources</span></span>

- <span data-ttu-id="4ca3d-134">**Azure-Hybrid Cloud**</span><span class="sxs-lookup"><span data-stu-id="4ca3d-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="4ca3d-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="4ca3d-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="4ca3d-136">**Active Directory-Dienst Konten für Windows-Container**</span><span class="sxs-lookup"><span data-stu-id="4ca3d-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="4ca3d-137">**Erstellen eines Containers mit Active Directory-Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="4ca3d-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="4ca3d-138">**Azure-Hybridvorteil Lizenzierung**</span><span class="sxs-lookup"><span data-stu-id="4ca3d-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="4ca3d-139">[Zurück](life-cycle-ci-cd-pipelines-devops-tools.md)
>[Weiter](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4ca3d-139">[Previous](life-cycle-ci-cd-pipelines-devops-tools.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
