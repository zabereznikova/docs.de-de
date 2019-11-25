---
title: Implementieren von Wertobjekten
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Einführung in die Details und Optionen zum Implementieren von Wertobjekten mithilfe neuer Features von Entity Framework
ms.date: 10/08/2018
ms.openlocfilehash: 2608517c4006f5e8da1d31b2c337d8ddd3ddd542
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739874"
---
# <a name="implement-value-objects"></a><span data-ttu-id="23ab0-103">Implementieren von Wertobjekten</span><span class="sxs-lookup"><span data-stu-id="23ab0-103">Implement value objects</span></span>

<span data-ttu-id="23ab0-104">Wie bereits in den vorherigen Abschnitten zu den Themen „Entitäten“ und „Aggregate“ ist die Identität ein grundlegender Bestandteil von Entitäten.</span><span class="sxs-lookup"><span data-stu-id="23ab0-104">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="23ab0-105">Allerdings sind viele Objekte und Datenelemente in einem System enthalten, für die keine Identität oder Identitätsnachverfolgung erforderlich ist, z.B. Wertobjekte.</span><span class="sxs-lookup"><span data-stu-id="23ab0-105">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="23ab0-106">Ein Wertobjekt kann auf mehrere Entitäten verweisen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-106">A value object can reference other entities.</span></span> <span data-ttu-id="23ab0-107">Ein Wertobjekt ist z.B. eine Route, die in einer Anwendung generiert wird und beschreibt, wie man von einem Punkt zu einem anderen gelangt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-107">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="23ab0-108">Dabei handelt es sich dann um eine Momentaufnahme von verschiedenen Punkten auf einer bestimmten Route. Die vorgeschlagene Route verfügt aber über keine Identität, obwohl sie intern möglicherweise auf Entitäten wie „City“ oder „Road“ verweist.</span><span class="sxs-lookup"><span data-stu-id="23ab0-108">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="23ab0-109">In Abbildung 7-13 wird das Wertobjekt „Address“ im Aggregat „Order“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-109">Figure 7-13 shows the Address value object within the Order aggregate.</span></span>

![Diagramm, das das Wertobjekt „Address“ im Aggregat „Order“ zeigt.](./media/implement-value-objects/value-object-within-aggregate.png)

<span data-ttu-id="23ab0-111">**Abbildung 7-13**.</span><span class="sxs-lookup"><span data-stu-id="23ab0-111">**Figure 7-13**.</span></span> <span data-ttu-id="23ab0-112">Wertobjekt „Address“ im Aggregat „Order“</span><span class="sxs-lookup"><span data-stu-id="23ab0-112">Address value object within the Order aggregate</span></span>

<span data-ttu-id="23ab0-113">Wie in Abbildung 7-13 dargestellt besteht eine Entität in der Regel aus mehreren Attributen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-113">As shown in Figure 7-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="23ab0-114">Beispielsweise kann die `Order`-Entität als Entität mit einer Identität modelliert sein und intern aus mehreren Attributen wie OrderId, OrderDate oder OrderItems bestehen. Die Adresse, bei der es sich lediglich um einen komplexen Wert handelt, der aus Attributen wie Land/Region, Straße, Ort usw. besteht und in dieser Domäne nicht über eine Identität verfügt, muss hingegen als Wertobjekt modelliert und behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="23ab0-114">For example, the `Order` entity can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex-value composed of country/region, street, city, etc. and has no identity in this domain, must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="23ab0-115">Wichtige Merkmale von Wertobjekten</span><span class="sxs-lookup"><span data-stu-id="23ab0-115">Important characteristics of value objects</span></span>

<span data-ttu-id="23ab0-116">Die beiden wichtigsten Merkmale von Wertobjekten lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="23ab0-116">There are two main characteristics for value objects:</span></span>

- <span data-ttu-id="23ab0-117">Sie haben keine Identität.</span><span class="sxs-lookup"><span data-stu-id="23ab0-117">They have no identity.</span></span>

- <span data-ttu-id="23ab0-118">Sie sind unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="23ab0-118">They are immutable.</span></span>

