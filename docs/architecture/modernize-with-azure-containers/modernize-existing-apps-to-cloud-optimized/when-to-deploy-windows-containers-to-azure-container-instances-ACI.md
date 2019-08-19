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
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Zeitpunkt der Bereitstellung von Windows-Containern für Azure Container Instances (ACI)

Azure Container Instances Haupt Wertbeitrag besteht darin, dass Sie sofort Container bereitstellen können, und Sie müssen diese Umgebung nicht pflegen. Sie müssen das zugrunde liegende Betriebssystem oder die VMs nicht aktualisieren/Patchen. das ist alles transparent, und Sie stellen einfach bereit. Container in einer einsatzbereiten Umgebung.

Die Gründe und Szenarios für die Verwendung von ACI ähneln den Haupt Szenarien, in denen Sie Azure-VMS mit Containern verwenden. im Grunde sind die wichtigsten Szenarien für die Verwendung von Azure Container Instances:

- **Dev/Test-Szenarios**
- **Aufgabenautomatisierung**
- **CI/CD-Agents**
- **Kleine/skalierbare Batch Verarbeitung**
- **Einfache Web-Apps**

Das einfache Web-Apps-Szenario ist ein faires Szenario für ACI, aber berücksichtigen Sie, dass Sie in ACI nur über eine einzelne Container Instanz pro Container Image verfügen können, weil Sie nicht über Hochverfügbarkeit verfügen und nur eine begrenzte Skalierbarkeit haben.

Auch wenn ACI als Infrastruktur betrachtet wird, weil es nur einzelne Container Instanzen bereitstellt, bietet es im Vergleich zu regulären Azure-VMS mit Windows Server einen großen Vorteil. Mit ACI stellen Sie die Container nur in einer selbstverwalteten Umgebung bereit, und Sie zahlen nur für diese Container. Sie müssen VMS nicht verwalten/aktualisieren/Patchen, sodass es für die meisten Szenarien, in denen Sie möglicherweise VMS mit Containern verwenden, eine viel bessere Plattform ist. Wenn Sie nur einen Container bereitstellen, ist es nicht erforderlich, eine VM-Umgebung zu erstellen, in der Sie nur Container bereitstellen.

Die Hauptvorteile von Azure Container Instances (ACI) sind:

- Ausführen von Containern ohne Serververwaltung
- Flexibilität durch Container Bedarfs gesteuert erhöhen
- Stellen Sie mit einem einzigen Befehl Container in der Cloud bereit, ohne die Einfachheit und Geschwindigkeit –.
- Sichere Anwendungen mit Hypervisor-Isolation

Kurz gesagt, mit ACI können Sie apps schnell entwickeln, ohne virtuelle Computer zu verwalten oder neue Tools erlernen zu müssen. Es ist nur Ihre Anwendung, in einem Container, der in der Cloud ausgeführt wird.

> [!div class="step-by-step"]
> [Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Weiter](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
