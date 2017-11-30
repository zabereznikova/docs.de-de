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
# <a name="implementing-value-objects"></a><span data-ttu-id="6becc-104">Implementieren des Value-Objekte</span><span class="sxs-lookup"><span data-stu-id="6becc-104">Implementing value objects</span></span>

<span data-ttu-id="6becc-105">Wie in früheren Abschnitten zu Entitäten und Aggregate erläutert wird, ist die Identität grundlegende für Entitäten.</span><span class="sxs-lookup"><span data-stu-id="6becc-105">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="6becc-106">Es gibt jedoch viele Objekte und Daten in einem System, die nicht mit einer Identität und Identität nachverfolgen, wie z. B. Wert Objekte erfordern.</span><span class="sxs-lookup"><span data-stu-id="6becc-106">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="6becc-107">Ein Wertobjekt kann mit anderen Entitäten verweisen.</span><span class="sxs-lookup"><span data-stu-id="6becc-107">A value object can reference other entities.</span></span> <span data-ttu-id="6becc-108">Beispielsweise ist in einer Anwendung, die eine Route generiert, die zum Abrufen von einem Punkt in eine andere beschreibt diese Route wäre ein Wertobjekt.</span><span class="sxs-lookup"><span data-stu-id="6becc-108">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="6becc-109">Wäre es, eine Momentaufnahme von Punkten auf einer bestimmten Route, aber diese vorgeschlagene Route müsste eine Identität nicht intern diese Entitäten wie Ort, Straße usw. beziehen sich zwar möglicherweise.</span><span class="sxs-lookup"><span data-stu-id="6becc-109">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="6becc-110">Abbildung 9 bis 13 zeigt die Adresse-Wertobjekt in der Order-Aggregat.</span><span class="sxs-lookup"><span data-stu-id="6becc-110">Figure 9-13 shows the Address value object within the Order aggregate.</span></span>

![](./media/image14.png)

<span data-ttu-id="6becc-111">**Abbildung 9 bis 13**.</span><span class="sxs-lookup"><span data-stu-id="6becc-111">**Figure 9-13**.</span></span> <span data-ttu-id="6becc-112">Behandeln von Wertobjekt in der Order-Aggregat</span><span class="sxs-lookup"><span data-stu-id="6becc-112">Address value object within the Order aggregate</span></span>

<span data-ttu-id="6becc-113">Wie in Abbildung 9 bis 13 gezeigt, besteht eine Entität in der Regel mehrere Attribute.</span><span class="sxs-lookup"><span data-stu-id="6becc-113">As shown in Figure 9-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="6becc-114">Reihenfolge kann z. B. als eine Entität mit einer Identität modelliert und intern besteht aus einem Satz von Attributen wie OrderId, OrderDate, OrderItems. Aber die Adresse, also einfach einen komplexen Wert besteht aus Land, Straße, Stadt, usw. modelliert und als ein Wertobjekt behandelt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6becc-114">For example, Order can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex value composed of country, street, city, etc. must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="6becc-115">Wichtige Merkmale der Value-Objekte</span><span class="sxs-lookup"><span data-stu-id="6becc-115">Important characteristics of value objects</span></span>

<span data-ttu-id="6becc-116">Es gibt zwei Hauptmerkmale für Wert Objekte:</span><span class="sxs-lookup"><span data-stu-id="6becc-116">There are two main characteristics for value objects:</span></span>

-   <span data-ttu-id="6becc-117">Sie verfügen über keine Identität.</span><span class="sxs-lookup"><span data-stu-id="6becc-117">They have no identity.</span></span>

-   <span data-ttu-id="6becc-118">Sie sind unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="6becc-118">They are immutable.</span></span>

