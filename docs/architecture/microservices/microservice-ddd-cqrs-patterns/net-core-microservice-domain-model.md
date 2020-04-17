---
title: Implementieren eines Microservicedomänenmodells mit .NET Core
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über die Implementierungsdetails eines DDD-orientierten Domänenmodells
ms.date: 10/08/2018
ms.openlocfilehash: 24f700b371d998cf99cbcf260a5278d797cb39d4
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988426"
---
# <a name="implement-a-microservice-domain-model-with-net-core"></a>Implementieren eines Microservicedomänenmodells mit .NET Core

Im letzten Abschnitt wurden die Prinzipen und Muster zum Design erläutert, die grundlegend für das Erstellen eines Domänenmodells sind. Jetzt soll dargestellt werden, wie Sie das Domänenmodell mithilfe von .NET Core (einfacher C\#-Code) und EF Core implementieren. Beachten Sie dass das Domänenmodell in diesem Beispiel nur aus Ihrem Code besteht. Es enthält nur die EF Core-Modellanforderungen, aber keine echten Abhängigkeiten von EF. Es sollten keine festen Abhängigkeiten oder Verweise auf EF Core auf eine objektrelationale Abbildung (Object-relational Mapping, ORM) in Ihrem Domänenmodell enthalten sein.

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a>Domänenmodellstruktur in einer benutzerdefinierten .NET Standard-Bibliothek

Die Ordnerorganisation, die für die Referenzanwendung „eShopOnContainers“ verwendet wird, stellt das Modell für das domänengesteuerte Design für die Anwendung dar. Möglicherweise stellen Sie fest, dass die Ordnerorganisation Ihren Überlegungen zum Anwendungsentwurf angepasst werden muss. Wie in Abbildung 7-10 dargestellt, gibt es im Domänenmodell für Bestellungen zwei Aggregate: das Aggregat „Order“ und das Aggregat „Buyer“. Jedes Aggregat besteht aus einer Gruppe von Domänenentitäten und Wertobjekten. Sie können aber auch über ein Aggregat verfügen, das aus genau einer Domänenentität besteht (dem Aggregatstamm oder der Stammentität).

:::image type="complex" source="./media/net-core-microservice-domain-model/ordering-microservice-container.png" alt-text="Screenshot des Projekts „Ordering.Domain“ im Projektmappen-Explorer.":::
Ansicht im Projektmappen-Explorer: Projekt Ordering.Domain mit dem Ordner „AggregatesModel“, der die Ordner „BuyerAggregate“ und „OrderAggregate“ enthält, die jeweils ihre Entitätsklassen, Wertobjektdateien und so weiter enthalten
:::image-end:::

**Abbildung 7-10**. Domänenmodellstruktur für den Microservice für Bestellungen in eShopOnContainers

Außerdem umfasst die Ebene des Domänenmodells Repositoryverträge (Schnittstellen), die die Infrastrukturanforderungen Ihres Domänemodells ausmachen. Anders gesagt: Diese Schnittstellen drücken aus, welche Repositorys und Methoden die Infrastrukturebene implementieren muss. Es ist wichtig, dass die Implementierung der Repositorys außerhalb der Domänenmodellebene in der Bibliothek auf Infrastrukturebene platziert wird, damit die Domänenmodellebene nicht durch die APIs oder Klassen von Infrastrukturtechnologien wie Entity Framework „verunreinigt“ wird.

Außerdem wird ein [SeedWork](https://martinfowler.com/bliki/Seedwork.html)-Ordner angezeigt, der benutzerbasierte Basisklassen enthält, die Sie als Grundlage für Ihre Domänenentitäten und Wertobjekte verwenden können, sodass redundanter Code in den Objektklassen der einzelnen Domänen vermieden wird.

## <a name="structure-aggregates-in-a-custom-net-standard-library"></a>Strukturieren von Aggregaten in einer benutzerdefinierten .NET Standard-Bibliothek

Ein Aggregat bezieht sich auf einen Cluster von Domänenobjekten, die entsprechend der Transaktionskonsistenz gruppiert sind. Bei diesen Objekten kann es sich um Instanzen von Entitäten (wobei eine der Entitäten der Aggregatstamm oder die Stammentität ist) einschließlich zusätzlicher Wertobjekte handeln.

Der Begriff „Transaktionskonsistenz“ bedeutet, dass ein Aggregat am Ende einer geschäftlichen Transaktion garantiert konsistent und aktuell ist. Das Aggregat „Order“ aus dem Domänenmodell des Microservices für Bestellungen setzt sich wie in Abbildung 7-11 dargestellt zusammen.

:::image type="complex" source="./media/net-core-microservice-domain-model/vs-solution-explorer-order-aggregate.png" alt-text="Screenshot des Ordners „OrderAggregate“ und seiner Klassen.":::
Detailansicht des Ordners OrderAggregate: „Address.cs“ ist ein Wertobjekt, „IOrderRepository“ eine Repositoryschnittstelle, „Order.cs“ ein Aggregatstamm, „OrderItem.cs“ eine untergeordnete Entität und „OrderStatus.cs“ eine Enumerationsklasse.
:::image-end:::

**Abbildung 7-11**. Das Aggregat „Order“ in einer Visual Studio-Projektmappe

Wenn Sie eine der Dateien in einem Aggregatordner öffnen, sehen Sie, dass diese entweder als benutzerdefinierte Basisklasse oder als benutzerdefinierte Schnittstelle markiert ist. Dies gilt z.B. für Entitäten oder Wertobjekte, die in den [SeedWork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork)-Ordner implementiert wurden.

## <a name="implement-domain-entities-as-poco-classes"></a>Implementieren von Domänenentitäten als POCO-Klassen

Domänenmodelle werden in .NET implementiert, indem POCO-Klassen erstellt werden, die Domänenentitäten implementieren. Im folgenden Beispiel ist die Klasse „Order“ als Entität und als Aggregatstamm definiert. Da die Klasse „Order“ von der Basisklasse „Entity“ abgeleitet wird, kann diese häufig verwendeten Code wiederverwenden, der in Zusammenhang mit den Entitäten steht. Denken Sie daran, dass diese Basisklassen und Schnittstellen von Ihnen im Domänenmodellprojekt definiert werden. Es handelt sich also um Ihren Code und nicht um Infrastrukturcode aus einer ORM wie EF.

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 2.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId;

    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    private string _description;
    private int? _paymentMethodId;

    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;

    public Order(string userId, Address address, int cardTypeId, string cardNumber, string cardSecurityNumber,
            string cardHolderName, DateTime cardExpiration, int? buyerId = null, int? paymentMethodId = null)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.Submitted.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;

        // ...Additional code ...
    }

    public void AddOrderItem(int productId, string productName,
                            decimal unitPrice, decimal discount,
                            string pictureUrl, int units = 1)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...

        var orderItem = new OrderItem(productId, productName, unitPrice, discount, pictureUrl, units);

        _orderItems.Add(orderItem);

    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

Beachten Sie, dass es sich dabei um eine Domänenentität handelt, die als POCO-Klasse implementiert ist. Diese Entität hat keine direkten Abhängigkeiten von EF Core oder anderen Infrastrukturframeworks. Diese Implementierung eignet sich hervorragend für domänengesteuertes Design, da es sich nur um C\#-Code handelt, der ein Domänenmodell implementiert.

Außerdem wird die Klasse durch eine Schnittstelle namens „IAggregateRoot“ ergänzt. Diese Schnittstelle ist leer und wird gelegentlich als *marker interface* (Markierungsschnittstelle) bezeichnet, die verwendet wird, um anzudeuten, dass es sich bei dieser Entitätsklasse ebenfalls um einen Aggregatstamm handelt.

Markierugsschnittstellen werden gelegentlich zwar als Antimuster bezeichnet, jedoch sind sie hilfreich, um eine Klasse zu markieren – insbesondere, wenn sich diese Schnittstelle weiterentwickelt. Der Marker kann zwar auch Attribute verwenden, jedoch geht es schneller, die Basisklasse (Entität) neben der IAggregate-Schnittstelle zu überprüfen, anstatt einen Attributmarker für Aggregate oberhalb der Klasse zu positionieren. Sie können hier nach Belieben entscheiden.

Wenn ein Aggregatstamm vorhanden ist, bedeutet dies, dass der meiste Code, der im Zusammenhang mit der Konsistenz und den Geschäftsregeln der Entitäten des Aggregats steht, als Methoden in der Aggregatstammklasse „Order“ implementiert werden soll (z. B. AddOrderItem beim Hinzufügen eines OrderItem-Objekts zum Aggregat). Sie sollten OrderItems-Objekte nicht unabhängig oder direkt erstellen oder aktualisieren. Stattdessen sollte die AggregateRoot-Klasse die Kontrolle und Konsistenz jedes Aktualisierungsvorgangs gegenüber der untergeordneten Entitäten behalten.

## <a name="encapsulate-data-in-the-domain-entities"></a>Kapseln von Daten in Domänenentitäten

Ein häufiges Problem im Zusammenhang mit Entitätsmodellen ist, dass sie Navigationseigenschaften für Auflistungen als öffentlich zugängliche Listentypen zur Verfügung stellen. Dadurch kann jedes Mitglied des Entwicklerteams die Inhalte dieser Auflistungstypen ändern. Dabei können möglicherweise wichtige Geschäftsregeln umgangen werden, die im Zusammenhang mit der Auflistung stehen, wodurch das Objekt im Status „ungültig“ hinterlassen wird. Zur Lösung dieses Problems können Sie den Zugriff auf verwandte Auslistungen auf „schreibgeschützt“ beschränken und explizit Methoden zur Verfügung stellen, über die Clients Änderungen vornehmen können.

Beachten Sie, dass viele Attribute im vorherigen Code schreibgeschützt oder privat sind und nur von Klassenmethoden aktualisiert werden können. So berücksichtigt jedes Update Invarianten der Geschäftsdomäne und die Logik, die in der Klassenmethode angegeben ist.

Wenn Sie sich z.B. an die Muster des domänengesteuerten Designs halten, **sollten Sie den folgenden Vorgang *nicht*** über eine Befehlshandlermethode oder Anwendungsschichtklasse ausführen (genau genommen, sollten Sie dazu gar nicht berechtigt sein):

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems collection directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

In diesem Fall handelt es sich bei der Methode „Add“ nur um einen Vorgang zum Hinzufügen von Daten mit Direktzugriff auf die OrderItems-Auflistung. Aus diesem Grund wird ein Großteil der Domänenlogik, Regeln oder Validierungen, der im Zusammenhang mit diesem Vorgang mit den untergeordneten Entitäten steht, auf die Anwendungsebene verteilt (Befehlshandler und Web-API-Controller).

Wenn Sie den Aggregatstamm umgehen, kann dieser weder seine Invarianten noch seine Gültigkeit oder Konsistenz garantieren. So wird Ihr Code mit der Zeit sehr unübersichtlich, oder es entsteht Transaktionsskriptcode.

Wenn Entitäten über öffentliche Setter in einer Entitätseigenschaft verfügen, steht dies im Widerspruch zu den Mustern des domänengesteuerten Designs. Änderungen einer Entität sollten durch explizite Methoden mit expliziten ubiquitären Sprachen zu den Änderungen ausgelöst werden, die in der Entität ausgeführt werden.

Außerdem soll es sich bei Auflistungen innerhalb der Entität (wie die der Bestellelemente) um schreibgeschützte Eigenschaften handeln (also um die nachfolgend erläuterte AsReadOnly-Methode). Sie sollten die Entität nur innerhalb der Methoden der Aggregatstammklasse oder der Methoden der untergeordneten Klasse aktualisieren können.

Wie Sie im Aggregatstamm „Order“ sehen können, sollten alle Setter den Status „privat“ aufweisen oder zumindest extern schreibgeschützt sein, sodass jeder Vorgang für die Daten der Entität oder der untergeordneten Entitäten über Methoden in der Entitätsklasse ausgeführt werden muss. Dadurch bleibt die Konsistenz auf kontrollierte und objektorientierte Weise erhalten, und es wird kein Transaktionsskriptcode verwendet.

Im folgenden Codeausschnitt sehen Sie, wie Sie am besten den Task codieren, über den das OrderItem-Objekt dem Aggregat „Order“ hinzugefügt wird.

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object's business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

In diesem Ausschnitt wird ein Großteil der Validierungen oder Logik, die im Zusammenhang mit dem OrderItem-Objekt stehen, vom Aggregatstamm „Order“ über die Methode „AddOrderItem“ gesteuert. Dies gilt insbesondere für Validierungen und Logik, die im Zusammenhang mit anderen Elementen im Aggregat stehen. Es kann z.B. sein, dass als Ergebnis mehrerer Aufrufe der AddOrderItem-Methode dasselbe Produktelement zurückgegeben wird. Sie können in dieser Methode die Produktelemente untersuchen und dieselben Produktelemente in ein OrderItem-Objekt mit mehreren Einheiten zusammenfassen. Wenn es außerdem unterschiedliche Rabatte gibt, aber die Produkt-ID unverändert bleibt, wird sehr wahrscheinlich der höhere Rabatt ausgewählt. Dieses Prinzip gilt in jeder anderen Domänenlogik für das OrderItem-Objekt.

Zudem wird der neue OrderItem(params)-Vorgang ebenfalls über die AddOrderItem-Methode aus dem Aggregatstamm „Order“ durchgeführt. Aus diesem Grund befindet sich ein Großteil der Logik oder Validierungen, die im Zusammenhang mit diesem Vorgang stehen, an einem gemeinsamen Ort im Aggregatstamm, insbesondere alle Elemente, die Auswirkungen auf die Konsistenz zwischen anderen untergeordneten Elementen haben. Dies ist der wichtigste Zweck des Aggregatstammmusters.

Wenn Sie Entity Framework Core 1.1 oder höher verwenden, kann besser eine Entität des domänengesteuerten Designs festgelegt werden, da diese neben Eigenschaften auch die [Zuordnung zu Feldern](https://docs.microsoft.com/ef/core/modeling/backing-field) zulässt. Dies ist nützlich, wenn Auflistungen von untergeordneten Entitäten oder Wertobjekten geschützt werden sollen. Mit dieser Erweiterung können Sie einfache private Felder anstelle von Eigenschaften nutzen, und Sie können jedes Update für die Feldauflistung in öffentlichen Methoden ausführen und schreibgeschützten Zugriff über die AsReadOnly-Methode bereitstellen.

Wenn Sie das domänengesteuerte Design verwenden, sollten Sie nur über die Methoden in der Entität (oder den Konstruktor) ein Update für diese ausführen, sodass Eigenschaften nur mit einem get-Accessor definiert werden. Die Eigenschaften werden über private Felder gesichert. Auf private Members kann nur innerhalb einer Klasse zugegriffen werden. Es gibt jedoch eine Ausnahme: EF Core muss auch diese Felder festlegen, damit das Objekt mit den richtigen Werten zurückgegeben werden kann.

### <a name="map-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a>Zuordnen von Eigenschaften zu Feldern in der Datenbanktabelle mit get-Accessors

Das Zuordnen von Eigenschaften zu Datenbanktabellen ist nicht allein Aufgabe der Domäne, sondern Teil der Infrastruktur und der Persistenzebene. Das wird an dieser Stelle erwähnt, damit Sie die neuen Funktionen von EF Core 1.1 oder höher kennen lernen, die mit der Vorgehensweise beim Modellieren von Entitäten im Zusammenhang stehen. Ausführliche Informationen zu diesem Thema finden Sie in dem Abschnitt zur Infrastruktur und Persistenz.

Wenn Sie EF Core 1.0 oder höher verwenden, müssen Sie im Zusammenhang mit DbContext die Eigenschaften zuordnen, die nur über Getter den Feldern in der Datenbanktabelle zugeordnet sind. Diesen Vorgang führen Sie mit der HasField-Methode der PropertyBuilder-Klasse aus.

### <a name="map-fields-without-properties"></a>Zuordnen von Feldern ohne Eigenschaften

Mit dem Feature in EF Core 1.1 oder höher, über das Sie Feldern Spalten zuordnen, müssen Sie nicht unbedingt Eigenschaften verwenden. Stattdessen reicht es aus, wenn Sie den Feldern nur Spalten aus einer Tabelle zuordnen. Dies ist ein häufiger auftretender Anwendungsfall, da es sich dabei um private Felder für einen internen Zustand handelt, auf den außerhalb der Entität nicht zugegriffen werden muss.

Beispielsweise enthält das nachfolgende OrderAggregate-Codebeispiel mehrere private Felder wie das `_paymentMethodId`-Feld, denen keine Eigenschaften für den Setter oder Getter zugeordnet sind. Dieses Feld könnte außerdem innerhalb der Geschäftslogik der Bestellung berechnet und über die Methoden der Bestellung verwendet werden. Es muss allerdings auch in der Datenbank beibehalten werden. In EF Core gibt es (ab Version 1.1) die Möglichkeit, ein Feld zuzuordnen, wenn keine passende Eigenschaft der Spalte in der Datenbank zugeordnet wird. Dies wird ebenfalls in diesem Handbuch im Abschnitt [Infrastrukturebene](ddd-oriented-microservice.md#the-infrastructure-layer) erläutert.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Vaughn Vernon. Modeling Aggregates with DDD and Entity Framework (Modellieren von Aggregaten mit dem domänengesteuerten Design und Entity Framework).** Hinweis: Dieser Artikel gilt *nicht* für Entity Framework Core. \
  <https://kalele.io/blog-posts/modeling-aggregates-with-ddd-and-entity-framework/>

- **Julie Lerman. Datenpunkte – Codierung für Domain-Driven Design: Tipps für Entwickler mit Datenschwerpunkt** \
  <https://docs.microsoft.com/archive/msdn-magazine/2013/august/data-points-coding-for-domain-driven-design-tips-for-data-focused-devs>

- **Udi Dahan. How to create fully encapsulated Domain Models (Erstellen eines vollständig gekapselten Domänenmodells)**  \
  <http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/>

> [!div class="step-by-step"]
> [Zurück](microservice-domain-model.md)
> [Weiter](seedwork-domain-model-base-classes-interfaces.md)