<span data-ttu-id="23ab0-119">Das erste Merkmal wurde bereits erwähnt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-119">The first characteristic was already discussed.</span></span> <span data-ttu-id="23ab0-120">Die Unveränderlichkeit ist eine wichtige Anforderung.</span><span class="sxs-lookup"><span data-stu-id="23ab0-120">Immutability is an important requirement.</span></span> <span data-ttu-id="23ab0-121">Die Werte eines Wertobjekts müssen unveränderlich sein, nachdem ein Objekt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="23ab0-121">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="23ab0-122">Aus diesem Grund müssen Sie beim Erstellen des Objekts die erforderlichen Werte zur Verfügung stellen. Dabei müssen Sie festlegen, dass es sich im Laufe seiner Lebensdauer nicht verändern kann.</span><span class="sxs-lookup"><span data-stu-id="23ab0-122">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="23ab0-123">Mithilfe von Wertobjekten können Sie aufgrund ihrer Unveränderlichkeit bestimmte Tricks verwenden, die sich positiv auf die Leistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="23ab0-123">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="23ab0-124">Dies gilt insbesondere für Systeme, in denen tausende von Wertobjektinstanzen enthalten sind, von denen viele denselben Wert haben.</span><span class="sxs-lookup"><span data-stu-id="23ab0-124">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="23ab0-125">Aufgrund ihrer Unveränderlichkeit können sie wiederverwendet werden, und da sie dieselben Werte haben, jedoch nicht über eine Identität verfügen, können sie als austauschbare Objekt fungieren.</span><span class="sxs-lookup"><span data-stu-id="23ab0-125">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="23ab0-126">Diese Art von Optimierung macht häufig den Unterschied zwischen langsamer Software und Software mit hoher Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="23ab0-126">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="23ab0-127">Trotzdem sind all diese Beispiele abhängig von der Anwendungsumgebung und dem Entwicklungskontext.</span><span class="sxs-lookup"><span data-stu-id="23ab0-127">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="23ab0-128">Implementieren von Wertobjekten in C\#</span><span class="sxs-lookup"><span data-stu-id="23ab0-128">Value object implementation in C\#</span></span>

<span data-ttu-id="23ab0-129">Im Hinblick auf die Implementierung können Sie über eine Wertobjektbasisklasse mit grundlegenden Hilfsprogrammmethoden wie Gleichheit, die auf einem Vergleich aller Attribute basiert (da Wertobjekte nicht auf einer Identität basieren dürfen), und anderen grundlegenden Merkmalen verfügen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-129">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="23ab0-130">Im folgenden Beispiel wird eine Wertobjektbasisklasse angezeigt, die im eShopOnContainers-Microservice für Bestellungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="23ab0-130">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

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

<span data-ttu-id="23ab0-131">Sie können diese Klasse verwenden, wenn Sie das tatsächliche Wertobjekt implementieren. Dies ist z.B. im nachfolgenden Beispiel zum Wertobjekt „Address“der Fall:</span><span class="sxs-lookup"><span data-stu-id="23ab0-131">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

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

<span data-ttu-id="23ab0-132">Sie können sehen, wie diese Implementierung des Wertobjekts „Address“ über keine Identität verfügt, weshalb sie weder in der Address-Klasse noch in der ValueObject-Klasse über ein ID-Feld verfügt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-132">You can see how this value object implementation of Address has no identity and therefore, no ID field, neither at the Address class not even at the ValueObject class.</span></span>

<span data-ttu-id="23ab0-133">In einer Klasse über kein von Entity Framework verwendbares ID-Feld zu verfügen, war bis EF Core 2.0 nicht möglich. Dies ist für das Implementieren besserer Wertobjekte ohne ID ausgesprochen hilfreich.</span><span class="sxs-lookup"><span data-stu-id="23ab0-133">Having no ID field in a class to be used by Entity Framework was not possible until EF Core 2.0, which greatly helps to implement better value objects with no ID.</span></span> <span data-ttu-id="23ab0-134">Außerdem entspricht dies der Erklärung des nächsten Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="23ab0-134">That is precisely the explanation of the next section.</span></span>

