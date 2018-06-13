---
title: Auswählen von Azure Compute-Plattformen für Container-basierte Anwendungen
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Auswählen von Azure Compute-Plattformen für Container-basierte Anwendungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: ebf022a52aaaf95ae335976f5e097921b0ac8006
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958010"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="487d0-103">Auswählen von Azure Compute-Plattformen für Container-basierte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="487d0-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="487d0-104">Wie Sie bemerkt haben, nachdem Sie die vorherigen Abschnitten gelesen haben, ist Azure ein Öffnen Cloud, die mehrere Möglichkeiten bietet.</span><span class="sxs-lookup"><span data-stu-id="487d0-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="487d0-105">Können Sie für Ihre Anforderungen am besten passenden, allerdings Flächen es auch Fragen dazu, welche Produkt/Sie für Ihre Sammelartikeleinheit verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="487d0-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="487d0-106">Als eine *standardmäßig* Empfehlung, im folgenden finden Sie die wichtigsten Kriterien, die in diesem Handbuch empfohlen:</span><span class="sxs-lookup"><span data-stu-id="487d0-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

  - <span data-ttu-id="487d0-107">**Einzelne monolithischen app:** -Azure App Service auswählen</span><span class="sxs-lookup"><span data-stu-id="487d0-107">**Single monolithic app:** Choose Azure App Service</span></span>
  - <span data-ttu-id="487d0-108">**N-Tier-app:** Orchestrators z. B. Azure Kubernetes Service (so), die Service Fabric (SF) oder die App Service auswählen, wenn Sie ein einzelnes oder einige Back-End-Diensten haben</span><span class="sxs-lookup"><span data-stu-id="487d0-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
  - <span data-ttu-id="487d0-109">**Linux-Microservices:** so/Kubernetes auswählen</span><span class="sxs-lookup"><span data-stu-id="487d0-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
  - <span data-ttu-id="487d0-110">**Windows-Microservices:** Service Fabric auswählen</span><span class="sxs-lookup"><span data-stu-id="487d0-110">**Windows microservices:** Choose Service Fabric</span></span>
  - <span data-ttu-id="487d0-111">**Serverlose Funktionen & Ereignishandler:** auswählen von Azure-Funktionen</span><span class="sxs-lookup"><span data-stu-id="487d0-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
  - <span data-ttu-id="487d0-112">**Umfangreiche Batch:** Azure Batch auswählen</span><span class="sxs-lookup"><span data-stu-id="487d0-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="487d0-113">Diese Empfehlung muss jedoch mit Salt-Wert, eine Prise ergriffen werden, wie das Produkt Auswahl von Anforderungen und die Merkmale der jeweiligen Anwendungsverzeichnis abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="487d0-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="487d0-114">Nicht alle Anwendungen sind identisch, selbst wenn zunächst sie ähnliche Pakettypen aussehen könnte.</span><span class="sxs-lookup"><span data-stu-id="487d0-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="487d0-115">Nach einem eine tiefer gehende Analyse der die Anforderungen der Anwendung konnte die ausgewählten Produkts unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="487d0-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="487d0-116">Allerdings als Ausgangspunkt, ist es gut, haben die erste Anleitung von auf der Auswertung starten können, und Testen basierend auf bestimmten Priorität.</span><span class="sxs-lookup"><span data-stu-id="487d0-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="487d0-117">In der nächsten Abbildung können Sie einen umfassenderen beim ausführliches Tabelle analysieren.</span><span class="sxs-lookup"><span data-stu-id="487d0-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="487d0-118">Beachten Sie, dass wie die zugrunde liegende Betriebssystem (Windows im Vergleich zu Linux) kann auch ein Entscheidungsfaktor für die sein, da einige Orchestrators ausgereifte auf Linux-Containern und andere für Windows-Container sind.</span><span class="sxs-lookup"><span data-stu-id="487d0-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="487d0-119">Linux-Container sind z. B. sehr ausgereifte in Kubernetes (so in Azure) aber weniger ausgereiften auf Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="487d0-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="487d0-120">Andererseits, sind Windows-Containern ausgereiftere in Service Fabric (Freigabe im Mai 2017) und weniger ausgereiften in so.</span><span class="sxs-lookup"><span data-stu-id="487d0-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="487d0-121">Jedoch berücksichtigt diese Unterschiede im Betriebssystem Reife zukünftig zur menüausblendung und mehrere Plattformen müssen vergleichbar sein, OS Maturity und die Entscheidung werden weitere Informationen zur Voreinstellungen basierend auf bestimmte Funktionen, die Ihre Anwendung möglicherweise oder basierend auf jeder Plattform Ökosystem liegen. Gründe.</span><span class="sxs-lookup"><span data-stu-id="487d0-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="487d0-122">[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="487d0-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
