---
title: Behandlung von teilweise fehlerhaft.
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Behandlung von teilweise fehlerhaft."
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7d16acf3de2d395da70e8f46e59c129dec24f71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="handling-partial-failure"></a>Behandlung von teilweise fehlerhaft.

Verteilter Systeme wie Microservices-basierte Anwendungen ist eine partielle allgegenwärtigen Ausfallrisiko. Z. B. ein einzelnen Microservice-Container kann fehlschlagen, möglicherweise nicht verfügbar für kurze Zeit reagieren bzw. einen einzelnen virtuellen Computer oder Server kann abstürzen. Da Clients und Dienste separate Vorgänge dar, ein Dienst zeitnah auf einem Client-Anforderung reagiert möglicherweise nicht. Der Dienst möglicherweise überladene ist und antwortet extrem langsam, Anforderungen oder einfach möglicherweise nicht verfügbar für kurze Zeit aufgrund von Netzwerkproblemen.

Angenommen Sie, die Detailseite Reihenfolge aus der eShopOnContainers beispielanwendung. Wenn die Sortierung Microservice nicht reagiert bei der Benutzer versucht, einen Auftrag, eine fehlerhafte Implementierung des Clientprozesses (MVC-Web-Anwendung) zu senden – Wenn der Clientcode synchrone RPCs mit kein Timeout verwendet würde beispielsweise – Threads für unbegrenzte Zeit blockiert würde eine Antwort warten. Zusätzlich zur Erstellung von einem Benutzer negatives Erlebnis, alle nicht reagierenden Wait belegt oder blockiert einen Thread, und Threads sind äußerst sinnvoll sein, in hoch skalierbare Anwendungen. Wenn viele blockierte Threads vorhanden sind, kann schließlich der Laufzeit der Anwendung nicht mehr genügend Threads ausführen. In diesem Fall die Anwendung kann reagiert Global anstelle von nur teilweise nicht mehr reagiert, wie in Abbildung 10 – 1.

![](./media/image1.png)

**Abbildung 10 – 1**. Teilweise Ausfälle aufgrund von Abhängigkeiten, die auf Thread-dienstverfügbarkeit auswirkt

In einer großen Microservices-basierte Anwendung kann jeder partiellen Fehler verstärkt werden, insbesondere dann, wenn die meisten der internen Microservices Interaktion basiert auf synchrone HTTP-Aufrufe (das eine Antimuster gilt). Überlegen Sie sich ein System, das der eingehenden Aufrufe pro Tag Millionen empfängt. Wenn Ihr System ein schlechtes Design, das lange statusketten synchronen HTTP-Aufrufen basiert aufweist, können diese eingehende Aufrufe führen viele weitere Millionen von ausgehenden aufrufen (angenommen, ein Verhältnis von 1:4) zu zahlreichen internen Microservices als synchrone Abhängigkeiten. Diese Situation ist in Abbildung 10-2, insbesondere Abhängigkeit gezeigt \#3.

![](./media/image2.png)

**Abbildung 10 – 2**. Die Auswirkungen einen falschen Entwurf mit lange statusketten HTTP-Anforderungen

Gelegentliche Fehler praktisch ist sichergestellt, dass in einer verteilten und cloud-basierten System, auch wenn jede Abhängigkeit selbst exzellenten Verfügbarkeit hat. Dies sollte ein Fakt sein, den Sie berücksichtigen müssen.

Wenn Sie keine entwerfen und Implementieren von Techniken, um die Fehlertoleranz zu gewährleisten, können selbst kleine Ausfallzeiten verstärkt werden. Beispielsweise würde 50 Abhängigkeiten mit 99,99 % Verfügbarkeit in mehreren Stunden Ausfallzeiten monatlich aufgrund dieser sich allmählich ausbreitenden Wirkung. Fällt eine Abhängigkeit Microservice Führungen eine große Anzahl von Anforderungen, Fehler schnell stark beanspruchen alle verfügbare Anforderung Threads in jedem Dienst und kann die gesamte Anwendung, stürzt ab.

![](./media/image3.png)

**Abbildung 10 – 3**. Teilweise verstärkt von Microservices mit lange statusketten synchronen Aufrufen von HTTP-Fehler

Zur Minimierung dieses Problems im Abschnitt "*asynchrone Microservice Integration Erzwingen des Microservice Autonomie*" (in der Architektur Kapitel) gefördert asynchronen Kommunikation über die interne Verwendung Microservices. Wir erläutern kurz mehr im nächsten Abschnitt.

Darüber hinaus ist es wichtig, dass Sie Ihre Microservices und Clientanwendungen teilfehler behandeln entwerfen – d. h. robusten Microservices und Client Anwendungen erstellen.


>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (teilweise Fehler strategies.md)
