---
title: "Entwerfen ein Domänenmodell microservice"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Entwerfen ein Domänenmodell microservice"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 455a2c5a39fb9b765b557610ab108f8c75882dbd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-microservice-domain-model"></a>Entwerfen ein Domänenmodell microservice

*Definieren Sie eine umfangreiche Domänenmodell für jeden Business Microservice oder begrenzt, die den Kontext*

Ziel ist es zum Erstellen eines Modells Einzeldomäne kann für jede Business Microservice oder begrenzt, die den Kontext (BC). Bedenken Sie jedoch, die eine BC oder Business Microservice konnte in einigen Fällen bestehen mehrere physische Dienste, die eine Einzeldomänenmodell gemeinsam nutzen. Das Domänenmodell muss erfassen, Regeln, Verhalten, Business-Sprache und die Einschränkungen der einzelnen begrenzt, die den Kontext oder Business-Microservice, die es darstellt.

## <a name="the-domain-entity-pattern"></a>Die Entität "Domain"-Muster

Entitäten Domänenobjekte darstellen und werden in erster Linie definiert, anhand ihrer Identität, die Geschäftskontinuität und die Persistenz mit der Zeit und nicht nur durch die Attribute, die sie zu bilden. Wie Eric Evans sagt dazu dass, ist "ein Objekt, das durch seine Identität in erster Linie definiert eine Entität aufgerufen." Entitäten sind im Domänenmodell, sehr wichtig, da es sich um die Basis für ein Modell sind. Aus diesem Grund sollten Sie identifizieren und sorgfältig zu entwerfen.

*Identität einer Entität kann mehrere Microservices oder begrenzter Kontexten überqueren.*

Die gleiche Identität (jedoch nicht die gleiche Entität) in mehreren Kontexten begrenzt oder Microservices modelliert werden kann. Allerdings, das bedeutet nicht, dass in mehreren Kontexten der begrenzt, die dieselbe Entität mit den gleichen Attributen und Logik implementiert würde. Stattdessen begrenzen Entitäten in unterschiedlichen Kontexten begrenzt, die ihre Attribute und Verhalten auf die erforderlichen in diesem begrenzt, die den Kontext Domäne.

Z. B. möglicherweise die Käuferentität die meisten der Attribute für eine Person, die in der Benutzerentität "in das Profil oder die Identität Microservice, einschließlich der Identität definiert sind. Aber Käuferentität in der Reihenfolge Microservice ggf. weniger Attribute, weil nur bestimmte Käufer-Daten mit den Bestellprozess verknüpft ist. Der Kontext der einzelnen Microservice oder begrenzt, die den Kontext wirkt sich auf die Domänenmodell.

*Domänenentitäten müssen zusätzlich zur Implementierung von Datenattributen Verhalten implementieren.*

Eine Entität "Domain" DDD muss die Domänenlogik oder das Verhalten im Zusammenhang mit der Entity Data (das Objekt im Arbeitsspeicher zugegriffen) implementieren. Z. B. als Teil einer Order-Entitätsklasse muss Geschäftslogik und Vorgänge, die als Methoden für Aufgaben wie das Hinzufügen von ein Bestellartikel, die datenvalidierung und die gesamte Berechnung implementiert haben. Die Entität Methoden übernehmen die Invarianten und den Regeln der Entität anstatt diese Regeln auf die Anwendungsschicht verteilt.

Abbildung 9 – 8 zeigt eine Entität "Domain", die nicht nur Datenattribute aber Vorgänge oder Methoden mit verwandten Domänenlogik implementiert.

![](./media/image9.png)

**Abbildung 9 – 8**. Beispiel für eine Entität "Domain" Entwerfen, implementieren Daten plus Verhalten

In einigen Fällen können Sie natürlich Entitäten haben, die als Teil der Entitätsklasse keine Logik implementieren. Dies kann auf untergeordneten Entitäten innerhalb eines Aggregats vorkommen, wenn die untergeordneten Entität keine besondere Logik nicht verfügt, da der Großteil der Logik in den aggregierten Stamm definiert ist. Wenn Sie eine komplexe Microservice, die einen Großteil der Logik in die Dienstklassen statt in der Domänenentitäten implementiert wurde verfügen, konnte Sie in der anemic Domänenmodell, die im folgenden Abschnitt erläutert fallen.

