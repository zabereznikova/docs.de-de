---
title: "Generische Typen (Generika) – Übersicht"
description: "Erfahren Sie, wie Generika als Codevorlagen fungieren, mit denen Sie typsichere Datenstrukturen definieren können, ohne sich auf einen Datentyp festlegen zu müssen."
keywords: .NET, .NET Core
author: kuhlenh
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
ms.translationtype: HT
ms.sourcegitcommit: 934373d61407c8cc19b7d6424898a582880f9c21
ms.openlocfilehash: 08b8de2fe17a0032a1c1180667f39b1d6ce0feb6
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---

# <a name="generic-types-generics-overview"></a><span data-ttu-id="7f0c6-104">Generische Typen (Generika) – Übersicht</span><span class="sxs-lookup"><span data-stu-id="7f0c6-104">Generic Types (Generics) Overview</span></span>

<span data-ttu-id="7f0c6-105">Generika werden andauernd in C# verwendet, entweder implizit oder explizit.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-105">We use generics all the time in C#, whether implicitly or explicitly.</span></span> <span data-ttu-id="7f0c6-106">Wenn Sie LINQ in C# verwenden, haben Sie schon einmal bemerkt, dass Sie mit IEnumerable<T> arbeiten?</span><span class="sxs-lookup"><span data-stu-id="7f0c6-106">When you use LINQ in C#, did you ever notice that you are working with IEnumerable<T>?</span></span> <span data-ttu-id="7f0c6-107">Oder haben Sie in einem Onlinebeispiel eines „generischen Repositorys“ zur Kommunikation mit Datenbanken über Entity Framework festgestellt, dass die meisten Methoden IQueryable<T> zurückgeben?</span><span class="sxs-lookup"><span data-stu-id="7f0c6-107">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return IQueryable<T>?</span></span> <span data-ttu-id="7f0c6-108">Haben Sie sich gefragt, wofür das **T** in diesen Beispielen steht und warum es dort ist?</span><span class="sxs-lookup"><span data-stu-id="7f0c6-108">You may have wondered what the **T** is in these examples and why is it in there?</span></span>

<span data-ttu-id="7f0c6-109">Generika wurden zum ersten Mal in .NET Framework 2.0 eingeführt und umfassten Änderungen sowohl an der Sprache C# als auch an der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7f0c6-109">First introduced to the .NET Framework 2.0, generics involved changes to both the C# language and the Common Language Runtime (CLR).</span></span> <span data-ttu-id="7f0c6-110">**Generika** sind im Grunde eine „Codevorlage“, mit der Entwickler [typsichere](https://msdn.microsoft.com/library/hbzz1a9a.aspx) Datenstrukturen definieren können, ohne sich tatsächlich auf einen Datentyp festlegen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-110">**Generics** are essentially a "code template" that allows developers to define [type-safe](https://msdn.microsoft.com/library/hbzz1a9a.aspx) data structures without committing to an actual data type.</span></span> <span data-ttu-id="7f0c6-111">`List<T>` ist beispielsweise eine [generische Auflistung](xref:System.Collections.Generic), die deklariert und mit beliebigen Typen verwendet werden kann: `List<int>`, `List<string>`, `List<Person>` usw.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-111">For example, `List<T>` is a [Generic Collection](xref:System.Collections.Generic) that can be declared and used with any type: `List<int>`, `List<string>`, `List<Person>`, etc.</span></span>

<span data-ttu-id="7f0c6-112">Worum liegt also der Sinn?</span><span class="sxs-lookup"><span data-stu-id="7f0c6-112">So, what’s the point?</span></span> <span data-ttu-id="7f0c6-113">Warum sind Generika nützlich?</span><span class="sxs-lookup"><span data-stu-id="7f0c6-113">Why are generics useful?</span></span> <span data-ttu-id="7f0c6-114">Um dies zu verstehen, müssen wir uns eine bestimmte Klasse ansehen, und zwar vor und nach dem Hinzufügen von Generika.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-114">In order to understand this, we need to take a look at a specific class before and after adding generics.</span></span> <span data-ttu-id="7f0c6-115">Wir sehen uns `ArrayList` an.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-115">Let’s look at the `ArrayList`.</span></span> <span data-ttu-id="7f0c6-116">In C# 1.0 wiesen die `ArrayList`-Elemente den Typ `object` auf.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-116">In C# 1.0, the `ArrayList` elements were of type `object`.</span></span> <span data-ttu-id="7f0c6-117">Dies bedeutete, dass jedes hinzugefügte Element im Hintergrund in ein `object` konvertiert wurde. Das Gleiche passierte beim Lesen der Elemente aus der Liste (dieser Prozess wird als [Boxing](https://msdn.microsoft.com/library/yz2be5wk.aspx) bzw. Unboxing bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="7f0c6-117">This meant that any element that was added was silently converted into an `object`; same thing happens on reading the elements from the list (this process is known as [boxing](https://msdn.microsoft.com/library/yz2be5wk.aspx) and unboxing respectively).</span></span> <span data-ttu-id="7f0c6-118">Boxing und Unboxing wirken sich auf die Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-118">Boxing and unboxing have an impact of performance.</span></span> <span data-ttu-id="7f0c6-119">Schlimmer noch: Zum Zeitpunkt der Kompilierung lässt sich nicht mitteilen, welchen Typ die Daten in der Liste tatsächlich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-119">More than that, however, there is no way to tell at compile time what is the actual type of the data in the list.</span></span> <span data-ttu-id="7f0c6-120">Dies beeinträchtigt die Stabilität des Codes.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-120">This makes for some fragile code.</span></span> <span data-ttu-id="7f0c6-121">Generika lösen dieses Problem, indem sie zusätzliche Informationen zum Datentyp bereitstellen, die in jeder Instanz der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-121">Generics solve this problem by providing additional information the type of data each instance of list will contain.</span></span> <span data-ttu-id="7f0c6-122">Einfach gesagt: Zu `List<int>` können Sie nur Ganzzahlen hinzufügen, zu `List<Person>` nur Personen usw.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-122">Put simply, you can only add integers to `List<int>` and only add Persons to `List<Person>`, etc.</span></span>

