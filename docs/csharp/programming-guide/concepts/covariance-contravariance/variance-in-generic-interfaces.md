---
title: Varianz in generischen Schnittstellen (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cc3fe009e89d5d8f6619b406c8c08f47620a881d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="5a627-102">Varianz in generischen Schnittstellen (C#)</span><span class="sxs-lookup"><span data-stu-id="5a627-102">Variance in Generic Interfaces (C#)</span></span>
<span data-ttu-id="5a627-103">In .NET Framework 4 wurde die Varianzunterstützung für mehrere vorhandene generische Schnittstellen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5a627-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="5a627-104">Die Varianzunterstützung lässt eine implizite Konvertierung von Klassen zu, die diese Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="5a627-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="5a627-105">Die folgenden Schnittstellen sind jetzt variant:</span><span class="sxs-lookup"><span data-stu-id="5a627-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="5a627-106"><xref:System.Collections.Generic.IEnumerable%601> (T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="5a627-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="5a627-107"><xref:System.Collections.Generic.IEnumerator%601> (T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="5a627-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="5a627-108"><xref:System.Linq.IQueryable%601> (T ist kovariant)</span><span class="sxs-lookup"><span data-stu-id="5a627-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="5a627-109"><xref:System.Linq.IGrouping%602> (`TKey` und `TElement` sind kovariant)</span><span class="sxs-lookup"><span data-stu-id="5a627-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="5a627-110"><xref:System.Collections.Generic.IComparer%601> (T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="5a627-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="5a627-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="5a627-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="5a627-112"><xref:System.IComparable%601> (T ist kontravariant)</span><span class="sxs-lookup"><span data-stu-id="5a627-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="5a627-113">Kovarianz ermöglicht einer Methode, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter der Schnittstelle definiert sind.</span><span class="sxs-lookup"><span data-stu-id="5a627-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="5a627-114">Betrachten Sie diese generischen Schnittstellen zur Veranschaulichung der Kovarianzfunktionen: `IEnumerable<Object>` und `IEnumerable<String>`.</span><span class="sxs-lookup"><span data-stu-id="5a627-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="5a627-115">Die Schnittstelle `IEnumerable<Object>` wird nicht von der Schnittstelle `IEnumerable<String>` geerbt.</span><span class="sxs-lookup"><span data-stu-id="5a627-115">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="5a627-116">Allerdings erbt der Typ `String` den Typ `Object`. In einigen Fällen können Sie vielleicht auch die Objekte dieser Schnittstellen einander zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5a627-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="5a627-117">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a627-117">This is shown in the following code example.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="5a627-118">In früheren Versionen des .NET Frameworks verursacht dieser Code einen Kompilierfehler mit `Option Strict On` in C#.</span><span class="sxs-lookup"><span data-stu-id="5a627-118">In earlier versions of the .NET Framework, this code causes a compilation error in C# with `Option Strict On`.</span></span> <span data-ttu-id="5a627-119">Jetzt können Sie aber `strings` anstelle von `objects` verwenden, wie im vorherigen Beispiel gezeigt wurde, da die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle kovariant ist.</span><span class="sxs-lookup"><span data-stu-id="5a627-119">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="5a627-120">Kontravarianz ermöglicht einer Methode, Argumenttypen zu verwenden, die weniger stark abgeleitet sind als durch die generischen Parameter der Schnittstelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="5a627-120">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="5a627-121">Nehmen Sie zur Veranschaulichung der Kontravarianz an, dass Sie eine `BaseComparer`-Klasse zum Vergleich von Instanzen der `BaseClass`-Klasse erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="5a627-121">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="5a627-122">Die `BaseComparer`-Klasse implementiert die `IEqualityComparer<BaseClass>`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5a627-122">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="5a627-123">Da die Schnittstelle <xref:System.Collections.Generic.IEqualityComparer%601> jetzt kontravariant ist, können Sie `BaseComparer` verwenden, um Instanzen von Klassen zu vergleichen, die die Klasse `BaseClass` erben.</span><span class="sxs-lookup"><span data-stu-id="5a627-123">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="5a627-124">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a627-124">This is shown in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="5a627-125">Weitere Beispiele finden Sie unter [Using Variance in Interfaces for Generic Collections (C#) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="5a627-125">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="5a627-126">Varianz in generischen Typparametern wird nur für Referenztypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5a627-126">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="5a627-127">Werttypen unterstützen keine Varianz.</span><span class="sxs-lookup"><span data-stu-id="5a627-127">Value types do not support variance.</span></span> <span data-ttu-id="5a627-128">Beispielweise kann `IEnumerable<int>` nicht implizit in `IEnumerable<object>` konvertiert werden, da Ganzzahlen durch Werttypen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5a627-128">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>  
  
```csharp  
IEnumerable<int> integers = new List<int>();  
// The following statement generates a compiler errror,  
// because int is a value type.  
// IEnumerable<Object> objects = integers;  
```  
  
 <span data-ttu-id="5a627-129">Es ist auch wichtig zu beachten, dass Klassen, die variante Schnittstellen implementieren, trotzdem noch invariant sind.</span><span class="sxs-lookup"><span data-stu-id="5a627-129">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="5a627-130">Obwohl <xref:System.Collections.Generic.List%601> beispielsweise die kovariante Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie `List<Object>` implizit in `List<String>` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="5a627-130">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<Object>` to `List<String>`.</span></span> <span data-ttu-id="5a627-131">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5a627-131">This is illustrated in the following code example.</span></span>  
  
```csharp  
// The following line generates a compiler error  
// because classes are invariant.  
// List<Object> list = new List<String>();  
  
// You can use the interface object instead.  
IEnumerable<Object> listObjects = new List<String>();  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a627-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a627-132">See Also</span></span>  
 [<span data-ttu-id="5a627-133">Using Variance in Interfaces for Generic Collections (C#) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#))</span><span class="sxs-lookup"><span data-stu-id="5a627-133">Using Variance in Interfaces for Generic Collections (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)  
 [<span data-ttu-id="5a627-134">Creating Variant Generic Interfaces (C#) (Erstellen von varianten generischen Schnittstellen (C#))</span><span class="sxs-lookup"><span data-stu-id="5a627-134">Creating Variant Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)  
 [<span data-ttu-id="5a627-135">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5a627-135">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)  
 [<span data-ttu-id="5a627-136">Variance in Delegates (C#) (Varianz bei Delegaten (C#))</span><span class="sxs-lookup"><span data-stu-id="5a627-136">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
