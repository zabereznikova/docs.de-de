---
title: Entwerfen eines DDD-orientierten Microservices
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über das Design DDD-orientierter Microservices für Bestellungen und die entsprechenden Anwendungsschichten
ms.date: 10/08/2018
ms.openlocfilehash: 583e103c8bd9d828731a658ea2fd2aa0758e7a12
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988738"
---
# <a name="design-a-ddd-oriented-microservice"></a>Erstellen eines DDD-orientierten Microservices

Durch domänengesteuertes Design (Domain-Driven Design, DDD) wird die Modellierung von den wirtschaftlichen Gegebenheiten beeinflusst, die für Ihre Anwendungsfälle relevant sind. Im Zusammenhang mit der Erstellung von Anwendungen bezeichnet DDD Domänen als Probleme. Unabhängige Problembereiche werden als Kontextgrenzen beschrieben (jede Kontextgrenze korreliert mit einem Microservice). Zudem wird die Verwendung einer gemeinsamen Sprache zur Erörterung dieser Probleme hervorgehoben. DDD schlägt auch viele technische Konzepte und Muster vor, z.B. Domänenentitäten mit umfangreichen Modellen (kein [anämisches Domänenmodell](https://martinfowler.com/bliki/AnemicDomainModel.html)), Wertobjekte, Aggregate und Regeln für Aggregatstämme (bzw. Stammentitäten) zur Unterstützung der internen Implementierung. Dieser Abschnitt bietet eine Einführung in den Entwurf und die Implementierung dieser internen Muster.

Manchmal werden diese technischen Konzepte und Muster von DDD als Hindernisse empfunden, die eine steile Lernkurve für die Implementierung von DDD-Ansätzen aufweisen. Wichtig sind jedoch nicht die Muster selbst, sondern die Organisation des Codes zur Ausrichtung auf die geschäftlichen Probleme und die Verwendung der gleichen Geschäftsbedingungen (ubiquitäre Sprache). Darüber hinaus sollten DDD-Ansätze nur angewendet werden, wenn Sie komplexe Microservices mit signifikanten Geschäftsregeln implementieren. Einfachere Aufgaben, wie z.B. ein CRUD-Dienst, können mit einfacheren Ansätzen verwaltet werden.

Die wichtigste Aufgabe beim Entwerfen und Definieren eines Microservices besteht darin, herauszufinden, wo die Grenzen gezogen werden sollen. Mithilfe von DDD-Mustern können Sie die Komplexität in der Domäne besser verstehen. Für das Domänenmodell der einzelnen Kontextgrenzen identifizieren und definieren Sie die Entitäten, Wertobjekte und Aggregate, mit denen Ihre Domäne modelliert wird. Sie erstellen und verfeinern ein Domänenmodell innerhalb einer Grenze, die Ihren Kontext definiert. Das wird bei der Form eines Microservice sehr deutlich. Die Komponenten innerhalb dieser Grenzen sind schließlich Ihre Microservices, auch wenn sich eine Kontextgrenze oder Unternehmensmicroservices in einigen Fällen ebenfalls aus mehreren physischen Diensten zusammensetzen können. Bei DDD geht es wie bei Microservices um Grenzen.

## <a name="keep-the-microservice-context-boundaries-relatively-small"></a>Kleinhalten der Kontextgrenzen für Microservices

Bei der Bestimmung, wo Grenzen zwischen Kontextgrenzen gesetzt werden sollen, werden zwei konkurrierende Ziele ausbalanciert. Erstellen Sie zunächst die kleinstmöglichen Microservices, auch wenn dies nicht der Haupttreiber sein sollte. Sie sollten eine Grenze um Komponenten erstellen, für die eine Kohäsion erforderlich ist. Zudem sollten umfangreiche Kommunikationen zwischen Microservices vermieden werden. Diese Ziele können im Widerspruch zueinander stehen. Sie sollten diese ausbalancieren, indem Sie sie so lange in möglichst viele kleine Microservices zerlegen, bis Sie sehen können, dass Kommunikationsgrenzen mit jedem zusätzlichen Versuch, eine neue Kontextgrenze zu trennen, schnell wachsen. Kohäsion ist der Schlüssel innerhalb einer einzelnen Kontextgrenze.

Dies ist vergleichbar mit dem [unangemessenen Code-Smell „Intimacy“](https://sourcemaking.com/refactoring/smells/inappropriate-intimacy) bei der Implementierung von Klassen. Wenn zwei Microservices viel zusammenarbeiten müssen, sollten sie möglicherweise derselbe Microservice sein.

Eine andere Betrachtungsweise ist die Autonomie. Wenn ein Microservice für eine direkte Serviceanfrage auf einen anderen Dienst angewiesen ist, ist er nicht wirklich autonom.

## <a name="layers-in-ddd-microservices"></a>Ebenen in DDD-Microservices

Die meisten Unternehmensanwendungen mit erheblicher geschäftlicher und technischer Komplexität werden durch mehrere Ebenen definiert. Die Ebenen stellen ein logisches Artefakt dar und beziehen sich nicht auf die Bereitstellung des Diensts. Sie sollen Entwickler bei der Verwaltung der Komplexität im Code unterstützen. Unterschiedliche Ebenen (z.B. die Domänenmodellebene im Vergleich zur Darstellungsebene usw.) weisen möglicherweise unterschiedliche Typen auf, wodurch Übersetzungen zwischen diesen Typen erforderlich werden.

Beispielsweise könnte eine Entität aus der Datenbank geladen werden. Ein Teil dieser Informationen, oder eine Aggregation von Informationen einschließlich zusätzlicher Daten aus anderen Entitäten, kann dann über eine REST-Web-API an die Clientbenutzeroberfläche gesendet werden. Der entscheidende Punkt hierbei ist, dass die Entität in der Domänenmodellebene enthalten ist und nicht an andere Bereiche weitergegeben werden sollte, zu denen sie nicht gehört, wie z.B. die Darstellungsebene.

Darüber hinaus müssen Sie über Entitäten verfügen, die immer gültig sind (siehe Abschnitt [Designing validations in the domain model layer (Entwerfen von Validierungen in der Domänenmodellebene)](domain-model-layer-validations.md)) und von Aggregatstämmen (Stammentitäten) gesteuert werden. Daher sollten Entitäten nicht an Clientansichten gebunden werden, da auf der Benutzeroberflächenebene einige Daten möglicherweise noch nicht überprüft wurden. Dies ist Aufgabe von ViewModel. Bei ViewModel handelt es sich um ein Datenmodell, das sich ausschließlich mit den Anforderungen auf der Darstellungsebene befasst. Die Domänenentitäten gehören nicht direkt zu ViewModel. Stattdessen müssen Sie zwischen ViewModel-Modellen und Domänenentitäten und umgekehrt übersetzen.

Bei der Komplexität ist es wichtig, über ein Domänenmodell zu verfügen, das von Aggregatstämmen gesteuert wird, durch die sichergestellt wird, dass alle Invarianten und Regeln, die sich auf diese Gruppe von Entitäten (Aggregat) beziehen, über einen einzigen Einstiegspunkt bzw. ein einziges Gate durchgeführt werden: den Aggregatstamm.

In Abbildung 7-5 wird gezeigt, wie ein Entwurf mit mehreren Ebenen in die eShopOnContainers-Anwendung implementiert wird.

![Diagramm, das die Ebenen in einem Microservice mit domänengesteuertem Design zeigt.](./media/ddd-oriented-microservice/domain-driven-design-microservice.png)

**Abbildung 7-5**. DDD-Ebenen für den Microservice für Bestellungen in eShopOnContainers

Die drei Ebenen in einem DDD-Microservice wie dem für Bestellungen Jede Ebene stellt ein VS-Projekt dar: Die Anwendungsebene ist „Ordering.API“, die Domänenebene „Ordering.Domain“ und die Infrastrukturebene „Ordering.Infrastructure“. Das System soll so entworfen werden, dass die einzelnen Ebenen nur mit bestimmten anderen Ebenen kommunizieren. Dies kann möglicherweise leichter durchgesetzt werden, wenn Ebenen als unterschiedliche Klassenbibliotheken implementiert werden, da Sie deutlich erkennen können, welche Abhängigkeiten zwischen Bibliotheken festgelegt wurden. Auf der Domänenmodellebene sollte beispielsweise keine Abhängigkeit für eine andere Ebene ausgewählt werden (bei den Domänenmodellklassen sollte es sich um Plain Old CLR Objects- bzw. um [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)-Klassen handeln). Wie in Abbildung 7-6 dargestellt, weist die Bibliothek der Ebene **Ordering.Domain** nur Abhängigkeiten für die .NET Core-Bibliotheken oder NuGet-Pakete auf – jedoch keine Abhängigkeiten zu anderen benutzerdefinierten Bibliothek, z.B. zu einer Daten- oder Persistenzbibliothek.

![Screenshot der Ordering.Domain-Abhängigkeiten.](./media/ddd-oriented-microservice/ordering-domain-dependencies.png)

**Abbildung 7-6**. Als Bibliotheken implementierte Ebenen lassen eine bessere Kontrolle der Abhängigkeiten zwischen Ebenen zu

### <a name="the-domain-model-layer"></a>Die Domänenmodellebene

Im Buch [Domain-Driven Design](https://domainlanguage.com/ddd/) von Eric Evan steht Folgendes über die Domänenmodellebene und die Anwendungsebene.

**Domänenmodellebene**: Ist für die Darstellung von Konzepten des Geschäfts, Informationen zur Geschäftslage und Geschäftsregeln verantwortlich. Der Zustand, der die Geschäftslage widerspiegelt, wird hier gesteuert und verwendet, auch wenn die technischen Details zur Speicherung an die Infrastruktur delegiert werden. Diese Ebene stellt das Kernstück von Geschäftssoftware dar.

Auf der Domänenmodellebene wird das Geschäft zum Ausdruck gebracht. Wenn Sie die Domänenmodellebene eines Microservices in .NET implementieren, wird diese Ebene als Klassenbibliothek mit den Domänenentitäten codiert, die Daten und Verhalten (Methoden mit Logik) erfassen.

Nach den Grundsätzen [Ignorieren der Persistenz](https://deviq.com/persistence-ignorance/) und [Ignorieren der Infrastruktur](https://ayende.com/blog/3137/infrastructure-ignorance) muss diese Ebene Details zur Datenpersistenz komplett ignorieren. Diese Persistenzaufgaben sollten auf der Infrastrukturebene durchgeführt werden. Daher sollte diese Ebene keine direkten Abhängigkeiten für die Infrastruktur berücksichtigen. Dies bedeutet, dass eine wichtige Regel vorsieht, dass es sich bei den Entitätsklassen Ihres Domänenmodells um [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)-Klassen handeln sollte.

Domänenentitäten sollten in keiner direkten Abhängigkeit (z.B. durch Ableitung von einer Basisklasse) zu einem Infrastrukturframework für den Datenzugriff wie Entity Framework oder NHibernate stehen. Im Idealfall sollten Ihre Domänenentitäten von keinem Typ abgeleitet werden bzw. keinen Typen implementieren, der in einem Infrastrukturframework definiert ist.

Die meisten modernen ORM-Frameworks wie Entity Framework Core lassen diesen Ansatz zu, damit Ihre Domänenmodellklassen nicht an die Infrastruktur gekoppelt sind. Allerdings ist es nicht immer möglich, über POCO-Entitäten zu verfügen, wenn bestimmte NoSQL-Datenbanken und Frameworks wie Actors und Reliable Collections in Azure Fabric Service verwendet werden.

Auch wenn es wichtig ist, bei Ihrem Domänenmodell dem Grundsatz „Ignorieren der Persistenz“ zu folgen, sollten Sie Persistenzprobleme nicht ignorieren. Es ist nach wie vor sehr wichtig, das physische Datenmodell und seine Zuordnung zu Ihrem Entitätsobjektmodell zu verstehen. Andernfalls erstellen Sie möglicherweise ungültige Entwürfe.

Dies bedeutet aber auch nicht, dass Sie ein Modell auswählen können, das für eine relationale Datenbank entworfen wurde, und es direkt in eine NoSQL- oder eine dokumentorientierte Datenbank verschieben können. Bei einigen Entitätsmodellen ist das Modell möglicherweise geeignet, in der Regel ist dies jedoch nicht der Fall. Es gibt nach wie vor Einschränkungen, denen Ihr Entitätsmodell unterworfen ist. Diese beziehen sich sowohl auf die Speichertechnologie als auch auf die ORM-Technologie.

### <a name="the-application-layer"></a>Die Anwendungsebene

Wir fahren nun mit der Anwendungsebene fort und können erneut aus dem Buch [Domain-Driven Design](https://domainlanguage.com/ddd/) von Eric Evan zitieren:

**Anwendungsebene**: Definiert die Aufträge, die von der Software ausgeführt werden sollen, und leitet die ausdrucksstarken Domänenobjekte zur Behebung von Problemen weiter. Die Aufgaben, für die diese Ebene verantwortlich ist, sind für das Geschäft von Bedeutung bzw. für die Interaktion mit den Anwendungsebenen anderer Systeme erforderlich. Diese Ebene wird dünn gehalten. Sie enthält keine Geschäftsregeln oder Wissen, sondern koordiniert nur Aufgaben und delegiert Arbeit an Kollaborationen von Domänenobjekten auf der darunterliegenden Ebene. Sie enthält keinen Zustand, der die Geschäftslage widerspiegelt, kann aber einen Zustand aufweisen, der dem Benutzer oder dem Programm den Fortschritt einer Aufgabe anzeigt.

Die Anwendungsschicht eines Microservices in .NET wird häufig als ASP.NET Core-Web-API-Projekt codiert. Das Projekt implementiert die Interaktion des Microservices, den Remotenetzwerkzugriff und die externen Web-APIs, die über die Benutzeroberfläche oder Client-Apps verwendet werden. Es enthält Abfragen, wenn ein CQRS-Ansatz verwendet wird, vom Microservice akzeptierte Befehle und sogar die ereignisgesteuerte Kommunikation zwischen Microservices (Integrationsereignisse). Die ASP.NET Core-Web-API, die die Anwendungsebene darstellt, darf keine Geschäftsregeln oder Domänenwissen enthalten (insbesondere Domänenregeln für Transaktionen oder Updates). Diese sollten der Bibliothek der Domänenmodellklassen zugeordnet sein. Die Anwendungsebene darf nur Aufgaben koordinieren und keinen Domänenstatus enthalten oder definieren (Domänenmodell). Sie delegiert die Ausführung von Geschäftsregeln für die Domänenmodellklassen (Aggregatstämme und Domänenentitäten), wodurch die Daten schließlich innerhalb dieser Domänenentitäten aktualisiert werden.

In der Anwendungslogik werden im Wesentlichen alle Fälle implementiert, die von einem bestimmten Front-End abhängen, zum Beispiel die mit einem Web-API-Dienst verbundene Implementierung.

Ziel ist, dass die Domänenlogik auf der Domänenmodellebene sowie die zugehörigen Invarianten, das Datenmodell und verwandte Geschäftsregeln komplett unabhängig von der Darstellungs- und der Anwendungsebene sind. Vor allem darf die Domänenmodellebene nicht direkt von einem Infrastrukturframework abhängig sein.

### <a name="the-infrastructure-layer"></a>Die Infrastrukturebene

Auf der Infrastrukturebene wird dargestellt, wie die Daten, die anfangs in Domänenentitäten (im Arbeitsspeicher) enthalten waren, dauerhaft in Datenbanken oder einem anderen permanenten Speicher gespeichert werden. Ein Beispiel ist die Verwendung von Entity Framework Core-Code für die Implementierung der Repository-Musterklassen, in denen DBContext für die Speicherung von Daten in einer relationalen Datenbank verwendet wird.

Gemäß den oben genannten Grundsätzen [Ignorieren der Persistenz](https://deviq.com/persistence-ignorance/) und [Ignorieren der Infrastruktur](https://ayende.com/blog/3137/infrastructure-ignorance) darf die Infrastrukturebene die Domänenmodellebene nicht „kontaminieren“. Die Entitätsklassen des Domänenmodells müssen von der Infrastruktur unabhängig sein, in der Sie Daten speichern (EF oder ein anderes Framework), indem keine harten Abhängigkeiten für Frameworks berücksichtigt werden. Ihre Klassenbibliothek auf der Domänenmodellebene sollte nur Ihren Domänencode enthalten und nur [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)-Entitätsklassen, die das Kernstück Ihrer Software implementieren und komplett entkoppelt von Infrastrukturtechnologien sind.

Deswegen sollten Ihre Ebenen bzw. Klassenbibliotheken und Projekte wie in Abbildung 7-7 dargestellt von Ihrer Domänenmodellebene (Bibliothek) abhängen, nicht umgekehrt.

![Diagramm, das Abhängigkeiten zeigt, die zwischen DDD-Dienstebenen bestehen.](./media/ddd-oriented-microservice/ddd-service-layer-dependencies.png)

**Abbildung 7-7**. Abhängigkeiten zwischen Ebenen in DDD

Abhängigkeiten in einem DDD-Dienst: Die Anwendungsschicht hängt von der Domäne und der Infrastruktur ab, die Infrastruktur von der Domäne – doch die Domäne hängt von keiner Ebene ab. Dieser Ebenenentwurf sollte bei jedem Microservice unabhängig erfolgen. Wie bereits erwähnt wurde, können Sie die komplexesten Microservices nach den DDD-Mustern implementieren, während einfachere datengesteuerte Microservices (einfacher CRUD-Vorgang auf einer einzelnen Ebene) auf einfachere Weise implementiert werden können.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **DevIQ. Persistence Ignorance principle (Prinzip „Ignorieren der Persistenz“)**  \
  <https://deviq.com/persistence-ignorance/>

- **Oren Eini. Infrastructure Ignorance (Ignorieren der Infrastruktur)**  \
  <https://ayende.com/blog/3137/infrastructure-ignorance>

- **Angel Lopez. Layered Architecture In Domain-Driven Design (Architektur mit Ebenen im domänengesteuerten Design)**  \
  <https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/>

>[!div class="step-by-step"]
>[Zurück](cqrs-microservice-reads.md)
>[Weiter](microservice-domain-model.md)
