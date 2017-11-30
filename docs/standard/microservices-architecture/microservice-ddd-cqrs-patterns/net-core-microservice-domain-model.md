---
title: "Ein Microservice Domänenmodell mit .NET Core implementieren"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Ein Microservice Domänenmodell mit .NET Core implementieren"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 26c480a82ad7bb806734decebdfbe5b4a07998e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-a-microservice-domain-model-with-net-core"></a>Ein Microservice Domänenmodell mit .NET Core implementieren 

Im vorherigen Abschnitt wurden die grundlegenden Entwurfsprinzipien und das Muster für das Entwerfen ein Domänenmodell erläutert. Jetzt es Zeit zum Untersuchen von Möglichkeiten, implementieren Sie die Domänenmodell mit .NET Core ist (plain C\# Code) und EF Core. Beachten Sie, dass Ihre Domänenmodell einfach Code besteht. Es wird nur das Modell im EF kernanforderungen, jedoch keine echten Abhängigkeiten für EF verfügen. Sie sollten kein harte Abhängigkeiten oder Verweise auf EF-Core-Installationen oder anderen ORM-in Ihrem Domänenmodell aufweisen.

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a>Modell Domänenstruktur in einer benutzerdefinierten .NET Standard-Bibliothek

Ordnerorganisation, die für die Anwendung der eShopOnContainers Verweis verwendet veranschaulicht das DDD-Modell für die Anwendung. Möglicherweise eine anderen Ordnerorganisation deutlicher Entwurf gewählten Optionen für Ihre Anwendung kommuniziert. Wie Sie in Abbildung 9 – 10 sehen können, in der Reihenfolge Domänenmodell sind zwei Aggregate, das Aggregat Reihenfolge und den Käufer-Aggregat. Jedes Aggregat ist eine Gruppe von Domänenentitäten und Value-Objekte, obwohl Sie ein Aggregat besteht aus einer Einzeldomäne Entität (aggregieren Stamm oder Stammentität) sowie möglicherweise.

![](./media/image11.png)

**Abbildung 9 – 10**. Modell Domänenstruktur für die Sortierung Microservice in eShopOnContainers

Darüber hinaus umfasst der Domäne der Ebene der Repository-Verträge (Schnittstellen), die die Anforderungen an die Infrastruktur des Modells Domäne sind. Das heißt, diese Schnittstellen express welche Repositorys, die die Infrastrukturebene implementieren muss und wie. Es ist wichtig, dass die Implementierung der Repositorys außerhalb der Modellebene Domäne in der Bibliothek der formularinfrastruktur Ebene platziert werden, damit die Domäne der Ebene nicht "durch-API oder Klassen von Technologien, wie Entity Framework-Infrastruktur verunreinigt ist".

Sie sehen auch eine [SeedWork](https://martinfowler.com/bliki/Seedwork.html) Ordner mit benutzerdefinierten Basisklassen, die Sie als Basis für Ihre Domänenentitäten und Wert verwenden können Objekte, müssen Sie nicht redundanten Code in jeder Domäne Objektklasse.

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a>Strukturieren von Aggregaten in einer benutzerdefinierten .NET Standard-Bibliothek

Ein Aggregat bezieht sich auf einem Cluster mit Domänenobjekte Transaktionskonsistenz entsprechend gruppiert. Diese Objekte möglicherweise Entitäteninstanzen (von denen die aggregierten Stamm- oder Stammentität ist) sowie alle zusätzlichen Wert Objekte.

Transaktionskonsistenz bedeutet, dass ein Aggregat unbedingt konsistent und am Ende einer Business-Aktion auf dem neuesten Stand ist. Das Order-Aggregat aus der Sortierung Microservice Domänenmodell eShopOnContainers besteht z. B. wie in Abbildung 9 – 11 dargestellt.

![](./media/image12.png)

**Abbildung 9 – 11**. Die Reihenfolge, die in Visual Studio-Projektmappe aggregieren

Wenn Sie eine der Dateien im Ordner "aggregate" öffnen, sehen Sie wie sie markiert ist, als benutzerdefinierte Basisklasse oder Schnittstelle, wie die Entität oder Wert-Objekt, wie im implementiert die [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) Ordner.

## <a name="implementing-domain-entities-as-poco-classes"></a>Implementieren von Domänenentitäten als POCO-Klassen

Sie implementieren ein Domänenmodell in .NET durch das Erstellen von POCO-Klassen, die die Domänenentitäten zu implementieren. Im folgenden Beispiel wird die Order-Klasse als Entität und auch als aggregate Stammzertifizierungsstelle definiert. Da die Order-Klasse von der Entität Basisklasse abgeleitet ist, können sie allgemeine Code in Bezug auf Entitäten wiederverwenden. Beachten Sie, dass diese Basis-Klassen und Schnittstellen von Ihnen in der Domäne Modellprojekt, definiert sind daher ist es Ihr Code, der nicht über ein ORM wie EF Infrastrukturcode der Diagnosefunktion berücksichtigen.

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 1.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    public int BuyerId { get; private set; }
    public DateTime OrderDate { get; private set; }
    public int StatusId { get; private set; }
    public ICollection<OrderItem> OrderItems { get; private set; }
    public Address ShippingAddress { get; private set; }
    public int PaymentId { get; private set; }
    protected Order() { } //Design constraint needed only by EF Core
    public Order(int buyerId, int paymentId)
    {
        BuyerId = buyerId;
        PaymentId = paymentId;
        StatusId = OrderStatus.InProcess.Id;
        OrderDate = DateTime.UtcNow;
        OrderItems = new List<OrderItem>();
    }

    public void AddOrderItem(productName,
        pictureUrl,
        unitPrice,
        discount,
        units)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...
        OrderItem item = new OrderItem(this.Id, ProductId, productName,
            pictureUrl, unitPrice, discount, units);
  
        OrderItems.Add(item);
    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

Es ist wichtig zu beachten, dass dies eine Entität "Domain" als POCO-Klasse implementiert ist. Es ist keine direkte Abhängigkeit von Entity Framework Core oder andere Infrastruktur-Framework kein. Diese Implementierung ist, sollte es sein, nur C#\# Code ein Domänenmodell implementieren.

Darüber hinaus wird die Klasse mit einer Schnittstelle, die mit dem Namen IAggregateRoot ergänzt. Diese Schnittstelle ist eine leere Schnittstelle, bezeichnet einen *markerschnittstelle*, d. h. nur, um anzugeben, dass dieser Entitätsklasse auch einen aggregierten Stamm wird verwendet.

Eine markerschnittstelle wird manchmal als ein Antimuster betrachtet. Es ist jedoch auch eine fehlerfreie Möglichkeit, eine Klasse zu markieren, insbesondere, wenn diese Schnittstelle möglicherweise weiterentwickelt werden. Ein Attribut ist möglicherweise die andere Auswahl für den Marker allerdings handelt es sich schneller die Basisklasse (Entität) neben der IAggregate-Schnittstelle, über die Klasse ein Aggregatattribut-Marker Probieren Sie anstelle angezeigt. Es ist ein Metter Voreinstellungen, in jedem Fall.

Müssen Sie ein Verfahren zum Aggregieren Stamm, der Großteil des Codes im Zusammenhang mit der Konsistenz und Geschäftsregeln für das Aggregat Entitäten als Methoden in der Reihenfolge-aggregate Stammklasse (z. B. AddOrderItem beim Hinzufügen eines OrderItem-Objekts, das Aggregat) implementiert werden sollte. . Sie sollten nicht erstellen oder OrderItems Objekten unabhängig voneinander oder direkt aktualisieren; die Klasse AggregateRoot muss Steuerelement und Konsistenz von jeder Updatevorgang für seine untergeordneten Entitäten beibehalten werden.

Beispielsweise sollten Sie *nicht* gehen beliebiger Befehl Handler-Methode oder einer Anwendung Ebene Klassen:

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems colletion directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

In diesem Fall wird die Add-Methode rein eines Vorgangs zum Hinzufügen von Daten, mit direktem Zugriff auf die Auflistung OrderItems. Aus diesem Grund beziehen sich die meisten Domänenlogik, Regeln oder Überprüfungen auf, dass der Vorgang mit den untergeordneten Entitäten auf der Anwendungsebene (Befehlshandler und Web-API-Controller) verteilt.

Wenn Sie um die aggregierten Stamm wechseln, kann nicht der aggregierte Stamm die Invarianten seine Gültigkeit bzw. ihre Konsistenz garantieren. Schließlich müssen Sie Spaghetti oder Transaktionsskripts Code.

Um DDD Muster folgen zu können, benötigen Entitäten nicht öffentlichen Setter in jeder Entitätseigenschaft. Änderungen in einer Entität sollte von expliziten Methoden mit expliziten ubiquitäre Sprache über die Änderung gesteuert, die sie in der Entität ausgeführt werden.

Darüber hinaus muss Sammlungen innerhalb der Entität (z. B. die Bestellartikel) schreibgeschützte Eigenschaften (die AsReadOnly Methode weiter unten erläutert). Sie sollten nur von innerhalb der aggregierten Stamm-Klasse, Methoden oder die Methoden der untergeordneten Entität aktualisieren können.

Wie Sie im Code für den Auftrag aggregieren Stamm sehen können, sollten alle Setter private oder mindestens schreibgeschützt sind und extern sein, damit alle Vorgang für die Entität Daten oder seinen untergeordneten Elementen verfügt über Methoden in die Entitätsklasse ausgeführt werden. Damit wird die Konsistenz auf eine gesteuerte und objektorientierte Weise anstelle von Transaktionsskripts Code implementieren.

Der folgende Codeausschnitt zeigt die richtige Methode zum Hinzufügen eines Objekts OrderItem des Aggregats Reihenfolge von code.

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

In diesem Codeausschnitt werden die meisten Überprüfungen oder Logik, die im Zusammenhang mit der Erstellung eines Objekts OrderItem unter der Kontrolle des Stamms aggregieren Reihenfolge werden – in der Methode AddOrderItem – insbesondere Überprüfungen und Logik im Zusammenhang mit anderen Elementen im aggregatfunktionsaufruf. Beispielsweise erhalten Sie möglicherweise das gleiche Produkt-Element als das Ergebnis von mehreren Aufrufen an AddOrderItem. In dieser Methode konnte Sie untersuchen die Produktelemente und dieselben Produktelemente zu einem einzigen OrderItem-Objekt mit mehreren Einheiten zu konsolidieren. Darüber hinaus würde, wenn es gibt verschiedene Rabatte die Produkt-ID ist jedoch gleich, Sie wahrscheinlich höheren Rabatt gelten. Dieses Prinzip gilt für alle anderen Domänenlogik für das Objekt OrderItem.

Darüber hinaus die neue OrderItem(params) Vorgang ebenfalls gesteuert und die von der Methode AddOrderItem vom Stamm aggregieren Reihenfolge ausgeführt. Daher im Zusammenhang Großteil der Logik oder Überprüfungen mit, dass Vorgang (besonders alles, was die Konsistenz zwischen anderen Entitäten untergeordneten wirkt sich auf) in einer einzelnen Stelle innerhalb des Stamms aggregieren kann. Also der ultimate Zweck des Musters aggregieren Stamm.

Bei Verwendung von Entity Framework 1.1 eine Entität DDD kann ausgedrückt werden, da einer der neuen Funktionen von Entity Framework Core 1.1 ist, dass es ermöglicht [zuordnen zu Feldern](https://docs.microsoft.com/ef/core/modeling/backing-field) zusätzlich zu den Eigenschaften. Dies ist hilfreich, wenn Sie eine Sammlung von untergeordneten Entitäten oder rückgabewertobjekte zu schützen. Mit dieser Erweiterung können Sie einfache private Felder anstelle von Eigenschaften, und Sie jede Aktualisierung an die feldauflistung in öffentlichen Methoden implementieren und Bereitstellen von nur-Lese-Zugriff über die AsReadOnly-Methode.

Eigenschaften werden daher in DDD, aktualisieren die Entität nur über Methoden in der Entität (oder der Konstruktor), um alle invariante und die Konsistenz der Daten zu steuern möchten, nur mit einem Get-Accessor definiert. Die Eigenschaften werden durch private Felder unterstützt. Private Member kann nur von innerhalb der Klasse zugegriffen werden. Allerdings dort eine Ausnahme: EF Core muss diese Felder ebenfalls festgelegt.

```csharp
// ENTITY FRAMEWORK CORE 1.1 OR LATER
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    // DDD Patterns comment
    // Using private fields, allowed since EF Core 1.1, is a much better
    // encapsulation aligned with DDD aggregates and domain entities (instead of
    // properties and property collections)
    private bool _someOrderInternalState;
    private DateTime _orderDate;
    public Address Address { get; private set; }
    public Buyer Buyer { get; private set; }
    private int _buyerId;
    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    // DDD patterns comment
    // Using a private collection field is better for DDD aggregate encapsulation.
    // OrderItem objects cannot be added from outside the aggregate root
    // directly to the collection, but only through the
    // OrderAggrergateRoot.AddOrderItem method, which includes behavior.
    private readonly List<OrderItem> _orderItems;
    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();
    // Using List<>.AsReadOnly()
    // This will create a read-only wrapper around the private list so it is
    // protected against external updates. It's much cheaper than .ToList(),
    // because it will not have to copy all items in a new collection.
    // (Just one heap alloc for the wrapper instance)
    // https://msdn.microsoft.com/en-us/library/e78dcd75(v=vs.110).aspx
    public PaymentMethod PaymentMethod { get; private set; }
    private int _paymentMethodId;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.InProcess.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;
    }

    // DDD patterns comment
    // The Order aggregate root method AddOrderitem() should be the only way
    // to add items to the Order object, so that any behavior (discounts, etc.)
    // and validations are controlled by the aggregate root in order to
    // maintain consistency within the whole aggregate.
    public void AddOrderItem(int productId, string productName, decimal unitPrice,
        decimal discount, string pictureUrl, int units = 1)
    {
        // ...
        // Domain rules/logic here for adding OrderItem objects to the order
        // ...
        OrderItem item = new OrderItem(this.Id, productId, productName,
            pictureUrl, unitPrice, discount, units);
        OrderItems.Add(item);
    }

    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a>Zuordnen von Eigenschaften nur mit get-Eigenschaftenaccessoren auf die Felder in der Datenbanktabelle

Zuordnen von Eigenschaften zu den Spalten der Datenbanktabelle ist kein Domäne Zuständigkeit, sondern Teil der Infrastruktur und Persistenz-Ebene. Wir erwähnt diese hier nur, damit die neuen Funktionen in der EF 1.1 im Zusammenhang mit, wie Sie Entitäten modellieren können bekannt sind. Weitere Informationen zu diesem Thema werden im Abschnitt-Infrastruktur und Persistenz erläutert.

Bei Verwendung von EF 1.0 müssen innerhalb der DbContext Sie ordnen Sie die Eigenschaften, die nur mit Getter auf die tatsächlichen Felder in der Datenbanktabelle definiert sind. Dies erfolgt mit der HasField-Methode der PropertyBuilder-Klasse.

### <a name="mapping-fields-without-properties"></a>Zuordnen von Feldern ohne Eigenschaften

Mit dem neuen Feature in EF Core 1.1 Spalten Felder zuordnen ist es auch möglich, verwenden die Eigenschaften nicht. Stattdessen können Sie nur Spalten aus einer Tabelle Felder zuordnen. Ein allgemeiner Verwendungsfall dafür wird die private Felder für einen internen Status, der nicht von außerhalb der Entität zugegriffen werden muss.

Angenommen, in der im vorangehenden Codebeispiel wird die \_SomeOrderInternalState Feld verfügt über keine verknüpften Eigenschaft für eine Setter oder Getter-Methode. Dieses Feld wird auch innerhalb der Reihenfolge von Geschäftslogik berechnet und aus der Order-Methoden verwendet werden, es muss jedoch in der Datenbank ebenfalls beibehalten werden. In der EF 1.1 ist daher eine Möglichkeit, ein Feld ohne eine zugehörige Eigenschaft einer Spalte in der Datenbank zugeordnet. Dies wird auch erläutert, der [Infrastrukturebene](#the-infrastructure-layer) Abschnitt dieses Handbuchs.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Vaughn Vernon. Modellieren von Aggregate mit DDD und Entity Framework.** Beachten Sie, dass dies *nicht* Entity Framework Core.
    [*https://vaughnvernon.Co/?p=879*](https://vaughnvernon.co/?p=879)

-   **Julie Lerman. Codierung für Domain Driven Design: Tipps für Entwickler Daten Developers**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)

-   **Udi Dahan. Vorgehensweise: Erstellen Sie vollständig gekapselt Domänenmodelle**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)


>[!div class="step-by-step"]
[Vorherigen] (Microservice-Domain-model.md) [weiter] (Seedwork-domain-model-base-classes-interfaces.md)
