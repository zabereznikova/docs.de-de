---
title: "Identifizieren von Domänenmodell Grenzen für jeden microservice"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Identifizieren von Domänenmodell Grenzen für jeden microservice"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6fef11e5718706701abb29149c4c4a23ba39bde0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="identify-domain-model-boundaries-for-each-microservice"></a>Identifizieren von Domänenmodell Grenzen für jeden microservice

Das Ziel beim Modellgrenzen und die Größe jedes Microservice identifizieren ist nicht um auf die unterste Trennung möglich, obwohl Sie in Richtung kleine Microservices möglichst in der Regel sollten. Stattdessen sollte der Erreichung Ihres Ziels, um die sinnvolle Trennung durch MDX Ihr spartenwissen zu erhalten. Der Schwerpunkt liegt nicht auf die Größe, sondern auf Unternehmensfunktionen. Darüber hinaus besteht deaktivieren Kohäsion für einen bestimmten Bereich der Anwendung basierend auf einer hohen Anzahl von Abhängigkeiten erforderlich ist, gibt an, dass die Notwendigkeit für eine einzelnes Microservice zu. Kohäsion ist eine Möglichkeit, wie Sie teilen oder Gruppe zusammen Microservices zu identifizieren. Während Sie weitere Informationen über die Domäne erhalten, sollten Sie die Größe Ihrer Microservice letztlich iterativ anpassen. Suchen die richtige Größe ist nicht prozessspezifisch One-Shot.

