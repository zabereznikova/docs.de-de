---
title: Umstände, unter denen eine Bereitstellung von Windows-Containern auf virtuellen Azure-Computern (IaaS-Cloud) erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Umstände, unter denen eine Bereitstellung von Windows-Containern auf virtuellen Azure-Computern (IaaS-Cloud) erfolgen sollte
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69577903"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Umstände, unter denen eine Bereitstellung von Windows-Containern auf virtuellen Azure-Computern (IaaS-Cloud) erfolgen sollte

Wenn Ihre Organisation Azure-VMs verwendet, auch wenn Sie ebenfalls Windows-Container verwenden, haben Sie immer noch mit IaaS zu tun. Dies bedeutet, dass Sie mit Infrastrukturvorgängen, VM-Betriebssystempatches und Infrastrukturkomplexität für hochgradig skalierbare Anwendungen zu tun haben, wenn Sie die Bereitstellung auf mehreren VMs in einer Infrastruktur mit Lastenausgleich durchführen müssen. Die wichtigsten Szenarien für die Verwendung von Windows-Containern auf einem virtuellen Azure-Computer sind:

- **Entwicklungs-/Testumgebung**: Ein virtueller Computer in der Cloud eignet sich ideal für Entwicklung und Tests in der Cloud. Sie können die Umgebung je nach Ihren Anforderungen schnell erstellen oder anhalten.

- **Kleine und mittlere Skalierbarkeitsanforderungen**: In Szenarien, in denen Sie eventuell nur ein paar virtuelle Computer für Ihre Produktionsumgebung benötigen, kann das Verwalten einer kleinen Anzahl von virtuellen Computern so lange kostengünstig sein, bis Sie zu komplexeren PaaS-Umgebungen wie Orchestratoren wechseln können.

- **Produktionsumgebung mit vorhandenen Bereitstellungstools**: Möglicherweise wechseln Sie von einer lokalen Umgebung, in der Sie in Tools investiert haben, um komplexe Bereitstellungen auf VMs oder physischen Servern (Bare-Metal) vorzunehmen (z. B. Puppet oder ähnliche Tools). Um mit nur minimalen Änderungen an den Bereitstellungsverfahren der Produktionsumgebung in die Cloud zu wechseln, könnten Sie diese Tools für die Bereitstellung auf Azure-VMs weiterhin verwenden. Allerdings sollten Sie Windows-Container als Bereitstellungseinheit verwenden, um die Bereitstellungserfahrung zu verbessern.

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[Weiter](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
