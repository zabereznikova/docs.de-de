---
title: Ausnahmen und Leistung
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: afa4e748599781a5979823320d8913ff5357d415
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741641"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="36754-102">Ausnahmen und Leistung</span><span class="sxs-lookup"><span data-stu-id="36754-102">Exceptions and Performance</span></span>
<span data-ttu-id="36754-103">Ein häufiges Problem im Zusammenhang mit Ausnahmen besteht darin, dass die Leistung der Implementierung nicht akzeptabel ist, wenn Ausnahmen für Code verwendet werden, der routinemäßig fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="36754-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="36754-104">Dies ist ein gültiges Problem.</span><span class="sxs-lookup"><span data-stu-id="36754-104">This is a valid concern.</span></span> <span data-ttu-id="36754-105">Wenn ein Member eine Ausnahme auslöst, kann die Leistung der Größenordnung langsamer sein.</span><span class="sxs-lookup"><span data-stu-id="36754-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="36754-106">Es ist jedoch möglich, eine gute Leistung zu erzielen, während Sie strikt den Ausnahme Richtlinien entsprechen, die die Verwendung von Fehlercodes nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="36754-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="36754-107">In den beiden in diesem Abschnitt beschriebenen Mustern werden Möglichkeiten vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="36754-107">Two patterns described in this section suggest ways to do this.</span></span>

 <span data-ttu-id="36754-108">❌ verwenden keine Fehlercodes, da sich Ausnahmen möglicherweise negativ auf die Leistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="36754-108">❌ DO NOT use error codes because of concerns that exceptions might affect performance negatively.</span></span>

 <span data-ttu-id="36754-109">Um die Leistung zu verbessern, können Sie entweder das Tester-doer-Muster oder das Try-Analyse-Muster verwenden, das in den folgenden beiden Abschnitten beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="36754-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>

## <a name="tester-doer-pattern"></a><span data-ttu-id="36754-110">Tester-doer-Muster</span><span class="sxs-lookup"><span data-stu-id="36754-110">Tester-Doer Pattern</span></span>
 <span data-ttu-id="36754-111">Manchmal kann die Leistung eines Ausnahme auslösenden Members verbessert werden, indem der Member in zwei unterteilt wird.</span><span class="sxs-lookup"><span data-stu-id="36754-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="36754-112">Sehen wir uns die <xref:System.Collections.Generic.ICollection%601.Add%2A>-Methode der <xref:System.Collections.Generic.ICollection%601> Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="36754-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 <span data-ttu-id="36754-113">Die-Methode `Add` ausgelöst, wenn die-Auflistung schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="36754-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="36754-114">Dies kann ein Leistungsproblem in Szenarien sein, in denen der Methodenaufrufe häufig fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="36754-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="36754-115">Eine Möglichkeit, das Problem zu beheben, besteht darin, zu testen, ob die Auflistung beschreibbar ist, bevor versucht wird, einen Wert hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="36754-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 <span data-ttu-id="36754-116">Der zum Testen einer Bedingung verwendete Member, bei dem es sich in unserem Beispiel um die Eigenschaften `IsReadOnly`handelt, wird als Tester bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="36754-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="36754-117">Der Member, der verwendet wird, um einen potenziell auslösenden Vorgang auszuführen, die `Add`-Methode in unserem Beispiel, wird als doer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="36754-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>

 <span data-ttu-id="36754-118">Beachten Sie ✔️ das Tester-doer-Muster für Member, die möglicherweise Ausnahmen in häufigen Szenarien auslösen, um Leistungsprobleme im Zusammenhang mit Ausnahmen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="36754-118">✔️ CONSIDER the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

## <a name="try-parse-pattern"></a><span data-ttu-id="36754-119">Try-Analyse Muster</span><span class="sxs-lookup"><span data-stu-id="36754-119">Try-Parse Pattern</span></span>
 <span data-ttu-id="36754-120">Bei extrem leistungsabhängigen APIs sollte ein noch schnelleres Muster verwendet werden, das nicht das im vorherigen Abschnitt beschriebene Tester-doer-Muster ist.</span><span class="sxs-lookup"><span data-stu-id="36754-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="36754-121">Das Muster erfordert, dass der Elementname angepasst wird, um einen klar definierten Testfall zu einem Teil der Element Semantik zu machen.</span><span class="sxs-lookup"><span data-stu-id="36754-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="36754-122">Beispielsweise definiert <xref:System.DateTime> eine <xref:System.DateTime.Parse%2A> Methode, die eine Ausnahme auslöst, wenn die Verarbeitung einer Zeichenfolge fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="36754-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="36754-123">Außerdem wird eine entsprechende <xref:System.DateTime.TryParse%2A> Methode definiert, die versucht, eine Analyse durchzuführen, aber false zurückgibt, wenn die Analyse nicht erfolgreich ist und das Ergebnis einer erfolgreichen Analyse mithilfe eines `out`-Parameters zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="36754-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 <span data-ttu-id="36754-124">Wenn Sie dieses Muster verwenden, ist es wichtig, die try-Funktionalität in Strict-Begriffen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="36754-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="36754-125">Wenn der Member aus einem anderen Grund als dem klar definierten Versuch ausfällt, muss der Member weiterhin eine entsprechende Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="36754-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>

 <span data-ttu-id="36754-126">Beachten Sie ✔️ das Muster "try-Analyse" für Member, die möglicherweise Ausnahmen in häufigen Szenarien auslösen, um Leistungsprobleme im Zusammenhang mit Ausnahmen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="36754-126">✔️ CONSIDER the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

 <span data-ttu-id="36754-127">✔️ Verwenden Sie das Präfix "Try" und den booleschen Rückgabetyp für Methoden, die dieses Muster implementieren.</span><span class="sxs-lookup"><span data-stu-id="36754-127">✔️ DO use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>

 <span data-ttu-id="36754-128">✔️ einen auslösenden Member für jedes Element mit dem Muster "try-Analyse" bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="36754-128">✔️ DO provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>

 <span data-ttu-id="36754-129">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="36754-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="36754-130">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="36754-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="36754-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36754-131">See also</span></span>

- [<span data-ttu-id="36754-132">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="36754-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="36754-133">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="36754-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
