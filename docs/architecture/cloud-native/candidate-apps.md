---
title: Kandidaten-Apps für Cloud native
description: Erfahren Sie, welche Anwendungstypen von einem Cloud-nativen Ansatz profitieren
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 8e58f5bd3aa0a4503ea73ab454e42e863eb0bb5d
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805612"
---
# <a name="candidate-apps-for-cloud-native"></a><span data-ttu-id="b4781-103">Kandidaten-Apps für Cloud native</span><span class="sxs-lookup"><span data-stu-id="b4781-103">Candidate apps for cloud native</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="b4781-104">Schauen Sie sich die Apps in Ihrem Portfolio an.</span><span class="sxs-lookup"><span data-stu-id="b4781-104">Look at the apps in your portfolio.</span></span> <span data-ttu-id="b4781-105">Wie viele von ihnen qualifizieren sich für eine Cloud-native Architektur?</span><span class="sxs-lookup"><span data-stu-id="b4781-105">How many of them qualify for a cloud-native architecture?</span></span> <span data-ttu-id="b4781-106">Alle genannten?</span><span class="sxs-lookup"><span data-stu-id="b4781-106">All of them?</span></span> <span data-ttu-id="b4781-107">Vielleicht einige?</span><span class="sxs-lookup"><span data-stu-id="b4781-107">Perhaps some?</span></span>

<span data-ttu-id="b4781-108">Wenn Sie eine Kosten-Nutzen-Analyse anwenden, besteht eine gute Chance, dass die meisten das saftige Preisschild, das für die Cloud-Native erforderlich ist, nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b4781-108">Applying a cost/benefit analysis, there's a good chance that most wouldn't support the hefty price tag required to be cloud native.</span></span> <span data-ttu-id="b4781-109">Die Kosten für Cloud-Nativ würden den geschäftlichen Wert der Anwendung bei weitem übersteigen.</span><span class="sxs-lookup"><span data-stu-id="b4781-109">The cost of being cloud native would far exceed the business value of the application.</span></span>

<span data-ttu-id="b4781-110">Welche Art von Anwendung könnte ein Kandidat für Cloud Native sein?</span><span class="sxs-lookup"><span data-stu-id="b4781-110">What type of application might be a candidate for cloud native?</span></span>

- <span data-ttu-id="b4781-111">Ein großes, strategisches Unternehmenssystem, das Geschäftsfähigkeiten/-features ständig weiterentwickeln muss</span><span class="sxs-lookup"><span data-stu-id="b4781-111">A large, strategic enterprise system that needs to constantly evolve business capabilities/features</span></span>

- <span data-ttu-id="b4781-112">Eine Anwendung, die eine hohe Freigabegeschwindigkeit erfordert - mit hoher Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b4781-112">An application that requires a high release velocity - with high confidence</span></span>

- <span data-ttu-id="b4781-113">Ein System, bei dem einzelne Funktionen *ohne* vollständige Umschichtung des gesamten Systems freigegeben werden müssen</span><span class="sxs-lookup"><span data-stu-id="b4781-113">A system with where individual features must release *without* a full redeployment of the entire system</span></span>

- <span data-ttu-id="b4781-114">Eine Anwendung, die von Teams mit Expertise in verschiedenen Technologie-Stacks entwickelt wurde</span><span class="sxs-lookup"><span data-stu-id="b4781-114">An application developed by teams with expertise in different technology stacks</span></span>

- <span data-ttu-id="b4781-115">Eine Anwendung mit Komponenten, die unabhängig skaliert werden müssen</span><span class="sxs-lookup"><span data-stu-id="b4781-115">An application with components that must scale independently</span></span>

<span data-ttu-id="b4781-116">Dann gibt es legacy Systeme.</span><span class="sxs-lookup"><span data-stu-id="b4781-116">Then there are legacy systems.</span></span> <span data-ttu-id="b4781-117">Obwohl wir alle gerne neue Anwendungen erstellen möchten, sind wir häufig für die Modernisierung von Legacy-Workloads verantwortlich, die für das Unternehmen von entscheidender Bedeutung sind.</span><span class="sxs-lookup"><span data-stu-id="b4781-117">While we'd all like to build new applications, we're often responsible for modernizing legacy workloads that are critical to the business.</span></span> <span data-ttu-id="b4781-118">Im Laufe der Zeit kann eine Legacyanwendung in Microservices zerlegt, containerisiert und schließlich in eine Cloud-native Architektur "neu platformiert" werden.</span><span class="sxs-lookup"><span data-stu-id="b4781-118">Over time, a legacy application could be decomposed into microservices, containerized, and ultimately "replatformed" into a cloud-native architecture.</span></span>

