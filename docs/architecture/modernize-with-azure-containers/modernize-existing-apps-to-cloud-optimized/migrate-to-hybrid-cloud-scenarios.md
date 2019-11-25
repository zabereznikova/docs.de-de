---
title: Migrieren zu Hybridcloudszenarios
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Migrieren zu Hybridcloudszenarios
ms.date: 04/30/2018
ms.openlocfilehash: 4348a9b538042fee7ebd9c08f480491f17425937
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "72394543"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="fd18c-103">Migrieren zu Hybridcloudszenarios</span><span class="sxs-lookup"><span data-stu-id="fd18c-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="fd18c-104">Manche Organisationen und Unternehmen können einige Ihrer Anwendungen aufgrund von Bestimmungen oder ihrer eigenen Richtlinien nicht in öffentliche Clouds wie Microsoft Azure oder eine andere öffentliche Cloud migrieren.</span><span class="sxs-lookup"><span data-stu-id="fd18c-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="fd18c-105">Es ist jedoch wahrscheinlich, dass alle Organisationen davon profitieren können, dass sich einige Ihrer Anwendungen in der öffentlichen Cloud befinden und andere Anwendungen lokal vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fd18c-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="fd18c-106">Eine gemischte Umgebung kann jedoch aufgrund verschiedener Plattformen und Technologien, die in öffentlichen Clouds im Gegensatz zu lokalen Umgebungen verwendet werden, zu übermäßiger Komplexität in Umgebungen führen.</span><span class="sxs-lookup"><span data-stu-id="fd18c-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="fd18c-107">Microsoft bietet die beste Hybrid Cloud-Lösung, bei der Sie Ihre vorhandenen Ressourcen lokal und in der öffentlichen Cloud optimieren können, während Sie die Konsistenz in einer Azure Hybrid Cloud gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="fd18c-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="fd18c-108">Dank Azure Stack (lokal) und Azure (Public Cloud) können Sie vorhandene Fähigkeiten maximieren und einen flexiblen, einheitlichen Ansatz zum Entwickeln von Apps nutzen, die in der Cloud oder lokal ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="fd18c-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="fd18c-109">Hinsichtlich Sicherheit können Sie die Verwaltung und Sicherheit in der gesamten Hybrid Cloud zentralisieren.</span><span class="sxs-lookup"><span data-stu-id="fd18c-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="fd18c-110">Sie können die Kontrolle über alle Ressourcen erhalten, von Ihrem Rechenzentrum bis in die Cloud, indem Sie einmaliges Anmelden für lokale und Cloud-Apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fd18c-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="fd18c-111">Dies erreichen Sie, indem Sie Active Directory in eine Hybrid Cloud erweitern und Identitätsverwaltung verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd18c-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="fd18c-112">Schließlich können Sie Daten nahtlos verteilen und analysieren, dieselben Abfragesprachen für Cloud- und lokale Ressourcen verwenden sowie Analysen und Deep Learning in Azure anwenden, um Ihre Daten unabhängig von deren Quelle anzureichern.</span><span class="sxs-lookup"><span data-stu-id="fd18c-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="fd18c-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="fd18c-113">Azure Stack</span></span>