<span data-ttu-id="6becc-119">Die erste Eigenschaft wurde bereits erläutert.</span><span class="sxs-lookup"><span data-stu-id="6becc-119">The first characteristic was already discussed.</span></span> <span data-ttu-id="6becc-120">Unveränderlichkeit ist eine wichtige Anforderung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="6becc-120">Immutability is an important requirement.</span></span> <span data-ttu-id="6becc-121">Die Werte der ein Wertobjekt müssen unveränderlich sein, nachdem das Objekt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6becc-121">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="6becc-122">Wenn das Objekt erstellt wird, deshalb müssen Sie die erforderlichen Werte bereitstellen, aber Sie müssen diese zu ändern, während der Lebensdauer des Objekts nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="6becc-122">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="6becc-123">Value-Objekte können Sie bestimmte Tricks für die Leistung aufgrund der Natur unveränderlichen stehen.</span><span class="sxs-lookup"><span data-stu-id="6becc-123">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="6becc-124">Dies gilt insbesondere in Systemen, wobei es möglicherweise Tausende von Wert Objektinstanzen, von denen viele dieselben Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6becc-124">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="6becc-125">Unveränderliche Natur Speicherschemas wiederverwendet wird; Sie können die austauschbar Objekte sein, da ihre Werte identisch sind, und sie keine Identität haben.</span><span class="sxs-lookup"><span data-stu-id="6becc-125">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="6becc-126">Dieser Typ der Optimierung kann manchmal einen Unterschied zwischen der Software, die langsam ausgeführt wird und Software leistungsfähige vornehmen.</span><span class="sxs-lookup"><span data-stu-id="6becc-126">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="6becc-127">Natürlich hängen all diesen Fällen die Umgebung der Anwendung und der Bereitstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6becc-127">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="6becc-128">Wert-Objekt-Implementierung in C\#</span><span class="sxs-lookup"><span data-stu-id="6becc-128">Value object implementation in C\#</span></span>

<span data-ttu-id="6becc-129">Im Hinblick auf die Implementierung haben Sie eine Basisklasse für die Wert-Objekt, die grundlegende Utility-Methoden wie Gleichheit auf Grundlage der Vergleich zwischen allen Attributen, die (seit Start ein Wertobjekt auf Identität nicht basieren muss) und andere grundlegenden Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="6becc-129">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="6becc-130">Das folgende Beispiel zeigt eine Objekt-Basisklasse Wert in der Reihenfolge Microservice aus eShopOnContainers verwendet.</span><span class="sxs-lookup"><span data-stu-id="6becc-130">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

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

<span data-ttu-id="6becc-131">Diese Klasse können Sie beim Implementieren des Istwert-Objekts, wie mit der Adresse Wertobjekt im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6becc-131">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

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

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a><span data-ttu-id="6becc-132">Die Identity-Eigenschaft ausblenden, wenn EF Core zum Wert Objekte beibehalten</span><span class="sxs-lookup"><span data-stu-id="6becc-132">Hiding the identity characteristic when using EF Core to persist value objects</span></span>

<span data-ttu-id="6becc-133">Eine Beschränkung bei der Verwendung von EF Core ist in der aktuellen Version (EF Core 1.1) Sie können daher nicht [komplexe Typen](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) gemäß Definition in EF 6.x.</span><span class="sxs-lookup"><span data-stu-id="6becc-133">A limitation when using EF Core is that in its current version (EF Core 1.1) you cannot use [complex types](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) as defined in EF 6.x.</span></span> <span data-ttu-id="6becc-134">Aus diesem Grund müssen Sie Ihre Wertobjekt als EF Entität speichern.</span><span class="sxs-lookup"><span data-stu-id="6becc-134">Therefore, you must store your value object as an EF entity.</span></span> <span data-ttu-id="6becc-135">Allerdings können Sie seine ID ausblenden, damit Sie sicherstellen, dass die Identität nicht im Modell wichtig ist, die das Wertobjekt gehört.</span><span class="sxs-lookup"><span data-stu-id="6becc-135">However, you can hide its ID so you make clear that the identity is not important in the model that the value object is part of.</span></span> <span data-ttu-id="6becc-136">Sie ausblenden, die ID ist, indem Sie die ID als ein Schatten-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6becc-136">You hide the ID is by using the ID as a shadow property.</span></span> <span data-ttu-id="6becc-137">Da in der Infrastrukturebene, die die Konfiguration für die ID im Modell ausblenden festgelegt ist, werden transparent für Ihr Domänenmodell, und ihre Implementierung der Infrastruktur konnte in der Zukunft ändern.</span><span class="sxs-lookup"><span data-stu-id="6becc-137">Since that configuration for hiding the ID in the model is set up in the infrastructure level, it will be transparent for your domain model, and its infrastructure implementation could change in the future.</span></span>

