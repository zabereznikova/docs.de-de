---
title: Implementieren von Wertobjekten
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Einführung in die Details und Optionen zum Implementieren von Wertobjekten mithilfe neuer Features von Entity Framework
ms.date: 01/30/2020
ms.openlocfilehash: 4a8a92a8dabcf09654ecd0e5dea2a7df25d7abf7
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805739"
---
# <a name="implement-value-objects"></a>Implementieren von Wertobjekten

Wie bereits in den vorherigen Abschnitten zu den Themen „Entitäten“ und „Aggregate“ ist die Identität ein grundlegender Bestandteil von Entitäten. Allerdings sind viele Objekte und Datenelemente in einem System enthalten, für die keine Identität oder Identitätsnachverfolgung erforderlich ist, z.B. Wertobjekte.

Ein Wertobjekt kann auf mehrere Entitäten verweisen. Ein Wertobjekt ist z.B. eine Route, die in einer Anwendung generiert wird und beschreibt, wie man von einem Punkt zu einem anderen gelangt. Dabei handelt es sich dann um eine Momentaufnahme von verschiedenen Punkten auf einer bestimmten Route. Die vorgeschlagene Route verfügt aber über keine Identität, obwohl sie intern möglicherweise auf Entitäten wie „City“ oder „Road“ verweist.

In Abbildung 7-13 wird das Wertobjekt „Address“ im Aggregat „Order“ angezeigt.

![Diagramm, das das Wertobjekt „Address“ im Aggregat „Order“ zeigt.](./media/implement-value-objects/value-object-within-aggregate.png)

**Abbildung 7-13**. Wertobjekt „Address“ im Aggregat „Order“

Wie in Abbildung 7-13 dargestellt besteht eine Entität in der Regel aus mehreren Attributen. Beispielsweise kann die `Order`-Entität als Entität mit einer Identität modelliert sein und intern aus mehreren Attributen wie OrderId, OrderDate oder OrderItems bestehen. Die Adresse, bei der es sich lediglich um einen komplexen Wert handelt, der aus Attributen wie Land/Region, Straße, Ort usw. besteht und in dieser Domäne nicht über eine Identität verfügt, muss hingegen als Wertobjekt modelliert und behandelt werden.

## <a name="important-characteristics-of-value-objects"></a>Wichtige Merkmale von Wertobjekten

Die beiden wichtigsten Merkmale von Wertobjekten lauten wie folgt:

- Sie haben keine Identität.

- Sie sind unveränderlich.

Das erste Merkmal wurde bereits erwähnt. Die Unveränderlichkeit ist eine wichtige Anforderung. Die Werte eines Wertobjekts müssen unveränderlich sein, nachdem ein Objekt erstellt wurde. Aus diesem Grund müssen Sie beim Erstellen des Objekts die erforderlichen Werte zur Verfügung stellen. Dabei müssen Sie allerdings festlegen, dass es während seiner gesamten Lebensdauer nicht änderbar ist.

Mithilfe von Wertobjekten können Sie aufgrund ihrer Unveränderlichkeit bestimmte Tricks verwenden, die sich positiv auf die Leistung auswirken. Dies gilt insbesondere für Systeme, in denen tausende von Wertobjektinstanzen enthalten sind, von denen viele denselben Wert haben. Aufgrund ihrer Unveränderlichkeit können sie wiederverwendet werden, und da sie dieselben Werte haben, jedoch nicht über eine Identität verfügen, können sie als austauschbare Objekt fungieren. Diese Art von Optimierung macht häufig den Unterschied zwischen langsamer Software und Software mit hoher Leistung aus. Trotzdem sind all diese Beispiele abhängig von der Anwendungsumgebung und dem Entwicklungskontext.

## <a name="value-object-implementation-in-c"></a>Implementieren von Wertobjekten in C\#

