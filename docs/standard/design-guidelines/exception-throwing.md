---
title: Auslösen von Ausnahmen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fbbe84811e3fa096b9e13c459143311bb75a198
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46288250"
---
# <a name="exception-throwing"></a><span data-ttu-id="39d3c-102">Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="39d3c-102">Exception Throwing</span></span>
<span data-ttu-id="39d3c-103">In diesem Abschnitt beschriebene Richtlinien für die eine Ausnahme auslösen müssen klare Definition der Bedeutung des Fehler bei der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="39d3c-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="39d3c-104">Fehler bei der Ausführung tritt auf, wenn ein Member nicht möglich, was es ist vorgesehen haben (was der Membername impliziert).</span><span class="sxs-lookup"><span data-stu-id="39d3c-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="39d3c-105">Z. B. wenn die `OpenFile` Methode kann keinen geöffneten Dateihandle an den Aufrufer zurückgeben, es Fehler bei der Ausführung betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="39d3c-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>  
  
 <span data-ttu-id="39d3c-106">Die meisten Entwickler sind mit der Verwendung von Ausnahmen für Fehler z. B. Division durch 0 (null) oder null-Verweise vertraut geworden.</span><span class="sxs-lookup"><span data-stu-id="39d3c-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="39d3c-107">Im Framework werden Ausnahmen für alle fehlerbedingungen, einschließlich der Fehler bei der Ausführung verwendet.</span><span class="sxs-lookup"><span data-stu-id="39d3c-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>  
  
 <span data-ttu-id="39d3c-108">**X DO NOT** Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="39d3c-108">**X DO NOT** return error codes.</span></span>  
  
 <span data-ttu-id="39d3c-109">Ausnahmen sind das primäre Mittel zum Melden von Fehlern in Frameworks.</span><span class="sxs-lookup"><span data-stu-id="39d3c-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>  
  
 <span data-ttu-id="39d3c-110">**✓ DO** Ausführungsfehler durch das Auslösen von Ausnahmen gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="39d3c-110">**✓ DO** report execution failures by throwing exceptions.</span></span>  
  
 <span data-ttu-id="39d3c-111">**✓ CONSIDER** Beenden des Prozesses durch Aufrufen von `System.Environment.FailFast` (Feature von .NET Framework 2.0) anstatt eine Ausnahme auszulösen, wenn Ihr Code eine Situation vorfindet, wo es unsicher, für die weitere Ausführung ist.</span><span class="sxs-lookup"><span data-stu-id="39d3c-111">**✓ CONSIDER** terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>  
  
 <span data-ttu-id="39d3c-112">**X DO NOT** verwenden Sie Ausnahmen für die normale ablaufsteuerung, falls möglich.</span><span class="sxs-lookup"><span data-stu-id="39d3c-112">**X DO NOT** use exceptions for the normal flow of control, if possible.</span></span>  
  
 <span data-ttu-id="39d3c-113">Mit Ausnahme von Systemfehlern und Vorgänge mit potenzielle Racebedingungen sollten Framework Designer APIs entwickeln, damit Sie Benutzercode schreiben können, die keine Ausnahmen auslöst.</span><span class="sxs-lookup"><span data-stu-id="39d3c-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="39d3c-114">Sie können z. B. angeben, dass eine Möglichkeit zum Überprüfen von Vorbedingungen vor dem Aufrufen eines Members, damit Sie Benutzercode schreiben können, die keine Ausnahmen auslöst.</span><span class="sxs-lookup"><span data-stu-id="39d3c-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>  
  
 <span data-ttu-id="39d3c-115">Das Element, das zum Überprüfen von Vorbedingungen eines anderen Elements verwendet wird häufig als ein Tester bezeichnet, und das Element, das eigentliche Arbeit übernimmt eine Doer aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="39d3c-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>  
  
 <span data-ttu-id="39d3c-116">Es gibt Fälle, bei dem Tester-Doer-Muster einen nicht akzeptablen Leistungsaufwand haben kann.</span><span class="sxs-lookup"><span data-stu-id="39d3c-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="39d3c-117">In solchen Fällen das so genannte Versuch der Analyse Muster angesehen werden (siehe [Ausnahmen und Leistung](../../../docs/standard/design-guidelines/exceptions-and-performance.md) für Weitere Informationen).</span><span class="sxs-lookup"><span data-stu-id="39d3c-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>  
  
 <span data-ttu-id="39d3c-118">**✓ CONSIDER** Leistungseinbußen bei der Auslösen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="39d3c-118">**✓ CONSIDER** the performance implications of throwing exceptions.</span></span> <span data-ttu-id="39d3c-119">Throw-Preise über 100 pro Sekunde werden wahrscheinlich deutlich die Leistung der meisten Anwendungen auswirken.</span><span class="sxs-lookup"><span data-stu-id="39d3c-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>  
  
 <span data-ttu-id="39d3c-120">**✓ DO** Dokument alle Ausnahmen öffentlich aufrufbare Member aufgrund einer Verletzung des Elements (anstatt aufgrund eines Systemfehlers) Vertrag, und behandeln Sie sie als Bestandteil des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="39d3c-120">**✓ DO** document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>  
  
 <span data-ttu-id="39d3c-121">Ausnahmen, die Teil des Vertrags sind sollten nicht von einer Version zur nächsten ändern (d. h. Typ der Ausnahme sollte nicht geändert werden und neue Ausnahmen sollten nicht hinzugefügt werden).</span><span class="sxs-lookup"><span data-stu-id="39d3c-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>  
  
 <span data-ttu-id="39d3c-122">**X DO NOT** haben öffentliche Member, die entweder auslösen oder keine können basierend auf bestimmte Option.</span><span class="sxs-lookup"><span data-stu-id="39d3c-122">**X DO NOT** have public members that can either throw or not based on some option.</span></span>  
  
 <span data-ttu-id="39d3c-123">**X DO NOT** öffentliche Member, die zum Zurückgeben von Ausnahmen als Rückgabewert oder ein `out` Parameter.</span><span class="sxs-lookup"><span data-stu-id="39d3c-123">**X DO NOT** have public members that return exceptions as the return value or an `out` parameter.</span></span>  
  
 <span data-ttu-id="39d3c-124">Zurückgeben von Ausnahmen von öffentlichen APIs, statt sie verfehlt viele der Vorteile bei der Fehlerberichterstattung ausnahmebasierten.</span><span class="sxs-lookup"><span data-stu-id="39d3c-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>  
  
 <span data-ttu-id="39d3c-125">**✓ CONSIDER** Ausnahme-Generator-Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="39d3c-125">**✓ CONSIDER** using exception builder methods.</span></span>  
  
 <span data-ttu-id="39d3c-126">Es ist üblich, die an verschiedenen Stellen die gleiche Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="39d3c-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="39d3c-127">Um codeüberfrachtung zu vermeiden, verwenden Sie Hilfsmethoden, die erstellen Sie Ausnahmen und deren Eigenschaften zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="39d3c-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>  
  
 <span data-ttu-id="39d3c-128">Darüber hinaus werden Elemente, die Ausnahmen auslösen nicht immer inline ersetzt.</span><span class="sxs-lookup"><span data-stu-id="39d3c-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="39d3c-129">Verschieben die Throw-Anweisung in der Generator, kann das Element zu setzende machen.</span><span class="sxs-lookup"><span data-stu-id="39d3c-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>  
  
 <span data-ttu-id="39d3c-130">**X DO NOT** lösen Ausnahmen aus Ausnahmeblöcke-Filter.</span><span class="sxs-lookup"><span data-stu-id="39d3c-130">**X DO NOT** throw exceptions from exception filter blocks.</span></span>  
  
 <span data-ttu-id="39d3c-131">Wenn ein Ausnahmefilter eine Ausnahme auslöst, wird die Ausnahme von der CLR und der Filter "false" zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="39d3c-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="39d3c-132">Dieses Verhalten wird nicht aus dem Filter ausführen, und false zurückgibt, explizit zu unterscheiden und ist daher sehr schwer zu beheben.</span><span class="sxs-lookup"><span data-stu-id="39d3c-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>  
  
 <span data-ttu-id="39d3c-133">**X AVOID** explizit Auslösen von Ausnahmen von finally-Blöcke.</span><span class="sxs-lookup"><span data-stu-id="39d3c-133">**X AVOID** explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="39d3c-134">Implizit ausgelöste Ausnahmen, die durch Aufrufen von Methoden, die auslösen, sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="39d3c-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>  
  
 <span data-ttu-id="39d3c-135">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="39d3c-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="39d3c-136">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="39d3c-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d3c-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39d3c-137">See also</span></span>

- [<span data-ttu-id="39d3c-138">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="39d3c-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="39d3c-139">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="39d3c-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
