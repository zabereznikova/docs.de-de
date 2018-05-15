---
title: Wenn Sie Windows-Container auf Azure-Container Instanzen (ACI) bereitstellen
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Wenn Sie Windows-Container auf Azure-Container Instanzen (ACI) bereitstellen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 3dc23c96543d9611763b571105f52b150dfec06f
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="97b51-103">Wenn Sie Windows-Container auf Azure-Container Instanzen (ACI) bereitstellen</span><span class="sxs-lookup"><span data-stu-id="97b51-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="97b51-104">Azure-Container-Instanzen, die wichtigsten Wertbeitrag ist, können sofort das Bereitstellen von Containern, und Sie diese Umgebung zu verwalten müssen, müssen Sie keine Upgrades/Patches zugrunde liegende Betriebssystem oder der virtuelle Computer, die transparent ist und Sie nur bereitstellen Container in einer Umgebung zu verwendende bereit.</span><span class="sxs-lookup"><span data-stu-id="97b51-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlaying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="97b51-105">Die Gründe und Szenarien, in denen Sie ACI verwenden möchten ähneln die Hauptszenarien beim Azure-VMs also im Grunde mit Containern verwenden, werden die Hauptszenarien für die Verwendung von Azure-Container-Instanzen:</span><span class="sxs-lookup"><span data-stu-id="97b51-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

-   <span data-ttu-id="97b51-106">**Entwicklungs-/Testszenarios**</span><span class="sxs-lookup"><span data-stu-id="97b51-106">**Dev/Test scenarios**</span></span>
-   <span data-ttu-id="97b51-107">**Automatisierung von Aufgaben**</span><span class="sxs-lookup"><span data-stu-id="97b51-107">**Task automation**</span></span>
-   <span data-ttu-id="97b51-108">**CI-CD-agents**</span><span class="sxs-lookup"><span data-stu-id="97b51-108">**CI/CD agents**</span></span>
-   <span data-ttu-id="97b51-109">**Kleine/Skalierung-Batchverarbeitung**</span><span class="sxs-lookup"><span data-stu-id="97b51-109">**Small/scale batch processing**</span></span>
-   <span data-ttu-id="97b51-110">**Einfache Web-apps**</span><span class="sxs-lookup"><span data-stu-id="97b51-110">**Simple web apps**</span></span>

<span data-ttu-id="97b51-111">Das einfache Web-apps-Szenario ist ein ziemlich Szenario für ACI, jedoch müssen Sie berücksichtigen, da in ACI Sie nur eine einzelnen Container-Instanz pro Container-Abbild aufweisen können, keine hohen Verfügbarkeit und Skalierbarkeit beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="97b51-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="97b51-112">Selbst wenn ACI Infrastruktur betrachtet, da sie nur Instanzen der einzelnen Container bereitstellt, besteht jedoch ein großer Vorteil im Vergleich zu normalen Azure-VMs mit Windows Server.</span><span class="sxs-lookup"><span data-stu-id="97b51-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="97b51-113">Mit ACI Sie nur die Container in einer Umgebung mit sich selbst bereitstellen, und Sie bezahlen nur für diesen Container.</span><span class="sxs-lookup"><span data-stu-id="97b51-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="97b51-114">Sie müssen nicht warten/aktualisieren/Patch-VMs, daher ist es eine viel bessere Plattform für die meisten Szenarien, in dem Sie virtuelle Computer mit Containern verwenden werden können.</span><span class="sxs-lookup"><span data-stu-id="97b51-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="97b51-115">Mithilfe von ACI nachvollziehbar ist ganz einfach, Sie stellen nur einen Container bereit, besteht keine Notwendigkeit zum Erstellen einer Umgebung mit virtuellen Computern nur Bereitstellen von Containern.</span><span class="sxs-lookup"><span data-stu-id="97b51-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="97b51-116">Die Hauptvorteile von Azure-Container Instanzen (ACI) sind:</span><span class="sxs-lookup"><span data-stu-id="97b51-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

-   <span data-ttu-id="97b51-117">Container ausgeführt werden, ohne die Verwaltung von Servern</span><span class="sxs-lookup"><span data-stu-id="97b51-117">Run containers without managing servers</span></span>
-   <span data-ttu-id="97b51-118">Erhöhen der Flexibilität mit Containern bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="97b51-118">Increase agility with containers on demand</span></span>
-   <span data-ttu-id="97b51-119">Container in der Cloud unvergleichlich hohe Einfachheit und gleicher Geschwindigkeit Bereitstellen – mit einem einzigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="97b51-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span> 
-   <span data-ttu-id="97b51-120">Sicherer Anwendungen Hypervisor Isolation</span><span class="sxs-lookup"><span data-stu-id="97b51-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="97b51-121">Kurz gesagt, können Sie apps mit ACI entwickeln, fast ohne Verwaltung virtueller Computer oder neuen Tools vertraut machen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="97b51-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="97b51-122">Es ist nur die Anwendung in einem Container, in der Cloud ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="97b51-122">It's just your application, in a container, running in the cloud.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="97b51-123">[Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Weiter](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="97b51-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
