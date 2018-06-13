---
title: Beim Bereitstellen von Windows-Container auf Azure-VMs (IaaS-Cloud)
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Beim Bereitstellen von Windows-Container auf Azure-VMs (IaaS-Cloud)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 7472745577f414062b460fd71ab45bae85d7a62e
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958020"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="54fd5-103">Beim Bereitstellen von Windows-Container auf Azure-VMs (IaaS-Cloud)</span><span class="sxs-lookup"><span data-stu-id="54fd5-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="54fd5-104">Wenn Ihre Organisation Azure-VMs verwendet, auch wenn Sie auch Windows-Container verwendet werden, werden Sie immer noch Umgang mit IaaS.</span><span class="sxs-lookup"><span data-stu-id="54fd5-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="54fd5-105">Das bedeutet, Umgang mit infrastrukturvorgängen VM Betriebssystempatches und Komplexität der Infrastruktur für hoch skalierbare Anwendungen, wenn Sie mehrere virtuelle Computer in einer Load balanced Infrastruktur bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="54fd5-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="54fd5-106">Die wichtigsten Szenarien für die Verwendung von Windows-Containern in einer Azure-VM werden:</span><span class="sxs-lookup"><span data-stu-id="54fd5-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

-   <span data-ttu-id="54fd5-107">**Entwicklungs-/testumgebung**: ein virtueller Computer in der Cloud ist ideal für Entwicklung und Tests in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="54fd5-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="54fd5-108">Sie können schnell erstellen, oder Beenden der Umgebung je nach Ihren Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="54fd5-108">You can rapidly create or stop the environment depending on your needs.</span></span>

-   <span data-ttu-id="54fd5-109">**Kleine und mittlere Skalierbarkeit muss**: In Szenarien, in denen Sie möglicherweise nur einige der virtuellen Computer für Ihre produktionsumgebung, verwalten eine kleine Anzahl von virtuellen Computern möglicherweise kostengünstige Entwicklung von bis zu komplexeren PaaS-Umgebungen, z. B. Orchestrators verschoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="54fd5-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

-   <span data-ttu-id="54fd5-110">**Produktionsumgebung mit vorhandenen Bereitstellungstools**: Sie können aus einer lokalen Umgebung in der Sie in den Tools zu komplexe Bereitstellungen auf virtuellen Computern oder bare-Metal-Servern (z. B. Puppet oder ähnliche Tools) investiert haben gebracht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="54fd5-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="54fd5-111">Um mit minimalen codeänderungen zur Produktion Umgebung Bereitstellungsverfahren in der Cloud zu verschieben, können Sie weiterhin diese Tools verwenden, um auf Azure-VMs bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="54fd5-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="54fd5-112">Allerdings sollten Sie Windows-Container als Einheit der Bereitstellung zu verwenden, um die Bereitstellung verbessern.</span><span class="sxs-lookup"><span data-stu-id="54fd5-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="54fd5-113">[Zurück](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Weiter](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span><span class="sxs-lookup"><span data-stu-id="54fd5-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span></span>
