---
title: Migrieren Sie zu hybridcloudszenarien
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Migrieren Sie zu hybridcloudszenarien
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 3d6fc272854654d890559d5db032b05667627d94
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147345"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="cde76-103">Migrieren Sie zu hybridcloudszenarien</span><span class="sxs-lookup"><span data-stu-id="cde76-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="cde76-104">Einige Organisationen und Unternehmen können nicht einige seiner Anwendungen in öffentlichen Clouds wie Microsoft Azure oder jede andere öffentliche Cloud, die aufgrund von Bestimmungen oder ihre eigenen Richtlinien migriert.</span><span class="sxs-lookup"><span data-stu-id="cde76-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="cde76-105">Allerdings ist es wahrscheinlich, dass jedes Unternehmen davon profitieren kann, dass einige seiner Anwendungen in der öffentlichen Cloud und andere Anwendungen vor Ort.</span><span class="sxs-lookup"><span data-stu-id="cde76-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="cde76-106">Eine gemischte Umgebung kann jedoch zu führen Übermäßige Komplexität in Umgebungen, die aufgrund von verschiedenen Plattformen und Technologien, die in öffentlichen Clouds und lokale Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="cde76-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="cde76-107">Microsoft bietet die beste Hybrid Cloud-Lösung, eine in der Sie Ihre vorhandenen Assets optimieren können lokal und in der öffentlichen Cloud, während Sie Konsistenz in einer Azure hybridcloud zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="cde76-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="cde76-108">Sie können vorhandene Fähigkeiten zu maximieren und erhalten einen flexibel und einheitlichen Ansatz zum Erstellen von apps, die in der Cloud oder lokal, Dank der Azure Stack (lokal) und Azure (öffentliche Cloud) ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="cde76-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="cde76-109">Wenn es um Sicherheit geht, können Sie die Verwaltung und Sicherheit in Ihre hybridcloud zentralisieren.</span><span class="sxs-lookup"><span data-stu-id="cde76-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="cde76-110">Sie können gewinnen, Kontrolle über alle Ressourcen aus Ihrem Datencenter in die Cloud, indem einmaligen Anmeldung mit lokalen und cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="cde76-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="cde76-111">Sie erreichen dies durch das Erweitern des Active Directory in einer hybridcloud, und mit der identitätsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="cde76-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="cde76-112">Sie können schließlich verteilen und analysieren Sie Daten nahtlos, verwenden dieselben Abfragesprachen für Cloud- und lokalen Ressourcen und Anwenden von Analytics und Deep learning in Azure, um Ihre Daten unabhängig von der Quelle zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="cde76-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="cde76-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="cde76-113">Azure Stack</span></span>

<span data-ttu-id="cde76-114">Azure Stack ist eine Hybrid Cloud-Plattform, die Sie Azure-Dienste über das Rechenzentrum Ihrer Organisation bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cde76-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="cde76-115">Azure Stack dient zur Unterstützung von neuer Options für Ihre modernen Anwendungen in gängigen Szenarien, z. B. Rand, und nicht verbundenen Umgebungen oder bestimmte Sicherheits- und Compliance-Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="cde76-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="cde76-116">Abbildung 4-13 zeigt eine Übersicht über die hybride Cloud-Plattform, die Microsoft anbietet.</span><span class="sxs-lookup"><span data-stu-id="cde76-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure](./media/image13.jpg)

> <span data-ttu-id="cde76-118">**Abbildung 4-13.**</span><span class="sxs-lookup"><span data-stu-id="cde76-118">**Figure 4-13.**</span></span> <span data-ttu-id="cde76-119">Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure</span><span class="sxs-lookup"><span data-stu-id="cde76-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="cde76-120">Azure Stack wird in zwei Bereitstellungsoptionen zur Erfüllung Ihrer Anforderungen angeboten:</span><span class="sxs-lookup"><span data-stu-id="cde76-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

-   <span data-ttu-id="cde76-121">Azure Stack integrierte Systeme</span><span class="sxs-lookup"><span data-stu-id="cde76-121">Azure Stack integrated systems</span></span>

-   <span data-ttu-id="cde76-122">Azure Stack Development Kits</span><span class="sxs-lookup"><span data-stu-id="cde76-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="cde76-123">Azure Stack integrierte Systeme</span><span class="sxs-lookup"><span data-stu-id="cde76-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="cde76-124">Azure Stack integrierte Systeme werden im Rahmen einer Partnerschaft zwischen Microsoft und Hardwarepartnern angeboten.</span><span class="sxs-lookup"><span data-stu-id="cde76-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="cde76-125">Die Partnerschaft erstellt eine Lösung, die von cloudbasierten Innovationen und komfortabler bietet, die Verwaltung ausgeglichen ist.</span><span class="sxs-lookup"><span data-stu-id="cde76-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="cde76-126">Da es sich bei Azure Stack als integriertes System von Hardware und Software angeboten wird, erhalten Sie das richtige Maß an Flexibilität und Kontrolle bei der Einführung von Innovationen in der Cloud weiterhin.</span><span class="sxs-lookup"><span data-stu-id="cde76-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="cde76-127">Azure Stack integrierte Systeme Größe von 4 bis zu 12 Knoten liegen, und Support wird vom Hardwarepartner und von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cde76-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="cde76-128">Verwenden Sie Azure Stack integrierte Systeme, um neue Szenarien für Ihre produktionsworkloads zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="cde76-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="cde76-129">Azure Stack Development Kits</span><span class="sxs-lookup"><span data-stu-id="cde76-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="cde76-130">Microsoft Azure Stack Development Kit ist eine einzelknotenbereitstellung von Azure Stack, die Sie zum Evaluieren und Kennenlernen von Azure Stack verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cde76-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="cde76-131">Sie können auch Azure Stack Development Kit als entwicklerumgebung verwenden, verwenden, wobei können Sie entwickeln, mithilfe von APIs und Tools, die mit Azure konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="cde76-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="cde76-132">Azure Stack Development Kit ist nicht als produktionsumgebung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cde76-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="cde76-133">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="cde76-133">Additional resources</span></span>

-   <span data-ttu-id="cde76-134">**Azure hybridcloud**</span><span class="sxs-lookup"><span data-stu-id="cde76-134">**Azure hybrid cloud**</span></span>

    [https://www.microsoft.com/cloud-platform/hybrid-cloud](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   <span data-ttu-id="cde76-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="cde76-135">**Azure Stack**</span></span>

    [https://azure.microsoft.com/overview/azure-stack/](https://azure.microsoft.com/overview/azure-stack/)

-   <span data-ttu-id="cde76-136">**Active Directory-Dienstkonten für Windows-Container**</span><span class="sxs-lookup"><span data-stu-id="cde76-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    [https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   <span data-ttu-id="cde76-137">**Erstellen Sie einen Container mit Active Directory-Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="cde76-137">**Create a container with Active Directory support**</span></span>

    [https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   <span data-ttu-id="cde76-138">**Lizenzieren von Azure-Hybridvorteil**</span><span class="sxs-lookup"><span data-stu-id="cde76-138">**Azure Hybrid Benefit licensing**</span></span>

    [https://azure.microsoft.com/pricing/hybrid-use-benefit/](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
><span data-ttu-id="cde76-139">[Zurück](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Weiter](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cde76-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>