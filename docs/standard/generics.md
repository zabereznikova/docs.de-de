---
title: Generische Typen (Generika) – Übersicht
description: Erfahren Sie, wie Generika als Codevorlagen fungieren, mit denen Sie typsichere Datenstrukturen definieren können, ohne sich auf einen Datentyp festlegen zu müssen.
author: kuhlenh
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
ms.openlocfilehash: ad6216998dff70ca7e36b52b374c5ffb9fd0cd45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="generic-types-generics-overview"></a><span data-ttu-id="0d335-103">Generische Typen (Generika) – Übersicht</span><span class="sxs-lookup"><span data-stu-id="0d335-103">Generic Types (Generics) Overview</span></span>

<span data-ttu-id="0d335-104">Generika werden andauernd in C# verwendet, entweder implizit oder explizit.</span><span class="sxs-lookup"><span data-stu-id="0d335-104">We use generics all the time in C#, whether implicitly or explicitly.</span></span> <span data-ttu-id="0d335-105">Wenn Sie LINQ in C# verwenden, haben Sie schon einmal bemerkt, dass Sie mit IEnumerable<T> arbeiten?</span><span class="sxs-lookup"><span data-stu-id="0d335-105">When you use LINQ in C#, did you ever notice that you are working with IEnumerable<T>?</span></span> <span data-ttu-id="0d335-106">Oder haben Sie in einem Onlinebeispiel eines „generischen Repositorys“ zur Kommunikation mit Datenbanken über Entity Framework festgestellt, dass die meisten Methoden IQueryable<T> zurückgeben?</span><span class="sxs-lookup"><span data-stu-id="0d335-106">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return IQueryable<T>?</span></span> <span data-ttu-id="0d335-107">Haben Sie sich gefragt, wofür das **T** in diesen Beispielen steht und warum es dort ist?</span><span class="sxs-lookup"><span data-stu-id="0d335-107">You may have wondered what the **T** is in these examples and why is it in there?</span></span>

<span data-ttu-id="0d335-108">Generika wurden zum ersten Mal in .NET Framework 2.0 eingeführt und umfassten Änderungen sowohl an der Sprache C# als auch an der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0d335-108">First introduced to the .NET Framework 2.0, generics involved changes to both the C# language and the Common Language Runtime (CLR).</span></span> <span data-ttu-id="0d335-109">**Generika** sind im Grunde eine „Codevorlage“, mit der Entwickler [typsichere](https://msdn.microsoft.com/library/hbzz1a9a.aspx) Datenstrukturen definieren können, ohne sich tatsächlich auf einen Datentyp festlegen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="0d335-109">**Generics** are essentially a "code template" that allows developers to define [type-safe](https://msdn.microsoft.com/library/hbzz1a9a.aspx) data structures without committing to an actual data type.</span></span> <span data-ttu-id="0d335-110">`List<T>` ist beispielsweise eine [generische Auflistung](xref:System.Collections.Generic), die deklariert und mit beliebigen Typen verwendet werden kann: `List<int>`, `List<string>`, `List<Person>` usw.</span><span class="sxs-lookup"><span data-stu-id="0d335-110">For example, `List<T>` is a [Generic Collection](xref:System.Collections.Generic) that can be declared and used with any type: `List<int>`, `List<string>`, `List<Person>`, etc.</span></span>

<span data-ttu-id="0d335-111">Worum liegt also der Sinn?</span><span class="sxs-lookup"><span data-stu-id="0d335-111">So, what’s the point?</span></span> <span data-ttu-id="0d335-112">Warum sind Generika nützlich?</span><span class="sxs-lookup"><span data-stu-id="0d335-112">Why are generics useful?</span></span> <span data-ttu-id="0d335-113">Um dies zu verstehen, müssen wir uns eine bestimmte Klasse ansehen, und zwar vor und nach dem Hinzufügen von Generika.</span><span class="sxs-lookup"><span data-stu-id="0d335-113">In order to understand this, we need to take a look at a specific class before and after adding generics.</span></span> <span data-ttu-id="0d335-114">Wir sehen uns `ArrayList` an.</span><span class="sxs-lookup"><span data-stu-id="0d335-114">Let’s look at the `ArrayList`.</span></span> <span data-ttu-id="0d335-115">In C# 1.0 wiesen die `ArrayList`-Elemente den Typ `object` auf.</span><span class="sxs-lookup"><span data-stu-id="0d335-115">In C# 1.0, the `ArrayList` elements were of type `object`.</span></span> <span data-ttu-id="0d335-116">Dies bedeutete, dass jedes hinzugefügte Element im Hintergrund in ein `object` konvertiert wurde. Das Gleiche passierte beim Lesen der Elemente aus der Liste (dieser Prozess wird als [Boxing](../../docs/csharp/programming-guide/types/boxing-and-unboxing.md) bzw. Unboxing bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="0d335-116">This meant that any element that was added was silently converted into an `object`; same thing happens on reading the elements from the list (this process is known as [boxing](../../docs/csharp/programming-guide/types/boxing-and-unboxing.md) and unboxing respectively).</span></span> <span data-ttu-id="0d335-117">Boxing und Unboxing wirken sich auf die Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="0d335-117">Boxing and unboxing have an impact of performance.</span></span> <span data-ttu-id="0d335-118">Schlimmer noch: Zum Zeitpunkt der Kompilierung lässt sich nicht mitteilen, welchen Typ die Daten in der Liste tatsächlich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0d335-118">More than that, however, there is no way to tell at compile time what is the actual type of the data in the list.</span></span> <span data-ttu-id="0d335-119">Dies beeinträchtigt die Stabilität des Codes.</span><span class="sxs-lookup"><span data-stu-id="0d335-119">This makes for some fragile code.</span></span> <span data-ttu-id="0d335-120">Generika lösen dieses Problem, indem sie zusätzliche Informationen zum Datentyp bereitstellen, die in jeder Instanz der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="0d335-120">Generics solve this problem by providing additional information the type of data each instance of list will contain.</span></span> <span data-ttu-id="0d335-121">Einfach gesagt: Zu `List<int>` können Sie nur Ganzzahlen hinzufügen, zu `List<Person>` nur Personen usw.</span><span class="sxs-lookup"><span data-stu-id="0d335-121">Put simply, you can only add integers to `List<int>` and only add Persons to `List<Person>`, etc.</span></span>

