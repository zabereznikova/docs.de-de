---
title: Behandeln von Teilfehlern
description: ".NET-Microservicesarchitektur für .NET-Containeranwendungen | Behandeln von Teilfehlern"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0b03a5d341dbaadde302692ed0ed236ff3423e63
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="handling-partial-failure"></a>Behandeln von Teilfehlern

In verteilten Systemen wie Anwendungen, die auf Microservices basieren, gibt es ein allgegenwärtiges Risiko für Teilfehler. Zum Beispiel kann ein einzelner Microservice oder Container fehlschlagen oder für eine kurze Zeit nicht verfügbar sein, oder eine einzelne VM oder ein Server kann abstürzen. Da Clients und Dienste separate Vorgänge sind, kann ein Dienst möglicherweise nicht schnell genug auf die Anforderung eines Clients reagieren. Der Dienst ist möglicherweise überlastet und antwortet sehr langsam auf Anforderungen, oder er ist aufgrund von Netzwerkproblemen vorübergehend nicht verfügbar.

Nehmen Sie sich ein Beispiel an der Seite „Auftragsdetails“ der Beispielanwendung „eShopOnContainers“. Wenn der Microservice für Bestellungen nicht mehr reagiert, wenn der Benutzer versucht, einen Auftrag zu übermitteln, würde eine schlechte Implementierung des Clientprozesses (die MVC-Webanwendung) Threads auf unbestimmte Zeit blockieren, da er auf eine Antwort wartet, z.B. wenn der Clientcode synchrone RPCs ohne Timeout verwendet. Dies reduziert nicht nur die Benutzerfreundlichkeit, denn zusätzlich verbraucht oder blockiert jeder Wartevorgang ohne Reaktion einen Thread. Threads sind in hochgradig skalierbaren Anwendungen jedoch sehr wertvoll. Wenn viele Threads blockiert werden, sind für die Laufzeit der Anwendung irgendwann keine Threads mehr verfügbar. In diesem Fall kann es dazu kommen, dass die Anwendung wie in Abbildung 10-1 dargestellt global statt nur teilweise nicht mehr reagiert.

![](./media/image1.png)

**Abbildung 10-1**. Teilfehler treten wegen Abhängigkeiten auf, die die Verfügbarkeit von Dienstthreads beeinflussen

In einer großen, auf Microservices basierten Anwendung können Teilfehler vor allem verstärkt werden, wenn der Großteil der internen Interaktionen von Microservices auf synchronen HTTP-Aufrufen basiert (dies gilt als Antimuster). Stellen Sie sich ein System vor, das täglich Millionen von eingehenden Aufrufen empfängt. Wenn Ihr System schlecht entworfen ist und auf langen Ketten von synchronen HTTP-Aufrufen basiert, können diese eingehenden Aufrufe in vielen weiteren Millionen von ausgehenden Aufrufen (z.B. ein Verhältnis von 1:4) an dutzende interne Microservices als synchrone Abhängigkeiten resultieren. Diese Situation wird in Abbildung 10-2 veranschaulicht, insbesondere in Abhängigkeit \#3.

![](./media/image2.png)

**Abbildung 10-2**. Die Auswirkungen eines falschen Entwurfs mit langen Ketten von HTTP-Anforderungen

Zeitweilige Fehler sind in einem System quasi garantiert, das auf der Verteilung und der Cloud basiert, selbst wenn jede Abhängigkeit eigens über eine hervorragende Verfügbarkeit verfügt. Diesen Fakt sollten Sie berücksichtigen.

Wenn Sie keine Techniken für die Fehlertoleranz entwerfen oder implementieren, können selbst kleine Ausfälle verstärkt werden. Wegen dieser ausbreitenden Wirkung würden zum Beispiel 50 Abhängigkeiten mit einer Verfügbarkeit von 99,99% für mehrere Stunden im Monat ausfallen. Wenn eine Microserviceabhängigkeit beim Behandeln einer großen Anzahl von Anforderungen fehlschlägt, kann dieser Fehler schnell alle verfügbaren Anforderungsthreads in jedem Dienst beanspruchen und die gesamte Anwendung zum Abstürzen bringen.

![](./media/image3.png)

**Abbildung 10-3**. Teilfehler, der durch Microservices mit langen Ketten von synchronen HTTP-Aufrufen verstärkt wurde

Zur Minimierung dieses Problems wird im Abschnitt *Asynchrone Integration von Microservices erzwingt die Autonomie eines Microservice* empfohlen, die asynchrone Kommunikation über die internen Microservices hinweg zu verwenden. Weitere Informationen dazu finden Sie im nächsten Abschnitt.

Darüber hinaus ist es wichtig, dass Sie Ihre Microservices und Clientanwendungen dafür entwerfen, Teilfehler zu behandeln – d.h. robuste Microservices und Clientanwendungen zu erstellen.


>[!div class="step-by-step"]
[Zurück] (index.md) [Weiter] (partial-failure-strategies.md)
