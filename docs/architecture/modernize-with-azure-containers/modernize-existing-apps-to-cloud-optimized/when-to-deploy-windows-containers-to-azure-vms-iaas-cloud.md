---
title: Umstände, unter denen eine Bereitstellung von Windows-Containern auf virtuellen Azure-Computern (IaaS-Cloud) erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Zeitpunkt der Bereitstellung von Windows-Containern in Azure-VMS (IaaS-Cloud)
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577903"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Umstände, unter denen eine Bereitstellung von Windows-Containern auf virtuellen Azure-Computern (IaaS-Cloud) erfolgen sollte

Wenn Ihre Organisation Azure-VMS verwendet, auch wenn Sie auch Windows-Container verwenden, sind Sie immer noch mit IAAS beschäftigt. Dies bedeutet, dass Sie sich mit Infrastruktur Vorgängen, VM-Betriebs Systempatches und Infrastruktur Komplexität für hochgradig skalierbare Anwendungen beschäftigen müssen, wenn Sie die Bereitstellung auf mehreren VMs in einer Infrastruktur mit Lastenausgleich durchzuführen. Die wichtigsten Szenarien für die Verwendung von Windows-Containern auf einem virtuellen Azure-Computer sind:

- **Dev/Test-Umgebung**: Ein virtueller Computer in der Cloud eignet sich ideal für Entwicklung und Tests in der Cloud. Die Umgebung kann je nach Ihren Anforderungen schnell erstellt oder angehalten werden.

- **Kleine und mittlere Skalierbarkeits Anforderungen**: In Szenarien, in denen Sie möglicherweise nur eine Reihe von virtuellen Computern für Ihre Produktionsumgebung benötigen, kann das Verwalten einer kleinen Anzahl von virtuellen Computern so lange kostengünstig sein, bis Sie zu erweiterten Umgebungen wie orchestratoren wechseln können.

- **Produktionsumgebung mit vorhandenen Bereitstellungs Tools**: Möglicherweise wechseln Sie von einer lokalen Umgebung, in der Sie in Tools investiert haben, um komplexe bereit Stellungen für VMS oder Bare-Metal-Server zu erstellen (z.b. Puppet oder ähnliche Tools). Um mit minimalen Änderungen an den Bereitstellungs Verfahren für die Produktionsumgebung in die Cloud zu wechseln, können Sie diese Tools für die Bereitstellung auf Azure-VMS verwenden. Allerdings möchten Sie Windows-Container als Bereitstellungs Einheit verwenden, um die Bereitstellung zu verbessern.

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[Weiter](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
