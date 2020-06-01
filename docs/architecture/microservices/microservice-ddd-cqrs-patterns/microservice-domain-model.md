---
title: Entwerfen eines Domänenmodells für Microservices
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über die Grundkonzepte beim Entwerfen eines DDD-orientierten Domänenmodells
ms.date: 01/30/2020
ms.openlocfilehash: 234d6e518eac8de5b2f130b91adb32b6a24a7265
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144590"
---
# <a name="design-a-microservice-domain-model"></a>Entwerfen eines Microservicedomänenmodells

*Definieren Sie ein umfassendes Domänenmodell für die einzelnen Unternehmensmicroservices oder begrenzten Kontexte.*

Ihr Ziel ist die Erstellung eines kohäsiven Domänenmodells für die einzelnen Unternehmensmicroservices oder Kontextgrenzen (Bounded Context, BC). Beachten Sie aber, dass ein BC oder Unternehmensmicroservice manchmal auch aus mehreren physischen Diensten bestehen kann, die ein einziges Domänenmodell gemeinsam nutzen. Das Domänenmodell muss die Regeln, das Verhalten, die Geschäftssprache und Einschränkungen der jeweiligen Kontextgrenzen oder des jeweiligen Unternehmensmicroservices erfassen, die es darstellt.

## <a name="the-domain-entity-pattern"></a>Das Domänenentitätsmuster

Entitäten stellen Domänenobjekte dar. Sie werden nicht nur durch die darin enthaltenen Attribute definiert, sondern primär durch ihre Identität, Kontinuität und Persistenz im Laufe der Zeit. Eric Evans sagt, dass ein Objekt, das primär durch seine Identität definiert wird, als Entität bezeichnet werde. Entitäten sind im Domänenmodell sehr wichtig, da sie die Basis eines Modells darstellen. Daher sollten Sie beim Identifizieren und Entwerfen der Entitäten behutsam vorgehen.

*Die Identität einer Entität kann sich über mehrere Microservices oder Kontextgrenzen erstrecken.*

Die gleiche Identität (d.h. der gleiche `Id`-Wert, wenn auch nicht unbedingt die gleiche Domänenentität) kann für mehrere begrenzte Kontexte oder Microservices modelliert werden. Dies impliziert jedoch nicht, dass die gleiche Entität mit den gleichen Attributen und der gleichen Logik in mehreren Kontextgrenzen implementiert würde. Stattdessen begrenzen die Entitäten in den einzelnen Kontextgrenzen ihre Attribute und Verhaltensweisen auf die in der Domäne der Kontextgrenze erforderlichen Attribute und Verhaltensweisen.

Die Entität „Buyer“ (Käufer) enthält z. B. möglicherweise die meisten Attribute für eine Person, die in der Benutzerentität im Microservice „Profile“ (Profil) oder „Identity“ (Identität), einschließlich der Identität, definiert sind. Die Entität „Buyer“ (Käufer) im Microservice „Ordering“ (Bestellung) enthält jedoch möglicherweise weniger Attribute, da sich nur bestimmte Käuferdaten auf den Bestellprozess beziehen. Der Kontext der einzelnen Microservices oder Kontextgrenzen hat Auswirkungen auf das zugehörige Domänenmodell.

*Domänenentitäten müssen neben Datenattributen auch Verhaltensweisen implementieren.*

Eine Domänenentität in DDD muss die Domänenlogik oder das Verhalten implementieren, die bzw. das sich auf die Entitätsdaten bezieht (das Objekt, auf das im Arbeitsspeicher zugegriffen wird). Als Teil einer Bestellentitätsklasse müssen beispielsweise eine Geschäftslogik und Vorgänge als Methoden für Aufgaben wie das Hinzufügen eines Bestellartikels, einer Datenvalidierung und einer Gesamtberechnung implementiert werden. Diese Regeln werden nicht auf der Anwendungsschicht verteilt, sondern sind Gegenstand der Entitätsmethoden, die sich auch mit den Invarianten befassen.

In Abbildung 7-8 wird eine Domänenentität dargestellt, die nicht nur Datenattribute, sondern auch Vorgänge oder Methoden mit verwandter Domänenlogik implementiert.

![Diagramm, das das Muster einer Domänenentität zeigt.](./media/microservice-domain-model/domain-entity-pattern.png)

**Abbildung 7-8**. Beispiel für den Entwurf einer Domänenentität, die Daten und Verhalten implementiert

Eine Domänenmodellentität implementiert Verhalten durch Methoden, d.h. es handelt sich um kein „anämisches“ Modell. Manchmal kann es natürlich auch Entitäten geben, die keine Logik als Teil der Entitätsklasse implementieren. Dies kann in untergeordneten Entitäten innerhalb eines Aggregats der Fall sein, wenn die untergeordnete Entität über keine spezielle Logik verfügt, da der Großteil der Logik im Aggregatstamm definiert ist. Wenn Sie über einen komplexen Microservice verfügen, bei dem ein Großteil der Logik in den Dienstklassen und nicht in den Domänenentitäten implementiert ist, könnten Sie in den Bereich des anämischen Domänenmodells fallen, das im folgenden Abschnitt erläutert wird.

