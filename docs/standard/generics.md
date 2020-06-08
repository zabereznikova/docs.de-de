---
title: Generische Typen (Generics) – Übersicht
description: Erfahren Sie, wie Generics als Codevorlagen fungieren, mit denen Sie typsichere Datenstrukturen definieren können, ohne sich auf einen Datentyp festlegen zu müssen.
author: kuhlenh
ms.author: wiwagn
ms.date: 10/09/2018
ms.openlocfilehash: 99e3b589cd67c9d7026966d3d48d0e06a91fcc86
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287544"
---
# <a name="generic-types-overview"></a><span data-ttu-id="82282-103">Generische Typen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="82282-103">Generic types overview</span></span>

<span data-ttu-id="82282-104">Entwickler verwenden Generics sehr häufig in .NET, entweder implizit oder explizit.</span><span class="sxs-lookup"><span data-stu-id="82282-104">Developers use generics all the time in .NET, whether implicitly or explicitly.</span></span> <span data-ttu-id="82282-105">Wenn Sie LINQ in .NET verwenden: Ist Ihnen schon aufgefallen, dass Sie mit <xref:System.Collections.Generic.IEnumerable%601> arbeiten?</span><span class="sxs-lookup"><span data-stu-id="82282-105">When you use LINQ in .NET, did you ever notice that you're working with <xref:System.Collections.Generic.IEnumerable%601>?</span></span> <span data-ttu-id="82282-106">Oder haben Sie in einem Onlinebeispiel eines „generischen Repositorys“ zur Kommunikation mit Datenbanken über Entity Framework festgestellt, dass die meisten Methoden `IQueryable<T>` zurückgeben?</span><span class="sxs-lookup"><span data-stu-id="82282-106">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return `IQueryable<T>`?</span></span> <span data-ttu-id="82282-107">Möglicherweise haben Sie sich gefragt, wofür das **T** in diesen Beispielen steht und warum es dort ist.</span><span class="sxs-lookup"><span data-stu-id="82282-107">You may have wondered what the **T** is in these examples and why it's in there.</span></span>

<span data-ttu-id="82282-108">Generics wurden in .NET Framework 2.0 eingeführt und sind im Grunde eine „Codevorlage“, mit der Entwickler [typsichere](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) Datenstrukturen definieren können, ohne sich tatsächlich auf einen Datentyp festlegen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="82282-108">First introduced in the .NET Framework 2.0, generics are essentially a "code template" that allows developers to define [type-safe](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) data structures without committing to an actual data type.</span></span> <span data-ttu-id="82282-109"><xref:System.Collections.Generic.List%601> ist beispielsweise eine [generische Auflistung](xref:System.Collections.Generic), die deklariert und mit beliebigen Typen wie `List<int>`, `List<string>` oder `List<Person>` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="82282-109">For example, <xref:System.Collections.Generic.List%601> is a [generic collection](xref:System.Collections.Generic) that can be declared and used with any type, such as `List<int>`, `List<string>`, or `List<Person>`.</span></span>

<span data-ttu-id="82282-110">Um zu verstehen, warum Generics nützlich sind, sehen wir uns eine bestimmte Klasse an, und zwar vor und nach dem Hinzufügen von Generics: <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="82282-110">To understand why generics are useful, let's take a look at a specific class before and after adding generics: <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="82282-111">In .NET Framework 1.0 wiesen die -`ArrayList` den Typ <xref:System.Object> auf.</span><span class="sxs-lookup"><span data-stu-id="82282-111">In .NET Framework 1.0, the `ArrayList` elements were of type <xref:System.Object>.</span></span> <span data-ttu-id="82282-112">Jedes der Sammlung hinzugefügte Element wurde im Hintergrund in ein `Object`-Element konvertiert.</span><span class="sxs-lookup"><span data-stu-id="82282-112">Any element added to the collection was silently converted into an `Object`.</span></span> <span data-ttu-id="82282-113">Das Gleiche passierte beim Lesen von Elementen aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="82282-113">The same would happen when reading elements from the list.</span></span> <span data-ttu-id="82282-114">Dieser Vorgang wird als [Boxing und Unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md) bezeichnet und wirkt sich auf die Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="82282-114">This process is known as [boxing and unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md), and it impacts performance.</span></span> <span data-ttu-id="82282-115">Abgesehen von der Leistung gibt es jedoch keine Möglichkeit, zur Kompilierzeit den Typ der Daten in der Liste zu bestimmen. Dies beeinträchtigt die Stabilität des Codes.</span><span class="sxs-lookup"><span data-stu-id="82282-115">Aside from performance, however, there's no way to determine the type of data in the list at compile time, which makes for some fragile code.</span></span> <span data-ttu-id="82282-116">Generics lösen dieses Problem, indem sie den Datentyp definieren, der in jeder Instanz der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="82282-116">Generics solve this problem by defining the type of data each instance of list will contain.</span></span> <span data-ttu-id="82282-117">Beispielsweise können Sie zu `List<int>` nur Ganzzahlen hinzufügen, zu `List<Person>` nur Personen.</span><span class="sxs-lookup"><span data-stu-id="82282-117">For example, you can only add integers to `List<int>` and only add Persons to `List<Person>`.</span></span>