<span data-ttu-id="23ab0-135">Man könnte behaupten, dass Wertobjekte schreibgeschützt sein sollten (d.h. schreibgeschützte Eigenschaften), da sie unveränderlich sind, und das ist tatsächlich so.</span><span class="sxs-lookup"><span data-stu-id="23ab0-135">It could be argued that value objects, being immutable, should be read-only (i.e. get-only properties), and that’s indeed true.</span></span> <span data-ttu-id="23ab0-136">Allerdings werden Wertobjekte in der Regel zum Durchlaufen von Warteschlangen serialisiert und deserialisiert. Wenn sie schreibgeschützt sind, kann das Deserialisierungsprogramm keine Werte zuweisen. Deshalb werden sie privat gelassen, damit sie in gewisser Weise schreibgeschützt sind, aber dennoch verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="23ab0-136">However, value objects are usually serialized and deserialized to go through message queues, and being read-only stops the deserializer from assigning values, so we just leave them as private set which is read-only enough to be practical.</span></span>

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20"></a><span data-ttu-id="23ab0-137">Beibehalten von Wertobjekten in der Datenbank mit EF Core 2.0</span><span class="sxs-lookup"><span data-stu-id="23ab0-137">How to persist value objects in the database with EF Core 2.0</span></span>

<span data-ttu-id="23ab0-138">Obenstehend wurde erläutert, wie Sie ein Wertobjekt in Ihrem Domänenmodell definieren.</span><span class="sxs-lookup"><span data-stu-id="23ab0-138">You just saw how to define a value object in your domain model.</span></span> <span data-ttu-id="23ab0-139">Nun soll erläutert werden, wie Sie dieses mithilfe von Entity Framework Core (EF Core) beibehalten, obwohl dieser Dienst in der Regel auf Entitäten mit Identitäten ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="23ab0-139">But, how can you actually persist it into the database through Entity Framework (EF) Core which usually targets entities with identity?</span></span>

### <a name="background-and-older-approaches-using-ef-core-11"></a><span data-ttu-id="23ab0-140">Hintergrund und ältere Ansätze zur Verwendung von EF Core 1.1</span><span class="sxs-lookup"><span data-stu-id="23ab0-140">Background and older approaches using EF Core 1.1</span></span>