Im Hinblick auf die Implementierung können Sie über eine Wertobjektbasisklasse mit grundlegenden Hilfsprogrammmethoden wie Gleichheit, die auf einem Vergleich aller Attribute basiert (da Wertobjekte nicht auf einer Identität basieren dürfen), und anderen grundlegenden Merkmalen verfügen. Im folgenden Beispiel wird eine Wertobjektbasisklasse angezeigt, die im eShopOnContainers-Microservice für Bestellungen verwendet wird.

```csharp
public abstract class ValueObject
{
    protected static bool EqualOperator(ValueObject left, ValueObject right)
    {
        if (ReferenceEquals(left, null) ^ ReferenceEquals(right, null))
        {
            return false;
        }
        return ReferenceEquals(left, null) || left.Equals(right);
    }

    protected static bool NotEqualOperator(ValueObject left, ValueObject right)
    {
        return !(EqualOperator(left, right));
    }

    protected abstract IEnumerable<object> GetAtomicValues();

    public override bool Equals(object obj)
    {
        if (obj == null || obj.GetType() != GetType())
        {
            return false;
        }

        ValueObject other = (ValueObject)obj;
        IEnumerator<object> thisValues = GetAtomicValues().GetEnumerator();
        IEnumerator<object> otherValues = other.GetAtomicValues().GetEnumerator();
        while (thisValues.MoveNext() && otherValues.MoveNext())
        {
            if (ReferenceEquals(thisValues.Current, null) ^
                ReferenceEquals(otherValues.Current, null))
            {
                return false;
            }

            if (thisValues.Current != null &&
                !thisValues.Current.Equals(otherValues.Current))
            {
                return false;
            }
        }
        return !thisValues.MoveNext() && !otherValues.MoveNext();
    }

    public override int GetHashCode()
    {
        return GetAtomicValues()
         .Select(x => x != null ? x.GetHashCode() : 0)
         .Aggregate((x, y) => x ^ y);
    }
    // Other utility methods
}
```

