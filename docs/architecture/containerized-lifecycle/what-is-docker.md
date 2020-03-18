---
title: Was ist Docker?
description: Beim tieferen Einstieg in Ihre Docker-Kenntnisse kann Ihnen vielleicht eine einfache Analogie helfen.
ms.date: 02/15/2019
ms.openlocfilehash: e3b3685f2fc6d5a9d33bb176d04ca910f0289344
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76919880"
---
# <a name="what-is-docker"></a>Was ist Docker?

[Docker](https://www.docker.com/) ist ein [Open Source-Projekt](https://github.com/docker/docker) zur Automatisierung der Bereitstellung von Apps als mobile, eigenständige Container, die in der Cloud oder lokal ausgeführt werden können. Docker ist darüber hinaus ein [Unternehmen](https://www.docker.com/), das diese Technologie fördert und weiterentwickelt und mit Cloud-, Linux- und Windows-Anbietern zusammenarbeitet, einschließlich Microsoft.

![Diagramm, das die Orte zeigt, an denen Docker-Container ausgeführt werden können.](./media/what-is-docker/docker-containers-run-anywhere.png)

**Abbildung 1–2**. Docker stellt Container auf allen Ebenen der hybriden Cloud bereit

Wie in dem vorherigen Diagramm gezeigt, können Docker-Container überall ausgeführt werden, lokal im Rechenzentrum des Kunden, bei einem externen Dienstanbieter oder in der Cloud auf Azure. Docker-Imagecontainer können auch nativ unter Linux und Windows ausgeführt werden. Allerdings können Windows-Images nur auf Windows-Hosts ausgeführt werden, während Linux-Images sowohl auf Linux-Hosts als auch auf Windows-Hosts ausgeführt werden können (bis dato mithilfe einer Hyper-V-Linux-VM), wobei Host einen Server oder eine VM bedeutet.

Entwickler können Entwicklungsumgebungen unter Windows, Linux oder macOS verwenden. Der Entwickler führt auf dem Entwicklungscomputer einen Docker-Host aus, in dem Docker-Images bereitgestellt werden, einschließlich der App und ihrer Abhängigkeiten. Entwickler, die unter Linux oder auf dem Mac arbeiten, verwenden einen Linux-basierten Docker-Host und können nur Images für Linux-Container erstellen. (Entwickler, die auf dem Mac arbeiten, können Code bearbeiten oder die Docker-CLI unter macOS ausführen, aber zum Entstehungszeitpunkt dieses Texts können Container nicht direkt unter macOS ausgeführt werden.) Entwickler, die unter Windows arbeiten, können Images wahlweise für Linux- oder für Windows-Container erstellen.

Um Container in Entwicklungsumgebungen zu hosten und zusätzliche Entwicklertools bereitzustellen, vertreibt Docker die [Docker Community Edition (CE)](https://www.docker.com/community-edition) für Windows oder für macOS. Diese Produkte installieren die erforderliche VM (den Docker-Host) zum Hosten der Container. Docker stellt außerdem [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition) zur Verfügung, das für die Entwicklung in Unternehmen vorgesehen ist und von IT-Teams verwendet wird, die große, unternehmenswichtige Anwendungen im Produktionsbetrieb erstellen, ausliefern und ausführen.

Es gibt zwei Typen von Runtimes zum Ausführen von [Windows-Containern](/virtualization/windowscontainers/about/):

- **Windows Server-Container** bieten Isolation von Anwendungen durch Technologie zur Isolation von Prozessen und Namespaces. Ein Windows Server-Container teilt sich einen Kernel mit dem Containerhost und allen Containern, die auf dem Host ausgeführt werden.

- **Hyper-V-Container** erweitern die durch Windows Server-Container bereitgestellte Isolierung, indem jeder Container in einem hochgradig optimierten virtuellen Computer ausgeführt wird. In dieser Konfiguration wird der Kernel des Containerhosts nicht für den Hyper-V-Container freigegeben, was die Isolierung verbessert.

Die Images für diese Container werden genauso erstellt und funktionieren auch so. Der Unterschied besteht darin, wie der Container aus dem Image erstellt wird: Für das Ausführen eines Hyper-V-Containers ist ein Zusatzparameter erforderlich. Weitere Informationen finden Sie unter [Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container).

## <a name="comparing-docker-containers-with-virtual-machines"></a>Vergleichen von Docker-Containern mit virtuellen Computern

In Abbildung 1–3 wird ein Vergleich zwischen virtuellen Computern und Docker Containern dargestellt.

![Diagramm, das einen Vergleich zwischen VM- und Containerumgebungen zeigt.](./media/what-is-docker/comparison-vms-docker-conatiners.png)

**Abbildung 1–3**. Vergleichen der herkömmlichen virtuellen Computer mit Docker-Containern

Wie im vorherigen Diagramm gezeigt, gibt es für VMs auf dem Hostserver drei Basisebenen. Von unten nach oben: Infrastruktur, Hostbetriebssystem und ein Hypervisor. Auf alledem besitzt jede VM ihr eigene Betriebssystem sowie alle notwendigen Bibliotheken. Auf der anderen Seite verfügt der Hostserver für Docker nur über die Infrastruktur und das Betriebssystem. Darüber hinaus hält die Container-Engine Container isoliert, lässt sie aber die Dienste des einzelnen Basisbetriebssystems gemeinsam nutzen.

Da Container wesentlich weniger Ressourcen benötigen (z.B. keine Vollversion des Betriebssystems), lassen sie sich einfach bereitstellen und schnell hochfahren. Das ermöglicht eine höhere Dichte, d.h. es erlaubt Ihnen, mehr Dienste auf der gleichen Hardwareeinheit auszuführen, was geringere Kosten verursacht.

Als Nebenwirkung der Ausführung auf dem gleichen Kernel erhalten Sie weniger Isolation als bei VMs.

Der Hauptzweck eines Images besteht darin, in verschiedenen Bereitstellungen die gleiche Umgebung (Abhängigkeiten) sicherzustellen. Das bedeutet, dass Sie sie auf Ihrem Computer debuggen und sie dann auf einem anderen Computer bereitstellen können, wenn dieselbe Umgebung gewährleistet ist.

Mit einem Containerimage können Sie eine Anwendung oder einen Dienst packen und beides auf zuverlässige und reproduzierbare Weise bereitstellen. Docker ist also nicht bloß eine Technologie, sondern eine Philosophie und ein Prozess.

Wenn Docker eingesetzt wird, hören Sie von Entwicklern nie: „Es funktioniert auf meinem Computer. Warum also nicht auch in der Produktion?“ Sie können einfach sagen : „Es funktioniert in Docker“, da die verpackte Docker-Anwendung in jeder unterstützten Docker-Umgebung ausgeführt werden kann, und sie funktioniert auf allen Bereitstellungszielen (wie Dev, QA, Staging und Produktion) wie vorgesehen.

## <a name="a-simple-analogy"></a>Eine einfache Analogie

Vielleicht kann eine einfache Analogie beim Verständnis des Kernkonzepts von Docker hilfreich sein.

Gehen wir einen Augenblick lang zurück in die 1950-er Jahre. Es gab keine Textverarbeitungsprogramme, und überall (naja, fast überall) wurden Fotokopierer benutzt.

Angenommen, Sie wären dafür zuständig gewesen, stapelweise Briefe nach Bedarf per Post an Kunden zu verschicken, auf richtigem Papier und in Umschlägen für die physische Zustellung an die Adresse jedes einzelnen Kunden (damals gab es noch keine E-Mail).

An einem bestimmten Punkt fällt Ihnen auf, dass die Briefe nur eine Zusammenstellung einer großen Sammlung von Absätzen sind, die nach Bedarf ausgewählt und angeordnet werden, je nach dem Zweck des Briefs, also denken Sie sich ein System aus, Briefe schnell fertigzustellen, und erwarten eine üppige Gehaltserhöhung.

Das System ist einfach:

1. Sie beginnen mit einem Satz Transparentfolien, die jeweils einen Absatz enthalten.

2. Um einen Satz Briefe fertigzustellen, wählen Sie die Folien mit den benötigten Absätzen aus, dann stapeln Sie sie und richten sie aus, so dass sie gut aussehen und sich einwandfrei lesen lassen.

3. Schließlich platzieren Sie den Stapel im Fotokopierer und drücken den Startknopf, um so viele Briefe wie nötig zu erstellen.

Vereinfacht ist das der Kerngedanke von Docker.

In Docker ist jede Schicht die sich ergebende Menge von Änderungen, die im Dateisystem nach dem Ausführen eines Befehls auftreten, etwa beim Installieren eines Programms.

Wenn Sie sich das Dateisystem nach dem Kopieren der Schicht „ansehen“, sehen Sie alle Dateien, einschließlich der Schicht, auf der das Programm installiert wurde.

Sie können sich ein Image als eine schreibgeschützte Behelfsfestplatte vorstellen, die zur Installation auf einem „Computer“ bereit ist, der bereits ein Betriebssystem enthält.

In ähnlicher Weise stellt ein Container diesen „Computer“ dar, mit angeschlossener Image-„Festplatte“. Der Container kann ein- und ausgeschaltet werden, ganz wie ein Computer.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](docker-terminology.md)
