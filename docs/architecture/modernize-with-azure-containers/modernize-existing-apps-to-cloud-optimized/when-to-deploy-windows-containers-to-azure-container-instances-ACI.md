---
title: Zeitpunkt der Bereitstellung von Windows-Containern für Azure Container Instances (ACI)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Zeitpunkt der Bereitstellung von Windows-Containern für Azure Container Instances (ACI)
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577933"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="e1fe8-103">Zeitpunkt der Bereitstellung von Windows-Containern für Azure Container Instances (ACI)</span><span class="sxs-lookup"><span data-stu-id="e1fe8-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="e1fe8-104">Azure Container Instances Haupt Wertbeitrag besteht darin, dass Sie sofort Container bereitstellen können, und Sie müssen diese Umgebung nicht pflegen. Sie müssen das zugrunde liegende Betriebssystem oder die VMs nicht aktualisieren/Patchen. das ist alles transparent, und Sie stellen einfach bereit. Container in einer einsatzbereiten Umgebung.</span><span class="sxs-lookup"><span data-stu-id="e1fe8-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="e1fe8-105">Die Gründe und Szenarios für die Verwendung von ACI ähneln den Haupt Szenarien, in denen Sie Azure-VMS mit Containern verwenden. im Grunde sind die wichtigsten Szenarien für die Verwendung von Azure Container Instances:</span><span class="sxs-lookup"><span data-stu-id="e1fe8-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="e1fe8-106">**Dev/Test-Szenarios**</span><span class="sxs-lookup"><span data-stu-id="e1fe8-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="e1fe8-107">**Aufgabenautomatisierung**</span><span class="sxs-lookup"><span data-stu-id="e1fe8-107">**Task automation**</span></span>
- <span data-ttu-id="e1fe8-108">**CI/CD-Agents**</span><span class="sxs-lookup"><span data-stu-id="e1fe8-108">**CI/CD agents**</span></span>
- <span data-ttu-id="e1fe8-109">**Kleine/skalierbare Batch Verarbeitung**</span><span class="sxs-lookup"><span data-stu-id="e1fe8-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="e1fe8-110">**Einfache Web-Apps**</span><span class="sxs-lookup"><span data-stu-id="e1fe8-110">**Simple web apps**</span></span>

<span data-ttu-id="e1fe8-111">Das einfache Web-Apps-Szenario ist ein faires Szenario für ACI, aber berücksichtigen Sie, dass Sie in ACI nur über eine einzelne Container Instanz pro Container Image verfügen können, weil Sie nicht über Hochverfügbarkeit verfügen und nur eine begrenzte Skalierbarkeit haben.</span><span class="sxs-lookup"><span data-stu-id="e1fe8-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="e1fe8-112">Auch wenn ACI als Infrastruktur betrachtet wird, weil es nur einzelne Container Instanzen bereitstellt, bietet es im Vergleich zu regulären Azure-VMS mit Windows Server einen großen Vorteil.</span><span class="sxs-lookup"><span data-stu-id="e1fe8-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="e1fe8-113">Mit ACI stellen Sie die Container nur in einer selbstverwalteten Umgebung bereit, und Sie zahlen nur für diese Container.</span><span class="sxs-lookup"><span data-stu-id="e1fe8-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="e1fe8-114">Sie müssen VMS nicht verwalten/aktualisieren/Patchen, sodass es für die meisten Szenarien, in denen Sie möglicherweise VMS mit Containern verwenden, eine viel bessere Plattform ist.</span><span class="sxs-lookup"><span data-stu-id="e1fe8-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="e1fe8-115">Wenn Sie nur einen Container bereitstellen, ist es nicht erforderlich, eine VM-Umgebung zu erstellen, in der Sie nur Container bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e1fe8-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="e1fe8-116">Die Hauptvorteile von Azure Container Instances (ACI) sind:</span><span class="sxs-lookup"><span data-stu-id="e1fe8-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="e1fe8-117">Ausführen von Containern ohne Serververwaltung</span><span class="sxs-lookup"><span data-stu-id="e1fe8-117">Run containers without managing servers</span></span>
- <span data-ttu-id="e1fe8-118">Flexibilität durch Container Bedarfs gesteuert erhöhen</span><span class="sxs-lookup"><span data-stu-id="e1fe8-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="e1fe8-119">Stellen Sie mit einem einzigen Befehl Container in der Cloud bereit, ohne die Einfachheit und Geschwindigkeit –.</span><span class="sxs-lookup"><span data-stu-id="e1fe8-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="e1fe8-120">Sichere Anwendungen mit Hypervisor-Isolation</span><span class="sxs-lookup"><span data-stu-id="e1fe8-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="e1fe8-121">Kurz gesagt, mit ACI können Sie apps schnell entwickeln, ohne virtuelle Computer zu verwalten oder neue Tools erlernen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="e1fe8-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="e1fe8-122">Es ist nur Ihre Anwendung, in einem Container, der in der Cloud ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e1fe8-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="e1fe8-123">[Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Weiter](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="e1fe8-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span></span>
