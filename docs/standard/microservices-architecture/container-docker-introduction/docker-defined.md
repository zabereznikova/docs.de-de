---
title: Was ist Docker?
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Was ist Docker?"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: aa9cb379628fa91e5dc5b1b529f92db98fa59305
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="what-is-docker"></a>Was ist Docker?

[Docker](https://www.docker.com/) ist ein [Open Source-Projekts](https://github.com/docker/docker) zum Automatisieren der Bereitstellung von Anwendungen als portable, eigenständiger Container, die auf die Cloud oder lokal ausgeführt werden können. Docker ist auch eine [Unternehmen](https://www.docker.com/) , stuft und diese Technologie weiterentwickelt. Docker funktioniert in Zusammenarbeit mit der Cloud, Linux und Windows-Herstellern, einschließlich Microsoft.

![](./media/image2.png)

**Abbildung 2 x 2**. Docker stellt Container auf allen Ebenen der hybridcloud

Docker-Image-Containern dann nativ unter Linux und Windows ausführen. Führen Sie Windows-Abbildern nur auf Hosts mit Windows und Linux-Images können nur auf Linux-Hosts ausgeführt. Der Host ist ein Server oder einem virtuellen Computer.

Sie können unter Windows, Linux oder MacOS entwickeln. Der Entwicklungscomputer wird einen Docker-Host ausgeführt, in dem Docker-Images, einschließlich der app und die zugehörigen Abhängigkeiten bereitgestellt werden. Unter Linux oder MacOS verwenden Sie einen Docker-Host, der Linux-basierten und Images nur für Linux-Container erstellen. (Auf MacOS können Sie Code bearbeiten oder Ausführen von Docker-Befehlszeilenschnittstelle, aber zum Zeitpunkt der Erstellung dieses Dokuments, Container führen Sie nicht direkt auf MacOS.) Unter Windows können Sie Bilder für Linux- oder Windows-Container erstellen.

Unter Windows oder MacOS [Docker Community Edition (CE)](https://www.docker.com/community-edition) Container in einer Entwicklungsumgebung gehostet und bietet zusätzliche Entwicklertools. [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition) dient der IT-Teams, die erstellen, senden und große unternehmenswichtige Anwendungen ausführen. ~ Beide Produkte installiert die erforderliche VM (die Docker-Host) zum Hosten der Container. ~ 

[Windows-Containern](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) funktionieren mit zwei Typen von Laufzeiten:

-   Windows Server-Container bieten Anwendungsisolation mittels einer isolationstechnologie für Prozesse und Namespaces. Windows Server-Container teilt sich einen Kernel mit dem containerhost und allen Container, die auf dem Host ausgeführt.

-   Hyper-V-Container werden erweitert, auf die Isolierung durch Windows Server-Container, indem jeder Container in einem hochgradig optimierten virtuellen Computer ausgeführt wird. In dieser Konfiguration wird der Kernel des containerhosts nicht gemeinsam mit Hyper-V-Container, eine bessere Isolierung bereitstellen. Hyper-V-Container ermöglichen als nicht vertrauenswürdig eingestuft und *feindlichen mit mehreren Mandanten* Anwendungen auf demselben Host ausgeführt. Hyper-V-Containern haben etwas weniger Effizienz in Startzeiten und die dichteergebnisse als Windows Server-Container.

Die Images für diese Container werden erstellt und funktionieren genauso. Sie unterscheiden sich im wie der Container erstellt wird. Weitere Informationen finden Sie unter [Hyper-V-Container](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview).

## <a name="comparing-docker-containers-with-virtual-machines"></a>Vergleich von Docker-Containern mit virtuellen Computern

Abbildung 2 – 3 zeigt einen Vergleich zwischen virtuellen Computern und die Docker Container.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Virtuelle Maschinen****Docker-Containern** 
                                                                                                                                                                                        
  ![](./media/image3.png)                                                                                                                                ![](./media/image4.png)
                                                                                                                                                                                        
  Virtuelle Computer enthalten, die Anwendung, die erforderlichen Bibliotheken oder Binärdateien und vollständige Gastbetriebssystem. Vollständige Virtualisierung erfordert mehr Ressourcen als Containerization. Container enthalten, die Anwendung und alle seine Abhängigkeiten. Allerdings Freigeben von Containern mit anderen Containern den Betriebssystem-Kernel. Container werden als isolierte Prozesse im Raum für Benutzer auf das Hostbetriebssystem ausgeführt. Außer in Hyper-V-Container, bei dem jeder Container in einem speziellen virtuellen Computer pro Container ausgeführt wird.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Abbildung 2 – 3**. Vergleich der herkömmlichen virtuellen Computern in Docker-Containern

Da Container wesentlich weniger Ressourcen benötigen (z. B. sie ist nicht erforderlich, eine Vollversion des Betriebssystems), sie starten schnell und einfach bereitzustellen sind. Geringe ressourcennutzung ermöglicht höhere Dichte an. Sie können weitere Dienste auf derselben Hardware Einheit ausführen und senken.

Ausgeführt wird, auf den gleichen Kernel-Ergebnissen weniger isoliert, die als virtuelle Computer bieten.

Der Hauptzweck eines Bilds ist, dass der Umgebung (Abhängigkeiten) die gleiche über verschiedene Bereitstellungen vereinfacht. Dies bedeutet, dass Sie auf Ihrem Computer debuggen und dann mit der gleichen Umgebung sichergestellt, dass auf einen anderen Computer bereitstellen können.

Ein Container-Abbild ist eine Möglichkeit zum Verpacken einer Anwendung oder einem Dienst und so zuverlässige und reproduzierbare bereitstellen. Konnte sagen, dass es sich bei Docker nicht nur eine Technologie, jedoch auch eine Philosophie und ein Prozess ist.

Docker-Entwickler z. nicht b. "Auf meinem Computer Warum nicht in der Produktion Funktionsweise?" Es wird argumentiert, "Es auf Docker runs". Docker-App-Paket-apps können auf alle unterstützten Docker-Umgebung ausgeführt werden. Docker App-Pakete, die konsistent auf alle Bereitstellungsziele verwenden (Dev, QA, staging, Produktion) ausgeführt.

>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (Docker-terminology.md)