### <a name="rich-domain-model-versus-anemic-domain-model"></a>Umfassendes Domänenmodell im Vergleich zum anämischen Domänenmodell

In seinem Beitrag [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html) beschreibt Martin Fowler ein anämisches Domänenmodell wie folgt:

Das grundlegende Merkmal eines anämischen Domänenmodells ist, dass es auf den ersten Blick täuschend echt aussieht. Es sind Objekte vorhanden, von denen viele nach den Nomen im Domänenbereich benannt sind, und diese Objekte sind mit den umfassenden Beziehungen und der Struktur eines echten Domänenmodells verbunden. Wenn Sie jedoch das Verhalten betrachten, stellen Sie fest, dass es für diese Objekte kaum Verhaltensweisen gibt, wodurch sie letztlich nur aus Gettern und Settern bestehen.

Wenn Sie ein anämisches Domänenmodell verwenden, werden diese Datenmodelle natürlich von einer Reihe von Dienstobjekten verwendet (üblicherweise *Geschäftsebene* genannt), die die gesamte Domänen- oder Geschäftslogik erfassen. Die Geschäftsebene befindet sich oberhalb des Datenmodells und verwendet das Datenmodell nur als Daten.

Beim anämischen Domänenmodell handelt es sich nur um einen prozeduralen Formatentwurf. Anämische Entitätsobjekte sind keine echten Objekte, da sie über keine Verhaltensweisen (Methoden) verfügen. Da sie nur Dateneigenschaften enthalten, handelt es sich bei dem Modell um keinen objektorientierten Entwurf. Indem das gesamte Verhalten in Serviceobjekte (die Geschäftsebene) eingefügt wird, verfügen Sie am Ende nur noch über [Spaghetticode](https://en.wikipedia.org/wiki/Spaghetti_code) oder [Transaktionsskripts](https://martinfowler.com/eaaCatalog/transactionScript.html). Dadurch verlieren Sie die Vorteile, die ein Domänenmodell mit sich bringt.

Unabhängig davon, ob Ihr Microservice oder Ihre Kontextgrenze sehr einfach ist (ein CRUD-Dienst), ist das anämische Domänenmodell in Form von Entitätsobjekten, die nur Dateneigenschaften enthalten, möglicherweise ausreichend, und möglicherweise wäre das Implementieren komplexerer DDD-Muster nicht sinnvoll. In diesem Fall handelt es sich nur um ein Persistenzmodell, da Sie absichtlich eine Entität erstellt haben, die nur Daten für CRUD-Zwecke enthält.

Daher sind Microservicearchitekturen abhängig von den einzelnen Kontextgrenzen perfekt für einen Ansatz mit mehreren Architekturen geeignet. In eShopOnContainers implementiert der Microservice „Ordering“ (Bestellung) beispielsweise DDD-Muster, der Microservice „Catalog“ (Katalog), bei dem es sich um einen einfachen CRUD-Dienst handelt, jedoch nicht.

Manche bezeichnen das anämische Domänenmodell als „Antimuster“. Dies hängt wirklich davon ab, was implementiert wird. Wenn der von Ihnen erstellte Microservice einfach genug ist (z.B. ein CRUD-Dienst), ist er nach dem anämischen Domänenmodell kein Antimuster. Wenn Sie mit der Komplexität der Domäne eines Microservices umgehen müssen, die über zahlreiche, sich ständig ändernde Geschäftsregeln verfügt, stellt das anämische Domänenmodell jedoch möglicherweise ein Antimuster für diesen Microservice oder diese Kontextgrenze dar. In diesem Fall könnte es für den langfristigen Erfolg eines solchen Microservice von großem Vorteil sein, wenn das Domänenmodell als umfassendes Modell mit Entitäten entworfen wird, die Daten und Verhaltensweisen enthalten, und wenn zusätzliche DDD-Muster (Aggregate, Wertobjekte usw.) implementiert werden.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **DevIQ. Domain Entity (Domänenentität)**  \
  <https://deviq.com/entity/>

- **Martin Fowler. The Domain Model (Das Domänenmodell)**  \
  <https://martinfowler.com/eaaCatalog/domainModel.html>

- **Martin Fowler. Anemic Domain Model (Anämisches Datenmodell)**  \
  <https://martinfowler.com/bliki/AnemicDomainModel.html>

### <a name="the-value-object-pattern"></a>Das Wertobjektmuster

Eric Evans hat festgestellt, dass viele Objekte keine konzeptionelle Identität aufweisen. Diese Objekte beschreiben bestimmte Merkmale einer Komponente.

Für eine Entität ist eine Identität erforderlich. Viele Objekte in einem System weisen jedoch keine Identität auf, wie z.B. das Wertobjektmuster. Ein Wertobjekt ist ein Objekt ohne konzeptionelle Identität, das einen Domänenaspekt beschreibt. Sie instanziieren diese Objekte, um Entwurfselemente darzustellen, die Sie nur vorübergehend betreffen. Für Sie ist wichtig, *was* die Objekte sind, nicht *wer* sie sind. Zu Beispielen zählen Zahlen und Zeichenfolgen, aber auch Konzepte auf höherer Ebene wie Attributgruppen.

Eine Entität in einem Microservice ist in einem anderen Microservice möglicherweise keine Entität, da die Kontextgrenze im zweiten Fall unter Umständen eine andere Bedeutung hat. Eine Adresse in einer E-Commerce-Anwendung hat z. B. möglicherweise gar keine Identität, da sie lediglich eine Gruppe von Attributen aus dem Kundenprofil einer Person oder eines Unternehmens darstellt. In diesem Fall sollte die Adresse als Wertobjekt klassifiziert werden. In einer Anwendung für ein Stromversorgungsunternehmen könnte die Kundenadresse jedoch wichtig für die Geschäftsdomäne sein. Daher muss die Adresse über eine Identität verfügen, damit das Abrechnungssystem direkt mit der Adresse verknüpft werden kann. In diesem Fall sollte eine Adresse als Domänenentität klassifiziert werden.

Eine Person mit Namen und Nachnamen ist in der Regel eine Entität, da eine Person eine Identität hat, selbst wenn der Name und Nachname mit anderen Werten übereinstimmen, z.B. wenn sich diese Namen auch auf eine andere Person beziehen.

Die Verwaltung von Wertobjekten in relationalen Datenbanken und ORMs wie Entity Framework (EF) ist schwierig. In dokumentorientierten Datenbanken können diese einfacher implementiert und verwendet werden.

EF Core 2.0 und neuere Versionen bieten das Feature [Nicht eigenständige Entitäten](https://devblogs.microsoft.com/dotnet/announcing-entity-framework-core-2-0/#owned-entities-and-table-splitting), das die Verarbeitung von Wertobjekten vereinfacht, wie wir später im Detail sehen werden.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Martin Fowler. Value Object pattern (Das Wertobjektmuster)**  \
  <https://martinfowler.com/bliki/ValueObject.html>

- **Value Object (Das Wertobjekt)**  \
  <https://deviq.com/value-object/>

- **Value Objects in Test-Driven Development (Wertobjekte in der testgesteuerten Entwicklung)**  \
  [https://leanpub.com/tdd-ebook/read\#leanpub-auto-value-objects](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)

- **Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software. (Domänengesteuertes Design (DDD): Umgang mit Komplexität im Kern einer Software.)** (Buch, das Erläuterungen zu Wertobjekten enthält) \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

### <a name="the-aggregate-pattern"></a>Das Aggregatmuster

Ein Domänenmodell enthält Cluster verschiedener Datenentitäten und Prozesse, die einen wesentlichen Bereich von Funktionen steuern können, z.B. Angebotserfüllung oder Bestand. Das Aggregat stellt eine differenziertere DDD-Einheit dar und beschreibt ein Cluster oder eine Gruppe mit Entitäten und Verhaltensweisen, die als kohäsive Einheit behandelt werden können.

Sie definieren ein Aggregat in der Regel basierend auf den erforderlichen Transaktionen. Ein klassisches Beispiel ist eine Bestellung, die auch eine Liste mit Bestellartikeln umfasst. Ein Bestellartikel ist in der Regel eine Entität. Im Bestellaggregat, das auch die Bestellentität als Stammentität enthält, handelt es sich dabei jedoch um eine untergeordnete Entität, die in der Regel als Aggregatstamm bezeichnet wird.

Das Identifizieren von Aggregaten kann sich als schwierig erweisen. Ein Aggregat ist eine Gruppe von Objekten, die zusammen konsistent sein müssen. Sie können aber nicht einfach eine Gruppe von Objekten auswählen und diese als Aggregat bezeichnen. Sie müssen mit einem Domänenkonzept beginnen und die Entitäten berücksichtigen, die in den am häufigsten verwendeten Transaktionen im Zusammenhang mit diesem Konzept verwendet werden. Diese Entitäten, die im Hinblick auf Transaktionen konsistent sein müssen, bilden ein Aggregat. Die beste Methode zum Identifizieren von Aggregaten ist wahrscheinlich, an Transaktionsvorgänge zu denken.

### <a name="the-aggregate-root-or-root-entity-pattern"></a>Das Aggregatstamm- oder Stammentitätsmuster

Ein Aggregat umfasst mindestens eine Entität: den Aggregatstamm, der auch als Stammentität oder primäre Entität bezeichnet wird. Darüber hinaus kann es über mehrere untergeordnete Entitäten und Wertobjekte verfügen, wobei alle Entitäten und Objekte zusammenarbeiten, um erforderliche Verhaltensweisen und Transaktionen zu implementieren.

Der Zweck eines Aggregatstamms besteht darin, die Konsistenz des Aggregats sicherzustellen. Es sollte der einzige Einstiegspunkt für Updates des Aggregats über Methoden oder Vorgänge in der Aggregatstammklasse sein. Änderungen an Entitäten innerhalb des Aggregats sollten nur über den Aggregatstamm vorgenommen werden. Bei der Konsistenzwächterklausel des Aggregats werden alle Invarianten und Konsistenzregeln berücksichtigt, die Sie in Ihrem Aggregat einhalten müssen. Wenn Sie eine untergeordnete Entität oder ein Wertobjekt unabhängig ändern, kann der Aggregatstamm nicht sicherstellen, dass das Aggregat einen gültigen Status aufweist. Dies wäre vergleichbar mit einem Tisch mit losem Tischbein. Der Hauptzweck des Aggregatstamms ist das Wahren der Konsistenz.

In Abbildung 7-9 sehen Sie Beispielaggregate wie das Aggregat „Buyer“, das eine einzelne Entität enthält (den Aggregatstamm „Buyer“(Käufer)). Das Aggregat „Order“ enthält mehrere Entitäten und ein Wertobjekt.

![Diagramm, das ein Buyer-Aggregat und ein Order-Aggregat vergleicht.](./media/microservice-domain-model/buyer-order-aggregate-pattern.png)

**Abbildung 7-9**. Beispiel für Aggregate mit mehreren oder einzelnen Entitäten

Ein DDD-Domänenmodell besteht aus Aggregaten. Ein Aggregat kann eine einzige Entität oder mehrere Entitäten sowie auch Wertobjekte beinhalten. Beachten Sie, dass das Aggregat „Buyer“ (Käufer) über zusätzliche untergeordnete Entitäten verfügen könnte. Dies hängt von Ihrer Domäne ab, wie auch beim Microservice „Ordering“ (Bestellung) in der eShopOnContainers-Referenzanwendung. In Abbildung 7-9 wird ein Fall veranschaulicht, in dem der Käufer über eine einzelne Entität verfügt. Dies ist ein Beispiel für ein Aggregat, das nur einen Aggregatstamm enthält.

Es hat sich bewährt, zur Einhaltung der Trennung der Aggregate und für eindeutige Grenzen zwischen den Aggregaten die direkte Navigation zwischen Aggregaten in einem DDD-Domänenmodell nicht zuzulassen und nur über das Feld für den Fremdschlüssel zu verfügen, das im [Domänenmodell des Microservices „Ordering“ (Bestellung)](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) in eShopOnContainers implementiert ist. Die Bestellentität verfügt wie im folgenden Code dargestellt nur über ein Fremdschlüsselfeld für den Käufer, jedoch über keine EF Core-Navigationseigenschaft:

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;
    // ... Additional code
}
```

Für das Identifizieren von und Arbeiten mit Aggregaten sind Recherchen und Erfahrung erforderlich. Weitere Informationen finden Sie in den folgenden Liste mit Zusatzressourcen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Vaughn Vernon. Effective Aggregate Design - Part I: Modeling a Single Aggregate (Effektive Aggregatentwicklung, Teil 1: Modellieren eines einzelnen Aggregats)** (von <https://dddcommunity.org/>) \
  <https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_1.pdf>

- **Vaughn Vernon. Effective Aggregate Design - Part II: Making Aggregates Work Together (Effektive Aggregatentwicklung Teil II: Kooperation von Aggregaten)** (von <https://dddcommunity.org/>) \
  <https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf>

- **Vaughn Vernon. Effective Aggregate Design - Part III: Gaining Insight Through Discovery (Effektive Aggregatentwicklung – Teil III: Gewinnen von Erkenntnissen durch Ermittlung)** (von <https://dddcommunity.org/>) \
  <https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_3.pdf>

- **Sergey Grybniak. DDD Tactical Design Patterns (Taktische DDD-Entwurfsmuster)**  \
  <https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part>

- **Chris Richardson. Developing Transactional Microservices Using Aggregates (Entwickeln von Transaktionsmicroservices mit Aggregaten)**  \
  <https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson>

- **DevIQ. The Aggregate pattern (Das Aggregatmuster)**  \
  <https://deviq.com/aggregate-pattern/>

>[!div class="step-by-step"]
>[Zurück](ddd-oriented-microservice.md)
>[Weiter](net-core-microservice-domain-model.md)
