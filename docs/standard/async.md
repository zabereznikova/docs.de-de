---
title: Async (Übersicht)
description: Erfahren Sie mehr über die asynchrone Programmierung als eine wichtige Technik, mit der E/A-Blockierung und gleichzeitige Vorgänge auf mehreren Kernen direkt behandelt werden können.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.openlocfilehash: 495f225a3732812666dfa2f5c8c07f6f5b849c95
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824804"
---
# <a name="async-overview"></a>Async (Übersicht)

Es ist noch nicht lange her, da wurden Apps einfach durch die Ausführung auf einem aktuelleren PC oder Server schneller, und dann endete dieser Trend. In der Tat hat er sich umgekehrt. Mobiltelefone mit 1-GHz-Single Core-ARM-Chips erschienen auf dem Markt, und Serverarbeitsauslastungen wurden VMs übertragen. Benutzer wünschen immer noch reaktionsfähige Benutzeroberflächen, und Geschäftsinhaber wünschen sich Server, die sich ihren Unternehmen anpassen können. Aus dem Übergang zu Mobilgeräten und zur Cloud und mehr als 3 Mrd. Internetbenutzern resultiert eine neue Gruppe von Softwaremustern.

- Clientanwendungen sollen Always On/Always Connected sein und ständig auf Benutzerinteraktionen reagieren (z.B. Berühren) – mit hohen App Store-Bewertungen!
- Dienste sollen Verkehrsspitzen durch ordnungsgemäßes zentrales Hoch- und Herunterskalieren behandeln.

Asynchrone Programmierung ist eine wichtige Technik, mit der E/A-Blockierung und gleichzeitige Vorgänge auf mehreren Kernen direkt behandelt werden können. .NET bietet mit benutzerfreundlichen asynchronen Programmiermodellen auf Sprachebene in C#, Visual Basic und F# die Möglichkeit, Apps und Dienste reaktionsfähig und flexibel zu machen.

## <a name="why-write-async-code"></a>Warum sollten Sie Async-Code schreiben?

Moderne Apps machen umfassenden Gebrauch von Datei- und Netzwerk-E/A. E/A-APIs sind üblicherweise Blockaden, was Benutzerfreundlichkeit und Hardwarenutzung beeinträchtigt, solange Sie keine herausfordernden Muster erlernen und verwenden möchten. Taskbasierte, asynchrone APIs und das asynchrone Programmiermodell auf Sprachebene kehren dieses Modell um, sodass die asynchrone Ausführung zum Standard wird, wobei einige neue Konzepte zu erlernen sind.

Asynchroner Code weist folgende Merkmale auf:

- Behandeln einer höheren Zahl von Serveranforderungen durch Erzeugen von Threads zum Behandeln einer höheren Zahl von Anforderungen während des Wartens auf die Rückmeldung von E/A-Anforderungen.
- Reaktionsfähigere Benutzeroberflächen durch Erzeugen von Threads für die Benutzeroberflächeninteraktion während des Wartens auf E/A-Anforderungen und durch Übertragen zeitintensiver Abläufe auf andere CPU-Kerne.
- Viele der neueren .NET-APIs sind asynchron.
- In .NET schreiben Sie im Handumdrehen asynchronen Code!

## <a name="whats-next"></a>Wie geht es weiter?

Weitere Informationen finden Sie im Artikel zu [Async](async-in-depth.md).

Das Thema [Muster für die asynchrone Programmierung](asynchronous-programming-patterns/index.md) bietet eine Übersicht über diese drei in .NET unterstützten asynchronen Programmierungsmuster:  
  
- [Asynchronous Programming Model (APM) (Asynchrones Programmiermodell (APM))](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (Legacy)  
  
- [Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Legacy)  
  
- [Task-based Asynchronous Pattern (TAP) (Taskbasierte asynchrone Muster (TAP))](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (für neue Entwicklung empfohlen)  

Weitere Informationen zum empfohlenen aufgabenbasierten Programmierungsmodell finden Sie im Artikel [Aufgabenbasierte asynchrone Programmierung](parallel-programming/task-based-asynchronous-programming.md).