<span data-ttu-id="7f0c6-123">Generika sind auch zur Laufzeit verfügbar und werden **konkretisiert**.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-123">Generics are also available at runtime, or **reified**.</span></span> <span data-ttu-id="7f0c6-124">Dies bedeutet, dass die Runtime weiß, welche Art Datenstruktur Sie verwenden, und die Daten effizienter im Arbeitsspeicher speichern kann.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-124">This means the runtime knows what type of data structure you are using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="7f0c6-125">Das folgende Programm zeigt, wie effizient es ist, wenn die Art der Datenstruktur zur Laufzeit bekannt ist:</span><span class="sxs-lookup"><span data-stu-id="7f0c6-125">Here is a small program that illustrates the efficiency of knowing the data structure type at runtime:</span></span>

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

<span data-ttu-id="7f0c6-126">Das Programm erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7f0c6-126">This program yields the following output:</span></span>

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms
```

<span data-ttu-id="7f0c6-127">Als erstes bemerken Sie, dass das Sortieren der generischen Liste erheblich schneller ist als bei der nicht generischen Liste.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-127">The first thing you notice here is that sorting the generic list is significantly faster than for the non-generic list.</span></span> <span data-ttu-id="7f0c6-128">Sie stellen vermutlich auch fest, dass der Typ für die generische Liste eindeutig ([System.Int32]), der Typ für die nicht generische Liste dagegen generalisiert ist.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-128">You might also notice that the type for the generic list is distinct ([System.Int32]) whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="7f0c6-129">Da der Runtime bekannt ist, dass die generische `List<int>` den Typ „int“ aufweist, kann sie die Listenelemente in einem zugrunde liegenden ganzzahligen Array im Arbeitsspeicher speichern. Die nicht generische `ArrayList` dagegen muss jedes Listenelement in ein Objekt umwandeln, das in einem Objektarray im Arbeitsspeicher gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-129">Because the runtime knows the generic `List<int>` is of type int, it can store the list elements in an underlying integer array in memory while the non-generic `ArrayList` has to cast each list element as an object as stored in an object array in memory.</span></span> <span data-ttu-id="7f0c6-130">Wie in diesem Beispiel gezeigt, beanspruchen die Umwandlungen Zeit und verlangsamen den Sortiervorgang für die Liste.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-130">As shown through this example, the extra castings take up time and slow down the list sort.</span></span>

<span data-ttu-id="7f0c6-131">Ein weiterer nützlicher Vorteil: Wenn die Runtime den Typ der Generika kennt, wird das Debuggen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-131">The last useful thing about the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="7f0c6-132">Wenn Sie Generika in C# debuggen, wissen Sie, welchen Typ jedes Element in Ihrer Datenstruktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-132">When you are debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="7f0c6-133">Ohne Generika wüssten Sie dies nicht.</span><span class="sxs-lookup"><span data-stu-id="7f0c6-133">Without generics, you would have no idea what type each element was.</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="7f0c6-134">Weitere Informationen und Ressourcen</span><span class="sxs-lookup"><span data-stu-id="7f0c6-134">Further reading and resources</span></span>

*   [<span data-ttu-id="7f0c6-135">Einführung in Generika in C#</span><span class="sxs-lookup"><span data-stu-id="7f0c6-135">An Introduction to C# Generics</span></span>](https://msdn.microsoft.com/library/ms379564.aspx)
*   [<span data-ttu-id="7f0c6-136">C#-Programmierhandbuch – Generika</span><span class="sxs-lookup"><span data-stu-id="7f0c6-136">C# Programming Guide - Generics</span></span>](https://msdn.microsoft.com/library/512aeb7t.aspx)