<span data-ttu-id="fd18c-114">Azure Stack ist eine Hybrid Cloud-Plattform, mit der Sie Azure-Dienste über das Rechenzentrum Ihrer Organisation bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="fd18c-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="fd18c-115">Azure Stack soll in wichtigen Szenarien (etwa in Edge-Umgebungen und nicht verbundenen Umgebungen) neue Möglichkeiten für Ihre modernen Anwendungen unterstützen und zur Erfüllung spezifischer Sicherheits- und Konformitätsanforderungen beitragen.</span><span class="sxs-lookup"><span data-stu-id="fd18c-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="fd18c-116">Abbildung 4-13 zeigt eine Übersicht über die echte Hybrid Cloud-Plattform, die Microsoft bietet.</span><span class="sxs-lookup"><span data-stu-id="fd18c-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Diagramm der Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="fd18c-118">**Abbildung 4-13.**</span><span class="sxs-lookup"><span data-stu-id="fd18c-118">**Figure 4-13.**</span></span> <span data-ttu-id="fd18c-119">Microsoft Hybrid Cloud-Plattform mit Azure Stack und Azure</span><span class="sxs-lookup"><span data-stu-id="fd18c-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="fd18c-120">Azure Stack wird in zwei auf Ihre Anforderungen abgestimmten Bereitstellungsoptionen angeboten:</span><span class="sxs-lookup"><span data-stu-id="fd18c-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="fd18c-121">Integrierte Azure Stack-Systeme</span><span class="sxs-lookup"><span data-stu-id="fd18c-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="fd18c-122">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="fd18c-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="fd18c-123">Integrierte Azure Stack-Systeme</span><span class="sxs-lookup"><span data-stu-id="fd18c-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="fd18c-124">Integrierte Azure Stack-Systeme werden im Rahmen einer Partnerschaft zwischen Microsoft und Hardwarepartnern angeboten.</span><span class="sxs-lookup"><span data-stu-id="fd18c-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="fd18c-125">Durch diese Partnerschaft entsteht eine Lösung mit cloudbasierten Innovationen und komfortabler Computeverwaltung.</span><span class="sxs-lookup"><span data-stu-id="fd18c-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="fd18c-126">Bei Azure Stack handelt es sich um ein integriertes System aus Hardware und Software. Somit bietet die Plattform genau das richtige Maß an Flexibilität und Kontrolle bei gleichzeitiger Bereitstellung von cloudbasierten Innovationen.</span><span class="sxs-lookup"><span data-stu-id="fd18c-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="fd18c-127">Integrierte Azure Stack-Systeme haben eine Größe von 4 bis 12 Knoten, und der Support wird vom Hardwarepartner und von Microsoft gemeinsam bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fd18c-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="fd18c-128">Mit integrierten Azure Stack-Systemen ermöglichen Sie die Implementierung neuer Szenarien für Ihre Produktionsworkloads.</span><span class="sxs-lookup"><span data-stu-id="fd18c-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="fd18c-129">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="fd18c-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="fd18c-130">Microsoft Azure Stack Development Kit ist eine Einzelknotenbereitstellung von Azure Stack, mit der Sie Azure Stack auswerten und näher kennenlernen können.</span><span class="sxs-lookup"><span data-stu-id="fd18c-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="fd18c-131">Sie können auch Azure Stack Development Kit als Entwicklerumgebung verwenden, in der Sie anhand von mit Azure konsistenten APIs und Tools Entwicklungsarbeiten durchführen können.</span><span class="sxs-lookup"><span data-stu-id="fd18c-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="fd18c-132">Azure Stack Development Kit ist nicht für die Verwendung als Produktionsumgebung konzipiert.</span><span class="sxs-lookup"><span data-stu-id="fd18c-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="fd18c-133">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="fd18c-133">Additional resources</span></span>

- <span data-ttu-id="fd18c-134">**Azure Hybrid Cloud**</span><span class="sxs-lookup"><span data-stu-id="fd18c-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="fd18c-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="fd18c-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="fd18c-136">**Active Directory-Dienstkonten für Windows-Container**</span><span class="sxs-lookup"><span data-stu-id="fd18c-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="fd18c-137">**Erstellen eines Containers mit Active Directory-Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="fd18c-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="fd18c-138">**Azure-Hybridvorteil – Lizenzierung**</span><span class="sxs-lookup"><span data-stu-id="fd18c-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="fd18c-139">[Zurück](life-cycle-ci-cd-pipelines-devops-tools.md)
>[Weiter](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fd18c-139">[Previous](life-cycle-ci-cd-pipelines-devops-tools.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
