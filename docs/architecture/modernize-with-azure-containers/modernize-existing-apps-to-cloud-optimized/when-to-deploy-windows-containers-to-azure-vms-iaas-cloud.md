---
title: Umstände, unter denen eine Bereitstellung von Windows-Containern auf virtuellen Azure-Computern (IaaS-Cloud) erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Umstände, unter denen eine Bereitstellung von Windows-Containern auf virtuellen Azure-Computern (IaaS-Cloud) erfolgen sollte
ms.date: 12/21/2020
ms.openlocfilehash: 64ba53fa56227266ee0e61a128d18373a2dbbc93
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025093"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Umstände, unter denen eine Bereitstellung von Windows-Containern auf virtuellen Azure-Computern (IaaS-Cloud) erfolgen sollte

Wenn Ihre Organisation Azure-VMs verwendet, auch wenn Sie ebenfalls Windows-Container verwenden, haben Sie immer noch mit IaaS zu tun. Dies bedeutet, dass Sie mit Infrastrukturvorgängen, VM-Betriebssystempatches und Infrastrukturkomplexität für hochgradig skalierbare Anwendungen zu tun haben, wenn Sie die Bereitstellung auf mehreren VMs in einer Infrastruktur mit Lastenausgleich durchführen müssen. Die wichtigsten Szenarien für die Verwendung von Windows-Containern auf einem virtuellen Azure-Computer sind:

- **Entwicklungs-/Testumgebung**: Ein virtueller Computer in der Cloud eignet sich ideal für Entwicklung und Tests in der Cloud. Sie können die Umgebung je nach Ihren Anforderungen schnell erstellen oder anhalten.

- **Kleine und mittlere Skalierbarkeitsanforderungen**: In Szenarios, in denen Sie möglicherweise nur einige wenige virtuelle Computer für Ihre Produktionsumgebung benötigen, kann das Verwalten weniger virtueller Computer so lange kostengünstig sein, bis Sie zu komplexeren PaaS-Umgebungen wie Orchestratoren wechseln können.

- **Produktionsumgebung mit vorhandenen Bereitstellungstools**: Möglicherweise wechseln Sie von einer lokalen Umgebung, in der Sie in Tools investiert haben, um komplexe Bereitstellungen auf VMs oder physischen Servern (Bare-Metal) vorzunehmen (z. B. Puppet oder ähnliche Tools). Um mit nur minimalen Änderungen an den Bereitstellungsverfahren der Produktionsumgebung in die Cloud zu wechseln, könnten Sie diese Tools für die Bereitstellung auf Azure-VMs weiterhin verwenden. Allerdings sollten Sie Windows-Container als Bereitstellungseinheit verwenden, um die Bereitstellungserfahrung zu verbessern.

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[Weiter](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