<span data-ttu-id="23ab0-141">Hintergrundinformation: Mit EF Core 1.0 und 1.1 konnten Sie keine [komplexen Typen](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) verwenden, die in EF 6.x im herkömmlichen .NET Framework definiert sind.</span><span class="sxs-lookup"><span data-stu-id="23ab0-141">As background, a limitation when using EF Core 1.0 and 1.1 was that you could not use [complex types](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) as defined in EF 6.x in the traditional .NET Framework.</span></span> <span data-ttu-id="23ab0-142">Aus diesem Grund mussten Sie ein Wertobjekt als EF-Entität mit einem ID-Feld speichern, wenn Sie EF Core 1.0 oder 1.1 verwenden.</span><span class="sxs-lookup"><span data-stu-id="23ab0-142">Therefore, if using EF Core 1.0 or 1.1, you needed to store your value object as an EF entity with an ID field.</span></span> <span data-ttu-id="23ab0-143">Anschließend konnten Sie die ID ausblenden, um eine Ähnlichkeit zum Wertobjekt ohne Identität herzustellen, und um deutlich zu machen, dass die Identität eines Wertobjekts im Domänenmodell nicht von Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="23ab0-143">Then, so it looked more like a value object with no identity, you could hide its ID so you make clear that the identity of a value object is not important in the domain model.</span></span> <span data-ttu-id="23ab0-144">Die ID konnte ausgeblendet werden, indem sie als [Schatteneigenschaft](https://docs.microsoft.com/ef/core/modeling/shadow-properties ) verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="23ab0-144">You could hide that ID by using the ID as a [shadow property](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span></span> <span data-ttu-id="23ab0-145">Da diese Konfiguration zum Ausblenden der ID im Modell in der EF-Infrastruktur eingerichtet ist, würde Ihr Domänenmodell diese durchschauen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-145">Since that configuration for hiding the ID in the model is set up in the EF infrastructure level, it would be kind of transparent for your domain model.</span></span>

<span data-ttu-id="23ab0-146">In der ersten Version von eShopOnContainers (.NET Core 1.1) wurde die von der EF Core-Infrastruktur verlangte versteckte ID wie folgt auf DbContext-Ebene implementiert. Dafür wurde die Fluent-API im Infrastrukturprojekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="23ab0-146">In the initial version of eShopOnContainers (.NET Core 1.1), the hidden ID needed by EF Core infrastructure was implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span> <span data-ttu-id="23ab0-147">Daher wurde die ID für das Domänenmodell ausgeblendet, sie war aber weiterhin in der Infrastruktur vorhanden.</span><span class="sxs-lookup"><span data-stu-id="23ab0-147">Therefore, the ID was hidden from the domain model point of view, but still present in the infrastructure.</span></span>

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

<span data-ttu-id="23ab0-148">Die Persistenz dieses Wertobjekts in die Datenbank wurde wie eine reguläre Entität in einer anderen Tabelle durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-148">However, the persistence of that value object into the database was performed like a regular entity in a different table.</span></span>

<span data-ttu-id="23ab0-149">Mit EF Core 2.0. gibt es neue und bessere Möglichkeiten, Wertobjekte beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="23ab0-149">With EF Core 2.0, there are new and better ways to persist value objects.</span></span>

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20"></a><span data-ttu-id="23ab0-150">Beibehalten von Wertobjekten als eigene Entitätstypen in EF Core 2.0</span><span class="sxs-lookup"><span data-stu-id="23ab0-150">Persist value objects as owned entity types in EF Core 2.0</span></span>

<span data-ttu-id="23ab0-151">Auch wenn das kanonische Wertobjektmuster im domänengesteuerten Design und der eigene Entitätstyp in EF Core Nachteile haben, so stellen diese derzeit die beste Möglichkeit dar, Wertobjekte mit EF Core 2.0 beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="23ab0-151">Even with some gaps between the canonical value object pattern in DDD and the owned entity type in EF Core, it's currently the best way to persist value objects with EF Core 2.0.</span></span> <span data-ttu-id="23ab0-152">Einschränkungen werden am Ende dieses Abschnitts erläutert.</span><span class="sxs-lookup"><span data-stu-id="23ab0-152">You can see limitations at the end of this section.</span></span>

<span data-ttu-id="23ab0-153">Das eigene Entitätstypenfeature wurde schon mit Version 2.0 von EF Core hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-153">The owned entity type feature was added to EF Core since version 2.0.</span></span>

<span data-ttu-id="23ab0-154">Über einen eigenen Entitätstyp können Sie Typen zuordnen, für die keine Identität im Domänenmodell explizit definiert ist und die als Eigenschaften verwendet werden, also z.B. als ein Wertobjekt in einer Entität.</span><span class="sxs-lookup"><span data-stu-id="23ab0-154">An owned entity type allows you to map types that do not have their own identity explicitly defined in the domain model and are used as properties, such as a value object, within any of your entities.</span></span> <span data-ttu-id="23ab0-155">Ein eigener Entitätstyp verfügt über denselben CLR-Typ wie ein anderer Entitätstyp (d.h., es handelt sich lediglich um eine normale Klasse).</span><span class="sxs-lookup"><span data-stu-id="23ab0-155">An owned entity type shares the same CLR type with another entity type (that is, it’s just a regular class).</span></span> <span data-ttu-id="23ab0-156">Die Entität, die die definierende Navigation enthält, ist die besitzende Entität.</span><span class="sxs-lookup"><span data-stu-id="23ab0-156">The entity containing the defining navigation is the owner entity.</span></span> <span data-ttu-id="23ab0-157">Beim Abfragen des Besitzers werden standardmäßig eigene Typen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-157">When querying the owner, the owned types are included by default.</span></span>

<span data-ttu-id="23ab0-158">Auf den ersten Blick scheint es, als verfüge ein eigener Typ im Domänenmodell nicht über eine Identität.</span><span class="sxs-lookup"><span data-stu-id="23ab0-158">Just by looking at the domain model, an owned type looks like it doesn’t have any identity.</span></span> <span data-ttu-id="23ab0-159">Die Identität des eigenen Typs befindet sich allerdings im Hintergrund, und die Eigenschaft zur Besitzernavigation ist Teil dieser Identität.</span><span class="sxs-lookup"><span data-stu-id="23ab0-159">However, under the covers, owned types do have identity, but the owner navigation property is part of this identity.</span></span>

<span data-ttu-id="23ab0-160">Die Identität von Instanzen von eigenen Typen ist nicht ausschließlich auf diese beschränkt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-160">The identity of instances of owned types is not completely their own.</span></span> <span data-ttu-id="23ab0-161">Sie besteht aus drei Hauptkomponenten:</span><span class="sxs-lookup"><span data-stu-id="23ab0-161">It consists of three components:</span></span>

- <span data-ttu-id="23ab0-162">Der Identität des Besitzers</span><span class="sxs-lookup"><span data-stu-id="23ab0-162">The identity of the owner</span></span>

- <span data-ttu-id="23ab0-163">Der Navigationseigenschaft, die auf diese zeigt</span><span class="sxs-lookup"><span data-stu-id="23ab0-163">The navigation property pointing to them</span></span>

- <span data-ttu-id="23ab0-164">Einer unabhängigen Komponente, wenn es um Auflistungen von eigenen Typen geht (in EF Core 2.0 noch nicht unterstützt, wird aber ab Version 2.2 unterstützt).</span><span class="sxs-lookup"><span data-stu-id="23ab0-164">In the case of collections of owned types, an independent component (not yet supported in EF Core 2.0, coming up on 2.2).</span></span>

<span data-ttu-id="23ab0-165">Beispielsweise wird im Domänenmodell für die Bestellung in eShopOnContainers das Wertobjekt „Address“ als Teil der Entität „Order“ als eigener Entitätstyp in die besitzende Entität (also der Entität „Order“) implementiert.</span><span class="sxs-lookup"><span data-stu-id="23ab0-165">For example, in the Ordering domain model at eShopOnContainers, as part of the Order entity, the Address value object is implemented as an owned entity type within the owner entity, which is the Order entity.</span></span> <span data-ttu-id="23ab0-166">Bei „Address“ handelt es sich um einen Typ ohne Identitätseigenschaft, der im Domänenmodell definiert ist.</span><span class="sxs-lookup"><span data-stu-id="23ab0-166">Address is a type with no identity property defined in the domain model.</span></span> <span data-ttu-id="23ab0-167">Dieser Typ wird als Eigenschaft des Typs „Order“ verwendet, um die Lieferadresse für eine bestimmte Bestellung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="23ab0-167">It is used as a property of the Order type to specify the shipping address for a particular order.</span></span>

<span data-ttu-id="23ab0-168">Gemäß den Konventionen wird ein Schattenprimärschlüssel für den eigenen Typ erstellt und mithilfe der Tabellenaufteilung derselben Tabelle wie der Besitzer zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="23ab0-168">By convention, a shadow primary key is created for the owned type and it will be mapped to the same table as the owner by using table splitting.</span></span> <span data-ttu-id="23ab0-169">Dies ermöglicht die Verwendung von eigenen Typen, ähnlich wie bei den in EF 6 im herkömmlichen .NET Framework verwendeten komplexen Typen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-169">This allows to use owned types similarly to how complex types are used in EF6 in the traditional .NET Framework.</span></span>

<span data-ttu-id="23ab0-170">Sie sollten wissen, dass eigene Typen standardmäßig nie von EF Core ermittelt werden. D.h., Sie müssen sie explizit deklarieren.</span><span class="sxs-lookup"><span data-stu-id="23ab0-170">It is important to note that owned types are never discovered by convention in EF Core, so you have to declare them explicitly.</span></span>

<span data-ttu-id="23ab0-171">In eShopOnContainers in der Datei „OrderingContext.cs“ in der Methode „OnModelCreating()“ gibt es mehrere Infrastrukturkonfigurationen, die angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="23ab0-171">In eShopOnContainers, at the OrderingContext.cs, within the OnModelCreating() method, there are multiple infrastructure configuration being applied.</span></span> <span data-ttu-id="23ab0-172">Eine dieser Konfigurationen steht in Beziehung zur Entität „Order“.</span><span class="sxs-lookup"><span data-stu-id="23ab0-172">One of them is related to the Order entity.</span></span>

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

<span data-ttu-id="23ab0-173">Im folgenden Code ist die Persistenzinfrastruktur für die Entität „Order“ definiert:</span><span class="sxs-lookup"><span data-stu-id="23ab0-173">In the following code, the persistence infrastructure is defined for the Order entity:</span></span>

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

<span data-ttu-id="23ab0-174">Im obigen Code gibt die `orderConfiguration.OwnsOne(o => o.Address)`-Methode an, dass es sich bei der `Address`-Eigenschaft um eine eigene Entität vom Typ `Order` handelt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-174">In the previous code, the `orderConfiguration.OwnsOne(o => o.Address)` method specifies that the `Address` property is an owned entity of the `Order` type.</span></span>

<span data-ttu-id="23ab0-175">Standardmäßig benennen die EF Core-Konventionen die Datenbankspalten für die Eigenschaften des eigenen Entitätstyps mit `EntityProperty_OwnedEntityProperty`.</span><span class="sxs-lookup"><span data-stu-id="23ab0-175">By default, EF Core conventions name the database columns for the properties of the owned entity type as `EntityProperty_OwnedEntityProperty`.</span></span> <span data-ttu-id="23ab0-176">Aus diesem Grund werden die internen Eigenschaften von `Address` in der Tabelle `Orders` mit den Namen `Address_Street` oder `Address_City` (usw. für `State`,`Country` und `ZipCode`) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-176">Therefore, the internal properties of `Address` will appear in the `Orders` table with the names `Address_Street`, `Address_City` (and so on for `State`, `Country` and `ZipCode`).</span></span>

<span data-ttu-id="23ab0-177">Sie können die Fluentmethode `Property().HasColumnName()` anfügen, um diese Spalten umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-177">You can append the `Property().HasColumnName()` fluent method to rename those columns.</span></span> <span data-ttu-id="23ab0-178">Wenn `Address` eine öffentliche Eigenschaft ist, sehen die Zuordnungen in etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="23ab0-178">In the case where `Address` is a public property, the mappings would be like the following:</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

<span data-ttu-id="23ab0-179">Sie können die `OwnsOne`-Methode auch in eine Fluentzuordnung ketten.</span><span class="sxs-lookup"><span data-stu-id="23ab0-179">It is possible to chain the `OwnsOne` method in a fluent mapping.</span></span> <span data-ttu-id="23ab0-180">Im folgenden hypothetischen Beispiel besitzt `OrderDetails` `BillingAddress` und `ShippingAddress`, wobei es sich um `Address`-Typen handelt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-180">In the following hypothetical example, `OrderDetails` owns `BillingAddress` and `ShippingAddress`, which are both `Address` types.</span></span> <span data-ttu-id="23ab0-181">Dann besitzt der `Order`-Typ `OrderDetails`.</span><span class="sxs-lookup"><span data-stu-id="23ab0-181">Then `OrderDetails` is owned by the `Order` type.</span></span>

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

### <a name="additional-details-on-owned-entity-types"></a><span data-ttu-id="23ab0-182">Zusätzliche Details zu eigenen Entitätstypen</span><span class="sxs-lookup"><span data-stu-id="23ab0-182">Additional details on owned entity types</span></span>

- <span data-ttu-id="23ab0-183">Eigene Typen werden definiert, wenn Sie eine Navigationseigenschaft für einen Typ mit der OwnsOne-Fluent-API konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="23ab0-183">Owned types are defined when you configure a navigation property to a particular type using the OwnsOne fluent API.</span></span>

- <span data-ttu-id="23ab0-184">Die Definition eines eigenen Typs im Metadatenmodell ist eine Zusammensetzung aus den folgenden Bestandteilen: Besitzertyp, Navigationseigenschaft und CLR-Typ des eigenen Typs.</span><span class="sxs-lookup"><span data-stu-id="23ab0-184">The definition of an owned type in our metadata model is a composite of: the owner type, the navigation property, and the CLR type of the owned type.</span></span>

- <span data-ttu-id="23ab0-185">Die Identität (der Schlüssel) einer eigenen Typinstanz in diesem Beispiel ist eine Zusammensetzung aus der Identität des Besitzertyps und der Definition des eigenen Typs.</span><span class="sxs-lookup"><span data-stu-id="23ab0-185">The identity (key) of an owned type instance in our stack is a composite of the identity of the owner type and the definition of the owned type.</span></span>

#### <a name="owned-entities-capabilities"></a><span data-ttu-id="23ab0-186">Funktionen der eigenen Entitäten:</span><span class="sxs-lookup"><span data-stu-id="23ab0-186">Owned entities capabilities:</span></span>

- <span data-ttu-id="23ab0-187">Eigene Typen können auf andere Entitäten verweisen, die entweder eigen (geschachtelte eigene Typen) oder nicht eigen (reguläre Navigationseigenschaften zum Verweis auf andere Entitäten) sind.</span><span class="sxs-lookup"><span data-stu-id="23ab0-187">Owned types can reference other entities, either owned (nested owned types) or non-owned (regular reference navigation properties to other entities).</span></span>

- <span data-ttu-id="23ab0-188">Sie können über separate Navigationseigenschaften denselben CLR-Typ als andere eigene Typen in derselben Besitzerentität zuordnen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-188">You can map the same CLR type as different owned types in the same owner entity through separate navigation properties.</span></span>

- <span data-ttu-id="23ab0-189">Die Tabellenaufteilung wird standardmäßig eingerichtet. Sie können diese Funktion aber auch deaktivieren, indem Sie den eigenen Typ mit ToTable einer anderen Tabelle zuordnen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-189">Table splitting is setup by convention, but you can opt out by mapping the owned type to a different table using ToTable.</span></span>

- <span data-ttu-id="23ab0-190">Für eigene Typen wird automatisch Eager Loading (eifriges Laden) durchgeführt. Es besteht also keine Notwendigkeit, „Include()“ in der Abfrage aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-190">Eager loading is performed automatically on owned types, i.e. no need to call Include() on the query.</span></span>

- <span data-ttu-id="23ab0-191">Kann ab EF Core 2.1 mit dem Attribut \[Owned\] konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="23ab0-191">Can be configured with attribute \[Owned\], as of EF Core 2.1</span></span>

#### <a name="owned-entities-limitations"></a><span data-ttu-id="23ab0-192">Einschränkungen der eigenen Entitäten:</span><span class="sxs-lookup"><span data-stu-id="23ab0-192">Owned entities limitations:</span></span>

- <span data-ttu-id="23ab0-193">Sie können kein DbSet\<T\>-Objekt eines eigenen Typs erstellen (entwurfsbedingt).</span><span class="sxs-lookup"><span data-stu-id="23ab0-193">You cannot create a DbSet\<T\> of an owned type (by design).</span></span>

- <span data-ttu-id="23ab0-194">Sie können für eigene Typen „ModelBuilder.Entity\<T\>()“ nicht aufrufen (derzeit entwurfsbedingt).</span><span class="sxs-lookup"><span data-stu-id="23ab0-194">You cannot call ModelBuilder.Entity\<T\>() on owned types (currently by design).</span></span>

- <span data-ttu-id="23ab0-195">Es gibt noch keine Sammlungen von eigenen Typen (Stand: EF Core 2.1, aber sie werden ab Version 2.2 unterstützt).</span><span class="sxs-lookup"><span data-stu-id="23ab0-195">No collections of owned types yet (as of EF Core 2.1, but they will be supported in 2.2).</span></span>

- <span data-ttu-id="23ab0-196">Optionale eigene Typen (d.h. Nullable-Typen), die (über Tabellenaufteilung) dem Besitzer in derselben Tabelle zugeordnet sind, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-196">No support for optional (that is, nullable) owned types that are mapped with the owner in the same table (i.e. using table splitting).</span></span> <span data-ttu-id="23ab0-197">Der Grund hierfür ist, dass die Zuordnung für jede Eigenschaft durchgeführt wird, weshalb es keinen separaten Sentinel für den komplexen NULL-Wert gibt.</span><span class="sxs-lookup"><span data-stu-id="23ab0-197">This is because mapping is done for each property, we don't have a separate sentinel for the null complex value a as whole.</span></span>

- <span data-ttu-id="23ab0-198">Die Vererbungszuordnung für eigene Typen wird nicht unterstützt, aber Sie sollten zwei Blatttypen derselben Schnittstellenvererbungshierarchie als unterschiedliche eigene Typen zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="23ab0-198">No inheritance mapping support for owned types, but you should be able to map two leaf types of the same inheritance hierarchies as different owned types.</span></span> <span data-ttu-id="23ab0-199">EF Core hat keine Probleme mit der Verarbeitung, weil diese Typen Teil derselben Hierarchie sind.</span><span class="sxs-lookup"><span data-stu-id="23ab0-199">EF Core will not reason about the fact that they are part of the same hierarchy.</span></span>

#### <a name="main-differences-with-ef6s-complex-types"></a><span data-ttu-id="23ab0-200">Wichtige Unterschiede zwischen den komplexen Typen für EF 6</span><span class="sxs-lookup"><span data-stu-id="23ab0-200">Main differences with EF6's complex types</span></span>

- <span data-ttu-id="23ab0-201">Die Tabellenaufteilung ist optional, d.h., diese Typen können einer anderen Tabelle zugeordnet werden und verlieren trotzdem nicht Ihren Status als eigene Typen.</span><span class="sxs-lookup"><span data-stu-id="23ab0-201">Table splitting is optional, i.e. they can optionally be mapped to a separate table and still be owned types.</span></span>

- <span data-ttu-id="23ab0-202">Sie können auf andere Entitäten verweisen, d.h., sie können als Abhängigkeiten in Beziehungen zu anderen nicht eigenen Typen agieren.</span><span class="sxs-lookup"><span data-stu-id="23ab0-202">They can reference other entities (i.e. they can act as the dependent side on relationships to other non-owned types).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="23ab0-203">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="23ab0-203">Additional resources</span></span>

- <span data-ttu-id="23ab0-204">**Martin Fowler. ValueObject pattern (ValueObject-Muster)**  </span><span class="sxs-lookup"><span data-stu-id="23ab0-204">**Martin Fowler. ValueObject pattern** </span></span>\
  <https://martinfowler.com/bliki/ValueObject.html>

- <span data-ttu-id="23ab0-205">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software. (Domänengesteuertes Design (DDD): Umgang mit Komplexität im Kern einer Software.)**</span><span class="sxs-lookup"><span data-stu-id="23ab0-205">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="23ab0-206">(Buch, das Erläuterungen zu Wertobjekten enthält) </span><span class="sxs-lookup"><span data-stu-id="23ab0-206">(Book; includes a discussion of value objects) </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- <span data-ttu-id="23ab0-207">**Vaughn Vernon. Implementing Domain-Driven Design (Implementieren des domänengesteuerten Designs.)**</span><span class="sxs-lookup"><span data-stu-id="23ab0-207">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="23ab0-208">(Buch, das Erläuterungen zu Wertobjekten enthält) </span><span class="sxs-lookup"><span data-stu-id="23ab0-208">(Book; includes a discussion of value objects) </span></span>\
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- <span data-ttu-id="23ab0-209">**Shadow Properties (Schatteneigenschaften)**  </span><span class="sxs-lookup"><span data-stu-id="23ab0-209">**Shadow Properties** </span></span>\
  [https://docs.microsoft.com/ef/core/modeling/shadow-properties](/ef/core/modeling/shadow-properties)

- <span data-ttu-id="23ab0-210">**Complex types and/or value objects (komplexe Typen und/oder Wertobjekte)** .</span><span class="sxs-lookup"><span data-stu-id="23ab0-210">**Complex types and/or value objects**.</span></span> <span data-ttu-id="23ab0-211">Diskussion im GitHub-Repository zu EF Core (Registerkarte „Issues“) </span><span class="sxs-lookup"><span data-stu-id="23ab0-211">Discussion in the EF Core GitHub repo (Issues tab) </span></span>\
  <https://github.com/aspnet/EntityFramework/issues/246>

- <span data-ttu-id="23ab0-212">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="23ab0-212">**ValueObject.cs.**</span></span> <span data-ttu-id="23ab0-213">Basisklasse der Wertobjekte in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="23ab0-213">Base value object class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs>

- <span data-ttu-id="23ab0-214">**Klasse „Address“**</span><span class="sxs-lookup"><span data-stu-id="23ab0-214">**Address class.**</span></span> <span data-ttu-id="23ab0-215">Beispielklasse der Wertobjekte in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="23ab0-215">Sample value object class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs>

> [!div class="step-by-step"]
> <span data-ttu-id="23ab0-216">[Zurück](seedwork-domain-model-base-classes-interfaces.md)
> [Weiter](enumeration-classes-over-enum-types.md)</span><span class="sxs-lookup"><span data-stu-id="23ab0-216">[Previous](seedwork-domain-model-base-classes-interfaces.md)
[Next](enumeration-classes-over-enum-types.md)</span></span>
