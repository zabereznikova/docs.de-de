---
title: Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "73736996"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="f7d93-103">Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f7d93-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="f7d93-104">Wie Sie nach dem Lesen der vorherigen Abschnitte bemerkt haben, ist Azure eine offene Cloud, die mehrere Optionen bietet.</span><span class="sxs-lookup"><span data-stu-id="f7d93-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="f7d93-105">Sie können die am beste passende Lösung für Ihre Anforderungen verwenden. Es wirft aber auch Fragen auf, welche/s Produkt/Technologie Sie für Ihre containerisierten Anwendungen verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="f7d93-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="f7d93-106">Als *standardmäßige* Empfehlung werden folgende Hauptkriterien in dieser Anleitung empfohlen:</span><span class="sxs-lookup"><span data-stu-id="f7d93-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="f7d93-107">**Einzelne monolithische App:** Azure App Service auswählen</span><span class="sxs-lookup"><span data-stu-id="f7d93-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="f7d93-108">**n-schichtige App:** Wählen Sie Orchestratoren wie Azure Kubernetes Service (AKS) oder App Service aus, wenn Sie einen einzelnen oder ein paar Back-End-Dienste haben.</span><span class="sxs-lookup"><span data-stu-id="f7d93-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS) or App Service if you have a single or a few back-end services</span></span>
- <span data-ttu-id="f7d93-109">**Microservices:** Wählen Sie AKS oder Azure-Web-Apps für Container aus.</span><span class="sxs-lookup"><span data-stu-id="f7d93-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="f7d93-110">**Serverlose Funktionen und Ereignishandler:** Wählen Sie Azure Functions aus.</span><span class="sxs-lookup"><span data-stu-id="f7d93-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="f7d93-111">**Massenstapel:** Wählen Sie Azure Batch aus.</span><span class="sxs-lookup"><span data-stu-id="f7d93-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="f7d93-112">Diese Empfehlung sollte jedoch mit ein wenig Vorsicht genossen werden, da die Auswahl des Produkts von den Anforderungen und Eigenschaften Ihrer spezifischen Anwendung abhängt.</span><span class="sxs-lookup"><span data-stu-id="f7d93-112">However, this recommendation should be taken with a pinch of salt, as the product's selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="f7d93-113">Nicht alle Anwendungen sind identisch, selbst wenn Sie anfänglich wie ähnliche Typen aussehen mögen.</span><span class="sxs-lookup"><span data-stu-id="f7d93-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="f7d93-114">Nach einer intensiveren Analyse der Anwendungsanforderungen könnte das ausgewählte Produkt abweichen.</span><span class="sxs-lookup"><span data-stu-id="f7d93-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="f7d93-115">Als Ausgangspunkt ist es jedoch gut, eine erste Orientierung zu haben, mit der Sie basierend auf einer bestimmten Priorität evaluieren und testen können.</span><span class="sxs-lookup"><span data-stu-id="f7d93-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="f7d93-116">In Abbildung 1 sehen Sie eine Aufschlüsselung der verschiedenen Arten von Apps und ihrer idealen Azure-Hostingszenarios.</span><span class="sxs-lookup"><span data-stu-id="f7d93-116">In Figure 1, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![Tabelle, welche Azure-Hostingszenarios für verschiedene Apps am besten geeignet sind.](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> <span data-ttu-id="f7d93-118">[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="f7d93-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
