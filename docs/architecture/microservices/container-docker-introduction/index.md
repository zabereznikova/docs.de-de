---
title: Einführung in Container und Docker
description: .NET-Microservices-Architektur für .NET-Containeranwendungen | Einführung in Container und Docker
ms.date: 08/31/2018
ms.openlocfilehash: 364cbc0ba8149be1873df628a1ca243f420e7d0b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740064"
---
# <a name="introduction-to-containers-and-docker"></a>Einführung in Container und Docker

Das Containerisieren ist ein Ansatz in der Softwareentwicklung, bei dem eine Anwendung oder ein Dienst sowie die zugehörigen Abhängigkeiten und Konfigurationen (abstrahiert als Bereitstellungsmanifestdateien) zusammen als Containerimage verpackt werden. Die Containeranwendung kann als Einheit getestet und als Instanz eines Containerimages für das Hostbetriebssystem (OS) bereitgestellt werden.

So wie das Versenden von Containern es ermöglicht, Güter unabhängig von der enthaltenen Fracht per Schiff, Zug oder LKW zu transportieren, agieren Softwarecontainer als Standardeinheit für Softwarebereitstellung und können verschiedenen Code und verschiedene Abhängigkeiten enthalten. Das Containerisieren von Software auf diese Weise ermöglicht es Entwicklern und IT-Experten, diese ohne oder mit geringfügigen Änderungen in verschiedenen Umgebungen bereitzustellen.

Container isolieren Anwendungen auf einem gemeinsamen Betriebssystem außerdem voneinander. Containeranwendungen werden auf einem Containerhost ausgeführt, der auf dem Betriebssystem (Linux oder Windows) ausgeführt wird. Daher haben Container einen erheblich geringeren Speicherbedarf als die Images für virtuelle Computer (VM).

Jeder Container kann wie in Abbildung 2-1 gezeigt eine gesamte Webanwendung oder einen gesamten Dienst ausführen. In diesem Beispiel ist Docker-Host ein Containerhost und App1, App2, Svc1 und Svc2 sind die Containeranwendungen oder -dienste.

![Diagramm, das vier Container zeigt, die auf einem virtuellen Computer oder einem Server ausgeführt werden.](./media/index/multiple-containers-single-host.png)

**Abbildung 2-1**. Mehrere Container, die auf einem Containerhost ausgeführt werden

Ein weiterer Vorteil der Containerisierung ist die Skalierbarkeit. Ein schnelles Skalieren ist möglich, indem Sie neue Container für kurzfristige Aufgaben erstellen. Aus der Sicht einer Anwendung ähnelt das Instanziieren eines Images (Erstellen eines Containers) dem Instanziieren eines Prozesses wie ein Dienst oder eine Web-App. Für die Zuverlässigkeit beim Ausführen von mehreren Instanzen desselben Images auf mehreren Hostservern sollte jedoch jeder Container (Instanz des Images) auf einem anderen Hostserver oder virtuellen Computer in verschiedenen Fehlerdomänen ausgeführt werden.

Kurz gesagt bieten Container die Vorteile der Isolation, Portabilität, Agilität, Skalierbarkeit und Steuerung des gesamten Workflows des Lebenszyklus der Anwendung. Der wichtigste Vorteil ist die Isolation der Umgebung zwischen Entwicklung und Betrieb (Dev and Ops).

>[!div class="step-by-step"]
>[Zurück](../index.md)
>[Weiter](docker-defined.md)
