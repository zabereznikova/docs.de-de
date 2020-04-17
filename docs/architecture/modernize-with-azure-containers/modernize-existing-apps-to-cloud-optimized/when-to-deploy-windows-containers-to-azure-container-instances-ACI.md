---
title: Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Instances (ACI) erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Instances (ACI) erfolgen sollte
ms.date: 04/29/2018
ms.openlocfilehash: 6c889db6f0475f24a196144c7fb62faec4c173ed
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989154"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Instances (ACI) erfolgen sollte

Der wesentliche Wertbeitrag, den Azure Container Instances bietet, besteht darin, dass Sie Container sofort bereitstellen können und diese Umgebung nicht verwalten müssen. Sie müssen kein Upgrade des zugrunde liegenden Betriebssystems bzw. der VMs durchführen oder diese patchen. Alles ist transparent, und Sie müssen Container lediglich in einer einsatzbereiten Umgebung bereitstellen.

Die Gründe und Szenarien, wann Sie ACI verwenden sollten, ähneln den wesentlichen Szenarien, in denen Sie Azure-VMs mit Containern verwenden. Im Grunde sind also dies die Hauptszenarien für die Verwendung von Azure Container Instances:

- **Entwicklungs-/Testszenarien**
- **Aufgabenautomatisierung**
- **CI/CD-Agents**
- **Verarbeitung kleiner/skalierter Stapel**
- **Einfache Web-Apps**

Das Szenario mit einfachen Web-Apps ist ein faires Szenario für ACI. Sie sollten aber berücksichtigen, dass Sie, weil Sie in ACI nur über eine einzelne Containerinstanz pro Containerimage verfügen können, keine Hochverfügbarkeit und nur begrenzte Skalierbarkeit besitzen werden.

Auch wenn ACI als Infrastruktur betrachtet wird, weil es nur einzelne Containerinstanzen bereitstellt, bietet es im Vergleich zu regulären Azure-VMs mit Windows Server einen immensen Vorteil. Mit ACI stellen Sie lediglich die Container in einer selbstunterhaltenden Umgebung bereit, und Sie zahlen nur für diese Container. Sie müssen keine VMs verwalten, aktualisieren oder patchen. Daher stellt dies eine deutlich bessere Plattform für die meisten Szenarios dar, in denen Sie VMs mit Containern verwenden. Die Verwendung von ACI ist einfach gestaltet, Sie stellen einfach einen Container bereit. Sie müssen keine VM-Umgebung erstellen.

Die Hauptvorteile von Azure Container Instances (ACI) sind:

- Ausführen von Containern ohne Verwaltung von Servern
- Erhöhte Flexibilität durch Container bei Bedarf
- Bereitstellen von Containern in der Cloud mit nie dagewesener Einfachheit und Geschwindigkeit – mit nur einem Befehl.
- Sichere Anwendungen mit Hypervisor-Isolierung

Kurz gesagt, mit ACI können Sie Apps schnell entwickeln, ohne virtuelle Computer verwalten oder neue Tools erlernen zu müssen. Es ist lediglich Ihre Anwendung, in einem Container, die in der Cloud ausgeführt wird.

> [!div class="step-by-step"]
> [Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Weiter](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
