---
title: Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Instances (ACI) erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Instances (ACI) erfolgen sollte
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577933"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Umstände, unter denen eine Bereitstellung von Windows-Containern in Azure Container Instances (ACI) erfolgen sollte

Der wesentliche Wertbeitrag, den Azure Container Instances bietet, ist, dass Sie Container sofort darin bereitstellen können und diese Umgebung nicht unterhalten müssen. Sie müssen kein Upgrade des zugrunde liegenden Betriebssystems bzw. der VMs durchführen oder diese patchen, während alles transparent ist, und Sie lediglich Container in einer einsatzbereiten Umgebung bereitstellen.

Die Gründe und Szenarien, wann Sie ACI verwenden sollten, ähneln den wesentlichen Szenarien, in denen Sie Azure-VMs mit Containern verwenden. Im Grunde sind also dies die Hauptszenarien für die Verwendung von Azure Container Instances:

- **Entwicklungs-/Testszenarien**
- **Aufgabenautomatisierung**
- **CI/CD-Agents**
- **Verarbeitung kleiner/skalierter Stapel**
- **Einfache Web-Apps**

Das Szenario mit einfachen Web-Apps ist ein faires Szenario für ACI. Sie sollten aber berücksichtigen, dass Sie, weil Sie in ACI nur über eine einzelne Containerinstanz pro Containerimage verfügen können, keine Hochverfügbarkeit und nur begrenzte Skalierbarkeit besitzen werden.

Auch wenn ACI als Infrastruktur betrachtet wird, weil es nur einzelne Containerinstanzen bereitstellt, bietet es im Vergleich zu regulären Azure-VMs mit Windows Server einen immensen Vorteil. Mit ACI stellen Sie lediglich die Container in einer selbstunterhaltenden Umgebung bereit, und Sie zahlen nur für diese Container. Sie müssen keine VMs verwalten/aktualisieren/patchen, sodass dies eine wesentlich bessere Plattform für die meisten Szenarien ist, in denen Sie möglicherweise VMs mit Containern verwenden würden. Die Verwendung von ACI ist geradlinig, wobei Sie nur einen Container bereitstellen und keine Notwendigkeit besteht, eine VM-Umgebung erstellen zu müssen – Sie stellen nur Container bereit.

Die Hauptvorteile von Azure Container Instances (ACI) sind:

- Ausführen von Containern ohne Verwaltung von Servern
- Erhöhte Flexibilität durch Container bei Bedarf
- Bereitstellen von Containern in der Cloud mit nie dagewesener Einfachheit und Geschwindigkeit – mit nur einem Befehl.
- Sichere Anwendungen mit Hypervisor-Isolierung

Kurz gesagt, mit ACI können Sie Apps schnell entwickeln, ohne virtuelle Computer verwalten oder neue Tools erlernen zu müssen. Es ist lediglich Ihre Anwendung, in einem Container, die in der Cloud ausgeführt wird.

> [!div class="step-by-step"]
> [Zurück](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Weiter](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