<span data-ttu-id="82282-118">Generics sind auch zur Laufzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="82282-118">Generics are also available at run time.</span></span> <span data-ttu-id="82282-119">Die Runtime weiß, welche Art Datenstruktur Sie verwenden, und kann die Daten effizienter im Arbeitsspeicher speichern.</span><span class="sxs-lookup"><span data-stu-id="82282-119">The runtime knows what type of data structure you're using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="82282-120">Das folgende Beispiel ist ein kleines Programm, das veranschaulicht, wie effizient es ist, wenn die Art der Datenstruktur zur Laufzeit bekannt ist:</span><span class="sxs-lookup"><span data-stu-id="82282-120">The following example is a small program that illustrates the efficiency of knowing the data structure type at run time:</span></span>

```csharp
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }
```

<span data-ttu-id="82282-121">Dieses Programm erzeugt eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="82282-121">This program produces output similar to the following:</span></span>

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

<span data-ttu-id="82282-122">Als Erstes können Sie feststellen, dass das Sortieren der generischen Liste erheblich schneller erfolgt als bei der nicht generischen Liste.</span><span class="sxs-lookup"><span data-stu-id="82282-122">The first thing you can notice here is that sorting the generic list is significantly faster than sorting the non-generic list.</span></span> <span data-ttu-id="82282-123">Sie werden vermutlich auch bemerken, dass der Typ für die generische Liste eindeutig ([System.Int32]), der Typ für die nicht generische Liste dagegen generalisiert ist.</span><span class="sxs-lookup"><span data-stu-id="82282-123">You might also notice that the type for the generic list is distinct ([System.Int32]), whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="82282-124">Da der Runtime bekannt ist, dass die generische `List<int>` den Typ <xref:System.Int32> aufweist, kann sie die Listenelemente in einem zugrunde liegenden Ganzzahlarray im Arbeitsspeicher speichern. Die nicht generische `ArrayList` muss hingegen jedes Listenelement in ein Objekt umwandeln.</span><span class="sxs-lookup"><span data-stu-id="82282-124">Because the runtime knows the generic `List<int>` is of type <xref:System.Int32>, it can store the list elements in an underlying integer array in memory, while the non-generic `ArrayList` has to cast each list element to an object.</span></span> <span data-ttu-id="82282-125">Wie dieses Beispiel zeigt, beanspruchen die zusätzlichen Umwandlungen Zeit und verlangsamen den Sortiervorgang für die Liste.</span><span class="sxs-lookup"><span data-stu-id="82282-125">As this example shows, the extra casts take up time and slow down the list sort.</span></span>

<span data-ttu-id="82282-126">Ein weiterer Vorteil: Wenn die Runtime den Typ der Generika kennt, wird das Debuggen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="82282-126">An additional advantage of the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="82282-127">Wenn Sie Generika in C# debuggen, wissen Sie, welchen Typ jedes Element in Ihrer Datenstruktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="82282-127">When you're debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="82282-128">Ohne Generics wüssten Sie dies nicht.</span><span class="sxs-lookup"><span data-stu-id="82282-128">Without generics, you would have no idea what type each element was.</span></span>

## <a name="see-also"></a><span data-ttu-id="82282-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82282-129">See also</span></span>

- [<span data-ttu-id="82282-130">C#-Programmierhandbuch – Generics</span><span class="sxs-lookup"><span data-stu-id="82282-130">C# Programming Guide - Generics</span></span>](../csharp/programming-guide/generics/index.md)
