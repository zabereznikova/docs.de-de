---
title: Implementieren des Value-Objekte
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren des Value-Objekte"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c20bc80d2ddb864a3a0172beb211974426a278a8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-value-objects"></a>Implementieren des Value-Objekte

Wie in früheren Abschnitten zu Entitäten und Aggregate erläutert wird, ist die Identität grundlegende für Entitäten. Es gibt jedoch viele Objekte und Daten in einem System, die nicht mit einer Identität und Identität nachverfolgen, wie z. B. Wert Objekte erfordern.

Ein Wertobjekt kann mit anderen Entitäten verweisen. Beispielsweise ist in einer Anwendung, die eine Route generiert, die zum Abrufen von einem Punkt in eine andere beschreibt diese Route wäre ein Wertobjekt. Wäre es, eine Momentaufnahme von Punkten auf einer bestimmten Route, aber diese vorgeschlagene Route müsste eine Identität nicht intern diese Entitäten wie Ort, Straße usw. beziehen sich zwar möglicherweise.

Abbildung 9 bis 13 zeigt die Adresse-Wertobjekt in der Order-Aggregat.

![](./media/image14.png)

**Abbildung 9 bis 13**. Behandeln von Wertobjekt in der Order-Aggregat

Wie in Abbildung 9 bis 13 gezeigt, besteht eine Entität in der Regel mehrere Attribute. Reihenfolge kann z. B. als eine Entität mit einer Identität modelliert und intern besteht aus einem Satz von Attributen wie OrderId, OrderDate, OrderItems. Aber die Adresse, also einfach einen komplexen Wert besteht aus Land, Straße, Stadt, usw. modelliert und als ein Wertobjekt behandelt werden müssen.

## <a name="important-characteristics-of-value-objects"></a>Wichtige Merkmale der Value-Objekte

Es gibt zwei Hauptmerkmale für Wert Objekte:

-   Sie verfügen über keine Identität.

-   Sie sind unveränderlich.

Die erste Eigenschaft wurde bereits erläutert. Unveränderlichkeit ist eine wichtige Anforderung erfüllt. Die Werte der ein Wertobjekt müssen unveränderlich sein, nachdem das Objekt erstellt wurde. Wenn das Objekt erstellt wird, deshalb müssen Sie die erforderlichen Werte bereitstellen, aber Sie müssen diese zu ändern, während der Lebensdauer des Objekts nicht zulassen.

Value-Objekte können Sie bestimmte Tricks für die Leistung aufgrund der Natur unveränderlichen stehen. Dies gilt insbesondere in Systemen, wobei es möglicherweise Tausende von Wert Objektinstanzen, von denen viele dieselben Werte aufweisen. Unveränderliche Natur Speicherschemas wiederverwendet wird; Sie können die austauschbar Objekte sein, da ihre Werte identisch sind, und sie keine Identität haben. Dieser Typ der Optimierung kann manchmal einen Unterschied zwischen der Software, die langsam ausgeführt wird und Software leistungsfähige vornehmen. Natürlich hängen all diesen Fällen die Umgebung der Anwendung und der Bereitstellung verwendet.

## <a name="value-object-implementation-in-c"></a>Wert-Objekt-Implementierung in C\#

Im Hinblick auf die Implementierung haben Sie eine Basisklasse für die Wert-Objekt, die grundlegende Utility-Methoden wie Gleichheit auf Grundlage der Vergleich zwischen allen Attributen, die (seit Start ein Wertobjekt auf Identität nicht basieren muss) und andere grundlegenden Eigenschaften verfügt. Das folgende Beispiel zeigt eine Objekt-Basisklasse Wert in der Reihenfolge Microservice aus eShopOnContainers verwendet.

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
    // Other utilility methods
}
```

Diese Klasse können Sie beim Implementieren des Istwert-Objekts, wie mit der Adresse Wertobjekt im folgenden Beispiel gezeigt:

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    public Address(string street, string city, string state,
        string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a>Die Identity-Eigenschaft ausblenden, wenn EF Core zum Wert Objekte beibehalten

Eine Beschränkung bei der Verwendung von EF Core ist in der aktuellen Version (EF Core 1.1) Sie können daher nicht [komplexe Typen](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) gemäß Definition in EF 6.x. Aus diesem Grund müssen Sie Ihre Wertobjekt als EF Entität speichern. Allerdings können Sie seine ID ausblenden, damit Sie sicherstellen, dass die Identität nicht im Modell wichtig ist, die das Wertobjekt gehört. Sie ausblenden, die ID ist, indem Sie die ID als ein Schatten-Eigenschaft. Da in der Infrastrukturebene, die die Konfiguration für die ID im Modell ausblenden festgelegt ist, werden transparent für Ihr Domänenmodell, und ihre Implementierung der Infrastruktur konnte in der Zukunft ändern.

In eShopOnContainers wird die ausgeblendete ID von EF Kerninfrastruktur benötigt auf folgende Weise in der DbContext-Ebene mithilfe der Fluent-API am Infrastructure-Projekt implementiert.

```csharp
// Fluent API within the OrderingContext:DbContext in the
// Ordering.Infrastructure project

void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

Aus diesem Grund wird die ID aus der Domäne Modell der Sicht ausgeblendet, und in Zukunft die Wert-Objekt-Infrastruktur auch als ein komplexer Typ oder eine andere Weise implementiert werden kann.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Martin Fowler. ValueObject Muster**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **Eric Evans. Domain Driven Design: Tackling, Complexity in the Heart of Software wird.** (Book; enthält eine Erläuterung der Value-Objekte) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

-   **Vaughn Vernon. Implementieren Domain Driven Design.** (Book; enthält eine Erläuterung der Value-Objekte) [ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)

-   **Shadowing von Eigenschaften**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)

-   **Komplexe Typen und/oder rückgabewertobjekte**. Erläuterung in der EF-Core-GitHub-Repository (Registerkarte "Probleme") [ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)

-   **ValueObject.cs.** Basiswert-Objektklasse im eShopOnContainers.
    [*https://github.com/dotnet/eShopOnContainers/BLOB/Master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   **Beheben Sie die Klasse.** Beispiel der Wert-Objektklasse im eShopOnContainers.
    [*https://github.com/dotnet/eShopOnContainers/BLOB/Master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
[Vorherigen] (Seedwork-domain-model-base-classes-interfaces.md) [weiter] (Enumeration-Klassen-Over-Enum-types.md)
