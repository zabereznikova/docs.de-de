---
title: Ausnahmen und Leistung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7972cf7d63ee22e791d46046f30c9be467cc758e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="0cced-102">Ausnahmen und Leistung</span><span class="sxs-lookup"><span data-stu-id="0cced-102">Exceptions and Performance</span></span>
<span data-ttu-id="0cced-103">Eine allgemeine Sorge, die im Zusammenhang mit Ausnahmen ist, dass Ausnahmen für Code verwendet werden, die routinemäßig fehlschlägt, die Leistung der Implementierung nicht akzeptabel ist.</span><span class="sxs-lookup"><span data-stu-id="0cced-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="0cced-104">Dies ist eine gültige relevant.</span><span class="sxs-lookup"><span data-stu-id="0cced-104">This is a valid concern.</span></span> <span data-ttu-id="0cced-105">Wenn ein Element eine Ausnahme auslöst, kann die Leistung erheblich langsamer sein.</span><span class="sxs-lookup"><span data-stu-id="0cced-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="0cced-106">Allerdings ist es möglich, die gute Leistung bei der Einhaltung streng an die Ausnahme, die mit Fehlercodes zu unterbinden, erzielen.</span><span class="sxs-lookup"><span data-stu-id="0cced-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="0cced-107">Zwei Muster, die in diesem Abschnitt beschriebenen Möglichkeiten vorgeschlagen, dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="0cced-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="0cced-108">**X nicht** Fehlercodes aufgrund von Bedenken, dass Ausnahmen die Leistung negativ beeinträchtigen können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cced-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="0cced-109">Um die Leistung zu verbessern, ist es möglich, verwenden Sie entweder die Tester-Ausführer oder Wiederholen Sie den Analyse-Muster, in den nächsten beiden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0cced-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="0cced-110">Tester-Ausführer-Muster</span><span class="sxs-lookup"><span data-stu-id="0cced-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="0cced-111">Manchmal kann die Leistung eines Members eine Ausnahme auslösen kann durch das Element in zwei wichtige verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="0cced-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="0cced-112">Sehen wir uns die <xref:System.Collections.Generic.ICollection%601.Add%2A> Methode der <xref:System.Collections.Generic.ICollection%601> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0cced-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="0cced-113">Die Methode `Add` löst aus, wenn die Auflistung schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="0cced-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="0cced-114">Dies kann ein Leistungsproblem in Szenarien, in dem häufig ein Aufruf der Methode erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="0cced-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="0cced-115">Eine der Methoden, um das Problem zu lindern ist zu prüfen, ob die Auflistung schreibgeschützt ist, bevor Sie versuchen, einen Wert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0cced-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="0cced-116">Das Element verwendet, um eine Bedingung zu testen, in unserem Beispiel die Eigenschaft ist `IsReadOnly`, wird als der Tester bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0cced-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="0cced-117">Das Element verwendet, um eine potenziell auslösenden Vorgang die `Add` Methode in unserem Beispiel ist als der Ausführer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0cced-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="0cced-118">**✓ GGF.** der Tester-Ausführer-Muster für Member, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="0cced-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="0cced-119">Wiederholen Sie den Analyse-Muster</span><span class="sxs-lookup"><span data-stu-id="0cced-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="0cced-120">Für extrem leistungsabhängigen-APIs sollte eine schnellere Muster als das Tester-Ausführer-Muster, die im vorherigen Abschnitt beschrieben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cced-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="0cced-121">Das Muster Ruft für die Anpassung der Elementname, um einen klar definierten Test case-Teil der Member-Semantik zu machen.</span><span class="sxs-lookup"><span data-stu-id="0cced-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="0cced-122">Beispielsweise <xref:System.DateTime> definiert eine <xref:System.DateTime.Parse%2A> Methode, die eine Ausnahme auslöst, wenn Analysieren einer Zeichenfolge ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="0cced-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="0cced-123">Er definiert außerdem eine entsprechende <xref:System.DateTime.TryParse%2A> -Methode, die versucht, zu analysieren, jedoch "false" zurückgegeben, wenn die Analyse nicht erfolgreich, und gibt das Ergebnis eines erfolgreichen Analyse mithilfe einer `out` Parameter.</span><span class="sxs-lookup"><span data-stu-id="0cced-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
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
  
 <span data-ttu-id="0cced-124">Wenn Sie dieses Muster zu verwenden, ist es wichtig, die Funktionen der Try strict ausgedrückt definieren.</span><span class="sxs-lookup"><span data-stu-id="0cced-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="0cced-125">Wenn das Element aus irgendeinem Grund klar definierten wiederholen Sie dann ein Fehler auftritt, muss das Element noch eine entsprechende Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="0cced-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="0cced-126">**✓ GGF.** des Try-Analyse-Musters für Elemente, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="0cced-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="0cced-127">**Führen Sie ✓** verwenden Sie das Präfix "Try" und einen booleschen Wert Rückgabetyp für Methoden, die dieses Muster implementieren.</span><span class="sxs-lookup"><span data-stu-id="0cced-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="0cced-128">**Führen Sie ✓** stellen eine Ausnahme auslösen kann für jedes Element mit dem Try-Analyse-Muster.</span><span class="sxs-lookup"><span data-stu-id="0cced-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="0cced-129">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="0cced-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0cced-130">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="0cced-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cced-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cced-131">See Also</span></span>  
 [<span data-ttu-id="0cced-132">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0cced-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="0cced-133">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0cced-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
