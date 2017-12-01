---
title: "Herausforderungen und Lösungen für die Verwaltung von verteilten Daten"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Herausforderungen und Lösungen für die Verwaltung von verteilten Daten"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f961475b40c74bf448cff1aeae04ae4866360e52
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="challenges-and-solutions-for-distributed-data-management"></a>Herausforderungen und Lösungen für die Verwaltung von verteilten Daten

## <a name="challenge-1-how-to-define-the-boundaries-of-each-microservice"></a>Herausforderung \#1: Gewusst wie: Definieren der Grenzen von jeder Microservice

Definieren von Grenzen Microservice ist wahrscheinlich die erste Abfrage angeboten, die jeder Benutzer auftritt. Jede Microservice muss ein Teil der Anwendung und jeder Microservice sollte autonome mit alle vor- und Nachteile, die es vermittelt. Aber wie erkennen Sie diese Grenzen?

Zunächst müssen Sie auf der Anwendungsverzeichnis logischen Domänenmodelle und zugehörige Daten konzentrieren. Sie müssen versuchen entkoppelte Inseln von Daten und unterschiedlichen Kontexten innerhalb derselben Anwendung zu identifizieren. Jeder Kontext möglicherweise eine andere Business-Sprache (unterschiedliche geschäftsbegriffe). Die Kontexte sollten definiert und unabhängig verwaltet werden. Die Begriffe und Entitäten, die in diesen unterschiedlichen Kontexten verwendet möglicherweise ähnlich klingen, aber Sie möglicherweise heraus, dass in einem bestimmten Kontext ein Geschäftskonzept mit einem für einen anderen Zweck in einem anderen Kontext verwendet wird, und möglicherweise auch einen anderen Namen. Z. B. ein Benutzer kann als ein Benutzer im Kontext Identität oder die Mitgliedschaft verwiesen werden, als ein Kunde in einem Kontext CRM als Käufer in einem Kontext Reihenfolge usw.

