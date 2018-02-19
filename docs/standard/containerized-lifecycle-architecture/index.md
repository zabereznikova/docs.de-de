---
title: "Einführung in Container und Docker"
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 31260dc372f87305ad9d4556673a1cc94e24bfcc
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="introduction-to-containers-and-docker"></a>Einführung in Container und Docker

Das Containerisieren ist ein Ansatz in der Softwareentwicklung, bei dem eine Anwendung oder ein Dienst sowie die zugehörigen Abhängigkeiten und Konfigurationen (abstrahiert als Bereitstellungsmanifestdateien) zusammen als Containerimage verpackt werden. Die Containeranwendung kann anschließend als Einheit getestet und als Instanz eines Containerimages für das Hostbetriebssystem bereitgestellt werden.

Genauso wie die Transportbranche standardisierte Container verwendet, um Waren per Schiff, Bahn oder LKW zu bewegen (unabhängig von der Ladung, die sich darin befindet), fungieren Softwarecontainer als eine Standardeinheit von Software, die verschiedenen Code und Abhängigkeiten enthalten kann. Das Containerisieren von Software ermöglicht es Entwicklern und IT-Experten, diese Container ohne oder mit nur geringfügigen Änderungen in verschiedenen Umgebungen bereitzustellen.

Container isolieren Anwendungen auf einem gemeinsamen Betriebssystem (OS) außerdem voneinander. Containeranwendungen werden auf einem Containerhost ausgeführt, der unter dem Betriebssystem (Linux oder Windows) ausgeführt wird. Daher haben Container einen erheblich geringeren Speicherbedarf als die Images für virtuelle Computer (VM).

Jeder Container kann wie in Abbildung 1-1 gezeigt eine gesamte Webanwendung oder einen gesamten Dienst ausführen.

![](./media/image1.png)

Abbildung 1-1: Mehrere Container, die auf einem Containerhost ausgeführt werden

In diesem Beispiel ist Docker-Host ein Containerhost und App1, App2, Svc1 und Svc2 sind die Containeranwendungen oder -dienste.

Ein weiterer Vorteil, den Containerisierung mit sich bringt, ist die Skalierbarkeit. Ein schnelles Skalieren ist möglich, indem Sie neue Container für kurzfristige Aufgaben erstellen. Aus der Sicht einer Anwendung ähnelt das *Instanziieren eines Images* (Erstellen eines Containers) dem Instanziieren eines Prozesses wie ein Dienst oder eine Web-App. Für die Zuverlässigkeit beim Ausführen von mehreren Instanzen desselben Images auf mehreren Hostservern sollte jedoch jeder Container (Instanz des Images) auf einem anderen Hostserver oder virtuellen Computer in verschiedenen Fehlerdomänen ausgeführt werden.

Kurz gesagt bieten Container die Vorteile der Isolation, Portabilität, Agilität, Skalierbarkeit und Steuerung des gesamten Workflows des Lebenszyklus der Anwendung. Der wichtigste Vorteil ist die Isolation zwischen Entwicklung und Vorgängen.


>[!div class="step-by-step"]
[Weiter] (what-is-docker.md)
