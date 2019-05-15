---
title: Einführung in Container und Docker
description: Erhalten Sie einen allgemeinen Überblick über die wichtigsten Vorteile der Verwendung von Docker.
ms.date: 02/15/2019
ms.openlocfilehash: a03c67ed4fbc55c84e69fba5b7978863c8305e00
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644961"
---
# <a name="introduction-to-containers-and-docker"></a>Einführung in Container und Docker

*Das containerisieren ist ein Ansatz für die Softwareentwicklung, bei dem eine Anwendung oder Dienst, Abhängigkeiten und Konfigurationen (abstrahiert als Bereitstellungsmanifestdateien) zusammen als containerimage verpackt werden. Anschließend können Sie die containeranwendung als Einheit getestet und als Instanz eines containerimages für das Hostbetriebssystem (OS) bereitstellen.*

So wie das Versenden von Containern es ermöglicht, Güter unabhängig von der enthaltenen Fracht per Schiff, Zug oder LKW zu transportieren, agieren Softwarecontainer als Standardeinheit für Softwarebereitstellung und können verschiedenen Code und verschiedene Abhängigkeiten enthalten. Das Containerisieren von Software auf diese Weise ermöglicht es Entwicklern und IT-Experten, diese ohne oder mit geringfügigen Änderungen in verschiedenen Umgebungen bereitzustellen.

Container isolieren Anwendungen auf einem gemeinsamen Betriebssystem außerdem voneinander. Containeranwendungen werden auf einem Containerhost ausgeführt, der auf dem Betriebssystem (Linux oder Windows) ausgeführt wird. Daher haben Container einen viel geringeren Speicherbedarf als die Images für virtuelle Computer (VM).

Jeder Container kann wie in Abbildung 1-1 gezeigt eine gesamte Webanwendung oder einen gesamten Dienst ausführen. In diesem Beispiel Docker-Host ist ein containerhost und App1, App2, Dienst1 und Svc2 sind containeranwendungen oder -Dienste.

![Zwei Anwendungen und zwei Dienste, die unter dem Betriebssystem in einer VM oder auf einem physischen Server ausgeführt werden.](./media/image1.png)

**(Abbildung 1-1)**. Mehrere Container, die auf einem Containerhost ausgeführt werden

Ein weiterer Vorteil, den Containerisierung mit sich bringt, ist die Skalierbarkeit. Ein schnelles Skalieren ist möglich, indem Sie neue Container für kurzfristige Aufgaben erstellen. Aus der Sicht einer Anwendung ähnelt das Instanziieren eines Images (Erstellen eines Containers) dem Instanziieren eines Prozesses wie ein Dienst oder eine Web-App. Für die Zuverlässigkeit beim Ausführen von mehreren Instanzen desselben Images auf mehreren Hostservern sollte jedoch jeder Container (Instanz des Images) auf einem anderen Hostserver oder virtuellen Computer in verschiedenen Fehlerdomänen ausgeführt werden.

Kurz gesagt bieten Container die Vorteile der Isolation, Portabilität, Agilität, Skalierbarkeit und Steuerelement des gesamten Lebenszyklus anwendungsworkflows. Der wichtigste Vorteil ist die Isolierung der Umgebung zwischen Dev und Ops bereitgestellt.

>[!div class="step-by-step"]
>[Nächste](what-is-docker.md)