<span data-ttu-id="6becc-138">In eShopOnContainers wird die ausgeblendete ID von EF Kerninfrastruktur benötigt auf folgende Weise in der DbContext-Ebene mithilfe der Fluent-API am Infrastructure-Projekt implementiert.</span><span class="sxs-lookup"><span data-stu-id="6becc-138">In eShopOnContainers, the hidden ID needed by EF Core infrastructure is implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span>

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

<span data-ttu-id="6becc-139">Aus diesem Grund wird die ID aus der Domäne Modell der Sicht ausgeblendet, und in Zukunft die Wert-Objekt-Infrastruktur auch als ein komplexer Typ oder eine andere Weise implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6becc-139">Therefore, the ID is hidden from the domain model point of view, and in the future, the value object infrastructure could also be implemented as a complex type or another way.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6becc-140">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6becc-140">Additional resources</span></span>

-   <span data-ttu-id="6becc-141">**Martin Fowler. ValueObject Muster**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span><span class="sxs-lookup"><span data-stu-id="6becc-141">**Martin Fowler. ValueObject pattern**
[*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span></span>

-   <span data-ttu-id="6becc-142">**Eric Evans. Domain Driven Design: Tackling, Complexity in the Heart of Software wird.**</span><span class="sxs-lookup"><span data-stu-id="6becc-142">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="6becc-143">(Book; enthält eine Erläuterung der Value-Objekte) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="6becc-143">(Book; includes a discussion of value objects) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="6becc-144">**Vaughn Vernon. Implementieren Domain Driven Design.**</span><span class="sxs-lookup"><span data-stu-id="6becc-144">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="6becc-145">(Book; enthält eine Erläuterung der Value-Objekte) [ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="6becc-145">(Book; includes a discussion of value objects) [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="6becc-146">**Shadowing von Eigenschaften**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="6becc-146">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>

-   <span data-ttu-id="6becc-147">**Komplexe Typen und/oder rückgabewertobjekte**.</span><span class="sxs-lookup"><span data-stu-id="6becc-147">**Complex types and/or value objects**.</span></span> <span data-ttu-id="6becc-148">Erläuterung in der EF-Core-GitHub-Repository (Registerkarte "Probleme") [ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span><span class="sxs-lookup"><span data-stu-id="6becc-148">Discussion in the EF Core GitHub repo (Issues tab) [*https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span></span>

-   <span data-ttu-id="6becc-149">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="6becc-149">**ValueObject.cs.**</span></span> <span data-ttu-id="6becc-150">Basiswert-Objektklasse im eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="6becc-150">Base value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="6becc-151">*https://github.com/dotnet/eShopOnContainers/BLOB/Master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*</span><span class="sxs-lookup"><span data-stu-id="6becc-151">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   <span data-ttu-id="6becc-152">**Beheben Sie die Klasse.**</span><span class="sxs-lookup"><span data-stu-id="6becc-152">**Address class.**</span></span> <span data-ttu-id="6becc-153">Beispiel der Wert-Objektklasse im eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="6becc-153">Sample value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="6becc-154">*https://github.com/dotnet/eShopOnContainers/BLOB/Master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*</span><span class="sxs-lookup"><span data-stu-id="6becc-154">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
<span data-ttu-id="6becc-155">[Vorherigen] (Seedwork-domain-model-base-classes-interfaces.md) [weiter] (Enumeration-Klassen-Over-Enum-types.md)</span><span class="sxs-lookup"><span data-stu-id="6becc-155">[Previous] (seedwork-domain-model-base-classes-interfaces.md) [Next] (enumeration-classes-over-enum-types.md)</span></span>
