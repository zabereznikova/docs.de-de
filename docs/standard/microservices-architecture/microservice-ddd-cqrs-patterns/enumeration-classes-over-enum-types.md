---
title: Verwenden von Enumerationsklassen anstelle von Enumerationstypen
description: .NET Microservicesarchitektur für Containerized .NET-Anwendungen | Nutzung von Enumerationsklassen anstelle von Enumerationen als Lösungsmöglichkeit für die Einschränkungen der Enumerationen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/08/2018
ms.openlocfilehash: 72a3e7ef8043e0016cefb45a4182b5c2e3061753
ms.sourcegitcommit: 3b9b7ae6771712337d40374d2fef6b25b0d53df6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54029709"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="a593a-103">Verwenden von Enumerationsklassen anstelle von Enumerationstypen</span><span class="sxs-lookup"><span data-stu-id="a593a-103">Use enumeration classes instead of enum types</span></span>

<span data-ttu-id="a593a-104">Bei [Enumerationen](../../../../docs/csharp/language-reference/keywords/enum.md) (bzw. *Enumerationstypen*) handelt es sich um dünne Sprachwrapper um einen integralen Typ.</span><span class="sxs-lookup"><span data-stu-id="a593a-104">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="a593a-105">Sie sollten deren Verwendung darauf beschränken, einen Wert aus einem vollständigen Wertesatz zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a593a-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="a593a-106">Klassifizierung anhand von Größen (klein, mittel, groß) ist ein gutes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a593a-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="a593a-107">Das Verwenden von Enumerationen zur Ablaufsteuerung oder für robustere Abstraktionen kann zu [schlecht strukturiertem Code](http://deviq.com/code-smells/) führen.</span><span class="sxs-lookup"><span data-stu-id="a593a-107">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="a593a-108">Diese Art der Verwendung führt zu instabilem Code mit vielen Anweisungen für die Ablaufsteuerung, die die Werte der Enumeration überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a593a-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="a593a-109">Sie können stattdessen Enumerationsklassen erstellen, um die umfassenden Features von objektorientierten Sprachen nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="a593a-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="a593a-110">Dabei handelt es sich jedoch nicht um ein kritisches Thema und in vielen Fällen können Sie aus Gründen der Einfachheit dennoch reguläre [Enumerationstypen](../../../csharp/language-reference/keywords/enum.md) verwenden, wenn Sie diese bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="a593a-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../csharp/language-reference/keywords/enum.md) if that's your preference.</span></span> <span data-ttu-id="a593a-111">Jedenfalls bezieht sich die Verwendung von Enumerationsklassen mehr auf geschäftliche Konzepte.</span><span class="sxs-lookup"><span data-stu-id="a593a-111">Anyway, the use of enumeration classes is more related to business-related concepts.</span></span>

## <a name="implement-an-enumeration-base-class"></a><span data-ttu-id="a593a-112">Implementieren einer Basisklasse für Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a593a-112">Implement an Enumeration base class</span></span>

<span data-ttu-id="a593a-113">Der Microservice für Bestellungen in eShopOnContainers stellt wie im Folgenden dargestellt ein Beispiel für die Implementierung einer Basisklasse für Enumerationen bereit:</span><span class="sxs-lookup"><span data-stu-id="a593a-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }

    public int Id { get; private set; }

    protected Enumeration()
    { }

    protected Enumeration(int id, string name) 
    {
        Id = id; 
        Name = name; 
    }

    public override string ToString() => Name;

    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public | 
                                         BindingFlags.Static | 
                                         BindingFlags.DeclaredOnly); 

        return fields.Select(f => f.GetValue(null)).Cast<T>();
    }

    public override bool Equals(object obj) 
    {
        var otherValue = obj as Enumeration; 

        if (otherValue == null) 
            return false;

        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);

        return typeMatches && valueMatches;
    }

    public int CompareTo(object other) => Id.CompareTo(((Enumeration)other).Id); 

    // Other utility methods ... 
}
```

<span data-ttu-id="a593a-114">Sie können diese Klasse als Typ in einem beliebigen Entitäts- oder Wertobjekt verwenden, z.B. für die folgende `CardType`:`Enumeration`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="a593a-114">You can use this class as a type in any entity or value object, as for the following `CardType` : `Enumeration` class:</span></span>

```csharp
public abstract class CardType : Enumeration
{
    public static CardType Amex = new AmexCardType();
    public static CardType Visa = new VisaCardType();
    public static CardType MasterCard = new MasterCardType();

    protected CardType(int id, string name)
        : base(id, name)
    { }

    private class AmexCardType : CardType
    {
        public AmexCardType(): base(1, "Amex")
        { }
    }
    
    private class VisaCardType : CardType
    {
        public VisaCardType(): base(2, "Visa")
        { }
    }
    
    private class MasterCardType : CardType
    {
        public MasterCardType(): base(3, "MasterCard")
        { }
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="a593a-115">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="a593a-115">Additional resources</span></span>

- <span data-ttu-id="a593a-116">**Enums are evil—Update (Warum Sie auf Enumerationen verzichten sollten (aktualisierte Version))** \\</span><span class="sxs-lookup"><span data-stu-id="a593a-116">**Enum’s are evil—update** \\</span></span>
  [*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)

- <span data-ttu-id="a593a-117">**Daniel Hardman. How Enums Spread Disease – And How To Cure It (Warum Enumerationen für Probleme sorgen und wie Sie diese vermeiden)** \\</span><span class="sxs-lookup"><span data-stu-id="a593a-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It** \\</span></span>
  [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)

- <span data-ttu-id="a593a-118">**Jimmy Bogard. Enumeration classes (Enumerationsklassen)** \\</span><span class="sxs-lookup"><span data-stu-id="a593a-118">**Jimmy Bogard. Enumeration classes** \\</span></span>
  [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)

- <span data-ttu-id="a593a-119">**Steve Smith. Enum Alternatives in C# (Alternativen zu Enumerationen in C#)** \\</span><span class="sxs-lookup"><span data-stu-id="a593a-119">**Steve Smith. Enum Alternatives in C#** \\</span></span>
  [*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)

- <span data-ttu-id="a593a-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="a593a-120">**Enumeration.cs.**</span></span> <span data-ttu-id="a593a-121">Base Enumeration class in eShopOnContainers (Die Basisklasse „Enumeration“ in eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="a593a-121">Base Enumeration class in eShopOnContainers \\</span></span>
  [*https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)

- <span data-ttu-id="a593a-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="a593a-122">**CardType.cs**.</span></span> <span data-ttu-id="a593a-123">Beispielklasse für Enumerationen in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="a593a-123">Sample Enumeration class in eShopOnContainers.</span></span> \
  [*https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)
    
- <span data-ttu-id="a593a-124">**SmartEnum**.</span><span class="sxs-lookup"><span data-stu-id="a593a-124">**SmartEnum**.</span></span> <span data-ttu-id="a593a-125">Ardalis: Klassen zum Erzeugen von stark typisierten intelligenteren Enumerationen in .NET</span><span class="sxs-lookup"><span data-stu-id="a593a-125">Ardalis - Classes to help produce strongly typed smarter enums in .NET.</span></span> \
  [*https://www.nuget.org/packages/Ardalis.SmartEnum/*](https://www.nuget.org/packages/Ardalis.SmartEnum/)

>[!div class="step-by-step"]
><span data-ttu-id="a593a-126">[Zurück](implement-value-objects.md)
>[Weiter](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="a593a-126">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>