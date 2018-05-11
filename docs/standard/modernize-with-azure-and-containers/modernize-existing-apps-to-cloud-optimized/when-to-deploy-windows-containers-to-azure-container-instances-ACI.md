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
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Wenn Sie Windows-Container auf Azure-Container Instanzen (ACI) bereitstellen

Azure-Container-Instanzen, die wichtigsten Wertbeitrag ist, können sofort das Bereitstellen von Containern, und Sie diese Umgebung zu verwalten müssen, müssen Sie keine Upgrades/Patches zugrunde liegende Betriebssystem oder der virtuelle Computer, die transparent ist und Sie nur bereitstellen Container in einer Umgebung zu verwendende bereit.

Die Gründe und Szenarien, in denen Sie ACI verwenden möchten ähneln die Hauptszenarien beim Azure-VMs also im Grunde mit Containern verwenden, werden die Hauptszenarien für die Verwendung von Azure-Container-Instanzen:

-   **Entwicklungs-/Testszenarios**
-   **Automatisierung von Aufgaben**
-   **CI-CD-agents**
-   **Kleine/Skalierung-Batchverarbeitung**
-   **Einfache Web-apps**

Das einfache Web-apps-Szenario ist ein ziemlich Szenario für ACI, jedoch müssen Sie berücksichtigen, da in ACI Sie nur eine einzelnen Container-Instanz pro Container-Abbild aufweisen können, keine hohen Verfügbarkeit und Skalierbarkeit beschränkt sind.

Selbst wenn ACI Infrastruktur betrachtet, da sie nur Instanzen der einzelnen Container bereitstellt, besteht jedoch ein großer Vorteil im Vergleich zu normalen Azure-VMs mit Windows Server. Mit ACI Sie nur die Container in einer Umgebung mit sich selbst bereitstellen, und Sie bezahlen nur für diesen Container. Sie müssen nicht warten/aktualisieren/Patch-VMs, daher ist es eine viel bessere Plattform für die meisten Szenarien, in dem Sie virtuelle Computer mit Containern verwenden werden können. Mithilfe von ACI nachvollziehbar ist ganz einfach, Sie stellen nur einen Container bereit, besteht keine Notwendigkeit zum Erstellen einer Umgebung mit virtuellen Computern nur Bereitstellen von Containern.

Die Hauptvorteile von Azure-Container Instanzen (ACI) sind:

-   Container ausgeführt werden, ohne die Verwaltung von Servern
-   Erhöhen der Flexibilität mit Containern bei Bedarf
-   Container in der Cloud unvergleichlich hohe Einfachheit und gleicher Geschwindigkeit Bereitstellen – mit einem einzigen Befehl. 
-   Sicherer Anwendungen Hypervisor Isolation

Kurz gesagt, können Sie apps mit ACI entwickeln, fast ohne Verwaltung virtueller Computer oder neuen Tools vertraut machen zu müssen. Es ist nur die Anwendung in einem Container, in der Cloud ausgeführt.

>[!div class="step-by-step"]
[Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Weiter](when-to-deploy-windows-containers-to-service-fabric.md)
