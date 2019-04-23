---
title: Varianz in generischen Schnittstellen (C#)
ms.date: 04/10/2019
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: 5874a39a57f85695bedc3d1ffa61adf19fcdbe37
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480780"
---
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="ce74f-102">Varianz in generischen Schnittstellen (C#)</span><span class="sxs-lookup"><span data-stu-id="ce74f-102">Variance in Generic Interfaces (C#)</span></span>

<span data-ttu-id="ce74f-103">In .NET Framework 4 wurde die Varianzunterstützung für mehrere vorhandene generische Schnittstellen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ce74f-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="ce74f-104">Die Varianzunterstützung lässt eine implizite Konvertierung von Klassen zu, die diese Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="ce74f-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> 

<span data-ttu-id="ce74f-105">Ab .NET Framework 4 sind die folgenden Schnittstellen Varianten:</span><span class="sxs-lookup"><span data-stu-id="ce74f-105">Staring with .NET Framework 4, the following interfaces are variant:</span></span>

- <xref:System.Collections.Generic.IEnumerable%601> <span data-ttu-id="ce74f-106">(T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="ce74f-106">(T is covariant)</span></span>

- <xref:System.Collections.Generic.IEnumerator%601> <span data-ttu-id="ce74f-107">(T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="ce74f-107">(T is covariant)</span></span>

- <xref:System.Linq.IQueryable%601> <span data-ttu-id="ce74f-108">(T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="ce74f-108">(T is covariant)</span></span>

- <xref:System.Linq.IGrouping%602> <span data-ttu-id="ce74f-109">(`TKey` und `TElement` sind kovariant)</span><span class="sxs-lookup"><span data-stu-id="ce74f-109">(`TKey` and `TElement` are covariant)</span></span>

- <xref:System.Collections.Generic.IComparer%601> <span data-ttu-id="ce74f-110">(T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="ce74f-110">(T is contravariant)</span></span>

- <xref:System.Collections.Generic.IEqualityComparer%601> <span data-ttu-id="ce74f-111">(T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="ce74f-111">(T is contravariant)</span></span>

- <xref:System.IComparable%601> <span data-ttu-id="ce74f-112">(T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="ce74f-112">(T is contravariant)</span></span>

<span data-ttu-id="ce74f-113">Ab .NET Framework 4.5 sind die folgenden Schnittstellen Varianten:</span><span class="sxs-lookup"><span data-stu-id="ce74f-113">Starting with .NET Framework 4.5, the following interfaces are variant:</span></span>

- <xref:System.Collections.Generic.IReadOnlyList%601> <span data-ttu-id="ce74f-114">(T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="ce74f-114">(T is contravariant)</span></span>

- <xref:System.Collections.Generic.IReadOnlyCollection%601> <span data-ttu-id="ce74f-115">(T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="ce74f-115">(T is contravariant)</span></span>

<span data-ttu-id="ce74f-116">Kovarianz ermöglicht einer Methode, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter der Schnittstelle definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ce74f-116">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="ce74f-117">Betrachten Sie diese generischen Schnittstellen zur Veranschaulichung der Kovarianzfunktionen: `IEnumerable<Object>` und `IEnumerable<String>`.</span><span class="sxs-lookup"><span data-stu-id="ce74f-117">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="ce74f-118">Die Schnittstelle `IEnumerable<Object>` wird nicht von der Schnittstelle `IEnumerable<String>` geerbt.</span><span class="sxs-lookup"><span data-stu-id="ce74f-118">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="ce74f-119">Allerdings erbt der Typ `String` den Typ `Object`. In einigen Fällen können Sie vielleicht auch die Objekte dieser Schnittstellen einander zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ce74f-119">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="ce74f-120">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce74f-120">This is shown in the following code example.</span></span>

```csharp
IEnumerable<String> strings = new List<String>();
IEnumerable<Object> objects = strings;
```

<span data-ttu-id="ce74f-121">In früheren Versionen des.NET-Frameworks verursacht dieser Code in Visual Basic einen Kompilierungsfehler in C# und, wenn `Option Strict` aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ce74f-121">In earlier versions of the .NET Framework, this code causes a compilation error in C# and, if `Option Strict` is on, in Visual Basic.</span></span> <span data-ttu-id="ce74f-122">Jetzt können Sie aber `strings` anstelle von `objects` verwenden, wie im vorherigen Beispiel gezeigt wurde, da die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle kovariant ist.</span><span class="sxs-lookup"><span data-stu-id="ce74f-122">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>

<span data-ttu-id="ce74f-123">Kontravarianz ermöglicht einer Methode, Argumenttypen zu verwenden, die weniger stark abgeleitet sind als durch die generischen Parameter der Schnittstelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="ce74f-123">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="ce74f-124">Nehmen Sie zur Veranschaulichung der Kontravarianz an, dass Sie eine `BaseComparer`-Klasse zum Vergleich von Instanzen der `BaseClass`-Klasse erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ce74f-124">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="ce74f-125">Die `BaseComparer`-Klasse implementiert die `IEqualityComparer<BaseClass>`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ce74f-125">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="ce74f-126">Da die Schnittstelle <xref:System.Collections.Generic.IEqualityComparer%601> jetzt kontravariant ist, können Sie `BaseComparer` verwenden, um Instanzen von Klassen zu vergleichen, die die Klasse `BaseClass` erben.</span><span class="sxs-lookup"><span data-stu-id="ce74f-126">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="ce74f-127">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce74f-127">This is shown in the following code example.</span></span>

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

<span data-ttu-id="ce74f-128">Weitere Beispiele finden Sie unter [Using Variance in Interfaces for Generic Collections (C#) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="ce74f-128">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>

<span data-ttu-id="ce74f-129">Varianz in generischen Typparametern wird nur für Referenztypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ce74f-129">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="ce74f-130">Werttypen unterstützen keine Varianz.</span><span class="sxs-lookup"><span data-stu-id="ce74f-130">Value types do not support variance.</span></span> <span data-ttu-id="ce74f-131">Beispielweise kann `IEnumerable<int>` nicht implizit in `IEnumerable<object>` konvertiert werden, da Ganzzahlen durch Werttypen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ce74f-131">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>

```csharp
IEnumerable<int> integers = new List<int>();
// The following statement generates a compiler error,
// because int is a value type.
// IEnumerable<Object> objects = integers;
```

<span data-ttu-id="ce74f-132">Es ist auch wichtig zu beachten, dass Klassen, die variante Schnittstellen implementieren, trotzdem noch invariant sind.</span><span class="sxs-lookup"><span data-stu-id="ce74f-132">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="ce74f-133">Obwohl <xref:System.Collections.Generic.List%601> beispielsweise die kovariante Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie `List<Object>` implizit in `List<String>` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ce74f-133">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<Object>` to `List<String>`.</span></span> <span data-ttu-id="ce74f-134">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ce74f-134">This is illustrated in the following code example.</span></span>

```csharp
// The following line generates a compiler error
// because classes are invariant.
// List<Object> list = new List<String>();

// You can use the interface object instead.
IEnumerable<Object> listObjects = new List<String>();
```

## <a name="see-also"></a><span data-ttu-id="ce74f-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce74f-135">See also</span></span>

- [<span data-ttu-id="ce74f-136">Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#)</span><span class="sxs-lookup"><span data-stu-id="ce74f-136">Using Variance in Interfaces for Generic Collections (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)
- [<span data-ttu-id="ce74f-137">Erstellen varianter generischer Schnittstellen (C#)</span><span class="sxs-lookup"><span data-stu-id="ce74f-137">Creating Variant Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)
- [<span data-ttu-id="ce74f-138">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ce74f-138">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)
- [<span data-ttu-id="ce74f-139">Varianz bei Delegaten (C#)</span><span class="sxs-lookup"><span data-stu-id="ce74f-139">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