### <a name="modernizing-legacy-apps"></a><span data-ttu-id="b4781-119">Modernisierung von Legacy-Apps</span><span class="sxs-lookup"><span data-stu-id="b4781-119">Modernizing legacy apps</span></span>

<span data-ttu-id="b4781-120">Das kostenlose Microsoft-E-Book [Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) bietet Anleitungen für die Migration lokaler Workloads in die Cloud.</span><span class="sxs-lookup"><span data-stu-id="b4781-120">The free Microsoft e-book [Modernize existing .NET applications with Azure cloud and Windows Containers](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) provides guidance for migrating on-premises workloads into cloud.</span></span> <span data-ttu-id="b4781-121">Abbildung 1-10 zeigt, dass es keine einzige Einheitsstrategie für die Modernisierung älterer Anwendungen gibt.</span><span class="sxs-lookup"><span data-stu-id="b4781-121">Figure 1-10 shows that there isn't a single, one-size-fits-all strategy for modernizing legacy applications.</span></span>

![Strategien für die Migration von Legacy-Workloads](./media/strategies-for-migrating-legacy-workloads.png)

<span data-ttu-id="b4781-123">**Abbildung 1-10**.</span><span class="sxs-lookup"><span data-stu-id="b4781-123">**Figure 1-10**.</span></span> <span data-ttu-id="b4781-124">Strategien für die Migration von Legacy-Workloads</span><span class="sxs-lookup"><span data-stu-id="b4781-124">Strategies for migrating legacy workloads</span></span>

