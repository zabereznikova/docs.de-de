---
title: Enum-Typen anstelle Enumeration Klassen
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Enum-Typen anstelle Enumeration Klassen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1745198720fd12a9d26aab2d2afb2c5dd6b6b49d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="87ff6-104">Enum-Typen anstelle Enumeration Klassen</span><span class="sxs-lookup"><span data-stu-id="87ff6-104">Using Enumeration classes instead of enum types</span></span>

<span data-ttu-id="87ff6-105">[Enumerationen](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*Enumerationen* kurz) sind ein schlanke Language-Wrapper um einen ganzzahligen Typ.</span><span class="sxs-lookup"><span data-stu-id="87ff6-105">[Enumerations](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*enums* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="87ff6-106">Sie möchten möglicherweise verwenden Sie diese eingeschränkt werden, wenn Sie einen Wert aus einen vollständigen Satz von Werten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="87ff6-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="87ff6-107">Klassifizierung basierend auf Geschlecht (z. B. Männlich, Weiblich unbekannt) oder Größe (S, M, L, XL) sind gute Beispiele für.</span><span class="sxs-lookup"><span data-stu-id="87ff6-107">Classification based on gender (for example, male, female, unknown), or sizes (S, M, L, XL) are good examples.</span></span> <span data-ttu-id="87ff6-108">Mithilfe von Enumerationen für ablaufsteuerung oder eine robustere Abstraktionen kann eine [code Geruch](http://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="87ff6-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="87ff6-109">Diese Art der Verwendung führt zu instabilen Code mit vielen Anweisungen für die ablaufsteuerung überprüfen die Werte der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="87ff6-109">This type of usage will lead to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="87ff6-110">Sie können stattdessen Enumeration Klassen erstellen, die die umfassenden Funktionen eine objektorientierte Sprache zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="87ff6-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span> <span data-ttu-id="87ff6-111">Allerdings wird dies ist nicht durch ein schwerwiegendes Problem, und in vielen Fällen aus Gründen der Einfachheit, noch können reguläre Enumerationen, die die Einstellung ist.</span><span class="sxs-lookup"><span data-stu-id="87ff6-111">However, this is not a critical issue and in many cases, for simplicity, you can still use regular enums if that is your preference.</span></span>

## <a name="implementing-enumeration-classes"></a><span data-ttu-id="87ff6-112">Klassenimplementierung-Enumeration</span><span class="sxs-lookup"><span data-stu-id="87ff6-112">Implementing Enumeration classes</span></span>

<span data-ttu-id="87ff6-113">Die Reihenfolge Microservice in eShopOnContainers bietet eine Beispiel-Enumeration basisklassenimplementierung, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="87ff6-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }
    public int Id { get; private set; }

    protected Enumeration()
    {
    }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString()
    {
        return Name;
    }

    public static IEnumerable<T> GetAll<T>() where T : Enumeration, new()
    {
        var type = typeof(T);
        var fields = type.GetTypeInfo().GetFields(BindingFlags.Public |
            BindingFlags.Static |
            BindingFlags.DeclaredOnly);
        foreach (var info in fields)
        {
            var instance = new T();
            var locatedValue = info.GetValue(instance) as T;
            if (locatedValue != null)
            {
                yield return locatedValue;
            }
        }
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;
        if (otherValue == null)
        {
            return false;
        }
        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);
        return typeMatches && valueMatches;
    }

    public int CompareTo(object other)
    {
        return Id.CompareTo(((Enumeration)other).Id);
    }

    // Other utility methods ...
}
```

<span data-ttu-id="87ff6-114">Sie können diese Klasse als eine Entität oder Wert-Objekt, für die folgenden CardType Enumerationsklasse-Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="87ff6-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class.</span></span>

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    protected CardType() { }

    public CardType(int id, string name)
        : base(id, name)
    {
    }


    public static IEnumerable<CardType> List()
    {
        return new[] { Amex, Visa, MasterCard };
    }
    // Other util methods
}
```

## <a name="additional-resources"></a><span data-ttu-id="87ff6-115">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="87ff6-115">Additional resources</span></span>

-   <span data-ttu-id="87ff6-116">**Enum gefährlich werden – aktualisieren**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="87ff6-116">**Enum’s are evil—update**
[*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="87ff6-117">**Daniel Hardman. Wie Enumerationen Krankheit verteilt, Und wie Sie es beheben**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="87ff6-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="87ff6-118">**Jimmy Bogard. Enumeration Klassen**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="87ff6-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="87ff6-119">**Steve Smith. Enum-alternativen in c#**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="87ff6-119">**Steve Smith. Enum Alternatives in C#**
[*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="87ff6-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="87ff6-120">**Enumeration.cs.**</span></span> <span data-ttu-id="87ff6-121">Basisklasse für Enumeration in eShopOnContainers [ *https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="87ff6-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="87ff6-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="87ff6-122">**CardType.cs**.</span></span> <span data-ttu-id="87ff6-123">Beispiel-Enumerationsklasse in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="87ff6-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [<span data-ttu-id="87ff6-124">*https://github.com/dotnet/eShopOnContainers/BLOB/Master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span><span class="sxs-lookup"><span data-stu-id="87ff6-124">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="87ff6-125">[Vorherigen] (implementieren-Wert-objects.md) [weiter] (Domäne-Modell-Ebene – validations.md)</span><span class="sxs-lookup"><span data-stu-id="87ff6-125">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
