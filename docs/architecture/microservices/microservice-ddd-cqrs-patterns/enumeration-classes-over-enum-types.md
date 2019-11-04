---
title: Verwenden von Enumerationsklassen anstelle von Enumerationstypen
description: .NET Microservicesarchitektur für Containerized .NET-Anwendungen | Nutzung von Enumerationsklassen anstelle von Enumerationen als Lösungsmöglichkeit für die Einschränkungen der Enumerationen
ms.date: 10/08/2018
ms.openlocfilehash: 255bccab0e1fe71e00c0d0b47c8af05f80cb760b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73093864"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="0270e-103">Verwenden von Enumerationsklassen anstelle von Enumerationstypen</span><span class="sxs-lookup"><span data-stu-id="0270e-103">Use enumeration classes instead of enum types</span></span>

<span data-ttu-id="0270e-104">Bei [Enumerationen](../../../csharp/language-reference/keywords/enum.md) (bzw. *Enumerationstypen*) handelt es sich um dünne Sprachwrapper um einen integralen Typ.</span><span class="sxs-lookup"><span data-stu-id="0270e-104">[Enumerations](../../../csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="0270e-105">Sie sollten deren Verwendung darauf beschränken, einen Wert aus einem vollständigen Wertesatz zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0270e-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="0270e-106">Klassifizierung anhand von Größen (klein, mittel, groß) ist ein gutes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0270e-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="0270e-107">Das Verwenden von Enumerationen zur Ablaufsteuerung oder für robustere Abstraktionen kann zu [schlecht strukturiertem Code](https://deviq.com/code-smells/) führen.</span><span class="sxs-lookup"><span data-stu-id="0270e-107">Using enums for control flow or more robust abstractions can be a [code smell](https://deviq.com/code-smells/).</span></span> <span data-ttu-id="0270e-108">Diese Art der Verwendung führt zu instabilem Code mit vielen Anweisungen für die Ablaufsteuerung, die die Werte der Enumeration überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0270e-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="0270e-109">Sie können stattdessen Enumerationsklassen erstellen, um die umfassenden Features von objektorientierten Sprachen nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="0270e-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="0270e-110">Dabei handelt es sich jedoch nicht um ein kritisches Thema und in vielen Fällen können Sie aus Gründen der Einfachheit dennoch reguläre [Enumerationstypen](../../../csharp/language-reference/keywords/enum.md) verwenden, wenn Sie diese bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="0270e-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../csharp/language-reference/keywords/enum.md) if that's your preference.</span></span> <span data-ttu-id="0270e-111">Jedenfalls bezieht sich die Verwendung von Enumerationsklassen mehr auf geschäftliche Konzepte.</span><span class="sxs-lookup"><span data-stu-id="0270e-111">Anyway, the use of enumeration classes is more related to business-related concepts.</span></span>

## <a name="implement-an-enumeration-base-class"></a><span data-ttu-id="0270e-112">Implementieren einer Basisklasse für Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0270e-112">Implement an Enumeration base class</span></span>

<span data-ttu-id="0270e-113">Der Microservice für Bestellungen in eShopOnContainers stellt wie im Folgenden dargestellt ein Beispiel für die Implementierung einer Basisklasse für Enumerationen bereit:</span><span class="sxs-lookup"><span data-stu-id="0270e-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }

    public int Id { get; private set; }

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

<span data-ttu-id="0270e-114">Sie können diese Klasse als Typ in einem beliebigen Entitäts- oder Wertobjekt verwenden, z.B. für die folgende `CardType`:`Enumeration`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="0270e-114">You can use this class as a type in any entity or value object, as for the following `CardType` : `Enumeration` class:</span></span>

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    public CardType(int id, string name)
        : base(id, name)
    {
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="0270e-115">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0270e-115">Additional resources</span></span>

- <span data-ttu-id="0270e-116">**Enums are evil—Update (Warum Sie auf Enumerationen verzichten sollten (aktualisierte Version))**  </span><span class="sxs-lookup"><span data-stu-id="0270e-116">**Enum’s are evil—update** </span></span>\
  <https://www.planetgeek.ch/2009/07/01/enums-are-evil/>

- <span data-ttu-id="0270e-117">**Daniel Hardman. How Enums Spread Disease – And How To Cure It (Warum Enumerationen für Probleme sorgen und wie Sie diese vermeiden)**  </span><span class="sxs-lookup"><span data-stu-id="0270e-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It** </span></span>\
  <https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/>

- <span data-ttu-id="0270e-118">**Jimmy Bogard. Enumeration classes (Enumerationsklassen)**  </span><span class="sxs-lookup"><span data-stu-id="0270e-118">**Jimmy Bogard. Enumeration classes** </span></span>\
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- <span data-ttu-id="0270e-119">**Steve Smith. Enum Alternatives in C# (Alternativen zu Enumerationen in C#)**  </span><span class="sxs-lookup"><span data-stu-id="0270e-119">**Steve Smith. Enum Alternatives in C#** </span></span>\
  <https://ardalis.com/enum-alternatives-in-c>

- <span data-ttu-id="0270e-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="0270e-120">**Enumeration.cs.**</span></span> <span data-ttu-id="0270e-121">Base Enumeration class in eShopOnContainers(Die Basisklasse „Enumeration“ in eShopOnContainers) </span><span class="sxs-lookup"><span data-stu-id="0270e-121">Base Enumeration class in eShopOnContainers </span></span>\
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- <span data-ttu-id="0270e-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="0270e-122">**CardType.cs**.</span></span> <span data-ttu-id="0270e-123">Beispielklasse für Enumerationen in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="0270e-123">Sample Enumeration class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>

- <span data-ttu-id="0270e-124">**SmartEnum**.</span><span class="sxs-lookup"><span data-stu-id="0270e-124">**SmartEnum**.</span></span> <span data-ttu-id="0270e-125">Ardalis: Klassen zum Erzeugen von stark typisierten intelligenteren Enumerationen in .NET</span><span class="sxs-lookup"><span data-stu-id="0270e-125">Ardalis - Classes to help produce strongly typed smarter enums in .NET.</span></span> \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
><span data-ttu-id="0270e-126">[Zurück](implement-value-objects.md)
>[Weiter](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="0270e-126">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
