---
title: Anwenden von CQRS- und CQS-Ansätzen in einem DDD-Microservice in eShopOnContainers
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über die Implementierung von CQRS im Microservice für Bestellungen in eShopOnContainers
ms.date: 01/13/2021
ms.openlocfilehash: 0c07ecad0fb2dfdaea85d47b519b858e0519f6bd
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188256"
---
# <a name="apply-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a>Anwenden von CQRS- und CQS-Ansätzen in einem DDD-Microservice in eShopOnContainers

Die Struktur des Microservices für Bestellungen in der Referenzanwendung „eShopOnContainers“ basiert auf CQRS-Prinzipien. Allerdings wird darin der einfachste Ansatz verwendet, bei dem Abfragen von Befehlen getrennt werden und dieselbe Datenbank für beide Aktionen dient.

Das Wesentliche dieser Muster und der wichtige Punkt bestehen hier darin, dass Abfragen idempotent sind: unabhängig davon, wie oft Sie Abfragen an ein System richten, ändert sich der Status des entsprechenden Systems nicht. Das heißt, Abfragen haben keine Nebeneffekte.

Darum könnten Sie auch ein anderes „reads“-Datenmodell als das transaktionale, logische „writes“-Domänenmodell verwenden, obwohl die Microservices für Bestellungen dieselbe Datenbank verwenden. Daher ist es ein vereinfachter CQRS-Ansatz.

Befehle, die Transaktionen und Datenupdates auslösen, ändern wiederum den Zustand im System. Mit Befehlen müssen Sie im Zusammenhang mit Komplexität und sich kontinuierlich ändernden Geschäftsregeln sorgfältig umgehen. An dieser Stelle können Sie DDD-Techniken anwenden, um das System besser zu modellieren.

Die in diesem Leitfaden vorgestellten DDD-Muster sollten nicht universell angewendet werden, denn sie wirken sich negativ auf Ihren Entwurf aus. Diese Einschränkungen haben zwar Vorteile wie höhere Qualität im Laufe der Zeit, vor allem bei Befehlen und anderen Codezeilen, die den Systemstatus ändern, erhöhen jedoch auch die Komplexität, was Nachteile für das Lesen und Abfragen von Daten hat.

Ein solches Muster ist das Aggregatmuster, das wir in späteren Abschnitten kennenlernen. Beim Aggregatmuster werden viele Domänenobjekte aufgrund ihrer Beziehung zur Domäne als eine einzelne Einheit behandelt. In Abfragen ist dieses Muster nicht immer vorteilhaft, da es die Komplexität der Abfragelogik verkomplizieren kann. Bei schreibgeschützten Abfragen werden viele Objekte nicht als einzelnes Aggregat behandelt. In diesem Fall erhöht sich nur die Komplexität.

Wie in Abbildung 7-2 im vorherigen Abschnitt dargestellt, empfiehlt dieser Leitfaden, DDD-Muster nur im Transaktions-/Updatebereich Ihres Microservices zu verwenden, d. h. durch Befehle ausgelöst. Abfragen können einem einfacheren Ansatz folgen und sollten im Sinne des CQRS-Ansatzes von Befehlen getrennt werden.

Bei der Implementierung der Abfrageseite können Sie zwischen vielen verschiedenen Ansätzen auswählen, z. B. eine vollständige ORM wie EF Core, AutoMapper-Projektionen, gespeicherte Prozeduren, Ansichten, materialisierte Sichten oder eine Mikro-ORM.

In diesem Leitfaden und in eShopOnContainers (insbesondere beim Microservice für Bestellungen) implementieren wir direkte Abfragen mit dem Mikro-ORM [Dapper](https://github.com/StackExchange/dapper-dot-net). In diesem Leitfaden lernen Sie, jede Abfrage auf SQL-Anweisungen basierend zu implementieren, um dank des schlanken Frameworks mit wenig Mehraufwand eine optimale Leistung zu erzielen.

Wenn Sie so vorgehen, erfordern alle Updates für das Modell, die in einer SQL-Datenbank aufbewahrt werden, auch separate Updates für SQL-Abfragen, die von Dapper oder anderen Abfrageansätzen (nicht EF) verwendet werden.

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a>CQRS und DDD-Muster sind keine Architekturen oberster Ebene

CQRS und die meisten DDD-Muster (z.B. DDD-Ebenen oder ein Domänenmodell mit Aggregaten) sind keine Architekturstile, sondern lediglich Architekturmuster. Microservices, SOA und ereignisgesteuerte Architekturen (Event-Driven Architecture, EDA) sind Beispiele für Architekturstile, denn Sie beschreiben ein System mit vielen Komponenten, z.B. viele Microservices. CQRS und DDD-Muster beschreiben etwas innerhalb eines einzelnen Systems oder einer einzelnen Komponente, in diesem Fall etwas in einem Microservice.

Unterschiedliche Kontextgrenzen (Bounded Contexts, BCs) wenden außerdem verschiedene Muster an. Sie haben unterschiedliche Aufgaben, und das führt häufig zu unterschiedlichen Lösungen. Wenn überall dasselbe Muster erzwungen wird, führt das jedoch zu einem Fehler. Daher sollten Sie dies auf keinen Fall tun. Viele Teilsysteme, BCs oder Microservices sind einfacher und können leichter mithilfe einfacher CRUD-Dienste oder einer anderen Lösung implementiert werden kann.

Es gibt nur eine Anwendungsarchitektur: die Architektur der System- oder der End-to-End-Anwendung, die Sie gerade entwerfen (z.B. die Microservicesarchitektur). Der Entwurf der einzelnen Kontextgrenzen oder Microservices in dieser Anwendung spiegelt die eigenen Vor-und Nachteile und die interne Entwurfsentscheidungen auf Ebene der Musterarchitektur wider. Wenden Sie auf keinen Fall überall dieselben Architekturmuster wie CQRS oder DDD an.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Martin Fowler. CQRS** \
  <https://martinfowler.com/bliki/CQRS.html>

- **Greg Young. CQRS Documents (CQRS-Dokumente)**  \
  <https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf>

- **Udi Dahan. Clarified CQRS (Erläuterung zu CQRS)**  \
  <https://udidahan.com/2009/12/09/clarified-cqrs/>

>[!div class="step-by-step"]
>[Zurück](apply-simplified-microservice-cqrs-ddd-patterns.md)
>[Weiter](cqrs-microservice-reads.md)
