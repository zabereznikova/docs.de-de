---
title: Migrieren Sie zu Hybrid Cloud-Szenarien
description: .NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Migrieren Sie zu Hybrid Cloud-Szenarien
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/2/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a2fc5a2118736d3491a5a0731e47c697edd674f1
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="c0d0e-103">Migrieren Sie zu Hybrid Cloud-Szenarien</span><span class="sxs-lookup"><span data-stu-id="c0d0e-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="c0d0e-104">Einige Organisationen und Unternehmen können nicht einige ihrer Anwendungen auf Öffentliche Clouds wie Microsoft Azure oder anderen öffentlichen Cloud aufgrund von Vorschriften oder ihre eigenen Richtlinien migriert.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="c0d0e-105">Allerdings ist es wahrscheinlich, dass jedes Unternehmen müssen einige ihrer Anwendungen in der öffentlichen Cloud sowie andere Anwendungen lokal profitieren könnten.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="c0d0e-106">Aber eine gemischte Umgebung kann dazu führen, dass Übermäßige Komplexität in Umgebungen, die aufgrund von verschiedenen Plattformen und in öffentlichen Clouds im Vergleich zu lokalen Umgebungen verwendeten Technologien.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="c0d0e-107">Microsoft bietet die beste Hybrid Cloud-Lösung, eine in der Sie Ihre vorhandenen Ressourcen optimieren können lokal und in der öffentlichen Cloud, während Sie sicherstellen, dass die Konsistenz in einer Azure hybridcloud.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="c0d0e-108">Sie können vorhandene Fähigkeiten zu maximieren und erhalten einen flexiblen, einheitlichen Ansatz zum Erstellen von apps, die in der Cloud oder lokal, aufgrund der Azure-Stack (lokal) und Azure (öffentliche Cloud) ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="c0d0e-109">Bei der Sicherheit, können Sie die Verwaltungs- und Sicherheitsfunktionen über Ihre hybridcloud zentralisieren.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="c0d0e-110">Sie können Kontrolle über alle Objekte aus Ihrem Datencenter in die Cloud durch einmaliges Anmelden für den Zugriff auf lokale Bereitstellung abrufen und cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="c0d0e-111">Sie erreichen dies durch das Erweitern des Active Directory in einer hybridcloud und mithilfe von Identitätsmanagement.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="c0d0e-112">Sie können schließlich verteilen und nahtlos Analysieren von Daten, Abfragesprachen für Cloud- und lokalen Ressourcen verwenden und Anwenden von Analysen und umfassende learning in Azure, um Ihre Daten, unabhängig von der Updatequelle optimal zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="c0d0e-113">Azure-Stapel</span><span class="sxs-lookup"><span data-stu-id="c0d0e-113">Azure Stack</span></span>

<span data-ttu-id="c0d0e-114">Azure Stapel ist ein Hybrid-Cloud-Plattform, mit der Azure-Dienste von Ihrer Organisation Datacenter übermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="c0d0e-115">Azure-Stapel dient zur Unterstützung der neuer Optionen für modernen Anwendungen in der wichtigsten Szenarien, z. B. Rand und nicht verbundenen Umgebungen oder Besprechung bestimmte Sicherheits- und Compliance-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="c0d0e-116">Abbildung 4 – 13 zeigt eine Übersicht der "true" Hybrid Cloud-Plattform, die Microsoft anbietet.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Microsoft Hybrid Cloud-Plattform mit Azure-Stapel und Azure](./media/image13.jpg)

> <span data-ttu-id="c0d0e-118">**Abbildung 4-13.**</span><span class="sxs-lookup"><span data-stu-id="c0d0e-118">**Figure 4-13.**</span></span> <span data-ttu-id="c0d0e-119">Microsoft Hybrid Cloud-Plattform mit Azure-Stapel und Azure</span><span class="sxs-lookup"><span data-stu-id="c0d0e-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="c0d0e-120">Azure-Stapel ist in zwei Bereitstellungsoptionen für Ihre Anforderungen angeboten:</span><span class="sxs-lookup"><span data-stu-id="c0d0e-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

-   <span data-ttu-id="c0d0e-121">Azure-Stapel integrierte Systeme</span><span class="sxs-lookup"><span data-stu-id="c0d0e-121">Azure Stack integrated systems</span></span>

-   <span data-ttu-id="c0d0e-122">Azure-Stapel Development Kits</span><span class="sxs-lookup"><span data-stu-id="c0d0e-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="c0d0e-123">Azure-Stapel integrierte Systeme</span><span class="sxs-lookup"><span data-stu-id="c0d0e-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="c0d0e-124">Azure Stapel integriert Systeme werden durch eine Partnerschaft Partner von Microsoft und Hardware angeboten.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="c0d0e-125">Die Partnerschaft erstellt eine Projektmappe, in der Cloud paced Innovation angeboten, die mit der Einfachheit halber in der Verwaltungsgruppe ausgeglichen wird.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="c0d0e-126">Da Azure Stapel als integrierte System von Hardware und Software angeboten wird, erhalten Sie die richtige Menge an Flexibilität und Kontrolle, während noch einführen Innovation aus der Cloud.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="c0d0e-127">Azure Stapel integriert Systeme in der Größe von 4 bis 12 Knoten im Bereich und werden gemeinsam von der Hardware-Partner und Microsoft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="c0d0e-128">Verwenden Sie Systeme von Azure-Stapel integriert, um neue Szenarien für die produktive Arbeitslast zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="c0d0e-129">Azure-Stapel Development Kits</span><span class="sxs-lookup"><span data-stu-id="c0d0e-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="c0d0e-130">Microsoft Azure Stapel Development Kit ist ein Einzelknoten-Bereitstellung von Azure-Stapel, die Sie verwenden können, um auszuwerten, und erfahren Sie mehr über Azure-Stapel.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="c0d0e-131">Sie können auch Azure Stapel Development Kit als entwicklerumgebung verwenden, in denen Sie können mithilfe von APIs und Tools, die mit Azure konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="c0d0e-132">Azure Stapel Development Kit ist nicht als einer produktiven Umgebung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="c0d0e-133">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c0d0e-133">Additional resources</span></span>

-   <span data-ttu-id="c0d0e-134">**Azure hybridcloud**</span><span class="sxs-lookup"><span data-stu-id="c0d0e-134">**Azure hybrid cloud**</span></span>

    [https://www.microsoft.com/cloud-platform/hybrid-cloud](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   <span data-ttu-id="c0d0e-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="c0d0e-135">**Azure Stack**</span></span>

    [https://azure.microsoft.com/overview/azure-stack/](https://azure.microsoft.com/overview/azure-stack/)

-   <span data-ttu-id="c0d0e-136">**Active Directory-Dienstkonten für Windows-Containern**</span><span class="sxs-lookup"><span data-stu-id="c0d0e-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    [https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   <span data-ttu-id="c0d0e-137">**Erstellen Sie einen Container mit Active Directory-Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="c0d0e-137">**Create a container with Active Directory support**</span></span>

    [https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   <span data-ttu-id="c0d0e-138">**Lizenzierung von Azure Hybrid-Vorteil**</span><span class="sxs-lookup"><span data-stu-id="c0d0e-138">**Azure Hybrid Benefit licensing**</span></span>

    [https://azure.microsoft.com/pricing/hybrid-use-benefit/](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
<span data-ttu-id="c0d0e-139">[Zurück](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Weiter](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c0d0e-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