<span data-ttu-id="0d335-122">Generika sind auch zur Laufzeit verfügbar und werden **konkretisiert**.</span><span class="sxs-lookup"><span data-stu-id="0d335-122">Generics are also available at runtime, or **reified**.</span></span> <span data-ttu-id="0d335-123">Dies bedeutet, dass die Runtime weiß, welche Art Datenstruktur Sie verwenden, und die Daten effizienter im Arbeitsspeicher speichern kann.</span><span class="sxs-lookup"><span data-stu-id="0d335-123">This means the runtime knows what type of data structure you are using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="0d335-124">Das folgende Programm zeigt, wie effizient es ist, wenn die Art der Datenstruktur zur Laufzeit bekannt ist:</span><span class="sxs-lookup"><span data-stu-id="0d335-124">Here is a small program that illustrates the efficiency of knowing the data structure type at runtime:</span></span>

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

<span data-ttu-id="0d335-125">Das Programm erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0d335-125">This program yields the following output:</span></span>

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms
```

<span data-ttu-id="0d335-126">Als erstes bemerken Sie, dass das Sortieren der generischen Liste erheblich schneller ist als bei der nicht generischen Liste.</span><span class="sxs-lookup"><span data-stu-id="0d335-126">The first thing you notice here is that sorting the generic list is significantly faster than for the non-generic list.</span></span> <span data-ttu-id="0d335-127">Sie stellen vermutlich auch fest, dass der Typ für die generische Liste eindeutig ([System.Int32]), der Typ für die nicht generische Liste dagegen generalisiert ist.</span><span class="sxs-lookup"><span data-stu-id="0d335-127">You might also notice that the type for the generic list is distinct ([System.Int32]) whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="0d335-128">Da der Runtime bekannt ist, dass die generische `List<int>` den Typ „int“ aufweist, kann sie die Listenelemente in einem zugrunde liegenden ganzzahligen Array im Arbeitsspeicher speichern. Die nicht generische `ArrayList` dagegen muss jedes Listenelement in ein Objekt umwandeln, das in einem Objektarray im Arbeitsspeicher gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="0d335-128">Because the runtime knows the generic `List<int>` is of type int, it can store the list elements in an underlying integer array in memory while the non-generic `ArrayList` has to cast each list element as an object as stored in an object array in memory.</span></span> <span data-ttu-id="0d335-129">Wie in diesem Beispiel gezeigt, beanspruchen die Umwandlungen Zeit und verlangsamen den Sortiervorgang für die Liste.</span><span class="sxs-lookup"><span data-stu-id="0d335-129">As shown through this example, the extra castings take up time and slow down the list sort.</span></span>

<span data-ttu-id="0d335-130">Ein weiterer nützlicher Vorteil: Wenn die Runtime den Typ der Generika kennt, wird das Debuggen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="0d335-130">The last useful thing about the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="0d335-131">Wenn Sie Generika in C# debuggen, wissen Sie, welchen Typ jedes Element in Ihrer Datenstruktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="0d335-131">When you are debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="0d335-132">Ohne Generika wüssten Sie dies nicht.</span><span class="sxs-lookup"><span data-stu-id="0d335-132">Without generics, you would have no idea what type each element was.</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="0d335-133">Weitere Informationen und Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0d335-133">Further reading and resources</span></span>

*   [<span data-ttu-id="0d335-134">Einführung in Generika in C#</span><span class="sxs-lookup"><span data-stu-id="0d335-134">An Introduction to C# Generics</span></span>](https://msdn.microsoft.com/library/ms379564.aspx)
*   [<span data-ttu-id="0d335-135">C#-Programmierhandbuch – Generika</span><span class="sxs-lookup"><span data-stu-id="0d335-135">C# Programming Guide - Generics</span></span>](../../docs/csharp/programming-guide/generics/index.md)
