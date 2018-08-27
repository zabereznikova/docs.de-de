---
title: Verwenden von Enumerationsklassen anstelle von Enumerationstypen
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Verwenden von Enumerationsklassen anstelle von Enumerationstypen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: f1b88d160d6532c2a768684b55cd236417699322
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933387"
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="9de25-103">Verwenden von Enumerationsklassen anstelle von Enumerationstypen</span><span class="sxs-lookup"><span data-stu-id="9de25-103">Using enumeration classes instead of enum types</span></span>

<span data-ttu-id="9de25-104">Bei [Enumerationen](../../../../docs/csharp/language-reference/keywords/enum.md) (bzw. *Enumerationstypen*) handelt es sich um dünne Sprachwrapper um einen integralen Typ.</span><span class="sxs-lookup"><span data-stu-id="9de25-104">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="9de25-105">Sie sollten deren Verwendung darauf beschränken, einen Wert aus einem vollständigen Wertesatz zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9de25-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="9de25-106">Klassifizierung anhand von Größen (klein, mittel, groß) ist ein gutes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="9de25-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="9de25-107">Das Verwenden von Enumerationen zur Ablaufsteuerung oder für robustere Abstraktionen kann zu [schlecht strukturiertem Code](http://deviq.com/code-smells/) führen.</span><span class="sxs-lookup"><span data-stu-id="9de25-107">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="9de25-108">Diese Art der Verwendung führt zu instabilem Code mit vielen Anweisungen für die Ablaufsteuerung, die die Werte der Enumeration überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9de25-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="9de25-109">Sie können stattdessen Enumerationsklassen erstellen, um die umfassenden Features von objektorientierten Sprachen nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="9de25-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="9de25-110">Dabei handelt es sich jedoch nicht um ein kritisches Thema und in vielen Fällen können Sie aus Gründen der Einfachheit dennoch reguläre [Enumerationstypen](../../../../docs/csharp/language-reference/keywords/enum.md) verwenden, wenn Sie diese bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="9de25-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../../docs/csharp/language-reference/keywords/enum.md) if that's your preference.</span></span>

## <a name="implementing-an-enumeration-base-class"></a><span data-ttu-id="9de25-111">Implementieren einer Basisklasse für Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9de25-111">Implementing an Enumeration base class</span></span>

<span data-ttu-id="9de25-112">Der Microservice für Bestellungen in eShopOnContainers stellt wie im Folgenden dargestellt ein Beispiel für die Implementierung einer Basisklasse für Enumerationen bereit:</span><span class="sxs-lookup"><span data-stu-id="9de25-112">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; }
    public int Id { get; }

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
    
    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public | BindingFlags.Static | BindingFlags.DeclaredOnly);

        return fields.Select(f => f.GetValue(null)).Cast<T>();
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

<span data-ttu-id="9de25-113">Sie können diese Klasse als Typ in einem beliebigen Entitäts- oder Wertobjekt verwenden, z.B. für die folgende Enumerationsklasse „CardType“:</span><span class="sxs-lookup"><span data-stu-id="9de25-113">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class:</span></span>

```csharp
public abstract class CardType : Enumeration
{
    public static CardType Amex = new AmexCardType();
    public static CardType Visa = new VisaCardType();
    public static CardType MasterCard = new MasterCardType();

    protected CardType(int id, string name)
        : base(id, name)
    {
    }

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

## <a name="additional-resources"></a><span data-ttu-id="9de25-114">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9de25-114">Additional resources</span></span>

-   <span data-ttu-id="9de25-115">**Enum’s are evil—update (Warum Sie auf Enumerationen verzichten sollten (aktualisierte Version))**
    [*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="9de25-115">**Enum’s are evil—update**
[*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="9de25-116">**Daniel Hardman. How Enums Spread Disease – And How To Cure It (Warum Enumerationen für Probleme sorgen und wie Sie diese vermeiden)**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="9de25-116">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="9de25-117">**Jimmy Bogard. Enumeration classes (Enumerationsklassen)**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="9de25-117">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="9de25-118">**Steve Smith. Enum Alternatives in C# (Alternativen zu Enumerationen in C#)**
    [*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="9de25-118">**Steve Smith. Enum Alternatives in C#**
[*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="9de25-119">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="9de25-119">**Enumeration.cs.**</span></span> <span data-ttu-id="9de25-120">Base Enumeration class in eShopOnContainers (Die Basisklasse „Enumeration“ in eShopOnContainers)[*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="9de25-120">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="9de25-121">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="9de25-121">**CardType.cs**.</span></span> <span data-ttu-id="9de25-122">Beispielklasse für Enumerationen in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="9de25-122">Sample Enumeration class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="9de25-123">[Zurück](implement-value-objects.md)
[Weiter](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="9de25-123">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
