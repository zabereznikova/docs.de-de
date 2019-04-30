---
title: Was ist Docker?
description: Erhalten Sie ein bisschen tiefer in Ihre Kenntnisse von Docker, hier eine einfache Analogie kann Ihnen ein.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: fbb91466a86c7082e89d0ac4a3673ad83ab39b88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921470"
---
# <a name="what-is-docker"></a>Was ist Docker?

[Docker](https://www.docker.com/) ist ein [Open Source-Projekt](https://github.com/docker/docker) zur Automatisierung der Bereitstellung von Apps als mobile, eigenständige Container, die in der Cloud oder lokal ausgeführt werden können. Docker ist darüber hinaus ein [Unternehmen](https://www.docker.com/), das diese Technologie fördert und weiterentwickelt und mit Cloud-, Linux- und Windows-Anbietern zusammenarbeitet, einschließlich Microsoft.

![Docker-Container können überall ausgeführt werden, lokal im Rechenzentrum des Kunden, bei einem externen Dienstanbieter oder in der Cloud auf Azure.](./media/image2.png)

**Abbildung 1 – 2**. Docker stellt Container auf allen Ebenen der hybriden Cloud bereit

Docker-Imagecontainer können nativ unter Linux und Windows ausgeführt werden. Allerdings können Windows-Images nur auf Windows-Hosts ausgeführt werden, während Linux-Images sowohl auf Linux-Hosts als auch auf Windows-Hosts ausgeführt werden können (bis dato mithilfe einer Hyper-V-Linux-VM), wobei Host einen Server oder eine VM bedeutet.

Entwickler können Entwicklungsumgebungen unter Windows, Linux oder macOS verwenden. Der Entwickler führt auf dem Entwicklungscomputer einen Docker-Host aus, in dem Docker-Images bereitgestellt werden, einschließlich der App und ihrer Abhängigkeiten. Entwickler, die auf dem Mac oder Linux arbeiten verwenden, die Linux-basierten Docker-Host aus, und sie können nur Images für Linux-Container erstellen. (Entwickler, die auf dem Mac arbeiten können Code bearbeiten, oder führen Sie die Docker-Befehlszeilenschnittstelle (CLI) von Mac OS, aber zum Zeitpunkt dieses Artikels nicht Container direkt unter MacOS ausführen.) Entwickler, die unter Windows arbeiten, können Images wahlweise für Linux- oder für Windows-Container erstellen.

Um Container in Entwicklungsumgebungen zu hosten und zusätzliche Entwicklertools bereitzustellen, vertreibt Docker die [Docker Community Edition (CE)](https://www.docker.com/community-edition) für Windows oder für macOS. Diese Produkte installieren die erforderliche VM (den Docker-Host) zum Hosten der Container. Docker stellt außerdem [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition) zur Verfügung, das für die Entwicklung in Unternehmen vorgesehen ist und von IT-Teams verwendet wird, die große, unternehmenswichtige Anwendungen im Produktionsbetrieb erstellen, ausliefern und ausführen.

Es gibt zwei Typen von Runtimes zum Ausführen von [Windows-Containern](/virtualization/windowscontainers/about/):

- **Windows Server-Container** bieten Anwendungsisolation mittels einer isolationstechnologie für Prozesse und Namespaces. Ein Windows Server-Container teilt sich einen Kernel mit dem Containerhost und allen Containern, die auf dem Host ausgeführt werden.

- **Hyper-V-Container** erweitern Sie dann auf die Isolation von Windows Server-Container bereitgestellt werden, indem jeder Container in einem hochgradig optimierten virtuellen Computer ausgeführt wird. In dieser Konfiguration wird der Kernel des Containerhosts nicht für den Hyper-V-Container freigegeben, was die Isolierung verbessert.

Die Images für diese Container werden erstellt und funktionieren nur die gleiche Weise. Der Unterschied besteht darin, wie der Container aus dem Image erstellt wird – ein Hyper-V-Container ausgeführt wird, erfordert einen zusätzlichen Parameter. Weitere Informationen finden Sie unter [Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container).

## <a name="comparing-docker-containers-with-virtual-machines"></a>Vergleichen von Docker-Containern mit virtuellen Computern

Abbildung 1 – 3 zeigt einen Vergleich zwischen virtuellen Computern und Docker Container.

![Bei VMs gibt es drei Basisebenen auf dem Host-Server. Unten beginnend sind dies: Infrastruktur, Hostbetriebssystem und Hypervisor, und auf all dem aufsetzend weist jede VM ihr eigenes Betriebssystem und alle erforderlichen Bibliotheken auf. Auf der anderen Seite für Docker, der Hostserver nur verfügt über die Infrastruktur und das Betriebssystem und auf, die Container-Engine, die verfolgt Container isoliert, aber die Betriebssystem-Basisdienste freigeben.](./media/image3.png)

**Abbildung 1 – 3**. Vergleichen der herkömmlichen virtuellen Computer mit Docker-Containern

Da Container wesentlich weniger Ressourcen benötigen (z.B. keine Vollversion des Betriebssystems), lassen sie sich einfach bereitstellen und schnell hochfahren. Das ermöglicht eine höhere Dichte, d.h. es erlaubt Ihnen, mehr Dienste auf der gleichen Hardwareeinheit auszuführen, was geringere Kosten verursacht.

Als Nebenwirkung der Ausführung auf dem gleichen Kernel erhalten Sie weniger Isolation als bei VMs.

Das Hauptziel eines Bilds wird die gleiche Umgebung (Abhängigkeiten) in verschiedene Bereitstellungen sichergestellt. Dies bedeutet, dass Sie ihn auf Ihrem Computer debuggen und klicken Sie dann auf einen anderen Computer, die dieselbe Umgebung gewährleistet bereitstellen können.

Mit einem Containerimage können Sie eine Anwendung oder einen Dienst packen und beides auf zuverlässige und reproduzierbare Weise bereitstellen. Docker ist also nicht bloß eine Technologie, sondern eine Philosophie und ein Prozess.

Wenn Docker eingesetzt wird, hören Sie von Entwicklern nie: „Es funktioniert auf meinem Computer. Warum also nicht auch in der Produktion?“ Sie dürfen auch einfach schreiben, "Ausführung in Docker", da die verpackte Docker-Anwendung ausgeführt werden kann, auf alle unterstützten Docker-Umgebung und die Möglichkeit, sie dafür konzipiert wurde, auf allen bereitstellungszielen ausgeführt (z. B. Entwicklung, Qualitätssicherung, Staging und Produktion).

## <a name="a-simple-analogy"></a>Eine einfache Analogie

Vielleicht kann eine einfache Analogie beim Verständnis des Kernkonzepts von Docker hilfreich sein.

Gehen wir einen Augenblick lang zurück in die 1950-er Jahre. Gab es keine Textverarbeitungsprogrammen, und die fotokopierer überall verwendet wurden (na ja, fast).

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