### <a name="rich-domain-model-versus-anemic-domain-model"></a>Rich-Domänenmodell im Vergleich zu anemic Domänenmodell

In seinen Beitrag [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html), Smell beschreibt ein anemic Domänenmodell auf diese Weise:

Die grundlegende Symptom für ein Anemic Domänenmodell ist, dass auf den ersten Blick es reale Sache aussieht. Objekte vorhanden sind, viele nach der Nomen in den Domänenbereich benannt wird und diese Objekte mit dem rich Beziehungen und die Struktur, die "true" Domänenmodelle haben verbunden sind. Der Catch angezeigt wird, wenn Sie sehen Sie sich das Verhalten, und Sie feststellen, dass es kaum trifft auf diese Objekte etwas mehr als dienen der Getter und Setter somit.

Natürlich, wenn Sie ein Domänenmodell anemic verwenden, diese Datenmodellen verwendet werden aus einer Gruppe von Dienstobjekten (bisher benannte der *Geschäftsebene*) die gesamte Domäne oder Business-Logik erfassen. Der Geschäftsebene befindet sich auf das Datenmodell und des Datenmodells nur als Daten verwendet.

Die anemic Domänenmodell ist nur ein prozeduralen Stil Design. Anemic Entitätsobjekten sind echte Objekte nicht, weil sie Verhalten (Methoden) fehlt. Sie enthalten nur Dateneigenschaften, und es handelt sich daher nicht eines objektorientierten Entwurfs. Verlegen Sie alle Verhalten out in Service-Objekten (der Geschäftsebene) Sie im Wesentlichen zum Schluss [Spaghetti Code](https://en.wikipedia.org/wiki/Spaghetti_code) oder [Transaktion Skripts](https://martinfowler.com/eaaCatalog/transactionScript.html), und daher verlieren Sie die Vorteile, die einem Domänenmodell bietet.

Unabhängig davon, wenn Ihre Microservice oder begrenzt, die den Kontext sehr einfach ist (ein CRUD-Dienst) der anemic Domänenmodell in Form von Entitätsobjekten mit nur Dateneigenschaften möglicherweise ausreichend und möglicherweise nicht zu komplexeren DDD-Muster implementieren. In diesem Fall werden einfach persistenzspeicherungsmodell, da Sie nur Daten für CRUD-Zwecke absichtlich eine Entität erstellt haben.

Aus diesem Grund Microservices Architekturen perfekt für ein mit mehreren architektonische Ansatz je nach jedem begrenzt, die den Kontext werden ist. Z. B. in eShopOnContainers, Sortierung Microservice implementiert DDD-Muster, jedoch die Katalog-Microservice, also eine einfache CRUD-Dienst nicht.

Einige Personen sagen, dass die anemic Domänenmodell ein Antimuster ist. Dies hängt was Sie implementieren. Ist die Microservice, die Sie erstellen einfach genug (z. B. ein CRUD-Dienst), befolgen die anemic Domänenmodell ein Antimuster ist nicht. Wenn Sie müssen die Komplexität einer Microservice Domäne konfigurieren, die zahlreiche sich stetig ändernden Geschäftsregeln enthält, möglicherweise die anemic Domänenmodell ein Antimuster für diesen Microservice oder begrenzt, die den Kontext sein. Entwerfen sie in diesem Fall als eine umfangreiche Modell mit Entitäten enthält, die Daten plus Verhalten als auch zusätzliche DDD-Muster (Aggregate, rückgabewertobjekte usw.) implementieren möglicherweise große Vorteile für den langfristigen Erfolg eine solche Microservice.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **DevIQ. Entität "Domain"**
    [*http://deviq.com/entity/*](http://deviq.com/entity/)

-   **Martin Fowler. Das Domänenmodell**
    [*https://martinfowler.com/eaaCatalog/domainModel.html*](https://martinfowler.com/eaaCatalog/domainModel.html)

-   **Martin Fowler. Die Anemic Domänenmodell**

    <https://martinfowler.com/bliki/AnemicDomainModel.HTML>

### <a name="the-value-object-pattern"></a>Das Wertobjekt-Muster

Wie Eric Evans erwähnt wurde, verfügen"viele Objekte nicht konzeptionelle Identität. Diese Objekte beschreiben bestimmte Merkmale von etwas."

Eine Entität erfordert eine Identität, aber es gibt viele Objekte in einem System, die keine wie das Wertobjekt-Muster. Ein Wertobjekt ist ein Objekt mit keine konzeptionelle Identität, die einer Domäne Aspekte beschreiben. Hierbei handelt es sich um Objekte, die Sie instanziieren, um Entwurfselemente darzustellen, die nur vorübergehend betreffen. Sie übertragbaren *was* sind, nicht *,* werden. Beispiele für können Zahlen und Zeichenfolgen enthalten, jedoch auch auf höherer Ebene Konzepten wie Gruppen von Attributen.

Etwas, das eine Entität in einer Microservice ist möglicherweise keiner Entität in einer anderen Microservice, da im zweiten Fall möglicherweise begrenzt, die den Kontext eine andere Bedeutung haben. Z. B. eine Adresse in einer e-Commerce-Anwendung eine Identität, möglicherweise nicht, da es nur eine Gruppe von Attributen des Kunden-Profils für eine Person oder Firma darstellen kann. In diesem Fall sollte die Adresse als ein Wertobjekt klassifiziert werden. In einer Anwendung für Unternehmen ein Strom-Hilfsprogramm konnte die Kundenadresse jedoch wichtig für die Business-Domäne sein. Daher muss die Adresse eine Identität verfügen, damit das Abrechnungssystem direkt mit der Adresse verknüpft werden kann. In diesem Fall muss eine Adresse als eine Entität "Domain" klassifiziert werden.

Eine Person mit einem Namen und den Nachnamen in der Regel ist eine Entität, da eine Person Identität verfügt, selbst wenn Sie den Namen und den Nachnamen in der Regel mit einem anderen Satz von Werten, z. B. wenn diese Namen bezieht sich auch auf einer anderen Person.

Value-Objekte sind in relationalen Datenbanken ORMs wie EF, Verwaltung schwierig, während im Dokument dienstorientierten Datenbanken, die sie einfacher zu implementieren und zu verwenden.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Martin Fowler. Wert Objektmuster**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **Wert des Objekts**
    [*http://deviq.com/value-object/*](http://deviq.com/value-object/)

-   **Wert von Objekten im Test-Driven Development**
    [*https://leanpub.com/tdd-ebook/read\#Leanpub-Auto-Wert-Objekte*](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)

-   **Eric Evans. Domain Driven Design: Tackling, Complexity in the Heart of Software wird.** (Book; enthält eine Erläuterung der Value-Objekte) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

### <a name="the-aggregate-pattern"></a>Die Aggregate-Muster

Ein Domänenmodell enthält Cluster von verschiedenen Datenentitäten und Prozesse, die einen signifikanten Bereich von Funktionen, z. B. Reihenfolge vertragserfüllung oder Inventur steuern können. Eine differenziertere DDD Einheit ist das Aggregat, das beschreibt einen Cluster oder eine Gruppe von Entitäten und Verhaltensweisen, die als eine zusammenhängende Einheit behandelt werden können.

Sie definieren in der Regel ein Aggregat basierend auf der Transaktionen, die Sie benötigen. Ein klassisches Beispiel ist eine Bestellung, die auch eine Liste der Bestellartikel enthält. Ein Bestellartikel werden in der Regel eine Entität. Es ist aber eine untergeordnete Entität innerhalb der Reihenfolge Aggregat, das auch die Order-Entität als seine Stammentität, in der Regel mit dem Namen eines aggregierten Stammverzeichnis enthält.

Identifizieren von Aggregaten kann schwierig sein. Ein Aggregat ist eine Gruppe von Objekten, die zusammen konsistent sein muss, aber einfach nicht möglich, wählen Sie eine Gruppe von Objekten und beschriften Sie sie ein Aggregat. Sie müssen mit einer Domäne Konzept beginnen und überlegen Sie sich die Entitäten, die in den am häufigsten verwendeten Transaktionen im Zusammenhang mit diesem Konzept verwendet werden. Diese Entitäten, die im Hinblick auf Transaktionen konsistent sein müssen sind, was ein Aggregat bildet. Darum geht, Transaktionsvorgänge ist wahrscheinlich die beste Möglichkeit, Aggregate zu identifizieren.

### <a name="the-aggregate-root-or-root-entity-pattern"></a>Das Aggregieren Stamm- oder Stammentität-Muster

Ein Aggregat ist mindestens eine Entität besteht: aggregieren Stamm, auch als Stammentität oder primäre Ientity bezeichnet. Es kann darüber hinaus mehrere untergeordnete Entitäten und rückgabewertobjekte mit allen Entitäten und Objekte, die zusammenarbeiten, um das erforderliche Verhalten und Transaktionen implementiert haben.

Eine aggregierte Stamm dient zum Sicherstellen der Konsistenz des Aggregats; Es sollte der einzige Einstiegspunkt für Updates des Aggregats über Methoden oder Vorgänge im aggregatfunktionsaufruf Stammklasse. Sie sollten Änderungen an Entitäten innerhalb des Aggregats nur über den aggregierten Stamm vornehmen. Es ist das Aggregat Konsistenz Guardian, und berücksichtigt alle Invarianten und Konsistenzregeln, die Sie möglicherweise zur Einhaltung in Ihrer Aggregat. Wenn Sie eine untergeordnete Entität oder Wert Objekt unabhängig ändern, kann nicht aggregierte Stamm stellen Sie sicher, dass das Aggregat in einem gültigen Zustand befindet. Es wäre z. B. eine Tabelle mit einer losen bezeichnet. Verwalten von Konsistenz ist die Hauptaufgabe des Stamms aggregieren.

In Abbildung 9 – 9, sehen Sie Beispiel-Aggregate, wie der Käufer aggregate, enthält eine einzelne Entität (Käufer über die aggregierten Root). Das Order-Aggregat enthält mehrere Entitäten und ein Wertobjekt.

![](./media/image10.png)

**Abbildung 9 – 9**. Beispiel für Aggregate mit mehrere oder einzelne Entitäten

Beachten Sie, dass der Käufer Aggregat zusätzliche untergeordnete-Entitäten, abhängig von Ihrer Problemdomäne sein kann, wie in der Reihenfolge Microservice in der Anwendung der eShopOnContainers-Verweis. Abbildung 9-9 zeigt nur einen Fall, in dem der Käufer eine einzelne Entität als ein Beispiel für ein Aggregat verfügt, nur einen aggregierten Stamm enthält.

Zum Verwalten der Trennung von Aggregaten und eindeutige Grenzen zwischen ihnen beibehalten, es empfiehlt sich in einem Domänenmodell DDD, direkte Navigation zwischen Aggregate und nur mit dem das Feld Fremdschlüssel (FS) zu unterbinden, wie im implementiert ist die [ Sortierung Microservice Domänenmodell](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) in eShopOnContainers. Die Order-Entität verfügt über nur ein FK Feld für den Käufer, aber keine EF Core Navigationseigenschaft, wie im folgenden Code gezeigt:

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
}
```

Identifizieren von und Arbeiten mit Aggregaten erfordert Forschung und benutzerfreundlichkeit. Weitere Informationen finden Sie die folgenden zusätzlichen Ressourcenliste.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Vaughn Vernon. Effektive aggregieren Design - Teil I: Modellieren einer einzelnen Gesamtverstärkung**
    [*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD\_COMMUNITY\_ABHANDLUNG\_ Aggregate\_Teil\_1. Pdf*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_1.pdf)

-   **Vaughn Vernon. Effektive aggregieren Design - Teil II: Festlegen, dass Aggregate zusammenarbeiten**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf>*

-   **Vaughn Vernon. Effektive aggregieren Design - Teil III: Erhalten von Einblicken, durch die Ermittlung**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf>*

-   **Sergey Grybniak. Taktisch Entwurfsmuster DDD**
    [*https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part*](https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part)

-   **Chris Rißling. Entwickeln von transaktionalen Microservices Aggregate**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson)

-   **DevIQ. Das Aggregieren Muster**
    [*http://deviq.com/aggregate-pattern/*](http://deviq.com/aggregate-pattern/)


>[!div class="step-by-step"]
[Vorherigen] (Ddd-orientierte-microservice.md) [weiter] (Net-Core-Microservice-Domain-model.md)
