---
title: Ausnahmen und Leistung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfffc2a1c0f607541194a7f51717d5bf8a8537f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575335"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="34afb-102">Ausnahmen und Leistung</span><span class="sxs-lookup"><span data-stu-id="34afb-102">Exceptions and Performance</span></span>
<span data-ttu-id="34afb-103">Eine allgemeine Sorge, die im Zusammenhang mit Ausnahmen ist, dass Ausnahmen für Code verwendet werden, die routinemäßig fehlschlägt, die Leistung der Implementierung nicht akzeptabel ist.</span><span class="sxs-lookup"><span data-stu-id="34afb-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="34afb-104">Dies ist eine gültige relevant.</span><span class="sxs-lookup"><span data-stu-id="34afb-104">This is a valid concern.</span></span> <span data-ttu-id="34afb-105">Wenn ein Element eine Ausnahme auslöst, kann die Leistung erheblich langsamer sein.</span><span class="sxs-lookup"><span data-stu-id="34afb-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="34afb-106">Allerdings ist es möglich, die gute Leistung bei der Einhaltung streng an die Ausnahme, die mit Fehlercodes zu unterbinden, erzielen.</span><span class="sxs-lookup"><span data-stu-id="34afb-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="34afb-107">Zwei Muster, die in diesem Abschnitt beschriebenen Möglichkeiten vorgeschlagen, dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="34afb-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="34afb-108">**X DO NOT** Fehlercodes aufgrund von Bedenken, dass Ausnahmen die Leistung negativ beeinträchtigen können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34afb-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="34afb-109">Um die Leistung zu verbessern, ist es möglich, verwenden Sie entweder die Tester-Ausführer oder Wiederholen Sie den Analyse-Muster, in den nächsten beiden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34afb-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="34afb-110">Tester-Ausführer-Muster</span><span class="sxs-lookup"><span data-stu-id="34afb-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="34afb-111">Manchmal kann die Leistung eines Members eine Ausnahme auslösen kann durch das Element in zwei wichtige verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="34afb-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="34afb-112">Sehen wir uns die <xref:System.Collections.Generic.ICollection%601.Add%2A> Methode der <xref:System.Collections.Generic.ICollection%601> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="34afb-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="34afb-113">Die Methode `Add` löst aus, wenn die Auflistung schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="34afb-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="34afb-114">Dies kann ein Leistungsproblem in Szenarien, in dem häufig ein Aufruf der Methode erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="34afb-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="34afb-115">Eine der Methoden, um das Problem zu lindern ist zu prüfen, ob die Auflistung schreibgeschützt ist, bevor Sie versuchen, einen Wert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="34afb-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="34afb-116">Das Element verwendet, um eine Bedingung zu testen, in unserem Beispiel die Eigenschaft ist `IsReadOnly`, wird als der Tester bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="34afb-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="34afb-117">Das Element verwendet, um eine potenziell auslösenden Vorgang die `Add` Methode in unserem Beispiel ist als der Ausführer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="34afb-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="34afb-118">**✓ CONSIDER** der Tester-Ausführer-Muster für Member, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="34afb-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="34afb-119">Wiederholen Sie den Analyse-Muster</span><span class="sxs-lookup"><span data-stu-id="34afb-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="34afb-120">Für extrem leistungsabhängigen-APIs sollte eine schnellere Muster als das Tester-Ausführer-Muster, die im vorherigen Abschnitt beschrieben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34afb-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="34afb-121">Das Muster Ruft für die Anpassung der Elementname, um einen klar definierten Test case-Teil der Member-Semantik zu machen.</span><span class="sxs-lookup"><span data-stu-id="34afb-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="34afb-122">Beispielsweise <xref:System.DateTime> definiert eine <xref:System.DateTime.Parse%2A> Methode, die eine Ausnahme auslöst, wenn Analysieren einer Zeichenfolge ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="34afb-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="34afb-123">Er definiert außerdem eine entsprechende <xref:System.DateTime.TryParse%2A> -Methode, die versucht, zu analysieren, jedoch "false" zurückgegeben, wenn die Analyse nicht erfolgreich, und gibt das Ergebnis eines erfolgreichen Analyse mithilfe einer `out` Parameter.</span><span class="sxs-lookup"><span data-stu-id="34afb-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 <span data-ttu-id="34afb-124">Wenn Sie dieses Muster zu verwenden, ist es wichtig, die Funktionen der Try strict ausgedrückt definieren.</span><span class="sxs-lookup"><span data-stu-id="34afb-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="34afb-125">Wenn das Element aus irgendeinem Grund klar definierten wiederholen Sie dann ein Fehler auftritt, muss das Element noch eine entsprechende Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="34afb-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="34afb-126">**✓ CONSIDER** des Try-Analyse-Musters für Elemente, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="34afb-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="34afb-127">**✓ DO** verwenden Sie das Präfix "Try" und einen booleschen Wert Rückgabetyp für Methoden, die dieses Muster implementieren.</span><span class="sxs-lookup"><span data-stu-id="34afb-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="34afb-128">**✓ DO** stellen eine Ausnahme auslösen kann für jedes Element mit dem Try-Analyse-Muster.</span><span class="sxs-lookup"><span data-stu-id="34afb-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="34afb-129">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="34afb-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="34afb-130">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="34afb-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34afb-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34afb-131">See Also</span></span>  
 [<span data-ttu-id="34afb-132">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="34afb-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="34afb-133">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="34afb-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
