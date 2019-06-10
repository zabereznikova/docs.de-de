---
title: Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Auswählen von Azure-Compute-Plattformen, für die containerbasierte Anwendungen
ms.date: 05/04/2018
ms.openlocfilehash: d91cd279402dc24beb5f766c06cb85ac8d74f482
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758832"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="a5d42-103">Auswählen von Azure Compute-Plattformen für containerbasierte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a5d42-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="a5d42-104">Wie Sie nach dem Lesen in den vorherigen Abschnitten bemerkt haben, ist Azure eine offene Cloud, die mehrere Auswahlmöglichkeiten bietet.</span><span class="sxs-lookup"><span data-stu-id="a5d42-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="a5d42-105">Können Sie für Ihre Anforderungen am besten geeignet, jedoch gibt es auch Fragen zu welchem Produkt/Technologie Sie für Ihre containeranwendungen verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="a5d42-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="a5d42-106">Als eine *standardmäßig* Empfehlungen zu erstellen, die folgenden ist das Hauptkriterium, die in diesem Handbuch empfohlen:</span><span class="sxs-lookup"><span data-stu-id="a5d42-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="a5d42-107">**Einzelne monolithischen app:** Wählen Sie Azure App Service</span><span class="sxs-lookup"><span data-stu-id="a5d42-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="a5d42-108">**N-schichtigen Anwendung:** Wählen Sie orchestratoren wie z. B. Azure Kubernetes Service (AKS) oder einen App Service aus, wenn Sie eine einzelne oder einige Back-End-Dienste verfügen</span><span class="sxs-lookup"><span data-stu-id="a5d42-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="a5d42-109">**Microservices für Linux:** Wählen Sie ACS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="a5d42-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
- <span data-ttu-id="a5d42-110">**Windows-Microservices:** Wählen Sie die Azure-Web-Apps für Container</span><span class="sxs-lookup"><span data-stu-id="a5d42-110">**Windows microservices:** Choose Azure Web Apps for Containers</span></span>
- <span data-ttu-id="a5d42-111">**Serverlose Funktionen & Ereignishandler:** Wählen Sie die Azure-Funktionen</span><span class="sxs-lookup"><span data-stu-id="a5d42-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="a5d42-112">**Umfangreiche Batch:** Wählen Sie mit Azure Batch</span><span class="sxs-lookup"><span data-stu-id="a5d42-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="a5d42-113">Allerdings sollten diese Empfehlung mit Salt-Wert, eine Prise ausgeführt werden, wie Ihre Anwendung die Anforderungen und Merkmale des Produkts Auswahl abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="a5d42-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="a5d42-114">Nicht alle Anwendungen sind identisch, auch wenn Anfangs sie ähnliche Typen aussehen könnte.</span><span class="sxs-lookup"><span data-stu-id="a5d42-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="a5d42-115">Nach der eine detailliertere Analyse der die Anforderungen der Anwendung konnte das ausgewählte Produkt unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="a5d42-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="a5d42-116">Allerdings als Ausgangspunkt, es ist ratsam, steht eine erste Anleitung aus, in dem Sie Ihre Evaluierung von starten können, und Tests basierend auf bestimmten Priorität.</span><span class="sxs-lookup"><span data-stu-id="a5d42-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="a5d42-117">In der nächsten Abbildung sehen Sie eine Aufschlüsselung der verschiedenen Arten von apps und die ideale Azure Hostingszenarien.</span><span class="sxs-lookup"><span data-stu-id="a5d42-117">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="a5d42-118">[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Weiter](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="a5d42-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
