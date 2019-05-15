---
title: Wenn zum Bereitstellen von Windows-Containern zu Azure Container Instances (ACI)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Wenn zum Bereitstellen von Windows-Containern zu Azure Container Instances (ACI)
ms.date: 04/29/2018
ms.openlocfilehash: 9bfa0688d07bd04964a1b28f688f125b5bcd2299
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638922"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Wenn zum Bereitstellen von Windows-Containern zu Azure Container Instances (ACI)

Azure Container Instances main Wertbeitrag liegt darin, dass Sie sofort Sie Container, damit bereitstellen können und zum Verwalten dieser Umgebung müssen nicht, Sie müssen nicht upgraden/Patchen des zugrunde liegenden Betriebssystems oder VMs, alle, die transparent ist und Sie einfach bereitstellen Container in einer Umgebung zu verwendende bereit.

Der Gründe und Szenarios, in denen Sie ACI verwenden möchten sind ähnlich wie die wichtigsten Szenarien, wenn Sie Azure-VMs im Grunde mit Containern verwenden, die wichtigsten Szenarien für die Verwendung von Azure Container Instances sind:

- **Entwicklungs-/Testszenarien**
- **Automatisierung von Aufgaben**
- **CI/CD-agents**
- **Batchverarbeitung von kleinen/Skalierung**
- **Einfache Web-apps**

Das einfache Web-apps-Szenario ist ein ziemlich Szenario für ACI, jedoch müssen Sie berücksichtigen, da in ACI Sie nur eine einzelne Containerinstanz pro Container-Abbild haben können, keine hohen Verfügbarkeit weisen und Skalierbarkeit begrenzt haben.

Auch wenn ACI Infrastruktur betrachtet wird, da sie nur Instanzen der einzelnen Container bereitstellt, besteht jedoch ein großer Vorteil im Vergleich zu regulären Azure-VMs mit Windows Server. Mit ACI Sie nur die Container in einer selbst verwalteten Umgebung bereitstellen, und Sie Zahlen nur für diesen Container. Sie müssen nicht warten/aktualisieren/Patch-VMs, daher ist es eine viel bessere Plattform für die meisten Szenarien, auf dem virtuellen Computer mit Containern verwendet werden kann. Mit ACI ist einfach, Sie stellen nur einen Container bereit, besteht keine Notwendigkeit zum Erstellen einer Umgebung mit virtuellen Computern einfach Bereitstellen von Containern.

Zu den wichtigsten Vorteilen von Azure Container Instances (ACI) sind:

- Führen Sie Container ohne Notwendigkeit zur serververwaltung aus
- Flexibilität durch Container bedarfsgerecht erhöhen
- Stellen Sie Container mit beispielloser Einfachheit und Geschwindigkeit in der Cloud bereit – mit einem einzigen Befehl.
- Sichern von Anwendungen mit hypervisorisolierung

Kurz gesagt, können Sie apps mit ACI entwickeln, schnell voran, ohne virtuelle Computer verwalten oder neue Tools erlernen müssen. Es ist nur Ihre Anwendung, in einem Container, in der Cloud ausgeführt.

> [!div class="step-by-step"]
> [Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Weiter](when-to-deploy-windows-containers-to-service-fabric.md)
