---
title: Vergleiche und Sortierungen innerhalb von Auflistungen
description: Vergleiche und Sortierungen innerhalb von Auflistungen
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c7b7c005-628d-427a-91ad-af0c3958c00e
translationtype: Human Translation
ms.sourcegitcommit: e07788926a995b41571be276379ad9285747951d
ms.openlocfilehash: bad7fd4e9cda1976a31f287d7c95d81d113a30fa

---

# <a name="comparisons-and-sorts-within-collections"></a>Vergleiche und Sortierungen innerhalb von Auflistungen

Die [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)-Klassen führen bei nahezu allen Vorgängen zur Verwaltung von Auflistungen Vergleiche durch, sei es bei der Suche nach zu entfernenden Elementen oder bei der Rückgabe eines Schlüssel-Wert-Paars.

Auflistungen verwenden in der Regel einen Gleichheitsvergleich und/oder einen Reihenfolgenvergleich. Für Vergleiche werden zwei Konstrukte verwendet. 

## <a name="checking-for-equality"></a>Durchführen von Gleichheitsüberprüfungen

Methoden wie `Contains`, `IndexOf`, `LastIndexOf` und `Remove` verwenden einen Gleichheitsvergleich für die Elemente der Auflistung. Wenn die Auflistung generisch ist, werden die Elemente anhand der folgenden Richtlinien auf Gleichheit hin verglichen:

*   Wenn Typ T die generische Schnittstelle [IEquatable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IEquatable-1) implementiert, dann ist der Gleichheitsvergleich die `Equals`-Methode dieser Schnittstelle.

*   Wenn der Typ T `IEquatable<T>` nicht implementiert, wird `Object.Equals` verwendet.

Darüber hinaus akzeptieren einige Konstruktorüberladungen für Wörterbuchauflistungen eine [IEqualityComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEqualityComparer-1)-Implementierung, die zum Vergleichen von Schlüsseln auf Gleichheit hin verwendet wird.

## <a name="determining-sort-order"></a>Festlegen der Sortierreihenfolge

Methoden, wie `BinarySearch` und `Sort`, verwenden einen Reihenfolgenvergleich für Elemente der Auflistung. Die Vergleiche können zwischen Elementen in der Auflistung oder zwischen einem Element und einem angegebenen Wert durchgeführt werden. Zum Vergleichen von Objekten stehen das Konzept eines Standardvergleichs und eines expliziten Vergleichs zur Verfügung. 

Der Standardvergleich beruht auf dem Vergleich von mindestens einem Objekt, um die `IComparable`-Schnittstelle zu implementieren. Es ist empfehlenswert, `IComparable` in allen Klassen zu implementieren, die als Werte in einer Listenauflistung oder als Schlüssel in einer Wörterbuchauflistung verwendet werden. Bei einer generischen Auflistung wird der Gleichheitsvergleich gemäß dem Folgenden bestimmt:

*   Wenn Typ T die generische Schnittstelle [System.IComparable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IComparable-1) implementiert, dann ist der Standardvergleich die `CompareTo(T)`-Methode dieser Schnittstelle.

