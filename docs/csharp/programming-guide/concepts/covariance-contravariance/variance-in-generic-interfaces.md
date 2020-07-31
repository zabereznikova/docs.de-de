---
title: Varianz in generischen Schnittstellen (C#)
description: Zeigen Sie Informationen zur Varianzunterstützung für generische Schnittstellen an, einschließlich aktualisierter Informationen für vorhandene Schnittstellen in .NET Framework 4 und 4.5.
ms.date: 06/06/2019
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: 91218742c01eeb6e65ea26d9dc41ed7c98827377
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105629"
---
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="1120e-103">Varianz in generischen Schnittstellen (C#)</span><span class="sxs-lookup"><span data-stu-id="1120e-103">Variance in Generic Interfaces (C#)</span></span>

<span data-ttu-id="1120e-104">In .NET Framework 4 wurde die Varianzunterstützung für mehrere vorhandene generische Schnittstellen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1120e-104">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="1120e-105">Die Varianzunterstützung lässt eine implizite Konvertierung von Klassen zu, die diese Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="1120e-105">Variance support enables implicit conversion of classes that implement these interfaces.</span></span>

<span data-ttu-id="1120e-106">Ab .NET Framework 4 sind die folgenden Schnittstellen Varianten:</span><span class="sxs-lookup"><span data-stu-id="1120e-106">Starting with .NET Framework 4, the following interfaces are variant:</span></span>

- <span data-ttu-id="1120e-107"><xref:System.Collections.Generic.IEnumerable%601> (T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="1120e-107"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>

- <span data-ttu-id="1120e-108"><xref:System.Collections.Generic.IEnumerator%601> (T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="1120e-108"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>

- <span data-ttu-id="1120e-109"><xref:System.Linq.IQueryable%601> (T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="1120e-109"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>

- <span data-ttu-id="1120e-110"><xref:System.Linq.IGrouping%602> (`TKey` und `TElement` sind kovariant)</span><span class="sxs-lookup"><span data-stu-id="1120e-110"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>

- <span data-ttu-id="1120e-111"><xref:System.Collections.Generic.IComparer%601> (T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="1120e-111"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="1120e-112"><xref:System.Collections.Generic.IEqualityComparer%601> (T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="1120e-112"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="1120e-113"><xref:System.IComparable%601> (T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="1120e-113"><xref:System.IComparable%601> (T is contravariant)</span></span>

<span data-ttu-id="1120e-114">Ab .NET Framework 4.5 sind die folgenden Schnittstellen Varianten:</span><span class="sxs-lookup"><span data-stu-id="1120e-114">Starting with .NET Framework 4.5, the following interfaces are variant:</span></span>

- <span data-ttu-id="1120e-115"><xref:System.Collections.Generic.IReadOnlyList%601> (T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="1120e-115"><xref:System.Collections.Generic.IReadOnlyList%601> (T is covariant)</span></span>

- <span data-ttu-id="1120e-116"><xref:System.Collections.Generic.IReadOnlyCollection%601> (T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="1120e-116"><xref:System.Collections.Generic.IReadOnlyCollection%601> (T is covariant)</span></span>

<span data-ttu-id="1120e-117">Kovarianz ermöglicht einer Methode, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter der Schnittstelle definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1120e-117">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="1120e-118">Betrachten Sie diese generischen Schnittstellen zur Veranschaulichung der Kovarianzfunktionen: `IEnumerable<Object>` und `IEnumerable<String>`.</span><span class="sxs-lookup"><span data-stu-id="1120e-118">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="1120e-119">Die Schnittstelle `IEnumerable<Object>` wird nicht von der Schnittstelle `IEnumerable<String>` geerbt.</span><span class="sxs-lookup"><span data-stu-id="1120e-119">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="1120e-120">Allerdings erbt der Typ `String` den Typ `Object`. In einigen Fällen können Sie vielleicht auch die Objekte dieser Schnittstellen einander zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1120e-120">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="1120e-121">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1120e-121">This is shown in the following code example.</span></span>

```csharp
IEnumerable<String> strings = new List<String>();
IEnumerable<Object> objects = strings;
```

<span data-ttu-id="1120e-122">In früheren Versionen des.NET-Frameworks verursacht dieser Code in Visual Basic einen Kompilierungsfehler in C# und, wenn `Option Strict` aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1120e-122">In earlier versions of .NET Framework, this code causes a compilation error in C# and, if `Option Strict` is on, in Visual Basic.</span></span> <span data-ttu-id="1120e-123">Jetzt können Sie aber `strings` anstelle von `objects` verwenden, wie im vorherigen Beispiel gezeigt wurde, da die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle kovariant ist.</span><span class="sxs-lookup"><span data-stu-id="1120e-123">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>

<span data-ttu-id="1120e-124">Kontravarianz ermöglicht einer Methode, Argumenttypen zu verwenden, die weniger stark abgeleitet sind als durch die generischen Parameter der Schnittstelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="1120e-124">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="1120e-125">Nehmen Sie zur Veranschaulichung der Kontravarianz an, dass Sie eine `BaseComparer`-Klasse zum Vergleich von Instanzen der `BaseClass`-Klasse erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1120e-125">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="1120e-126">Die `BaseComparer`-Klasse implementiert die `IEqualityComparer<BaseClass>`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1120e-126">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="1120e-127">Da die Schnittstelle <xref:System.Collections.Generic.IEqualityComparer%601> jetzt kontravariant ist, können Sie `BaseComparer` verwenden, um Instanzen von Klassen zu vergleichen, die die Klasse `BaseClass` erben.</span><span class="sxs-lookup"><span data-stu-id="1120e-127">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="1120e-128">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1120e-128">This is shown in the following code example.</span></span>

```csharp
// Simple hierarchy of classes.
class BaseClass { }
class DerivedClass : BaseClass { }

// Comparer class.
class BaseComparer : IEqualityComparer<BaseClass>
{
    public int GetHashCode(BaseClass baseInstance)
    {
        return baseInstance.GetHashCode();
    }
    public bool Equals(BaseClass x, BaseClass y)
    {
        return x == y;
    }
}
class Program
{
    static void Test()
    {
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();

        // Implicit conversion of IEqualityComparer<BaseClass> to
        // IEqualityComparer<DerivedClass>.
        IEqualityComparer<DerivedClass> childComparer = baseComparer;
    }
}
```

<span data-ttu-id="1120e-129">Weitere Beispiele finden Sie unter [Using Variance in Interfaces for Generic Collections (C#) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#))](./using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="1120e-129">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](./using-variance-in-interfaces-for-generic-collections.md).</span></span>

<span data-ttu-id="1120e-130">Varianz in generischen Typparametern wird nur für Referenztypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1120e-130">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="1120e-131">Werttypen unterstützen keine Varianz.</span><span class="sxs-lookup"><span data-stu-id="1120e-131">Value types do not support variance.</span></span> <span data-ttu-id="1120e-132">Beispielweise kann `IEnumerable<int>` nicht implizit in `IEnumerable<object>` konvertiert werden, da Ganzzahlen durch Werttypen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1120e-132">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>

```csharp
IEnumerable<int> integers = new List<int>();
// The following statement generates a compiler error,
// because int is a value type.
// IEnumerable<Object> objects = integers;
```

<span data-ttu-id="1120e-133">Es ist auch wichtig zu beachten, dass Klassen, die variante Schnittstellen implementieren, trotzdem noch invariant sind.</span><span class="sxs-lookup"><span data-stu-id="1120e-133">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="1120e-134">Obwohl <xref:System.Collections.Generic.List%601> beispielsweise die kovariante Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie `List<String>` implizit in `List<Object>` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1120e-134">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<String>` to `List<Object>`.</span></span> <span data-ttu-id="1120e-135">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1120e-135">This is illustrated in the following code example.</span></span>

```csharp
// The following line generates a compiler error
// because classes are invariant.
// List<Object> list = new List<String>();

// You can use the interface object instead.
IEnumerable<Object> listObjects = new List<String>();
```

## <a name="see-also"></a><span data-ttu-id="1120e-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1120e-136">See also</span></span>

- [<span data-ttu-id="1120e-137">Using Variance in Interfaces for Generic Collections (C#) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#))</span><span class="sxs-lookup"><span data-stu-id="1120e-137">Using Variance in Interfaces for Generic Collections (C#)</span></span>](./using-variance-in-interfaces-for-generic-collections.md)
- [<span data-ttu-id="1120e-138">Creating Variant Generic Interfaces (C#) (Erstellen von varianten generischen Schnittstellen (C#))</span><span class="sxs-lookup"><span data-stu-id="1120e-138">Creating Variant Generic Interfaces (C#)</span></span>](./creating-variant-generic-interfaces.md)
- [<span data-ttu-id="1120e-139">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1120e-139">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)
- [<span data-ttu-id="1120e-140">Variance in Delegates (C#) (Varianz bei Delegaten (C#))</span><span class="sxs-lookup"><span data-stu-id="1120e-140">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
