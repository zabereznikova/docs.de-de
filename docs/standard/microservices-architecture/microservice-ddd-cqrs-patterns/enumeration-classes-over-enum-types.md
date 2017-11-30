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
# <a name="using-enumeration-classes-instead-of-enum-types"></a>Enum-Typen anstelle Enumeration Klassen

[Enumerationen](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*Enumerationen* kurz) sind ein schlanke Language-Wrapper um einen ganzzahligen Typ. Sie möchten möglicherweise verwenden Sie diese eingeschränkt werden, wenn Sie einen Wert aus einen vollständigen Satz von Werten gespeichert sind. Klassifizierung basierend auf Geschlecht (z. B. Männlich, Weiblich unbekannt) oder Größe (S, M, L, XL) sind gute Beispiele für. Mithilfe von Enumerationen für ablaufsteuerung oder eine robustere Abstraktionen kann eine [code Geruch](http://deviq.com/code-smells/). Diese Art der Verwendung führt zu instabilen Code mit vielen Anweisungen für die ablaufsteuerung überprüfen die Werte der Enumeration.

Sie können stattdessen Enumeration Klassen erstellen, die die umfassenden Funktionen eine objektorientierte Sprache zu ermöglichen. Allerdings wird dies ist nicht durch ein schwerwiegendes Problem, und in vielen Fällen aus Gründen der Einfachheit, noch können reguläre Enumerationen, die die Einstellung ist.

## <a name="implementing-enumeration-classes"></a>Klassenimplementierung-Enumeration

Die Reihenfolge Microservice in eShopOnContainers bietet eine Beispiel-Enumeration basisklassenimplementierung, wie im folgenden Beispiel gezeigt:

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

Sie können diese Klasse als eine Entität oder Wert-Objekt, für die folgenden CardType Enumerationsklasse-Typ verwenden.

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

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Enum gefährlich werden – aktualisieren**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)

-   **Daniel Hardman. Wie Enumerationen Krankheit verteilt, Und wie Sie es beheben**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)

-   **Jimmy Bogard. Enumeration Klassen**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)

-   **Steve Smith. Enum-alternativen in c#**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)

-   **Enumeration.cs.** Basisklasse für Enumeration in eShopOnContainers [ *https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)

-   **CardType.cs**. Beispiel-Enumerationsklasse in eShopOnContainers.
    [*https://github.com/dotnet/eShopOnContainers/BLOB/Master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
[Vorherigen] (implementieren-Wert-objects.md) [weiter] (Domäne-Modell-Ebene – validations.md)
