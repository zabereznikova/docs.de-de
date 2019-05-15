---
title: Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Auswählen von Azure-Compute-Plattformen, für die containerbasierte Anwendungen
ms.date: 05/04/2018
ms.openlocfilehash: 28e103c67f47d63582384c9ab468a5f631b5ce9e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638973"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="3feba-103">Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3feba-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="3feba-104">Wie Sie nach dem Lesen in den vorherigen Abschnitten bemerkt haben, ist Azure eine offene Cloud, die mehrere Auswahlmöglichkeiten bietet.</span><span class="sxs-lookup"><span data-stu-id="3feba-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="3feba-105">Können Sie für Ihre Anforderungen am besten geeignet, jedoch gibt es auch Fragen zu welchem Produkt/Technologie Sie für Ihre containeranwendungen verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="3feba-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="3feba-106">Als eine *standardmäßig* Empfehlungen zu erstellen, die folgenden ist das Hauptkriterium, die in diesem Handbuch empfohlen:</span><span class="sxs-lookup"><span data-stu-id="3feba-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="3feba-107">**Einzelne monolithischen app:** Wählen Sie Azure App Service</span><span class="sxs-lookup"><span data-stu-id="3feba-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="3feba-108">**N-schichtigen Anwendung:** Wählen Sie orchestratoren wie z. B. Azure Kubernetes Service (AKS), Service Fabric (AE) oder App Service aus, wenn Sie eine einzelne oder einige Back-End-Dienste verfügen</span><span class="sxs-lookup"><span data-stu-id="3feba-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="3feba-109">**Microservices für Linux:** Wählen Sie ACS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="3feba-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
- <span data-ttu-id="3feba-110">**Windows-Microservices:** Wählen Sie Service Fabric</span><span class="sxs-lookup"><span data-stu-id="3feba-110">**Windows microservices:** Choose Service Fabric</span></span>
- <span data-ttu-id="3feba-111">**Serverlose Funktionen & Ereignishandler:** Wählen Sie die Azure-Funktionen</span><span class="sxs-lookup"><span data-stu-id="3feba-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="3feba-112">**Umfangreiche Batch:** Wählen Sie mit Azure Batch</span><span class="sxs-lookup"><span data-stu-id="3feba-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="3feba-113">Allerdings sollten diese Empfehlung mit Salt-Wert, eine Prise ausgeführt werden, wie Ihre Anwendung die Anforderungen und Merkmale des Produkts Auswahl abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="3feba-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="3feba-114">Nicht alle Anwendungen sind identisch, auch wenn Anfangs sie ähnliche Typen aussehen könnte.</span><span class="sxs-lookup"><span data-stu-id="3feba-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="3feba-115">Nach der eine detailliertere Analyse der die Anforderungen der Anwendung konnte das ausgewählte Produkt unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="3feba-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="3feba-116">Allerdings als Ausgangspunkt, es ist ratsam, steht eine erste Anleitung aus, in dem Sie Ihre Evaluierung von starten können, und Tests basierend auf bestimmten Priorität.</span><span class="sxs-lookup"><span data-stu-id="3feba-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="3feba-117">In der nächsten Abbildung können Sie einen umfassenderen beim ausführliche Entscheidungstabelle analysieren.</span><span class="sxs-lookup"><span data-stu-id="3feba-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="3feba-118">Beachten Sie, dass die zugrunde liegende Betriebssystem (im Vergleich zu Windows. Linux) kann auch ein Entscheidungsfaktor sein, da einige orchestratoren ausgereifte auf Linux-Container und andere auf Windows-Container sind.</span><span class="sxs-lookup"><span data-stu-id="3feba-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="3feba-119">Beispielsweise sind die Linux-Container in Kubernetes (AKS in Azure) sehr ausgereiften aber ausgereifter als unter Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="3feba-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="3feba-120">Sind auf der anderen Seite Windows-Container auf, umso reifer in Service Fabric (veröffentlicht im Mai 2017) und ausgereifter als unter AKS.</span><span class="sxs-lookup"><span data-stu-id="3feba-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="3feba-121">Jedoch diese Unterschiede im Betriebssystem Maturity in der Zukunft eingeblendet werden und mehrere Plattformen vergleichbar OS Reife und die Entscheidung wird mehr über Einstellungen, die basierend auf bestimmten Features, die Ihre Anwendung möglicherweise oder basierend auf jeder Plattform Ökosystem anordnen Gründe.</span><span class="sxs-lookup"><span data-stu-id="3feba-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="3feba-122">[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="3feba-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
