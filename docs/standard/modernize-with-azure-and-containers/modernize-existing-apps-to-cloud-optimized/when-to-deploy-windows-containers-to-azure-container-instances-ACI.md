---
title: Wenn zum Bereitstellen von Windows-Containern zu Azure Container Instances (ACI)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Wenn zum Bereitstellen von Windows-Containern zu Azure Container Instances (ACI)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 03ee7c8b65e1a92dcc7fd40b44e9ba081f571487
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674405"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="f4005-103">Wenn zum Bereitstellen von Windows-Containern zu Azure Container Instances (ACI)</span><span class="sxs-lookup"><span data-stu-id="f4005-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="f4005-104">Azure Container Instances main Wertbeitrag liegt darin, dass Sie sofort Sie Container, damit bereitstellen können und zum Verwalten dieser Umgebung müssen nicht, Sie müssen nicht upgraden/Patchen des zugrunde liegenden Betriebssystems oder VMs, alle, die transparent ist und Sie einfach bereitstellen Container in einer Umgebung zu verwendende bereit.</span><span class="sxs-lookup"><span data-stu-id="f4005-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="f4005-105">Der Gründe und Szenarios, in denen Sie ACI verwenden möchten sind ähnlich wie die wichtigsten Szenarien, wenn Sie Azure-VMs im Grunde mit Containern verwenden, die wichtigsten Szenarien für die Verwendung von Azure Container Instances sind:</span><span class="sxs-lookup"><span data-stu-id="f4005-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="f4005-106">**Entwicklungs-/Testszenarien**</span><span class="sxs-lookup"><span data-stu-id="f4005-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="f4005-107">**Automatisierung von Aufgaben**</span><span class="sxs-lookup"><span data-stu-id="f4005-107">**Task automation**</span></span>
- <span data-ttu-id="f4005-108">**CI/CD-agents**</span><span class="sxs-lookup"><span data-stu-id="f4005-108">**CI/CD agents**</span></span>
- <span data-ttu-id="f4005-109">**Batchverarbeitung von kleinen/Skalierung**</span><span class="sxs-lookup"><span data-stu-id="f4005-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="f4005-110">**Einfache Web-apps**</span><span class="sxs-lookup"><span data-stu-id="f4005-110">**Simple web apps**</span></span>

<span data-ttu-id="f4005-111">Das einfache Web-apps-Szenario ist ein ziemlich Szenario für ACI, jedoch müssen Sie berücksichtigen, da in ACI Sie nur eine einzelne Containerinstanz pro Container-Abbild haben können, keine hohen Verfügbarkeit weisen und Skalierbarkeit begrenzt haben.</span><span class="sxs-lookup"><span data-stu-id="f4005-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="f4005-112">Auch wenn ACI Infrastruktur betrachtet wird, da sie nur Instanzen der einzelnen Container bereitstellt, besteht jedoch ein großer Vorteil im Vergleich zu regulären Azure-VMs mit Windows Server.</span><span class="sxs-lookup"><span data-stu-id="f4005-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="f4005-113">Mit ACI Sie nur die Container in einer selbst verwalteten Umgebung bereitstellen, und Sie Zahlen nur für diesen Container.</span><span class="sxs-lookup"><span data-stu-id="f4005-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="f4005-114">Sie müssen nicht warten/aktualisieren/Patch-VMs, daher ist es eine viel bessere Plattform für die meisten Szenarien, auf dem virtuellen Computer mit Containern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f4005-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="f4005-115">Mit ACI ist einfach, Sie stellen nur einen Container bereit, besteht keine Notwendigkeit zum Erstellen einer Umgebung mit virtuellen Computern einfach Bereitstellen von Containern.</span><span class="sxs-lookup"><span data-stu-id="f4005-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="f4005-116">Zu den wichtigsten Vorteilen von Azure Container Instances (ACI) sind:</span><span class="sxs-lookup"><span data-stu-id="f4005-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="f4005-117">Führen Sie Container ohne Notwendigkeit zur serververwaltung aus</span><span class="sxs-lookup"><span data-stu-id="f4005-117">Run containers without managing servers</span></span>
- <span data-ttu-id="f4005-118">Flexibilität durch Container bedarfsgerecht erhöhen</span><span class="sxs-lookup"><span data-stu-id="f4005-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="f4005-119">Stellen Sie Container mit beispielloser Einfachheit und Geschwindigkeit in der Cloud bereit – mit einem einzigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="f4005-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="f4005-120">Sichern von Anwendungen mit hypervisorisolierung</span><span class="sxs-lookup"><span data-stu-id="f4005-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="f4005-121">Kurz gesagt, können Sie apps mit ACI entwickeln, schnell voran, ohne virtuelle Computer verwalten oder neue Tools erlernen müssen.</span><span class="sxs-lookup"><span data-stu-id="f4005-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="f4005-122">Es ist nur Ihre Anwendung, in einem Container, in der Cloud ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f4005-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="f4005-123">[Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Weiter](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="f4005-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
