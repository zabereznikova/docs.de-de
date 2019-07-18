---
title: Umstände, unter denen eine Bereitstellung von Windows-Containern auf virtuellen Azure-Computern (IaaS-Cloud) erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Beim Bereitstellen von Windows-Containern in Azure-VMs (IaaS-Cloud)
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638997"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Umstände, unter denen eine Bereitstellung von Windows-Containern auf virtuellen Azure-Computern (IaaS-Cloud) erfolgen sollte

Wenn Ihre Organisation Azure-VMs verwendet, auch wenn Sie auch Windows-Container verwenden, können Sie weiterhin Umgang mit IaaS. Das bedeutet, Umgang mit infrastrukturvorgängen, VM-Betriebssystem-Patches und Komplexität der Infrastruktur für hochgradig skalierbare Anwendungen aus, wenn Sie mehrere virtuelle Computer in einer Load-balanced-Infrastruktur bereitstellen müssen. Die wichtigsten Szenarien für die Verwendung von Windows-Containern in einer Azure-VM sind:

- **Entwicklungs-/testumgebung**: Ein virtuellen Computer in der Cloud eignet sich ideal für Entwicklung und Tests in der Cloud. Sie können schnell erstellen, oder Beenden der Umgebung je nach Ihren Anforderungen.

- **Kleine und mittlere Skalierbarkeit muss**: In Szenarien, in dem Sie nur einige virtuelle Computer für Ihre produktionsumgebung benötigen, ist möglicherweise eine kleine Anzahl von VMs verwalten kostengünstige, solange erweiterte PaaS-Umgebungen, z. B. orchestratoren verschoben werden können.

- **Produktionsumgebung mit vorhandenen Bereitstellungstools**: Sie können aus einer lokalen Umgebung verschieben werden, in denen Sie in den Tools, um komplexe Bereitstellungen zu virtuellen Computern oder bare-Metal-Servern (z. B. Puppet oder ähnliche Tools) stellen investiert haben. Um mit minimalen codeänderungen zur Bereitstellungsverfahren für Produktions-Umgebung in die Cloud zu verschieben, können Sie weiterhin diese Tools verwenden, um die Azure-VMs bereitstellen. Allerdings sollten Sie die Windows-Container als Einheit der Bereitstellung zu verwenden, um die Bereitstellung zu erleichtern.

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[Weiter](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