<span data-ttu-id="b4781-125">Monolithische Apps, die nicht kritisch sind, profitieren größtenteils von einer schnellen Migration mit["Cloud Infrastructure-Ready "Cloud Infrastructure".](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)</span><span class="sxs-lookup"><span data-stu-id="b4781-125">Monolithic apps that are non-critical largely benefit from a quick lift-and-shift ([Cloud Infrastructure-Ready](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)) migration.</span></span> <span data-ttu-id="b4781-126">Hier wird die lokale Workload ohne Änderungen auf einer cloudbasierten VM wieder gehostet.</span><span class="sxs-lookup"><span data-stu-id="b4781-126">Here, the on-premises workload is rehosted to a cloud-based VM, without changes.</span></span> <span data-ttu-id="b4781-127">Bei diesem Ansatz wird das [IaaS-Modell (Infrastructure as a Service) verwendet.](https://azure.microsoft.com/overview/what-is-iaas/)</span><span class="sxs-lookup"><span data-stu-id="b4781-127">This approach uses the [IaaS (Infrastructure as a Service) model](https://azure.microsoft.com/overview/what-is-iaas/).</span></span> <span data-ttu-id="b4781-128">Azure enthält mehrere Tools wie [Azure Migrate](https://azure.microsoft.com/services/azure-migrate/), Azure [Site Recovery](https://azure.microsoft.com/services/site-recovery/)und Azure Database [Migration Service,](https://azure.microsoft.com/campaigns/database-migration/) um eine solche Verschiebung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="b4781-128">Azure includes several tools such as [Azure Migrate](https://azure.microsoft.com/services/azure-migrate/), [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/), and [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) to make such a move easier.</span></span> <span data-ttu-id="b4781-129">Obwohl diese Strategie einige Kosteneinsparungen bringen kann, wurden solche Anwendungen in der Regel nicht entwickelt, um die Vorteile des Cloud Computing freizuschalten und zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="b4781-129">While this strategy can yield some cost savings, such applications typically weren't architected to unlock and leverage the benefits of cloud computing.</span></span>

<span data-ttu-id="b4781-130">Monolithische Apps, die für das Unternehmen von entscheidender Bedeutung sind, profitieren häufig von einer verbesserten Migration mit Lift-and-Shift (*Cloud Optimized*).</span><span class="sxs-lookup"><span data-stu-id="b4781-130">Monolithic apps that are critical to the business oftentimes benefit from an enhanced lift-and-shift (*Cloud Optimized*) migration.</span></span> <span data-ttu-id="b4781-131">Dieser Ansatz umfasst Bereitstellungsoptimierungen, die wichtige Clouddienste ermöglichen , ohne die Kernarchitektur der Anwendung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b4781-131">This approach includes deployment optimizations that enable key cloud services - without changing the core architecture of the application.</span></span> <span data-ttu-id="b4781-132">Sie können die Anwendung z. B. [containerisieren](https://docs.microsoft.com/virtualization/windowscontainers/about/) und in einem Containerorchestrator bereitstellen, z. B. [Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/), der weiter unten in diesem Buch erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="b4781-132">For example, you might [containerize](https://docs.microsoft.com/virtualization/windowscontainers/about/) the application and deploy it to a container orchestrator, like [Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/), discussed later in this book.</span></span> <span data-ttu-id="b4781-133">Einmal in der Cloud, kann die Anwendung andere Clouddienste wie Datenbanken, Nachrichtenwarteschlangen, Überwachung und verteiltes Zwischenspeichern nutzen.</span><span class="sxs-lookup"><span data-stu-id="b4781-133">Once in the cloud, the application could consume other cloud services such as databases, message queues, monitoring, and distributed caching.</span></span>

<span data-ttu-id="b4781-134">Schließlich könnten monolithische Apps, die strategische Unternehmensfunktionen ausführen, am besten von einem *Cloud-Native-Ansatz* profitieren, der Gegenstand dieses Buches ist.</span><span class="sxs-lookup"><span data-stu-id="b4781-134">Finally, monolithic apps that perform strategic enterprise functions might best benefit from a *Cloud-Native* approach, the subject of this book.</span></span> <span data-ttu-id="b4781-135">Dieser Ansatz bietet Agilität und Geschwindigkeit.</span><span class="sxs-lookup"><span data-stu-id="b4781-135">This approach provides agility and velocity.</span></span> <span data-ttu-id="b4781-136">Aber es kostet die Neu-, Neuarchitektur und das Umschreiben von Code.</span><span class="sxs-lookup"><span data-stu-id="b4781-136">But, it comes at a cost of replatforming, rearchitecting, and rewriting code.</span></span>

<span data-ttu-id="b4781-137">Wenn Sie und Ihr Team einen Cloud-nativen Ansatz für angemessen halten, müssen Sie die Entscheidung mit Ihrer Organisation rationalisieren.</span><span class="sxs-lookup"><span data-stu-id="b4781-137">If you and your team believe a cloud-native approach is appropriate, it behooves you to rationalize the decision with your organization.</span></span> <span data-ttu-id="b4781-138">Was genau ist das Geschäftsproblem, das ein Cloud-nativer Ansatz lösen wird?</span><span class="sxs-lookup"><span data-stu-id="b4781-138">What exactly is the business problem that a cloud-native approach will solve?</span></span> <span data-ttu-id="b4781-139">Wie würde sie sich an den geschäftlichen Bedürfnissen orientieren?</span><span class="sxs-lookup"><span data-stu-id="b4781-139">How would it align with business needs?</span></span>

- <span data-ttu-id="b4781-140">Schnelle Veröffentlichungen von Funktionen mit erhöhtem Selbstvertrauen?</span><span class="sxs-lookup"><span data-stu-id="b4781-140">Rapid releases of features with increased confidence?</span></span>

- <span data-ttu-id="b4781-141">Feinkörnige Skalierbarkeit - effizientere Nutzung von Ressourcen?</span><span class="sxs-lookup"><span data-stu-id="b4781-141">Fine-grained scalability - more efficient usage of resources?</span></span>

- <span data-ttu-id="b4781-142">Verbesserte Systemresilienz?</span><span class="sxs-lookup"><span data-stu-id="b4781-142">Improved system resiliency?</span></span>

- <span data-ttu-id="b4781-143">Verbesserte Systemleistung?</span><span class="sxs-lookup"><span data-stu-id="b4781-143">Improved system performance?</span></span>

- <span data-ttu-id="b4781-144">Mehr Einblick in Vorgänge?</span><span class="sxs-lookup"><span data-stu-id="b4781-144">More visibility into operations?</span></span>

- <span data-ttu-id="b4781-145">Verschmelzen Sie Entwicklungsplattformen und Datenspeicher, um das beste Tool für den Job zu finden?</span><span class="sxs-lookup"><span data-stu-id="b4781-145">Blend development platforms and data stores to arrive at the best tool for the job?</span></span>

- <span data-ttu-id="b4781-146">Zukunftssichere Anwendungsinvestition?</span><span class="sxs-lookup"><span data-stu-id="b4781-146">Future-proof application investment?</span></span>

<span data-ttu-id="b4781-147">Die richtige Migrationsstrategie hängt von den organisatorischen Prioritäten und den Systemen ab, auf die Sie abzielen.</span><span class="sxs-lookup"><span data-stu-id="b4781-147">The right migration strategy depends on organizational priorities and the systems you're targeting.</span></span> <span data-ttu-id="b4781-148">Für viele kann es kostengünstiger sein, eine monolithische Anwendung in der Cloud zu optimieren oder einer N-Tier-App grobkörnige Dienste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b4781-148">For many, it may be more cost effective to cloud-optimize a monolithic application or add coarse-grained services to an N-Tier app.</span></span> <span data-ttu-id="b4781-149">In diesen Fällen können Sie weiterhin die Cloud-PaaS-Funktionen, wie sie von Azure App Service angeboten werden, voll ausschöpfen.</span><span class="sxs-lookup"><span data-stu-id="b4781-149">In these cases, you can still make full use of cloud PaaS capabilities like the ones offered by Azure App Service.</span></span>

## <a name="summary"></a><span data-ttu-id="b4781-150">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b4781-150">Summary</span></span>

<span data-ttu-id="b4781-151">In diesem Kapitel haben wir Cloud-Native Computing eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b4781-151">In this chapter, we introduced cloud-native computing.</span></span> <span data-ttu-id="b4781-152">Wir haben eine Definition zusammen mit den wichtigsten Funktionen bereitgestellt, die eine cloudnative Anwendung antreiben.</span><span class="sxs-lookup"><span data-stu-id="b4781-152">We provided a definition along with the key capabilities that drive a cloud-native application.</span></span> <span data-ttu-id="b4781-153">Wir haben uns die Arten von Anwendungen angesehen, die diese Investition und diesen Aufwand rechtfertigen könnten.</span><span class="sxs-lookup"><span data-stu-id="b4781-153">We looked at the types of applications that might justify this investment and effort.</span></span>

<span data-ttu-id="b4781-154">Mit der Einführung im Rücken tauchen wir nun in einen viel detaillierteren Blick auf Cloud Native ein.</span><span class="sxs-lookup"><span data-stu-id="b4781-154">With the introduction behind, we now dive into a much more detailed look at cloud native.</span></span>

### <a name="references"></a><span data-ttu-id="b4781-155">References</span><span class="sxs-lookup"><span data-stu-id="b4781-155">References</span></span>

- [<span data-ttu-id="b4781-156">Cloud Native Computing Foundation</span><span class="sxs-lookup"><span data-stu-id="b4781-156">Cloud Native Computing Foundation</span></span>](https://www.cncf.io/)

- [<span data-ttu-id="b4781-157">.NET Microservices: Architektur für containerisierte .NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b4781-157">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [<span data-ttu-id="b4781-158">Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows Containers</span><span class="sxs-lookup"><span data-stu-id="b4781-158">Modernize existing .NET applications with Azure cloud and Windows Containers</span></span>](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [<span data-ttu-id="b4781-159">Cloud Native Patterns von Cornelia Davis</span><span class="sxs-lookup"><span data-stu-id="b4781-159">Cloud Native Patterns by Cornelia Davis</span></span>](https://www.manning.com/books/cloud-native-patterns)

- [<span data-ttu-id="b4781-160">Jenseits der Zwölf-Faktor-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b4781-160">Beyond the Twelve-Factor Application</span></span>](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [<span data-ttu-id="b4781-161">Was ist Infrastruktur als Code</span><span class="sxs-lookup"><span data-stu-id="b4781-161">What is Infrastructure as Code</span></span>](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [<span data-ttu-id="b4781-162">Micro Deploy von Uber Engineering: Täglich mit Zuversicht bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b4781-162">Uber Engineering's Micro Deploy: Deploying Daily with Confidence</span></span>](https://eng.uber.com/micro-deploy/)

- [<span data-ttu-id="b4781-163">Wie Netflix Code bereitstellt</span><span class="sxs-lookup"><span data-stu-id="b4781-163">How Netflix Deploys Code</span></span>](https://www.infoq.com/news/2013/06/netflix/)

- [<span data-ttu-id="b4781-164">Überlaststeuerung für die Skalierung von WeChat Microservices</span><span class="sxs-lookup"><span data-stu-id="b4781-164">Overload Control for Scaling WeChat Microservices</span></span>](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
><span data-ttu-id="b4781-165">[Zurück](definition.md)
>[Weiter](introduce-eshoponcontainers-reference-app.md)</span><span class="sxs-lookup"><span data-stu-id="b4781-165">[Previous](definition.md)
[Next](introduce-eshoponcontainers-reference-app.md)</span></span>
