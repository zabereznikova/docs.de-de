---
title: Vereinfachte CQRS und DDD Muster in ein Microservice anwenden
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Vereinfachte CQRS und DDD Muster in ein Microservice anwenden"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 99fd7ce32039742e23f8e01aa4c33cddd7a9f698
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="applying-simplified-cqrs-and-ddd-patterns-in-a-microservice"></a>Vereinfachte CQRS und DDD Muster in ein Microservice anwenden

CQRS ist eine architektonische Muster, die eine Trennung der Modelle zum Lesen und Schreiben von Daten. Der zugehörige Begriff [Befehl Abfrage Trennung (CQS)](https://martinfowler.com/bliki/CommandQuerySeparation.html) ursprünglich von Bertrand Meyer in seinem Buch definierten *dienstorientierten Software Objektkonstruktion*. Die Grundidee ist, dass Sie eine Systemvorgänge zwei scharf getrennten Kategorien aufteilen können:

-   Abfragen. Diese ein Ergebnis zurückgeben, und ändern Sie den Status des Systems nicht, und sie sind keine Nebenwirkungen.

-   Befehle. Diese ändern den Status eines Systems.

CQS ist ein einfaches Konzept – es geht um Methoden innerhalb desselben Objekts wird von Abfragen oder Befehle. Jede Methode Zustand zurückgibt, oder gar Status, aber nicht beides. Auch ein einzelnes Muster Repositoryobjekt kann CQS entsprechen. CQS können einen grundlegenden Prinzip CQRS betrachtet werden.

[Befehl und Abfrage Verantwortung Segregation (CQRS)](https://martinfowler.com/bliki/CQRS.html) von Greg Young eingeführt und stark vom Udi Dahan und andere höher gestuft wurde. Es basiert auf dem Prinzip CQS, auch wenn es mehr detailliert erläutert wird. Sie können ein Muster basierend auf Befehle und Ereignisse sowie optional auf asynchrone Nachrichten berücksichtigt werden. CQRS bezieht sich in vielen Fällen für erweiterte Szenarios, verfügen Sie über eine andere physische Datenbank für Lesevorgänge (Abfragen) als für Schreibvorgänge (Updates). Darüber hinaus kann ein mehr evolved CQRS System implementieren [Ereignis Insourcing (ES)](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/) für Ihre Datenbank Updates so Sie würde nur Speichern von Ereignissen im Domänenmodell speichern die aktuellen Zustandsdaten, statt. Dies ist jedoch nicht die in diesem Handbuch verwendeten Ansatz; Wir verwenden die einfachste CQRS Vorgehensweise umfasst nur die Abfragen mit den Befehlen unterteilen.

Der Aspekt Trennung CQRS erfolgt durch Gruppieren von Abfrageoperationen in einer Ebene und Befehle in einer anderen Ebene. Jede Ebene weist einen eigenen Datenmodell (Beachten Sie, dass das Modell, nicht unbedingt eine andere Datenbank zutrifft) und basiert auf einem eigenen Kombination von Mustern und -Technologien. Vor allem können die beiden Ebenen innerhalb der gleichen Ebene oder Microservice, wie im Beispiel (Reihenfolge Microservice) zu diesem Handbuch verwendet werden. Oder kann auf verschiedene Microservices oder Prozesse implementiert werden, damit optimiert und ohne Auswirkungen auf voneinander getrennt dezentral skaliert werden können.

CQRS bedeutet dies, dass zwei Objekte für einen Vorgang Lese-/Schreibzugriff, in denen in anderen Kontexten vorhanden ist. Es gibt Gründe für eine nicht normalisierte Lesevorgänge-Datenbank verfügen, die in erweiterten CQRS Literatur Sie lernen aus. Jedoch nicht verwenden wir hier diesen Ansatz, in dem das Ziel besteht darin, mehr Flexibilität in den Abfragen statt beschränken die Abfragen mit Einschränkungen DDD Muster wie Aggregate zu haben.

Ein Beispiel für diese Art des Diensts ist die Reihenfolge Microservice aus der eShopOnContainers Referenz-Anwendung. Dieser Dienst implementiert einen Microservice basierend auf einen vereinfachten Ansatz ein CQRS. Es verwendet einer einzelnen Datenquelle oder Datenbank, jedoch zwei logischen Modellen plus DDD Muster für die transaktionale Domäne, wie in Abbildung 9 – 2 gezeigt.

![](./media/image2.png)

**Abbildung 9 – 2**. Vereinfachte CQRS und DDD-basierte microservice

Die Anwendungsebene kann die Web-API selbst sein. Hier die wichtiger Design Aspekt ist, dass die Microservice der Abfragen und ViewModels (insbesondere für die Clientanwendungen erstellte Datenmodelle) aufgeteilt wurde aus der Befehle, Domänenmodell und Transaktionen, die das CQRS-Muster folgen. Dadurch bleibt die Abfragen unabhängig von Einschränkungen und Einschränkungen von DDD-Muster, die nur für Transaktionen und Updates, sinnvoll stammen, wie in späteren Abschnitten erläutert.


>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (Eshoponcontainers-Cqrs-Ddd-microservice.md)
