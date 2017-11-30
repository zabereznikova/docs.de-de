---
title: Ein Microservice DDD-orientierten entwerfen
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Ein Microservice DDD-orientierten entwerfen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: df45441089fd59d5e0e52b4bcec409adcc11fb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-ddd-oriented-microservice"></a>Ein Microservice DDD-orientierten entwerfen

Domain driven Design (DDD) Fürsprecher Modellierung basierend auf die Realität Unternehmen als relevant für Ihre Anwendungsfälle. Im Kontext der Erstellung von Anwendungen dreht DDD Probleme als Domänen. Unabhängige Problembereiche als begrenzt Kontexte beschrieben (jeder begrenzt, die den Kontext entspricht ein Microservice), und hebt hervor, die eine einheitliche Sprache, um diese Probleme zu erörtern. Es wird auch vorgeschlagen viele technische Konzepte und Muster, z. B. Domänenentitäten mit umfangreichen Modellen (keine [anemic Domänenmodell](https://martinfowler.com/bliki/AnemicDomainModel.html)), Objekte, Aggregate und aggregieren Stamm (bzw. Stammentität) zur Unterstützung der internen Implementierung Regeln. Dieser Abschnitt enthält den Entwurf und die Implementierung dieser interne Muster.

In einigen Fällen sind diese technischen DDD-Regeln und Muster als Hindernisse angesehen, die eine steile Lernkurve für die Implementierung DDD Ansätze aufweisen. Aber der wichtigste Teil ist nicht die Muster selbst, aber den Code organisieren, sodass es auf die geschäftlichen Probleme ausgerichtet ist, und mithilfe der gleichen geschäftsbegriffe (ubiquitäre Sprache). Darüber hinaus sollten DDD Ansätze angewendet werden, nur, wenn Sie komplexe Microservices mit erheblichen Geschäftsregeln implementieren. Mit einfacher Ansätzen können einfachere Aufgaben, wie ein CRUD-Dienst verwaltet werden.

WHERE zum Zeichnen der Grenzen ist die wichtigste Aufgabe beim Entwerfen und eine Microservice definieren. DDD Muster können Sie die Komplexität in der Domäne zu verstehen. Für das Domänenmodell für jede begrenzt, die den Kontext identifizieren und definieren die Entitäten, die Wert-Objekte und die Aggregate, die Ihre Domäne zu modellieren. Sie erstellen und optimieren ein Domänenmodell, die innerhalb einer Grenze enthalten ist, die den Kontext definiert. Und das ist in Form einer Microservice sehr explizit. Die Komponenten innerhalb dieser Grenzen am Ende Ihrer Microservices wird zwar in manchen Fällen a BC oder Business Microservices können mehrere physische Dienste bestehen. DDD geht es um Grenzen und deshalb Microservices.

## <a name="keep-the-microservice-context-boundaries-relatively-small"></a>Behalten Sie die Microservice Kontextgrenzen relativ klein

Bestimmen die Grenzen zwischen den Kontexten begrenzt platzieren gleicht zwei konkurrierenden Ziele. Zuerst möchten Sie anfänglich die kleinste mögliche Microservices erstellen zwar, die nicht der Haupt-Treiber werden soll; Erstellen Sie eine Begrenzung um Dinge, die Kohäsion benötigen. Zweitens, möchten Sie ' geschwätzige ' Kommunikation zwischen Microservices zu vermeiden. Diese Ziele können miteinander widersprechen. Sie sollten diese verteilen, indem Zerlegen von das System in beliebig viele kleine Microservices wie möglich bis Kommunikationsgrenzen schnell wächst mit jeder weitere Verbindungsversuche trennen Sie einen neuen begrenzt, die den Kontext angezeigt. Kohäsion ist-Schlüssel in einem einzelnen gebundene Kontext.

Ähnliches gilt für die [Unangemessene Intimität Codegeruch](https://sourcemaking.com/refactoring/smells/inappropriate-intimacy) bei der Implementierung von Klassen. Wenn zwei Microservices viel miteinander zusammenarbeiten müssen, sollten sie möglicherweise die gleichen Microservice sein.

Eine andere Möglichkeit, dies ist die Autonomie. Wenn ein Microservice auf einen anderen Dienst direkt eine Anfrage angewiesen ist, ist es nicht tatsächlich autonome.

## <a name="layers-in-ddd-microservices"></a>Ebenen in DDD microservices

Die meisten unternehmensanwendungen mit erheblichen geschäftlichen und technischen Komplexität werden durch mehrere Ebenen definiert. Die Ebenen sind eine logische Artefakt und beziehen sich nicht auf die Bereitstellung des Diensts. Sie vorhanden sind, um die Komplexität im Code verwalten Entwicklern zu helfen. Unterschiedliche Ebenen (z. B. die Domäne Modellebene im Vergleich zu der Darstellungsschicht usw.) möglicherweise unterschiedliche Typen der Übersetzungen zwischen diesen Typen erfordert.

Beispielsweise könnte eine Entität aus der Datenbank geladen werden. Teil dieser Informationen oder eine Aggregation von Informationen, einschließlich weiterer Daten von anderen Entitäten kann dann an den Client-Benutzeroberfläche über eine REST-Web-API gesendet werden. Der Punkt hier ist, dass die Entität "Domain" in der Domäne der Ebene enthalten ist und sollten nicht an anderen Bereichen, die es nicht zu, z. B. auf die Präsentationsebene gehört weitergegeben werden.

Darüber hinaus benötigen Sie immer gültige Entitäten (finden Sie unter der [entwerfen Überprüfungen in der Domäne der Ebene](#designing-validations-in-the-domain-model-layer) Abschnitt) durch aggregieren Stammelemente (Stamm-Entitäten) gesteuert. Entitäten sollten daher nicht mit Clientansichten gebunden werden, weil auf Benutzeroberflächenebene einige Daten immer noch nicht überprüft werden können. Dies ist das ViewModel für. Das ViewModel ist ein Datenmodell ausschließlich für die Präsentation Ebene benötigt. Die Domänenentitäten gehören nicht direkt auf das ViewModel. Stattdessen müssen Sie zwischen Entitäten ViewModels "und" Domäne und umgekehrt zu übersetzen.

Wenn bewältigt Fortschritts relativ komplex ist, es ist wichtig, haben ein Domänenmodell, der durch aggregieren Stammelemente, die (wir gehen in diese ausführlicher weiter unten) Sie sicher stellen, dass die Invarianten und die Regeln bezüglich gesteuert werden dieser Gruppe von Entitäten (aggregate) über einen einzelnen Eintrag ausgeführt Punkt oder ein Tor aggregieren Stamm.

Abbildung 9 – 5 veranschaulicht, wie ein mehrstufigen Entwurf in der eShopOnContainers-Anwendung implementiert wird.

![](./media/image6.png)

**Abbildung 9 – 5**. DDD Ebenen in der Reihenfolge Microservice in eShopOnContainers

Möchten Sie das System so entwerfen, dass jede Ebene nur mit bestimmten anderen Ebenen kommuniziert. Die möglicherweise leichter zu erzwingen, wenn Ebenen als unterschiedliche Klassenbibliotheken implementiert werden, da Sie deutlich erkennen können, welche Abhängigkeiten zwischen Bibliotheken festgelegt ist. Für die Instanz, die Domäne der Ebene nicht ergreift eine Abhängigkeit auf eine beliebige andere Ebene (die Domäne Modellklassen Plain Old CLR Objects, werden sollte oder [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object), Klassen). Wie in Abbildung 9 – 6 gezeigt die **Ordering.Domain** Ebene Bibliothek weist Abhängigkeiten nur für die .NET Core-Bibliotheken jedoch nicht auf eine beliebige andere benutzerdefinierte Bibliothek (Data-Bibliothek, Persistenz-Bibliothek, usw.).

![](./media/image7.PNG)

**Abbildung 9 – 6**. Ebenen implementiert werden, wie Bibliotheken eine bessere Steuerung des Abhängigkeiten zwischen Ebenen zulassen

### <a name="the-domain-model-layer"></a>Die Domäne der Ebene

Ausgezeichnete Buch des Eric Evans [Domain Driven Design](http://domainlanguage.com/ddd/) besagt, dass die folgenden zu der Ebene der Domäne und der Anwendungsschicht.

**Domäne der Ebene**: verantwortlich für die Darstellung von Konzepten der Business, Informationen zu den Unternehmenssituation und Geschäftsregeln. Zustand, der die Unternehmenssituation wird gesteuert, und hier verwendet werden, obwohl alle technischen Konfigurationsdetails, speichern es an die Infrastruktur delegiert werden. Diese Ebene ist das Kernstück von Business-Software.

Die Domäne der Ebene ist, in denen das Unternehmen ausgedrückt wird. Wenn Sie eine Domäne der Ebene Microservice in .NET implementieren, wird, auf dieser Ebene als eine Klassenbibliothek mit den Domänenentitäten codiert, die Daten plus Verhalten (Methoden mit Logik) zu erfassen.

Nach der [Persistenz Unkenntnis](http://deviq.com/persistence-ignorance/) und [Infrastruktur Unkenntnis](https://ayende.com/blog/3137/infrastructure-ignorance) Prinzipien, die dieser Ebene müssen Details zur Persistenz von Daten vollständig ignorieren. Diese Aufgaben Persistenz sollte durch die Infrastrukturebene erfolgen. Aus diesem Grund diese Ebene nicht abwartet, direkte Abhängigkeiten in der Infrastruktur, was bedeutet, dass eine Regel wichtige ist, dass die Domäne Modell Entitätsklassen werden soll [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)s.

Domänenentitäten sollte direkte Abhängigkeit (z. B. von einer Basisklasse ableiten) nicht auf alle Data Access-Infrastruktur-Framework wie Entity Framework oder NHibernate aufweisen. Im Idealfall sollten Ihrer Domänenentitäten nicht abgeleitet bzw. implementiert diesen beliebigen Typs in einem Infrastruktur-Framework definiert.

Die meisten modernen ORM-Frameworks wie Entity Framework Core können dieser Ansatz, sodass der Infrastruktur nicht Ihren Modellklassen Domäne verknüpft sind. Allerdings ist mit POCO-Entitäten nicht immer möglich, wenn bestimmte NoSQL-Datenbanken und Frameworks, z. B. Akteure und zuverlässige Auflistungen in Azure Service Fabric verwenden.

Auch wenn es auf dem Prinzip der Persistenz Unkenntnis für Sie Domänenmodell folgen wichtig ist, sollte nicht Persistenz Bedenken ignoriert werden. Es ist immer noch sehr wichtig zu verstehen, die physische Datenmodell und wie sie Ihr Objektmodell Entität zugeordnet. Andernfalls können Sie Entwürfe gar nicht erstellen.

Dies bedeutet auch, nicht können Sie ein Modell für eine relationale Datenbank dauern und verschieben Sie sie direkt zu einem NoSQL oder dokumentorientiert Datenbank. In anderen Modellen Entität kann das Modell entsprechen, aber in der Regel nicht. Es sind noch Einschränkungen, die Ihre Entitätsmodell, sowohl auf die speichertechnologie und ORM-Technologie als Grundlage folgen muss.

### <a name="the-application-layer"></a>Die Anwendungsebene

Verschieben in einen für die Anwendungsebene, wir können erneut cite-Eric Evanss Buchs [Domain Driven Design](http://domainlanguage.com/ddd/):

**Anwendungsschicht:** definiert die Aufträge, die Software führen soll, und leitet die ausdrucksbasierte Domänenobjekte um Probleme zu arbeiten. Die Aufgaben, denen dieser Ebene für die verantwortliche sind für das Unternehmen sinnvoll oder erforderlich ist, für die Interaktion mit den Anwendungsschichten auf anderen Systemen. Diese Ebene wird schlanke beibehalten. Er enthält keinen Geschäftsregeln oder zur Wissensermittlung, aber nur Koordinaten Aufgaben und Delegaten arbeiten, zusammenarbeitselemente von Domänenobjekten in der nächsten Ebene nach unten. Es muss kein Status reflektieren die Unternehmenssituation allerdings Zustand, der den Fortschritt einer Aufgabe für den Benutzer oder die Anwendung aufweisen.

Ein Microservice-Anwendungsebene in .NET wird häufig als ASP.NET Core Web-API-Projekt codiert. Das Projekt implementiert die Microservice Interaktion, Remotezugriff auf das Netzwerk und die externe Web-APIs, die über die Benutzeroberfläche oder Client-apps verwendet. Es schließt Abfragen, wenn mit einem CQRS-Ansatz, Befehle, die von der Microservice und sogar die ereignisgesteuerte Kommunikation zwischen Microservices (integrationsereignisse) akzeptiert. Die ASP.NET Core-Web-API, die die Anwendungsebene darstellt dürfen keine Geschäftsregeln oder domänenwissen (insbesondere Domänenregeln für Transaktionen oder Updates); enthalten. Diese sollte Besitz der Domäne Modell-Klassenbibliothek. Die Anwendung Ebene muss nur Koordinate muss Aufgaben und nicht halten oder eine beliebige Domäne Zustand (Domänenmodell) definieren. Es delegiert die Ausführung von Geschäftsregeln für die Domäne Modellklassen selbst (aggregieren Stämme und Domänenentitäten), die letztlich die Daten in dieser Domänenentitäten aktualisiert werden.

Grundsätzlich ist die Anwendungslogik, in allen Fällen implementieren, die von einem bestimmten front-End-abhängen. Beispielsweise muss die Implementierung im Zusammenhang mit einem Web-API-Dienst.

Das Ziel ist, dass die Domänenlogik in die Domäne der Ebene, die Invarianten, das Datenmodell und entsprechende Geschäftsregeln definieren völlig unabhängig von der Präsentation und Anwendungsschicht sein muss. Am häufigsten daran, muss die Domäne der Ebene nicht direkt von einem Infrastructure-Framework abhängig.

### <a name="the-infrastructure-layer"></a>Die Infrastrukturebene

Die Infrastrukturebene ist wie die Daten, die anfänglich, in der Domänenentitäten (im Arbeitsspeicher gehalten werden) in Datenbanken oder anderen persistenten Speicher beibehalten werden. Entity Framework Core-Code verwendet ein Beispiel für die Klassen der Repository-Muster implementieren, die ein ' DbContext ' zu verwenden, um Daten in einer relationalen Datenbank beizubehalten.

In Übereinstimmung mit den oben erwähnten [Persistenz Unkenntnis](http://deviq.com/persistence-ignorance/) und [Infrastruktur Unkenntnis](https://ayende.com/blog/3137/infrastructure-ignorance) Prinzipien, die Infrastrukturebene müssen nicht "verunreinigt" die Domäne der Ebene. Sie müssen die Domäne Modell Entität Klassen agnostisch aus der Infrastruktur, mit denen Sie Daten (EF oder einem anderen Framework) beizubehalten halten, indem nicht harte Abhängigkeiten Frameworks dauert. Die Domäne Modell Layer-Klassenbibliothek müssen nur Ihr domänencode nur [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object) Entität Klassen implementieren das Kernstück der Software und vollständig vom infrastrukturtechnologien.

Daher Ihre Ebenen oder Klassenbibliotheken und Projekte sollten letztlich richten sich nach der Domäne der Ebene (Library), nicht umgekehrt, wie in Abbildung 9 – 7 dargestellt.

![](./media/image8.png)

**Abbildung 9 – 7**. Abhängigkeiten zwischen Ebenen in DDD

Dieser Entwurf Ebene sollte unabhängig für jeden Microservice erfolgen. Wie bereits erwähnt, können Sie den komplexesten Microservices implementieren befolgen DDD-Muster, bei der Implementierung einfacher datengesteuerte Microservices (einfache CRUD in einer einzelnen Ebene) auf einfachere Weise.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **DevIQ. Persistenz Unkenntnis Prinzip**
    [*http://deviq.com/persistence-ignorance/*](http://deviq.com/persistence-ignorance/)

-   **Oren Eini. Infrastruktur Unkenntnis**
    [*https://ayende.com/blog/3137/infrastructure-ignorance*](https://ayende.com/blog/3137/infrastructure-ignorance)

-   **Angel Lopez. In den Ebenen-Architektur In Domain Driven Design**
    [*https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/*](https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/)


>[!div class="step-by-step"]
[Vorherigen] (Cqrs-Microservice-reads.md) [weiter] (Microservice Domäne model.md)