*   Wenn Typ T die nicht generische Schnittstelle [System.IComparable](https://docs.microsoft.com/dotnet/core/api/System.IComparable) implementiert, dann ist der Standardvergleich die `CompareTo`(Object)-Methode dieser Schnittstelle.

*   Wenn Typ T keine der Schnittstellen implementiert, gibt es keinen Standardvergleich, und ein Vergleich oder ein Vergleichsdelegat muss explizit angegeben werden.

Um explizite Vergleiche zu ermöglichen, akzeptieren einige Methoden eine `IComparer`-Implementierung als Parameter. Z.B. akzeptiert die `List<T>.Sort`-Methode eine [System.Collections.Generic.IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1)-Implementierung. 

## <a name="equality-and-sort-example"></a>Beispiel für Gleichheit und Sortierung

Der folgende Code zeigt eine Implementierung von [IEquatable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IEquatable-1) und [IComparable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IComparable-1) für ein einfaches Geschäftsobjekt. Wenn das Objekt in einer Liste gespeichert und sortiert wird, sehen Sie darüber hinaus, dass durch den Aufruf der `Sort()`-Methode der Standardvergleich für den 'Part'-Typ verwendet wird und die `Sort(Comparison<T>)`-Methode mit einer anonymen Methode implementiert wird.

A#

```csharp
using System;
using System.Collections.Generic;
// Simple business object. A PartId is used to identify the type of part 
// but the part name can change. 
public class Part : IEquatable<Part> , IComparable<Part>
{
    public string PartName { get; set; }

    public int PartId { get; set; }

    public override string ToString()
    {
        return "ID: " + PartId + "   Name: " + PartName;
    }
    public override bool Equals(object obj)
    {
        if (obj == null) return false;
        Part objAsPart = obj as Part;
        if (objAsPart == null) return false;
        else return Equals(objAsPart);
    }
    public int SortByNameAscending(string name1, string name2)
    {

        return name1.CompareTo(name2);
    }

    // Default comparer for Part type.
    public int CompareTo(Part comparePart)
    {
          // A null value means that this object is greater.
        if (comparePart == null)
            return 1;

        else
            return this.PartId.CompareTo(comparePart.PartId);
    }
    public override int GetHashCode()
    {
        return PartId;
    }
    public bool Equals(Part other)
    {
        if (other == null) return false;
        return (this.PartId.Equals(other.PartId));
    }
    // Should also override == and != operators.

}
public class Example
{
    public static void Main()
    {
        // Create a list of parts.
        List<Part> parts = new List<Part>();

        // Add parts to the list.
        parts.Add(new Part() { PartName = "regular seat", PartId = 1434 });
        parts.Add(new Part() { PartName= "crank arm", PartId = 1234 });
        parts.Add(new Part() { PartName = "shift lever", PartId = 1634 }); ;
        // Name intentionally left null.
        parts.Add(new Part() {  PartId = 1334 });
        parts.Add(new Part() { PartName = "banana seat", PartId = 1444 });
        parts.Add(new Part() { PartName = "cassette", PartId = 1534 });


        // Write out the parts in the list. This will call the overridden 
        // ToString method in the Part class.
        Console.WriteLine("\nBefore sort:");
        foreach (Part aPart in parts)
        {
            Console.WriteLine(aPart);
        }


        // Call Sort on the list. This will use the 
        // default comparer, which is the Compare method 
        // implemented on Part.
        parts.Sort();


        Console.WriteLine("\nAfter sort by part number:");
        foreach (Part aPart in parts)
        {
            Console.WriteLine(aPart);
        }

        // This shows calling the Sort(Comparison(T) overload using 
        // an anonymous method for the Comparison delegate. 
        // This method treats null as the lesser of two values.
        parts.Sort(delegate(Part x, Part y)
        {
            if (x.PartName == null && y.PartName == null) return 0;
            else if (x.PartName == null) return -1;
            else if (y.PartName == null) return 1;
            else return x.PartName.CompareTo(y.PartName);
        });

        Console.WriteLine("\nAfter sort by name:");
        foreach (Part aPart in parts)
        {
            Console.WriteLine(aPart);
        }

        /*

            Before sort:
        ID: 1434   Name: regular seat
        ID: 1234   Name: crank arm
        ID: 1634   Name: shift lever
        ID: 1334   Name:
        ID: 1444   Name: banana seat
        ID: 1534   Name: cassette

        After sort by part number:
        ID: 1234   Name: crank arm
        ID: 1334   Name:
        ID: 1434   Name: regular seat
        ID: 1444   Name: banana seat
        ID: 1534   Name: cassette
        ID: 1634   Name: shift lever

        After sort by name:
        ID: 1334   Name:
        ID: 1444   Name: banana seat
        ID: 1534   Name: cassette
        ID: 1234   Name: crank arm
        ID: 1434   Name: regular seat
        ID: 1634   Name: shift lever

         */

    }
}
```

## <a name="see-also"></a>Siehe auch

[IComparer](https://docs.microsoft.com/dotnet/core/api/System.Collections.IComparer)

[IEquatable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IEquatable-1)

[IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1)

[IComparable](https://docs.microsoft.com/dotnet/core/api/System.IComparable)

[IComparable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IComparable-1)



<!--HONumber=Nov16_HO3-->


