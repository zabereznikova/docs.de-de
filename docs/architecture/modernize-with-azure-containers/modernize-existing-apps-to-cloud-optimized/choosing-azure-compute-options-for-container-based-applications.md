---
title: Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Auswählen von Azure-computeplattformen für Container basierte Anwendungen
ms.date: 05/04/2018
ms.openlocfilehash: 64ae542e006bf7a5d7a0be08fe1cff9770552a77
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578343"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="9b91f-103">Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="9b91f-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="9b91f-104">Wie Sie nach dem Lesen der vorherigen Abschnitte bemerkt haben, ist Azure eine offene Cloud, die mehrere Optionen bietet.</span><span class="sxs-lookup"><span data-stu-id="9b91f-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="9b91f-105">Sie können die beste Lösung für Ihre Anforderungen verwenden, aber auch Fragen zu den Produkten und Technologien, die Sie für Ihre containerisierten Anwendungen verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="9b91f-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="9b91f-106">Als *Standard* Empfehlung werden folgende Hauptkriterien in dieser Anleitung empfohlen:</span><span class="sxs-lookup"><span data-stu-id="9b91f-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="9b91f-107">**Einzelne monolithische App:** Wählen Sie Azure App Service</span><span class="sxs-lookup"><span data-stu-id="9b91f-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="9b91f-108">**N-Tier-App:** Wählen Sie orchestratoren wie Azure Kubernetes Service (AKS) oder App Service aus, wenn Sie einen oder mehrere Back-End-Dienste haben.</span><span class="sxs-lookup"><span data-stu-id="9b91f-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="9b91f-109">**Microservices** AKS oder Azure-Web-Apps für Container auswählen</span><span class="sxs-lookup"><span data-stu-id="9b91f-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="9b91f-110">**Server lose Funktionen & Ereignishandler:** Wählen Sie Azure Functions</span><span class="sxs-lookup"><span data-stu-id="9b91f-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="9b91f-111">**Umfangreicher Batch:** Wählen Sie Azure Batch</span><span class="sxs-lookup"><span data-stu-id="9b91f-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="9b91f-112">Diese Empfehlung sollte jedoch mit einem Salt-Salt-Vorgang durchgeführt werden, da die Auswahl des Produkts von den Anforderungen und Merkmalen ihrer jeweiligen Anwendung abhängt.</span><span class="sxs-lookup"><span data-stu-id="9b91f-112">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="9b91f-113">Nicht alle Anwendungen sind identisch, auch wenn Sie anfänglich ähnliche Typen sehen könnten.</span><span class="sxs-lookup"><span data-stu-id="9b91f-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="9b91f-114">Nach einer tieferen Analyse der Anwendungsanforderungen könnte sich das ausgewählte Produkt unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9b91f-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="9b91f-115">Als Ausgangspunkt empfiehlt es sich jedoch, eine erste Anleitung zu erhalten, in der Sie basierend auf einer bestimmten Priorität evaluieren und testen können.</span><span class="sxs-lookup"><span data-stu-id="9b91f-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="9b91f-116">In der nächsten Abbildung sehen Sie eine Aufschlüsselung der verschiedenen Arten von apps und ihrer idealen Azure-Hostingszenarios.</span><span class="sxs-lookup"><span data-stu-id="9b91f-116">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="9b91f-117">[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="9b91f-117">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