Die Möglichkeit, die Grenzen zwischen mehreren Anwendungskontexten mit einer anderen Domäne zu identifizieren, für jeden Kontext genau ist, wie Sie die Grenzen für jedes Unternehmen Microservice und die zugehörigen identifizieren können Domänenmodell und Daten. Sie versuchen immer die Kopplung zwischen diesen Microservices zu minimieren. Dieses Handbuch wird ausführlicher Informationen zu dieser Kennung und Domäne Modellentwurfs im Abschnitt [identifizieren Domänenmodell Grenzen für jeden Microservice](#identifying-domain-model-boundaries-for-each-microservice) später.

## <a name="challenge-2-how-to-create-queries-that-retrieve-data-from-several-microservices"></a>Herausforderung \#2: Erstellen von Abfragen, die Daten aus mehreren Microservices abrufen

Eine zweite Abfrage wird erklärt, wie Abfragen zu implementieren, die Abrufen von Daten aus mehreren Microservices ' geschwätzige ' Kommunikation von remote-Client-apps, die Microservices zu vermeiden. Ein Beispiel ist möglicherweise einer einzigen Seite aus einer mobilen app, die benötigt werden, um Benutzerinformationen anzuzeigen, die die Warenkorb-Katalog und Benutzer Identität Microservices gehört. Ein weiteres Beispiel wäre eine komplexe Bericht im Zusammenhang mit vielen Tabellen in mehreren Microservices. Die richtige Lösung hängt von der Komplexität der Abfragen ab. Jedoch in jedem Fall benötigen Sie eine Möglichkeit, aggregierte Informationen gegebenenfalls verbessern die Effizienz der Kommunikation des Systems. Die am häufigsten verwendeten Lösungen sind die folgenden.

**API-Gateway**. Für einfache Datenaggregation aus mehreren Microservices, die verschiedene Datenbanken besitzen, ist die empfohlene Vorgehensweise eine Aggregation Microservice als ein API-Gateway bezeichnet. Allerdings müssen Sie berücksichtigen, dieses Muster implementieren, da es kann einen Punkt Drossel in Ihrem System, und können sie das Prinzip der Microservice Autonomie verletzen. Um diese Gefahr zu minimieren, können Sie mehrere detaillierte-API-Gateways verwenden, jede eine Fokussierung auf einer vertikalen "Segment" oder ein Geschäftsbereich des Systems. Die API-Gateway-Muster wird ausführlicher im Abschnitt in der Using später ein API-Gateway.

**CQRS mit Abfrage/Lesevorgänge Tabellen**. Eine andere Lösung für das Aggregieren von Daten aus mehreren Microservices wird die [materialisierte Sicht Muster](https://docs.microsoft.com/azure/architecture/patterns/materialized-view). Dieser Ansatz bietet Sie generiert haben, im voraus (vorbereiten denormalisierte Daten vor dem Auftreten von der tatsächlichen Abfragen), eine schreibgeschützte Tabelle mit den Daten, die mehrere Microservices gehört. Die Tabelle besitzt ein Format für die Client-app-Anforderungen geeignet sind.

Betrachten Sie etwa im Bildschirm zur einer mobilen app. Wenn Sie eine einzelne Datenbank verfügen, können Sie zusammen Pullvorgänge für die Daten für einen Bildschirm mit einer SQL-Abfrage, die eine komplexe Verknüpfung, die im Zusammenhang mit mehreren Tabellen ausführt. Wenn Sie mehrere Datenbanken vorhanden sein, und jede Datenbank ist im Besitz einer anderen Microservice, können keine Sie jedoch diese Datenbanken abzufragen und erstellt einen Join in SQL. Die komplexe Abfrage wird eine neue Herausforderung dar. Können Sie die Anforderung mithilfe des Ansatzes CQRS beheben, erstellen Sie eine nicht normalisierte Tabelle in einer anderen Datenbank, die nur für Abfragen verwendet wird. Die Tabelle kann speziell für die Daten entworfen werden, Sie mit der komplexen Abfrage mit einer 1: 1-Beziehung zwischen Feldern, die von Ihrer Anwendung Bildschirm und die Spalten in der Abfragetabelle benötigt müssen. Es kann auch für Berichtszwecke dienen.

Dieser Ansatz löst nicht nur das ursprüngliche Problem (wie die Abfrage und Join über Microservices); Es verbessert auch die Leistung erheblich, wenn mit dem eine komplexe Verknüpfung verglichen, da Sie bereits über Daten verfügen, die in der Abfragetabelle in der Anwendung benötigt. Natürlich Abfrage/Lesevorgänge Tabellen mit Befehl und Abfrage Verantwortung Segregation (CQRS) bedeutet, dass weitere Entwicklungsarbeit erforderlich, und Sie müssen eventuelle Konsistenz zu nutzen. Dennoch eine überaus Anforderungen auf Leistung und hoher Skalierbarkeit in [zusammenarbeitsszenarien](http://udidahan.com/2011/10/02/why-you-should-be-using-cqrs-almost-everywhere/) (oder Wettbewerber Szenarien, abhängig von der Sicht) ist, in denen CQRS mit mehreren Datenbanken angewendet werden sollen.

**"Kalte Daten" in der zentralen Datenbanken**. Für komplexe Berichte oder Abfragen, die möglicherweise nicht in Echtzeit Daten erfordern, ist eine gängige Methode so exportieren Sie Ihre "hot Data" (Transaktionsdaten aus der Microservices) als "kalte Daten" in großen Datenbanken, die nur für die Berichterstattung verwendet werden. Das System für die zentrale Datenbank kann eine Big Data-basierten System, z. B. Hadoop, ein Datawarehouse wie basierend auf Azure SQL Data Warehouse oder sogar einer einzelnen SQL-Datenbank nur für Berichte verwendet werden, (wenn die Größe nicht über ein Problem werden) sein.

Bedenken Sie, dass dieser zentralisierten Datenbank verwendet werden würde, nur für Abfragen und Berichte, die Daten in Echtzeit nicht benötigen. Die ursprünglichen Updates und Transaktionen, wie Ihre Datenquelle besteht, müssen sich in Ihren Daten Microservices befinden. Die Möglichkeit, Daten zu synchronisieren, würde wäre mit ereignisgesteuerte Kommunikation (in den nächsten Abschnitten behandelt) oder mit anderen Datenbank-Infrastruktur-Import/Export-Tools. Bei Verwendung von ereignisgesteuerten Kommunikation wäre, Integrationsprozesses ähnlich wie bei Daten zu übertragen, wie oben für CQRS Abfragetabellen beschrieben.

Jedoch wenn Ihren Anwendungsentwurf ständig Aggregieren von Daten aus mehreren Microservices für komplexe Abfragen umfasst, möglicherweise ein Symptom für ein schlechtes Design – ein Microservice sollte möglichst aus anderen Microservices als isolierte sein. (Dies schließt Berichte/Analysen, die immer kalten Daten zentralen Datenbanken verwenden soll.) Häufig haben dieses Problem möglicherweise einen Grund Microservices zusammengeführt. Sie müssen die Autonomie der Entwicklung und Bereitstellung von jeder Microservice mit starke Abhängigkeiten, Kohäsion und Datenaggregation abwägen.

## <a name="challenge-3-how-to-achieve-consistency-across-multiple-microservices"></a>Herausforderung \#3: wie Konsistenz über mehrere Microservices zu erreichen.

Wie bereits erwähnt, werden die Daten, die im Besitz von jeder Microservice ist für diese Microservice privat und können nur mit seiner Microservice API zugegriffen werden. Aus diesem Grund wird eine Aufforderung angezeigt wie End-to-End-Geschäftsprozesse Weiterleitungstopologie Konsistenz über mehrere Microservices implementiert.

Um dieses Problem zu analysieren, sehen wir uns ein Beispiel aus der [eShopOnContainers verweisen Anwendung](http://aka.ms/eshoponcontainers). Der Katalog Microservice verwaltet Informationen zu allen Produkten, einschließlich der vordefinierten Ebene. Die Reihenfolge Microservice Bestellungen verwaltet und muss sicherstellen, dass eine neue Bestellung Aktie Produkt verfügbaren Katalog nicht überschritten wird. (Oder das Szenario kann das Logik, die behandelt rückständigen Produkte umfassen.) In einer hypothetischen monolithischen Version dieser Anwendung konnte die Reihenfolge Subsystem einfach verwenden eine ACID-Transaktion überprüfen Sie den verfügbaren Bestand, erstellen die Reihenfolge, in der Tabelle Orders, und aktualisieren den verfügbaren Bestand in der Tabelle Products.

In einer Microservices-basierte Anwendung, die Bestellungen und Produkten Tabellen jedoch durch ihre jeweiligen Microservices gehören. Keine Microservice sollte jemals Datenbanken im Besitz einer anderen Microservice in einem eigenen Transaktionen oder Abfragen, enthalten, wie in Abbildung 4-9 gezeigt.

![](./media/image9.PNG)

**Abbildung 4-9**. Ein Microservice kann nicht direkt auf eine Tabelle in einer anderen Microservice zugreifen.

Die Reihenfolge Microservice sollte nicht direkt, die Products-Tabelle aktualisieren, da die Products-Tabelle der Katalog Microservice gehört. Um ein Update für den Katalog Microservice zu machen, sollten die Reihenfolge Microservice immer nur asynchronen Kommunikation, z. B. integrationsereignisse (Nachricht und das ereignisbasierte Kommunikation) verwenden. Dies ist wie die [eShopOnContainers](http://aka.ms/eshoponcontainers) Verweis Anwendung ausführt, diese Art von Update.

Wie angegeben durch die [CAP theorems](https://en.wikipedia.org/wiki/CAP_theorem), müssen Sie die Wahl zwischen Verfügbarkeit und ACID starke Konsistenz. Die meisten Microservice-basierten Szenarien mit "demand" Verfügbarkeit und hoher Skalierbarkeit, im Gegensatz zu starke Konsistenz. Unternehmenswichtige Anwendungen müssen sich bleiben und ausgeführt wird, und Entwickler können umgehen, die starke Konsistenz mithilfe von Techniken zum Arbeiten mit schwachen oder eventuellen Konsistenz. Dies ist der Ansatz, der meisten Microservice basierende Architekturen.

Darüber hinaus werden ACID-Format oder Transaktionen mit Zweiphasen-Commit nicht nur mit den Prinzipien Microservices; Die meisten NoSQL-Datenbanken (z. B. Azure-Cosmos-DB, MongoDB, usw.) unterstützen keine Transaktionen mit Zweiphasen-Commit. Allerdings ist bei Verwalten von Daten die Konsistenz zwischen Diensten und Datenbanken wichtig. Dieses Problem bezieht sich auch auf die Frage, wie Änderungen über mehrere Microservices weitergegeben, wenn bestimmte Daten redundant sein müssen – z. B. Wenn Sie müssen das Produkt Namen\noder Beschreibung in den Katalog Microservice und Korb haben Microservice.

Eine geeignete Lösung für dieses Problem ist die Verwendung von eventuellen Konsistenz zwischen Microservices formuliert, die über eine ereignisgesteuerte Kommunikation und einem System veröffentlichen und abonnieren. In diesen Themen finden Sie im Abschnitt [asynchrone ereignisgesteuerte Kommunikation](#async_event_driven_communication) weiter unten in diesem Handbuch.

## <a name="challenge-4-how-to-design-communication-across-microservice-boundaries"></a>Herausforderung \#4: Kommunikation Microservice hinweg entwerfen

Kommunikation über Microservice Grenzen ist eine echte Herausforderung. In diesem Kontext Kommunikation verweist nicht auf welches Sie Protokoll (HTTP und REST AMQP, messaging, usw.) verwenden soll. Stattdessen, adressiert er welche Kommunikation-Stil, die Sie verwenden sollten, und insbesondere wie gekoppelten Ihrer Microservices sein soll. Je nach der Kopplung Wenn ein Fehler auftritt, variieren die Auswirkungen dieses Ausfalls auf Ihrem System erheblich.

Komponenten werden in einem verteilten System wie eine Microservices basierende Anwendung, mit so vielen Elementen navigieren und mit verteilten Dienste über mehrere Server oder Hosts letztendlich fehlschlagen. Partielle Fehler, und auch größere Ausfälle erfolgt daher Sie Ihre Microservices und die Kommunikation zwischen diesen und berücksichtigt die Risiken allgemeine bei dieser Art der verteilten System entwerfen müssen.

Eine gängige Vorgehensweise ist zum Implementieren von HTTP (REST)-basierten Microservices, aufgrund deren Einfachheit. Ein HTTP-basierten Ansatz ist vollkommen akzeptabel; Hier das Problem bezieht sich auf dessen Verwendung. Wenn Sie HTTP-Anforderungen und Antworten nur für die Interaktion mit Ihrem Microservices von Clientanwendungen oder von API-Gateways verwenden, ist dies in Ordnung. Sondern bei der Erstellung lange statusketten synchronen HTTP-Aufrufen über Microservices Kommunikation über Umrisslinien, als wären die Microservices Objekte in einer Anwendung aufgrund eines monolithischen Ihrer Anwendung schließlich Probleme.

Stellen Sie sich z. B. vor, dass Ihre Clientanwendung ein HTTP-API aufruft, die auf eine einzelne Microservice wie die Sortierung Microservice. Wenn die Sortierung Microservice ruft anschließend zusätzliche Microservices über HTTP innerhalb der gleichen Anforderung/Antwort-Zyklus, erstellen Sie eine Kette von HTTP-aufrufen. Anfänglich möglicherweise angemessen sound werden. Es gibt jedoch wichtige Punkte zu berücksichtigen, wenn Sie diesen Pfad:

-   Blockierende und mit niedriger Leistung. Aufgrund der synchronen HTTP wird die ursprüngliche Anforderung keine Antwort erhalten, bis alle internen HTTP-Aufrufe abgeschlossen sind. Stellen Sie vor, wenn die Anzahl der Aufrufe deutlich erhöht und zum gleichen Zeitpunkt eine intermediate HTTP-an ein Microservice Aufrufe blockiert wird. Das Ergebnis ist, dass die Leistung wird beeinträchtigt, und die allgemeine Skalierbarkeit exponentiell wirkt sich als zusätzliche Zunahme der HTTP-Anforderungen.

-   Kopplung Microservices mit HTTP. Business Microservices sollte nicht mit anderen Microservices Business verbunden werden. Im Idealfall sollten sie "über das Vorhandensein der anderen Microservices weiß" nichts. Wenn Ihre Anwendung Kopplung Microservices wie im Beispiel abhängig, werden Autonomie pro Microservice erreichen nahezu unmöglich.

-   Fehler in jeder ein Microservice. Wenn Sie eine Kette von Microservices, die durch HTTP-aufrufen, verknüpft werden, wenn die gesamte Kette der Microservices keines der Microservices ein Fehler auftritt (und sie werden letztendlich fehlschlagen) implementiert schlägt fehl. Ein Microservice-basiertes System sollten so entworfen werden, um den Vorgang fortzusetzen, um möglichst hohe Leistungsfähigkeit während teilfehler zu arbeiten. Auch wenn Sie Client-Logik implementieren, Wiederholungen mit exponenzieller oder Trennschalter Mechanismen verwendet, sind weitere komplexe der HTTP-Aufruf Ketten es wird eine Strategie umzusetzen Fehler HTTP-basierte je komplexer.

Tatsächlich, wenn durch das Erstellen von Ketten der HTTP-Anforderungen gemäß Ihrer internen Microservices kommunizieren, konnte geltend gemacht werden, dass Sie eine Anwendung aufgrund eines monolithischen bis auf eine HTTP-basierte zwischen Prozessen statt intraprocess Kommunikationsmechanismen verfügen.

Um Microservice Autonomie zu erzwingen und eine bessere resilienz haben, sollten Sie daher die Verwendung von Ketten Anforderung/Antwort-Kommunikation über Microservices minimieren. Es wird empfohlen, nur asynchrone Aktivität für die übergreifende Microservice Kommunikation mithilfe von asynchronen und Ereignis-meldungsbasierte Kommunikation oder mithilfe von HTTP-Abruf unabhängig von der ursprünglichen HTTP-Anforderung/Antwort-Zyklus verwenden.

Erläutert die Verwendung der asynchronen Kommunikation mit zusätzlichen Details weiter unten in diesem Handbuch in den Abschnitten [asynchrone Microservice Integration erzwingt die Microservice Autonomie](#asynchronous-microservice-integration-enforce-microservices-autonomy) und [asynchrone – meldungsbasierte Kommunikation](#asynchronous-message-based-communication).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **CAP theorems**
    [*https://en.wikipedia.org/wiki/CAP\_theorems*](https://en.wikipedia.org/wiki/CAP_theorem)

-   **Eventuelle Konsistenz**
    [*https://en.wikipedia.org/wiki/Eventual\_Konsistenz*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Einführung in Data-Konsistenz**
    [*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)

-   **Martin Fowler. CQRS (Befehl und Query Responsibility Segregation)**
    [*http://martinfowler.com/bliki/CQRS.html*](http://martinfowler.com/bliki/CQRS.html)

-   **Materialisierte Sicht**
    [*https://docs.microsoft.com/azure/architecture/patterns/materialized-view*](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

-   **Charles Zeile. ACID im Vergleich zu Basis: Der verändern-pH der Datenbank Transaction Processing**
    [*http://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/*](http://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/)

-   **Kompensierende Transaktion**
    [*https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction*](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

-   **Udi Dahan. Dienstorientierte Komposition**
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)


>[!div class="step-by-step"]
[Vorherigen] (logisches-im Vergleich zur-Physical-architecture.md) [weiter] (identifizieren-Microservice-Domain-Modell-boundaries.md)
