---
title: Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Auswählen von Azure-Compute-Plattformen, für die containerbasierte Anwendungen
ms.date: 05/04/2018
ms.openlocfilehash: 64ae542e006bf7a5d7a0be08fe1cff9770552a77
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833858"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="58d47-103">Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="58d47-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="58d47-104">Wie Sie nach dem Lesen in den vorherigen Abschnitten bemerkt haben, ist Azure eine offene Cloud, die mehrere Auswahlmöglichkeiten bietet.</span><span class="sxs-lookup"><span data-stu-id="58d47-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="58d47-105">Können Sie für Ihre Anforderungen am besten geeignet, jedoch gibt es auch Fragen zu welchem Produkt/Technologie Sie für Ihre containeranwendungen verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="58d47-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="58d47-106">Als eine *standardmäßig* Empfehlungen zu erstellen, die folgenden ist das Hauptkriterium, die in diesem Handbuch empfohlen:</span><span class="sxs-lookup"><span data-stu-id="58d47-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="58d47-107">**Einzelne monolithischen app:** Wählen Sie Azure App Service</span><span class="sxs-lookup"><span data-stu-id="58d47-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="58d47-108">**N-schichtigen Anwendung:** Wählen Sie orchestratoren wie z. B. Azure Kubernetes Service (AKS) oder einen App Service aus, wenn Sie eine einzelne oder einige Back-End-Dienste verfügen</span><span class="sxs-lookup"><span data-stu-id="58d47-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="58d47-109">**Microservices:** Wählen Sie AKS oder Azure-Web-Apps für Container</span><span class="sxs-lookup"><span data-stu-id="58d47-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="58d47-110">**Serverlose Funktionen & Ereignishandler:** Wählen Sie die Azure-Funktionen</span><span class="sxs-lookup"><span data-stu-id="58d47-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="58d47-111">**Umfangreiche Batch:** Wählen Sie mit Azure Batch</span><span class="sxs-lookup"><span data-stu-id="58d47-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="58d47-112">Allerdings sollten diese Empfehlung mit Salt-Wert, eine Prise ausgeführt werden, wie Ihre Anwendung die Anforderungen und Merkmale des Produkts Auswahl abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="58d47-112">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="58d47-113">Nicht alle Anwendungen sind identisch, auch wenn Anfangs sie ähnliche Typen aussehen könnte.</span><span class="sxs-lookup"><span data-stu-id="58d47-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="58d47-114">Nach der eine detailliertere Analyse der die Anforderungen der Anwendung konnte das ausgewählte Produkt unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="58d47-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="58d47-115">Allerdings als Ausgangspunkt, es ist ratsam, steht eine erste Anleitung aus, in dem Sie Ihre Evaluierung von starten können, und Tests basierend auf bestimmten Priorität.</span><span class="sxs-lookup"><span data-stu-id="58d47-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="58d47-116">In der nächsten Abbildung sehen Sie eine Aufschlüsselung der verschiedenen Arten von apps und die ideale Azure Hostingszenarien.</span><span class="sxs-lookup"><span data-stu-id="58d47-116">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="58d47-117">[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="58d47-117">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
