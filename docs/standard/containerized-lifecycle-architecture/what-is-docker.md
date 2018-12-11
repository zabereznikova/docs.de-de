---
title: Was ist Docker?
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 360a404e38651b78acc3a52d8102a4dae71f3e30
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152709"
---
# <a name="what-is-docker"></a>Was ist Docker?

[Docker](https://www.docker.com/) ist ein [Open Source-Projekt](https://github.com/docker/docker) zur Automatisierung der Bereitstellung von Anwendungen als Mobile, eigenständige Container, die in der Cloud oder lokal ausgeführt werden kann (siehe Abbildung 1: 2). Docker ist außerdem eine [Unternehmen](https://www.docker.com/) , stuft und arbeiten in Zusammenarbeit mit Cloud-, Linux- und Windows-Herstellern einschließlich Microsoft diese Technologie entwickelt.

![](./media/image2.png)

Abbildung 1 – 2: Docker stellt Container auf allen Ebenen der hybriden Cloud bereit

Docker-Imagecontainer können nativ unter Linux und Windows ausgeführt werden. Allerdings können Windows-Images nur auf Windows-Hosts ausführen und Linux-Images können nur auf Linux-Hosts, d. h. einen Hostserver oder einen virtuellen Computer ausgeführt.

Entwickler können Entwicklungsumgebungen unter Windows, Linux oder macOS verwenden. Auf dem Entwicklungscomputer führt der Entwickler einen Docker-Host, welche docker Images bereitgestellt werden, einschließlich der app und die zugehörigen Abhängigkeiten, an. Entwickler, die unter Linux oder auf dem Mac arbeiten, verwenden einen Linux-basierten Docker-Host und können nur Images für Linux-Container erstellen. (Entwickler, die auf dem Mac arbeiten Code bearbeiten oder Ausführen der Docker-Befehlszeilenschnittstelle können \[CLI\] unter MacOS, aber, während ich dies schreibe, sind Container nicht direkt unter MacOS ausgeführt.) Entwickler, die unter Windows arbeiten, können Images wahlweise für Linux- oder für Windows-Container erstellen.

Um Container in Entwicklungsumgebungen zu hosten und zusätzliche Entwicklertools bereitzustellen, vertreibt Docker die [Docker Community Edition (CE)](https://www.docker.com/community-edition) für Windows oder für macOS. Diese Produkte installieren die erforderliche VM (den Docker-Host) zum Hosten der Container. Docker stellt außerdem [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition) zur Verfügung, das für die Entwicklung in Unternehmen vorgesehen ist und von IT-Teams verwendet wird, die große, unternehmenswichtige Anwendungen im Produktionsbetrieb erstellen, ausliefern und ausführen.

Es gibt zwei Typen von Runtimes zum Ausführen von [Windows-Containern](/virtualization/windowscontainers/about/):

-   **Windows Server-Container** diese Runtime bietet Anwendungsisolation mittels einer isolationstechnologie für Prozesse und Namespaces. Ein Windows Server-Container teilt sich einen Kernel mit dem Containerhost und allen Containern, die auf dem Host ausgeführt werden.

-   **Hyper-V-Container** erstreckt sich auf die Isolation von Windows Server-Container bereitgestellt werden, indem jeder Container in einem hochgradig optimierten virtuellen Computer ausgeführt wird. In dieser Konfiguration wird der Kernel des Containerhosts nicht für den Hyper-V-Container freigegeben, was die Isolierung verbessert.

Die Images für diese Container werden auf die gleiche Weise erstellt und sind funktional gleich. Der Unterschied besteht darin, wie der Container aus dem Image erstellt wird – ein Hyper-V-Container ausgeführt wird, erfordert einen zusätzlichen Parameter. Weitere Informationen finden Sie unter [Windows-Container](/virtualization/windowscontainers/about/).

## <a name="comparing-docker-containers-with-vms"></a>Vergleichen von Docker-Containern mit virtuellen Computern

Abbildung 1 – 3 zeigt einen Vergleich zwischen virtuellen Computern und Docker Container.

Da Container wesentlich weniger Ressourcen benötigen (z. B. sie ist nicht erforderlich, eine Vollversion des Betriebssystems), sie sind einfach bereitzustellen und sie schnell starten. Dies ermöglicht es Ihnen, höheren Dichte, was bedeutet, dass Sie weitere Dienste auf derselben Hardware-Einheit, wodurch Kosten ausführen können.

Als Nebeneffekt der auf demselben Kernel ausgeführt wird erzielen Sie weniger Isolierung, als virtuelle Computer.

Der Hauptzweck eines Images ist, die Umgebung (Abhängigkeiten) in verschiedene Bereitstellungen anzugleichen. Das bedeutet, dass Sie sie auf Ihrem Computer debuggen und sie dann auf einem anderen Computer bereitstellen können, wenn dieselbe Umgebung gewährleistet ist.

Ein Container-Abbild ist eine Möglichkeit zum Verpacken einer app oder einem Dienst und in eine zuverlässige und reproduzierbare Weise bereitstellen. In dieser Hinsicht Docker nicht nur eine Technologie, es ist auch eine Philosophie und einen Prozess.

Mithilfe von Docker nicht hören Sie Entwickler sagen, "Es auf meinem Computer funktioniert, warum also nicht in der Produktion?" Sie können beispielsweise "Für Docker, Ausführung", da die verpackte Docker-Anwendung auf jeder unterstützten Docker-Umgebung ausgeführt werden kann und wie gewünscht, für alle Bereitstellungsziele (Entwicklung, Qualitätssicherung, staging, Produktion usw..) ausgeführt wird.

![](./media/image3.png)

Abbildung 1 – 3: Vergleich der herkömmlichen virtuellen Computern in Docker-Containern

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](docker-terminology.md)