[SAM Newman](http://samnewman.io/), eine anerkannten Promoter Microservices und der Autor des Buchs [Gebäude Microservices](http://samnewman.io/books/building_microservices/), werden hervorgehoben, die basierend auf dem begrenzt, die den Kontext (BC)-Muster (Bestandteil des Microservices zu entwickeln Domain driven Design), wie zuvor eingeführt. In manchen Fällen konnte eine BC mehrere physische Dienste, aber nicht umgekehrt zusammengesetzt werden.

Ein Domänenmodell mit einer bestimmten Domänenentitäten innerhalb einer konkreten BC gilt oder Microservice. Ein BC begrenzt die Anwendbarkeit ein Domänenmodell, und erhalten Entwickler Teammitglieder einen klare und freigegebenen Überblick über was zusammenhängenden sein müssen und was unabhängig entwickelt werden können. Hierbei handelt es sich um dasselbe Ergebnis für Microservices.

Ein weiteres Tool, mit denen Ihre Entwurfsoption informiert ist [Conways Gesetz](https://en.wikipedia.org/wiki/Conway%27s_law), die besagt, dass eine Anwendung die sozialen Grenzen der Organisation widerspiegeln, die sie erstellt. Aber in einigen Fällen ist das Gegenteil "true": das Unternehmen wird gebildet, indem die Software. Müssen möglicherweise Conways Gesetz umkehren, und erstellen Sie die Grenzen wie gewünscht des Unternehmens organisiert werden, in Richtung Business Process consulting leaning.

Um gebundene Kontexten zu ermitteln, eine DDD-Muster, die dafür verwendet werden kann, ist die [Kontext zuordnen Muster](https://www.infoq.com/articles/ddd-contextmapping). Beim Zuordnen des Kontexts zu die verschiedenen Kontexten in der Anwendung und deren Grenzen identifizieren. Es ist üblich, z. B. über einen anderen Kontext und die Grenze für jedes Subsystem kleine verfügen. Die Kontext-Karte ist eine Möglichkeit zum Definieren und explizite diese Grenzen zwischen Domänen. Ein BC ist autonome und enthält die Details einer einzelnen Domäne – Details wie die Domänenentitäten – und Integration Verträge mit anderen BCs definiert. Dies ist vergleichbar mit der Definition einer Microservice: autonome ist, bestimmte-Funktion implementiert und es muss Schnittstellen bereitstellen. Deshalb wird Kontext zuordnen und das Muster, begrenzt, die den Kontext gute Ansätze zum Identifizieren der Domäne Modellgrenzen von Ihrem Microservices sind.

Bei eine große Anwendung zu entwerfen, sehen Sie wie seine Domänenmodell fragmentiert werden kann – ein Experte Domäne aus der Domäne Katalog benennt Entitäten unterschiedlich in den Katalog und Inventardaten Domänen als eine Protokollversand Domänenexperten, für die Instanz. Oder der Entität "Domain" Benutzer möglicherweise verschiedene in Größe und Anzahl der Attribute, beim Umgang mit einem CRM-Experten, der alle Details über die Kunden als Experte Domäne Sortierung zu speichern, die Teil der Daten über den Kunden nur benötigt möchte. Es ist sehr schwierig ist, um alle domänenbegriffe für alle Domänen, die im Zusammenhang mit einer großen Anwendung zu unterscheiden. Aber sehr wichtig ist, dass Sie nicht versuchen, die Begriffe zu vereinheitlichen. Stattdessen akzeptieren Sie die Unterschiede und die Funktionsvielfalt von jeder Domäne bereitgestellt. Wenn Sie versuchen, eine einheitliche Datenbank für die gesamte Anwendung haben, wird Versuche zur ein einheitliches Vokabular werden umständliche und nicht an ein beliebiges von mehreren Domänenexperten rechten sound. Aus diesem Grund hilft BCs (implementiert als Microservices) Ihnen, um zu verdeutlichen, dort können Sie bestimmte domänenbegriffe verwenden und vorgesehenden Teilen des Systems und zusätzliche BCs mit unterschiedlichen Domänen erstellen.

Sie wissen, dass Sie die richtigen Grenzen und die Größe der einzelnen BC und die zugehörigen Domänenmodell Wenn Ihnen einige starke Beziehungen zwischen Domänenmodelle, und Sie nicht in der Regel müssen Informationen aus mehreren Domänenmodelle Zusammenführen beim normalen Anwendung ausführen DDL-Vorgänge.

Vielleicht die bestmögliche Antwort auf die Frage, wie groß ein Domänenmodell für jede Microservice liegen lautet wie folgt: sie sollten eine autonome BC aufweisen als isolierte wie möglich, die Ihnen ermöglicht, ohne sich ständig in anderen Kontexten (andere wechseln arbeiten der Microservice-Modelle). In Abbildung 4 bis 10 können Sie sehen, wie mehrere Microservices (mehrere BCs) jeder haben ihre eigenen Modell- und wie die Entitäten definiert werden können, je nach den spezifischen Anforderungen für jeden identifizierten Domänen in der Anwendung.

![](./media/image10.png)

**Abbildung 4 – 10**. Identifizieren von Entitäten und Microservice Modellgrenzen

Abbildung 4 – 10 wird ein Beispielszenario, die im Zusammenhang mit einer online-Konferenz-Verwaltungssystem veranschaulicht. Sie haben mehrere BCs identifiziert, die als Microservices, basierend auf Domänen, die für Sie Domänenexperten definiert implementiert werden konnte. Wie Sie sehen können, sind Entitäten, die nur in einem einzelnen Microservice Modell wie Zahlungen in die Zahlung Microservice vorhanden sind. Diese werden einfach zu implementieren.

Jedoch, müssen Sie möglicherweise auch Entitäten, die eine andere Form, aber die gleiche Identität von mehreren Domänenmodelle aus mehreren Microservices gemeinsam genutzt. Beispielsweise wird die Benutzerentität in der Verwaltung von Konferenzen Microservice identifiziert. Demselben Benutzer, mit der gleichen Identität ist der Käufer in der Reihenfolge Microservice Namens oder der mit dem Namen des Zahlungspflichtigen in die Zahlung Microservice und sogar named ein Kunde in der Customer Service Microservice. Dies liegt daran, je nachdem, auf die [ubiquitäre Sprache](https://martinfowler.com/bliki/UbiquitousLanguage.html) , dass jede Domäne Expert verwendet, kann ein Benutzer möglicherweise eine andere Perspektive auch mit verschiedenen Attributen. Die Benutzerentität im Modell Microservice Namen Konferenzen Management möglicherweise die meisten ihrer persönlichen Daten Attribute. Demselben Benutzer in der Form von zahlenden in die Microservice Zahlung oder in der Form des Kunden in den Microservice Kundendienst möglicherweise jedoch nicht dieselbe Liste von Attributen.

Ein ähnlichen Ansatz wird in Abbildung 4 – 11 veranschaulicht.

![](./media/image11.png)

**Abbildung 4 – 11**. Zerlegen von herkömmlichen Datenmodelle in mehrere Domänenmodelle

Sie können sehen, wie der Benutzer in der Konferenzen Verwaltungsmodell-Microservice wie die Benutzer-Entität vorhanden ist, und ist auch in der Form der Käuferentität in der Microservice Preise mit anderen Attributen oder Details zum Benutzer, wenn es tatsächlich ein Käufer ist vorhanden. Jede Microservice oder BC möglicherweise nicht alle Daten, die im Zusammenhang mit der eine Benutzerentität, nur einen Teil davon je nach dem zu lösenden Problems oder des Kontexts. Für die Instanz, in der die Preise Microservice Modell benötigen nicht Sie die Adresse oder die ID des Benutzers, der nur-ID (als Identität) und der Status, die Auswirkungen auf Rabatte haben wird, wenn die Arbeitsplätze pro Käufer Preise.

Die Entität "Arbeitsplatz" hat die gleiche Namen aber unterschiedlichen Attribute in jeder Domänenmodell. Allerdings Arbeitsplatz Identität basierend auf der gleichen ID gemeinsam wie mit Benutzer- und Käufer geschieht.

Grundsätzlich ist ein freigegebener Konzept eines Benutzers, der in mehreren Diensten Domänen (Domänen) vorhanden ist das Freigeben die Identität des Benutzers. In jedem Domänenmodell möglicherweise zusätzliche oder andere Details zur Benutzerentität aber. Daher muss es eine Möglichkeit, eine Benutzerentität aus einer Domäne (Microservice) zu einem anderen zugeordnet werden.

Es gibt mehrere Vorteile zur gemeinsamen Nutzung nicht den gleichen Benutzerentität mit derselben Anzahl von Attributen über Domänengrenzen hinweg. Ein Vorteil ist Duplizierung zu reduzieren, sodass Microservice Modelle keine Daten enthalten, die sie nicht benötigen. Ein weiterer Vorteil ist ein Hauptschlüssel Microservice vorliegt, der eine bestimmte Art von Daten pro Entität besitzt, damit Updates und Abfragen für diese Art von Daten nur von diesem Microservice gesteuert werden.


>[!div class="step-by-step"]
[Vorherigen] (distributed-Daten-management.md) [weiter] (Direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
