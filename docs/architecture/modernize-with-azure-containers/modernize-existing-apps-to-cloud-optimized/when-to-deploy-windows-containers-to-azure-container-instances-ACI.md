---
title: Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Instances (ACI) erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Instances (ACI) erfolgen sollte
ms.date: 12/21/2020
ms.openlocfilehash: 556fe7cbec7d259db9ec886b777feda9eed09116
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025132"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="9d01d-103">Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Instances (ACI) erfolgen sollte</span><span class="sxs-lookup"><span data-stu-id="9d01d-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="9d01d-104">Das wesentliche Leistungsmerkmal von Azure Container Instances besteht darin, dass Sie Container sofort bereitstellen können und diese Umgebung nicht verwalten müssen. Sie müssen kein Upgrade des zugrunde liegenden Betriebssystems bzw. der VMs durchführen oder diese patchen. Alles ist transparent, und Sie müssen Container lediglich in einer einsatzbereiten Umgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9d01d-104">The main value proposition of Azure Container Instances is that you can right away deploy containers to it and you don't need to maintain that environment, you don't need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="9d01d-105">Die Gründe und Szenarien, wann Sie ACI verwenden sollten, ähneln den wesentlichen Szenarien, in denen Sie Azure-VMs mit Containern verwenden. Im Grunde sind also dies die Hauptszenarien für die Verwendung von Azure Container Instances:</span><span class="sxs-lookup"><span data-stu-id="9d01d-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="9d01d-106">**Entwicklungs-/Testszenarien**</span><span class="sxs-lookup"><span data-stu-id="9d01d-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="9d01d-107">**Aufgabenautomatisierung**</span><span class="sxs-lookup"><span data-stu-id="9d01d-107">**Task automation**</span></span>
- <span data-ttu-id="9d01d-108">**CI/CD-Agents**</span><span class="sxs-lookup"><span data-stu-id="9d01d-108">**CI/CD agents**</span></span>
- <span data-ttu-id="9d01d-109">**Verarbeitung kleiner/skalierter Stapel**</span><span class="sxs-lookup"><span data-stu-id="9d01d-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="9d01d-110">**Einfache Web-Apps**</span><span class="sxs-lookup"><span data-stu-id="9d01d-110">**Simple web apps**</span></span>

<span data-ttu-id="9d01d-111">Das Szenario mit einfachen Web-Apps ist ein faires Szenario für ACI. Sie sollten aber berücksichtigen, dass Sie, weil Sie in ACI nur über eine einzelne Containerinstanz pro Containerimage verfügen können, keine Hochverfügbarkeit und nur begrenzte Skalierbarkeit besitzen werden.</span><span class="sxs-lookup"><span data-stu-id="9d01d-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won't have high availability and only have limited scalability.</span></span>

<span data-ttu-id="9d01d-112">Auch wenn ACI als Infrastruktur betrachtet wird, weil es nur einzelne Containerinstanzen bereitstellt, bietet es im Vergleich zu regulären Azure-VMs mit Windows Server einen immensen Vorteil.</span><span class="sxs-lookup"><span data-stu-id="9d01d-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="9d01d-113">Mit ACI stellen Sie lediglich die Container in einer selbstunterhaltenden Umgebung bereit, und Sie zahlen nur für diese Container.</span><span class="sxs-lookup"><span data-stu-id="9d01d-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="9d01d-114">Sie müssen keine VMs verwalten, aktualisieren oder patchen. Daher stellt dies eine deutlich bessere Plattform für die meisten Szenarios dar, in denen Sie VMs mit Containern verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d01d-114">You don't need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="9d01d-115">Die Verwendung von ACI ist einfach gestaltet, Sie stellen einfach einen Container bereit. Sie müssen keine VM-Umgebung erstellen.</span><span class="sxs-lookup"><span data-stu-id="9d01d-115">Using ACI is straight forward, you just deploy a container, there's no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="9d01d-116">Die Hauptvorteile von Azure Container Instances (ACI) sind:</span><span class="sxs-lookup"><span data-stu-id="9d01d-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="9d01d-117">Ausführen von Containern ohne Verwaltung von Servern</span><span class="sxs-lookup"><span data-stu-id="9d01d-117">Run containers without managing servers</span></span>
- <span data-ttu-id="9d01d-118">Erhöhte Flexibilität durch Container bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="9d01d-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="9d01d-119">Bereitstellen von Containern in der Cloud mit nie dagewesener Einfachheit und Geschwindigkeit – mit nur einem Befehl.</span><span class="sxs-lookup"><span data-stu-id="9d01d-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="9d01d-120">Sichere Anwendungen mit Hypervisor-Isolierung</span><span class="sxs-lookup"><span data-stu-id="9d01d-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="9d01d-121">Kurz gesagt, mit ACI können Sie Apps schnell entwickeln, ohne virtuelle Computer verwalten oder neue Tools erlernen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="9d01d-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="9d01d-122">Es ist lediglich Ihre Anwendung, in einem Container, die in der Cloud ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d01d-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="9d01d-123">[Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Weiter](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="9d01d-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span></span>
