---
title: Was ist Docker?
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Was ist Docker?
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: fadd2611283f0a7dadbf1734fe48f7d1a13096ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576193"
---
# <a name="what-is-docker"></a>Was ist Docker?

[Docker](https://www.docker.com/) ist ein [Open Source-Projekt](https://github.com/docker/docker) zur Automatisierung der Bereitstellung von Apps als mobile, eigenständige Container, die in der Cloud oder lokal ausgeführt werden können. Docker ist außerdem ein [Unternehmen](https://www.docker.com/), das diese Technologie weiterentwickelt. Docker arbeitet mit Cloud-, Linux- und Windows-Herstellern einschließlich Microsoft zusammen.

![](./media/image2.png)

**Abbildung 2-2:** Docker stellt Container auf allen Ebenen der hybriden Cloud bereit

Docker-Imagecontainer werden nativ unter Linux und Windows ausgeführt, wobei Windows-Images nur auf Windows-Hosts und Linux-Images nur auf Linux-Hosts ausgeführt werden. Der Host wiederum ist ein Server oder ein virtueller Computer.

Sie können unter Windows, Linux oder macOS entwickeln. Auf dem Entwicklungscomputer wird dabei ein Docker-Host ausgeführt, in dem Docker-Images bereitgestellt werden, einschließlich der App und ihrer Abhängigkeiten. Unter Linux oder macOS verwenden Sie stattdessen einen Linux-basierten Docker-Host, der nur Images für Linux-Container erstellt. Unter macOS können Sie zwar Code bearbeiten oder die Docker-Befehlszeilenschnittstelle ausführen, zum Zeitpunkt der Erstellung dieses Dokuments konnten Container jedoch nicht direkt unter macOS ausgeführt werden. Unter Windows können Sie Images für Linux- oder Windows-Container erstellen.

Unter Windows oder macOS werden Container in der [Docker Community Edition (CE)](https://www.docker.com/community-edition) in einer Entwicklungsumgebung gehostet. In dieser Edition werden außerdem zusätzliche Entwicklertools bereitgestellt. Die [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition) wurde für IT-Teams entworfen, die große geschäftskritische Anwendungen erstellen, bereitstellen und ausführen. ~Beide Produkte installieren die erforderliche VM (den Docker-Host) zum Hosten der Container.~ 

[Windows-Container](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) funktionieren mit zwei Typen von Runtimes:

-   Windows Server-Container bieten dank der Isolation von Prozessen und Namespaces auch Anwendungsisolierung. Ein Windows Server-Container teilt sich einen Kernel mit dem Containerhost und allen Containern, die auf dem Host ausgeführt werden.

-   Hyper-V-Container erweitern die durch Windows Server-Container bereitgestellte Isolierung, indem jeder Container in einem hochgradig optimierten virtuellen Computer ausgeführt wird. In dieser Konfiguration wird der Kernel des Containerhosts nicht für den Hyper-V-Container freigegeben, was die Isolierung verbessert. Hyper-V-Container lassen als nicht vertrauenswürdig eingestufte und *schädliche Anwendungen mit mehreren Mandanten* auf demselben Host zu. Hyper-V-Container sind, was die Startzeit und die Dichte betrifft, etwas weniger effizient als Windows Server-Container.

Die Images für diese Container werden genauso erstellt und funktionieren auch so. Der Unterschied besteht darin, wie der Container erstellt wird. Weitere Informationen finden Sie unter [Windows-Container](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview).

## <a name="comparing-docker-containers-with-virtual-machines"></a>Vergleichen von Docker-Containern mit virtuellen Computern

In Abbildung 2-3 wird einen Vergleich zwischen virtuellen Computern und die Docker Container dargestellt.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Virtuelle Computer****Docker-Container** 
                                                                                                                                                                                        
  ![](./media/image3.png)                                                                                                                                ![](./media/image4.png)
                                                                                                                                                                                        
  Virtuelle Computer enthalten die Anwendung, die erforderlichen Bibliotheken oder Binärdateien und ein vollständiges Gastbetriebssystem. Eine vollständige Virtualisierung erfordert mehr Ressourcen als die Containerisierung. Container enthalten die Anwendung und alle ihre Abhängigkeiten. Sie teilen sich jedoch den Betriebssystemkernel mit anderen Containern. Container werden als isolierte Prozesse im Benutzerbereich des Hostbetriebssystems ausgeführt. Die einzige Ausnahme stellen Hyper-V-Container dar, wo jeder Container in einem speziellen virtuellen Computer pro Container ausgeführt wird.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Abbildung 2-3:** Vergleichen der herkömmlichen virtuellen Computer mit Docker-Containern

Da Container wesentlich weniger Ressourcen benötigen (z.B. keine Vollversion des Betriebssystems), lassen sie sich schnell hochfahren und einfach bereitstellen. Eine geringe Ressourcennutzung ermöglicht eine höhere Dichte. Aus diesem Grund können Sie verschiedene Dienste auf derselben Hardware-Einheit ausführen und so die Kosten senken.

Da Container auf demselben Kernel ausgeführt werden, gibt es weniger Isolierung, als virtuelle Computer bereitstellen können.

Der Hauptzweck eines Images ist, die Umgebung (Abhängigkeiten) in verschiedene Bereitstellungen anzugleichen. Das bedeutet, dass Sie sie auf Ihrem Computer debuggen und sie dann auf einem anderen Computer bereitstellen können, wenn dieselbe Umgebung gewährleistet ist.

Mit einem Containerimage können Sie eine Anwendung oder einen Dienst packen und beides auf zuverlässige und reproduzierbare Weise bereitstellen. Docker ist also nicht bloß eine Technologie, sondern eine Philosophie und ein Prozess.

Docker-Entwickler würden niemals sagen: „Es funktioniert auf meinem Computer. Warum also nicht auch in der Produktion?“ Sie würden eher folgenden Satz hören: „Es wird unter Docker ausgeführt.“ Von Docker gepackte Apps können in allen unterstützten Docker-Umgebungen ausgeführt werden. Von Docker gepackte Apps werden konsistent auf allen Bereitstellungszielen ausgeführt (Entwicklung, Qualitätssicherung, Staging, Produktion).

>[!div class="step-by-step"]
[Zurück] (index.md) [Weiter] (docker-terminology.md)
