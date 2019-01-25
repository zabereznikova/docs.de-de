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
author: KrzysztofCwalina
ms.openlocfilehash: f9fe3045d8bd8b4d625c5cd49bc18574ebb740de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707725"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="95b7f-102">Ausnahmen und Leistung</span><span class="sxs-lookup"><span data-stu-id="95b7f-102">Exceptions and Performance</span></span>
<span data-ttu-id="95b7f-103">Eine häufige Problem im Zusammenhang mit Ausnahmen ist, wenn Ausnahmen für Code, die routinemäßig ein Fehler auftritt verwendet werden, die Leistung der Implementierung nicht akzeptabel sein wird.</span><span class="sxs-lookup"><span data-stu-id="95b7f-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="95b7f-104">Dies ist ein Grund zur Sorge.</span><span class="sxs-lookup"><span data-stu-id="95b7f-104">This is a valid concern.</span></span> <span data-ttu-id="95b7f-105">Wenn ein Element eine Ausnahme auslöst, kann die Leistung erheblich langsamer sein.</span><span class="sxs-lookup"><span data-stu-id="95b7f-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="95b7f-106">Allerdings ist es möglich, erzielen gute Leistung bei strikt befolgen Sie die Ausnahme-Richtlinien, die nicht zulassen, mit Fehlercodes.</span><span class="sxs-lookup"><span data-stu-id="95b7f-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="95b7f-107">Zwei Muster, die in diesem Abschnitt beschriebenen Möglichkeiten vorgeschlagen, dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="95b7f-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="95b7f-108">**X DO NOT** Fehlercodes aufgrund von Bedenken, dass Ausnahmen die Leistung negativ beeinträchtigen können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="95b7f-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="95b7f-109">Zur Verbesserung der Leistung ist es möglich, verwenden entweder die Tester-Doer-Muster oder dem Versuch der Analyse Muster in den nächsten beiden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95b7f-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="95b7f-110">Tester-Doer-Muster</span><span class="sxs-lookup"><span data-stu-id="95b7f-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="95b7f-111">Leistung der ein Element eine Ausnahme auslösen kann manchmal verbessert werden, von der Members in zwei wichtige.</span><span class="sxs-lookup"><span data-stu-id="95b7f-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="95b7f-112">Sehen wir uns die <xref:System.Collections.Generic.ICollection%601.Add%2A> Methode der <xref:System.Collections.Generic.ICollection%601> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="95b7f-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="95b7f-113">Die Methode `Add` wird ausgelöst, wenn die Auflistung schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="95b7f-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="95b7f-114">Dies kann ein Leistungsproblem in Szenarien sein, die dem Aufruf der Methode erwartet wird, häufig fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="95b7f-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="95b7f-115">Eine der Möglichkeiten, um das Problem zu lindern ist zum Überprüfen, ob die Auflistung schreibgeschützt ist, bevor Sie versuchen, einen Wert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="95b7f-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="95b7f-116">Der Member, die mit dem Testen einer Bedingung, die in unserem Beispiel die Eigenschaft ist `IsReadOnly`, wird als der Tester bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="95b7f-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="95b7f-117">Das Element verwendet, um eine ggf. auslösenden Operation ausführen, die `Add` -Methode in unserem Beispiel ist als die Doer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="95b7f-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="95b7f-118">**✓ CONSIDER** der Tester-Ausführer-Muster für Member, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="95b7f-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="95b7f-119">Try-Analysemuster</span><span class="sxs-lookup"><span data-stu-id="95b7f-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="95b7f-120">Für äußerst leistungsabhängigen-APIs sollte eine Muster für die sogar noch schnellere als das Tester-Doer-Muster, das im vorherigen Abschnitt beschrieben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="95b7f-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="95b7f-121">Das Muster Ruft für die Anpassung der Membername, um eine klar definierte Test case-Teil von der Members-Semantik zu machen.</span><span class="sxs-lookup"><span data-stu-id="95b7f-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="95b7f-122">Z. B. <xref:System.DateTime> definiert eine <xref:System.DateTime.Parse%2A> -Methode, die eine Ausnahme auslöst, wenn ein Fehler mit der Analyse einer Zeichenfolge auftritt.</span><span class="sxs-lookup"><span data-stu-id="95b7f-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="95b7f-123">Sie definiert außerdem eine entsprechende <xref:System.DateTime.TryParse%2A> -Methode, die versucht, zu analysieren, gibt aber "false" zurück, wenn die Analyse nicht erfolgreich ist, und gibt das Ergebnis eines erfolgreichen Analyse mit einer `out` Parameter.</span><span class="sxs-lookup"><span data-stu-id="95b7f-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
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
  
 <span data-ttu-id="95b7f-124">Wenn Sie dieses Muster verwenden, ist es wichtig, die die Funktionalität versuchen Sie es im strict-Bedingungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="95b7f-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="95b7f-125">Wenn das Element einem anderen Grund als der klar definierte Versuch fehlschlägt, muss das Element immer noch eine entsprechende Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="95b7f-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="95b7f-126">**✓ CONSIDER** des Try-Analyse-Musters für Elemente, die Ausnahmen auslösen können Szenarien, um Leistungsprobleme zu vermeiden gemeinsam mit Ausnahmen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="95b7f-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="95b7f-127">**✓ DO** verwenden Sie das Präfix "Try" und einen booleschen Wert Rückgabetyp für Methoden, die dieses Muster implementieren.</span><span class="sxs-lookup"><span data-stu-id="95b7f-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="95b7f-128">**✓ DO** stellen eine Ausnahme auslösen kann für jedes Element mit dem Try-Analyse-Muster.</span><span class="sxs-lookup"><span data-stu-id="95b7f-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="95b7f-129">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="95b7f-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="95b7f-130">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="95b7f-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b7f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95b7f-131">See also</span></span>

- [<span data-ttu-id="95b7f-132">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="95b7f-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="95b7f-133">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="95b7f-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