Sie können diese Klasse verwenden, wenn Sie das tatsächliche Wertobjekt implementieren. Dies ist z.B. im nachfolgenden Beispiel zum Wertobjekt „Address“der Fall:

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    private Address() { }

    public Address(string street, string city, string state, string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        // Using a yield return statement to return each element one at a time
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

Sie können sehen, wie diese Implementierung des Wertobjekts „Address“ über keine Identität verfügt, weshalb sie weder in der Address-Klasse noch in der ValueObject-Klasse über ein ID-Feld verfügt.

In einer Klasse über kein von Entity Framework (EF) verwendbares ID-Feld zu verfügen, war bis EF Core 2.0 nicht möglich. Dies ist für das Implementieren besserer Wertobjekte ohne ID ausgesprochen hilfreich. Außerdem entspricht dies der Erklärung des nächsten Abschnitts.

Es ließe sich die Ansicht vertreten, dass Wertobjekte – da sie unveränderlich sind – schreibgeschützte Eigenschaften aufweisen sollten, und dies stimmt tatsächlich. Allerdings werden Wertobjekte in der Regel zum Durchlaufen von Warteschlangen serialisiert und deserialisiert. Wenn sie schreibgeschützt sind, kann das Deserialisierungsprogramm keine Werte zuweisen. Daher wird die Eigenschaft `private set` beibehalten, wodurch sie zu eine Maß schreibgeschützt sind, dass sie dennoch verwendet werden können.

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20-and-later"></a>Beibehalten von Wertobjekten in der Datenbank mit EF Core 2.0 und höher

Obenstehend wurde erläutert, wie Sie ein Wertobjekt in Ihrem Domänenmodell definieren. Nun soll erläutert werden, wie Sie es mithilfe von Entity Framework Core dauerhaft in der Datenbank speichern, obwohl dieser Dienst in der Regel auf Entitäten mit Identitäten ausgerichtet ist.

### <a name="background-and-older-approaches-using-ef-core-11"></a>Hintergrund und ältere Ansätze zur Verwendung von EF Core 1.1

Hintergrundinformation: Mit EF Core 1.0 und 1.1 konnten Sie keine [komplexen Typen](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) verwenden, die in EF 6.x im herkömmlichen .NET Framework definiert sind. Aus diesem Grund mussten Sie ein Wertobjekt als EF-Entität mit einem ID-Feld speichern, wenn Sie EF Core 1.0 oder 1.1 verwenden. Anschließend konnten Sie die ID ausblenden, um eine Ähnlichkeit zum Wertobjekt ohne Identität herzustellen, und um deutlich zu machen, dass die Identität eines Wertobjekts im Domänenmodell nicht von Bedeutung ist. Die ID konnte ausgeblendet werden, indem sie als [Schatteneigenschaft](https://docs.microsoft.com/ef/core/modeling/shadow-properties ) verwendet wurde. Da diese Konfiguration zum Ausblenden der ID im Modell in der EF-Infrastruktur eingerichtet ist, würde Ihr Domänenmodell diese durchschauen.

In der ersten Version von eShopOnContainers (.NET Core 1.1) wurde die von der EF Core-Infrastruktur verlangte versteckte ID wie folgt auf DbContext-Ebene implementiert. Dafür wurde die Fluent-API im Infrastrukturprojekt verwendet. Daher wurde die ID für das Domänenmodell ausgeblendet, sie war aber weiterhin in der Infrastruktur vorhanden.

```csharp
// Old approach with EF Core 1.1
// Fluent API within the OrderingContext:DbContext in the Infrastructure project
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);

    addressConfiguration.Property<int>("Id")  // Id is a shadow property
        .IsRequired();
    addressConfiguration.HasKey("Id");   // Id is a shadow property
}
```

Die Persistenz dieses Wertobjekts in die Datenbank wurde wie eine reguläre Entität in einer anderen Tabelle durchgeführt.

Ab EF Core 2.0 gibt es neue und bessere Möglichkeiten, Wertobjekte permanent zu speichern.

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20-and-later"></a>Permanentes Speichern von Wertobjekten als nicht eigenständige Entitätstypen in EF Core 2.0 und höher

Auch wenn das kanonische Wertobjektmuster im domänengesteuerten Design und der nicht eigenständige Entitätstyp in EF Core Nachteile haben, so stellen diese derzeit die beste Möglichkeit dar, Wertobjekte mit EF Core 2.0 und höher permanent zu speichern. Einschränkungen werden am Ende dieses Abschnitts erläutert.

Das eigene Entitätstypenfeature wurde schon mit Version 2.0 von EF Core hinzugefügt.

Über einen eigenen Entitätstyp können Sie Typen zuordnen, für die keine Identität im Domänenmodell explizit definiert ist und die als Eigenschaften verwendet werden, also z.B. als ein Wertobjekt in einer Entität. Ein nicht eigenständiger Entitätstyp teilt sich denselben CLR-Typ mit einem anderen Entitätstyp (d. h., es handelt sich lediglich um eine reguläre Klasse). Die Entität, die die definierende Navigation enthält, ist die besitzende Entität. Beim Abfragen des Besitzers werden standardmäßig eigene Typen eingeschlossen.

Bei alleiniger Betrachtung des Domänenmodell sieht es so aus, als ob ein nicht eigenständiger Typ keine Identität aufweist. Die Identität des eigenen Typs befindet sich allerdings im Hintergrund, und die Eigenschaft zur Besitzernavigation ist Teil dieser Identität.

Die Identität von Instanzen von eigenen Typen ist nicht ausschließlich auf diese beschränkt. Sie besteht aus drei Hauptkomponenten:

- Der Identität des Besitzers

- Der Navigationseigenschaft, die auf diese zeigt

- Im Fall von Sammlungen nicht eigenständiger Entitätstypen eine unabhängige Komponente (unterstützt ab EF Core 2.2).

Beispielsweise wird im Domänenmodell für die Bestellung in eShopOnContainers das Wertobjekt „Address“ als Teil der Entität „Order“ als eigener Entitätstyp in die besitzende Entität (also der Entität „Order“) implementiert. Bei „Address“ handelt es sich um einen Typ ohne Identitätseigenschaft, der im Domänenmodell definiert ist. Dieser Typ wird als Eigenschaft des Typs „Order“ verwendet, um die Lieferadresse für eine bestimmte Bestellung anzugeben.

Gemäß den Konventionen wird ein Schattenprimärschlüssel für den eigenen Typ erstellt und mithilfe der Tabellenaufteilung derselben Tabelle wie der Besitzer zugeordnet. Dies ermöglicht die Verwendung von eigenen Typen, ähnlich wie bei den in EF 6 im herkömmlichen .NET Framework verwendeten komplexen Typen.

Sie sollten wissen, dass eigene Typen standardmäßig nie von EF Core ermittelt werden. D.h., Sie müssen sie explizit deklarieren.

In der Datei „OrderingContext.cs“ innerhalb der `OnModelCreating()`-Methode des eShopOnContainers-Beispiels werden mehrere Infrastrukturkonfigurationen angewendet. Eine dieser Konfigurationen steht in Beziehung zur Entität „Order“.

```csharp
// Part of the OrderingContext.cs class at the Ordering.Infrastructure project
//
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.ApplyConfiguration(new ClientRequestEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new PaymentMethodEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderItemEntityTypeConfiguration());
    //...Additional type configurations
}
```

Im folgenden Code ist die Persistenzinfrastruktur für die Entität „Order“ definiert:

```csharp
// Part of the OrderEntityTypeConfiguration.cs class
//
public void Configure(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Ignore(b => b.DomainEvents);
    orderConfiguration.Property(o => o.Id)
        .ForSqlServerUseSequenceHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

    //Address value object persisted as owned entity in EF Core 2.0
    orderConfiguration.OwnsOne(o => o.Address);

    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();

    //...Additional validations, constraints and code...
    //...
}
```

Im obigen Code gibt die `orderConfiguration.OwnsOne(o => o.Address)`-Methode an, dass es sich bei der `Address`-Eigenschaft um eine eigene Entität vom Typ `Order` handelt.

Standardmäßig benennen die EF Core-Konventionen die Datenbankspalten für die Eigenschaften des eigenen Entitätstyps mit `EntityProperty_OwnedEntityProperty`. Aus diesem Grund werden die internen Eigenschaften von `Address` in der Tabelle `Orders` mit den Namen `Address_Street` und `Address_City` (usw. für `State`, `Country` und `ZipCode`) angezeigt.

Sie können die Fluentmethode `Property().HasColumnName()` anfügen, um diese Spalten umzubenennen. Wenn `Address` eine öffentliche Eigenschaft ist, sehen die Zuordnungen in etwa wie folgt aus:

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

Sie können die `OwnsOne`-Methode auch in eine Fluentzuordnung ketten. Im folgenden hypothetischen Beispiel besitzt `OrderDetails``BillingAddress` und `ShippingAddress`, wobei es sich um `Address`-Typen handelt. Dann besitzt der `Order`-Typ `OrderDetails`.

```csharp
orderConfiguration.OwnsOne(p => p.OrderDetails, cb =>
    {
        cb.OwnsOne(c => c.BillingAddress);
        cb.OwnsOne(c => c.ShippingAddress);
    });
//...
//...
public class Order
{
    public int Id { get; set; }
    public OrderDetails OrderDetails { get; set; }
}

public class OrderDetails
{
    public Address BillingAddress { get; set; }
    public Address ShippingAddress { get; set; }
}

public class Address
{
    public string Street { get; set; }
    public string City { get; set; }
}
```

### <a name="additional-details-on-owned-entity-types"></a>Zusätzliche Details zu eigenen Entitätstypen

- Eigene Typen werden definiert, wenn Sie eine Navigationseigenschaft für einen Typ mit der OwnsOne-Fluent-API konfigurieren.

- Die Definition eines eigenen Typs im Metadatenmodell ist eine Zusammensetzung aus den folgenden Bestandteilen: Besitzertyp, Navigationseigenschaft und CLR-Typ des eigenen Typs.

- Die Identität (der Schlüssel) einer eigenen Typinstanz in diesem Beispiel ist eine Zusammensetzung aus der Identität des Besitzertyps und der Definition des eigenen Typs.

#### <a name="owned-entities-capabilities"></a>Funktionen nicht eigenständiger Entitätstypen

- Eigene Typen können auf andere Entitäten verweisen, die entweder eigen (geschachtelte eigene Typen) oder nicht eigen (reguläre Navigationseigenschaften zum Verweis auf andere Entitäten) sind.

- Sie können über separate Navigationseigenschaften denselben CLR-Typ als andere eigene Typen in derselben Besitzerentität zuordnen.

- Die Tabellenaufteilung wird standardmäßig eingerichtet. Sie können diese Funktion aber auch deaktivieren, indem Sie den eigenen Typ mit ToTable einer anderen Tabelle zuordnen.

- Für nicht eigenständige Entitätstypen erfolgt automatisch Eager Loading (vorzeitiges Laden). Es besteht also keine Notwendigkeit, `.Include()` in der Abfrage aufzurufen.

- Kann ab EF Core 2.1 mit dem Attribut `[Owned]` konfiguriert werden.

- Kann Sammlungen nicht eigenständiger Entitätstypen verarbeiten (ab Version 2.2).

#### <a name="owned-entities-limitations"></a>Einschränkungen nicht eigenständiger Entitätstypen

- Sie können (gezielt) kein `DbSet<T>` eines nicht eigenständigen Entitätstyps erstellen.

- Sie können für nicht eigenständige Entitätstypen (derzeit gezielt) `ModelBuilder.Entity<T>()` nicht aufrufen.

- Optionale (d. h. Nullwerte zulassende) nicht eigenständige Entitätstypen, die (über Tabellenaufteilung) dem Besitzer in derselben Tabelle zugeordnet sind, werden nicht unterstützt. Der Grund hierfür ist, dass die Zuordnung für jede Eigenschaft durchgeführt wird, weshalb es keinen separaten Sentinel für den komplexen NULL-Wert gibt.

- Die Vererbungszuordnung für eigene Typen wird nicht unterstützt, aber Sie sollten zwei Blatttypen derselben Schnittstellenvererbungshierarchie als unterschiedliche eigene Typen zuordnen können. EF Core hat keine Probleme mit der Verarbeitung, weil diese Typen Teil derselben Hierarchie sind.

#### <a name="main-differences-with-ef6s-complex-types"></a>Wichtige Unterschiede zwischen den komplexen Typen für EF 6

- Die Tabellenaufteilung ist optional, d. h., diese Typen können einer anderen Tabelle zugeordnet werden und bleiben trotzdem nicht eigenständige Typen.

- Sie können auf andere Entitäten verweisen, d. h., sie können als die abhängige Seite in Beziehungen zu anderen eigenständigen Typen fungieren.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Martin Fowler. ValueObject pattern (ValueObject-Muster)**  \
  <https://martinfowler.com/bliki/ValueObject.html>

- **Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software. (Domänengesteuertes Design (DDD): Umgang mit Komplexität im Kern einer Software.)** (Buch, das Erläuterungen zu Wertobjekten enthält) \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- **Vaughn Vernon. Implementing Domain-Driven Design (Implementieren des domänengesteuerten Designs.)** (Buch, das Erläuterungen zu Wertobjekten enthält) \
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- **Nicht eigenständige Entitätstypen** \
  <https://docs.microsoft.com/ef/core/modeling/owned-entities>

- **Shadow Properties (Schatteneigenschaften)**  \
  <https://docs.microsoft.com/ef/core/modeling/shadow-properties>

- **Complex types and/or value objects (komplexe Typen und/oder Wertobjekte)** . Diskussion im GitHub-Repository zu EF Core (Registerkarte „Issues“) \
  <https://github.com/dotnet/efcore/issues/246>

- **ValueObject.cs.** Basisklasse der Wertobjekte in eShopOnContainers. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs>

- **Klasse „Address“** Beispielklasse der Wertobjekte in eShopOnContainers. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs>

> [!div class="step-by-step"]
> [Zurück](seedwork-domain-model-base-classes-interfaces.md)
> [Weiter](enumeration-classes-over-enum-types.md)
