---
title: Beim Bereitstellen von Windows-Containern in Azure-VMs (IaaS-Cloud)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Beim Bereitstellen von Windows-Containern in Azure-VMs (IaaS-Cloud)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 51217e2c94fd9727c8f7907e791cdebaec98f14f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152148"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="17f88-103">Beim Bereitstellen von Windows-Containern in Azure-VMs (IaaS-Cloud)</span><span class="sxs-lookup"><span data-stu-id="17f88-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="17f88-104">Wenn Ihre Organisation Azure-VMs verwendet, auch wenn Sie auch Windows-Container verwenden, können Sie weiterhin Umgang mit IaaS.</span><span class="sxs-lookup"><span data-stu-id="17f88-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="17f88-105">Das bedeutet, Umgang mit infrastrukturvorgängen, VM-Betriebssystem-Patches und Komplexität der Infrastruktur für hochgradig skalierbare Anwendungen aus, wenn Sie mehrere virtuelle Computer in einer Load-balanced-Infrastruktur bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="17f88-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="17f88-106">Die wichtigsten Szenarien für die Verwendung von Windows-Containern in einer Azure-VM sind:</span><span class="sxs-lookup"><span data-stu-id="17f88-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

-   <span data-ttu-id="17f88-107">**Entwicklungs-/testumgebung**: Ein virtuellen Computer in der Cloud eignet sich ideal für Entwicklung und Tests in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="17f88-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="17f88-108">Sie können schnell erstellen, oder Beenden der Umgebung je nach Ihren Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="17f88-108">You can rapidly create or stop the environment depending on your needs.</span></span>

-   <span data-ttu-id="17f88-109">**Kleine und mittlere Skalierbarkeit muss**: In Szenarien, in dem Sie nur einige virtuelle Computer für Ihre produktionsumgebung benötigen, ist möglicherweise eine kleine Anzahl von VMs verwalten kostengünstige, solange erweiterte PaaS-Umgebungen, z. B. orchestratoren verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="17f88-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

-   <span data-ttu-id="17f88-110">**Produktionsumgebung mit vorhandenen Bereitstellungstools**: Sie können aus einer lokalen Umgebung verschieben werden, in denen Sie in den Tools, um komplexe Bereitstellungen zu virtuellen Computern oder bare-Metal-Servern (z. B. Puppet oder ähnliche Tools) stellen investiert haben.</span><span class="sxs-lookup"><span data-stu-id="17f88-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="17f88-111">Um mit minimalen codeänderungen zur Bereitstellungsverfahren für Produktions-Umgebung in die Cloud zu verschieben, können Sie weiterhin diese Tools verwenden, um die Azure-VMs bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="17f88-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="17f88-112">Allerdings sollten Sie die Windows-Container als Einheit der Bereitstellung zu verwenden, um die Bereitstellung zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="17f88-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="17f88-113">[Zurück](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[Weiter](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span><span class="sxs-lookup"><span data-stu-id="17f88-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span></span>