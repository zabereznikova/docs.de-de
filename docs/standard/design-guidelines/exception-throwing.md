---
title: Auslösen von Ausnahmen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 7d1b63e5fde57cbe37a1250d16b6bf74a2d5dc8e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709399"
---
# <a name="exception-throwing"></a><span data-ttu-id="358f7-102">Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="358f7-102">Exception Throwing</span></span>
<span data-ttu-id="358f7-103">Die in diesem Abschnitt beschriebenen Richtlinien zum Auslösen von Ausnahmen erfordern eine gute Definition der Bedeutung von Ausführungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="358f7-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="358f7-104">Ein Ausführungsfehler tritt auf, wenn ein Member nicht die Aufgaben ausführen kann, die er ausführen soll (was der Elementname impliziert).</span><span class="sxs-lookup"><span data-stu-id="358f7-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="358f7-105">Wenn die `OpenFile`-Methode z. b. kein geöffnetes Datei Handle an den Aufrufer zurückgeben kann, wird Sie als Ausführungsfehler betrachtet.</span><span class="sxs-lookup"><span data-stu-id="358f7-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>  
  
 <span data-ttu-id="358f7-106">Die meisten Entwickler sind mit der Verwendung von Ausnahmen für Verwendungs Fehler wie der Division durch Null oder NULL-Verweise vertraut.</span><span class="sxs-lookup"><span data-stu-id="358f7-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="358f7-107">Im Framework werden Ausnahmen für alle Fehlerbedingungen verwendet, einschließlich Ausführungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="358f7-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>  
  
 <span data-ttu-id="358f7-108">**X DO NOT** Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="358f7-108">**X DO NOT** return error codes.</span></span>  
  
 <span data-ttu-id="358f7-109">Ausnahmen sind die primäre Methode, Fehler in Frameworks zu melden.</span><span class="sxs-lookup"><span data-stu-id="358f7-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>  
  
 <span data-ttu-id="358f7-110">**✓ DO** Ausführungsfehler durch das Auslösen von Ausnahmen gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="358f7-110">**✓ DO** report execution failures by throwing exceptions.</span></span>  
  
 <span data-ttu-id="358f7-111">**✓ CONSIDER** Beenden des Prozesses durch Aufrufen von `System.Environment.FailFast` (Feature von .NET Framework 2.0) anstatt eine Ausnahme auszulösen, wenn Ihr Code eine Situation vorfindet, wo es unsicher, für die weitere Ausführung ist.</span><span class="sxs-lookup"><span data-stu-id="358f7-111">**✓ CONSIDER** terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>  
  
 <span data-ttu-id="358f7-112">**X DO NOT** verwenden Sie Ausnahmen für die normale ablaufsteuerung, falls möglich.</span><span class="sxs-lookup"><span data-stu-id="358f7-112">**X DO NOT** use exceptions for the normal flow of control, if possible.</span></span>  
  
 <span data-ttu-id="358f7-113">Mit Ausnahme von Systemfehlern und-Vorgängen mit potenziellen Racebedingungen sollten frameworkdesigner APIs entwerfen, damit Benutzercode schreiben können, der keine Ausnahmen auslöst.</span><span class="sxs-lookup"><span data-stu-id="358f7-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="358f7-114">Sie können z. b. eine Möglichkeit zum Überprüfen von Vorbedingungen vor dem Aufrufen eines Members bereitstellen, damit Benutzercode schreiben können, der keine Ausnahmen auslöst.</span><span class="sxs-lookup"><span data-stu-id="358f7-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>  
  
 <span data-ttu-id="358f7-115">Der Member, der zum Prüfen der Vorbedingungen eines anderen Elements verwendet wird, wird häufig als Tester bezeichnet, und der Member, der die Arbeit tatsächlich erledigt, wird als doer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="358f7-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>  
  
 <span data-ttu-id="358f7-116">Es gibt Fälle, in denen das Tester-doer-Muster einen unzulässigen Leistungs Aufwand verursachen kann.</span><span class="sxs-lookup"><span data-stu-id="358f7-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="358f7-117">In solchen Fällen sollte das so genannte try-Analyse-Muster berücksichtigt werden (Weitere Informationen finden Sie unter [Ausnahmen und Leistung](../../../docs/standard/design-guidelines/exceptions-and-performance.md) ).</span><span class="sxs-lookup"><span data-stu-id="358f7-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>  
  
 <span data-ttu-id="358f7-118">**✓ CONSIDER** Leistungseinbußen bei der Auslösen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="358f7-118">**✓ CONSIDER** the performance implications of throwing exceptions.</span></span> <span data-ttu-id="358f7-119">Auslöse Raten oberhalb von 100 pro Sekunde bewirken wahrscheinlich die Leistung der meisten Anwendungen merklich.</span><span class="sxs-lookup"><span data-stu-id="358f7-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>  
  
 <span data-ttu-id="358f7-120">**✓ DO** Dokument alle Ausnahmen öffentlich aufrufbare Member aufgrund einer Verletzung des Elements (anstatt aufgrund eines Systemfehlers) Vertrag, und behandeln Sie sie als Bestandteil des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="358f7-120">**✓ DO** document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>  
  
 <span data-ttu-id="358f7-121">Ausnahmen, die Teil des Vertrags sind, sollten sich nicht von einer Version zur nächsten ändern (d. h., der Ausnahmetyp sollte nicht geändert werden, und es sollten keine neuen Ausnahmen hinzugefügt werden).</span><span class="sxs-lookup"><span data-stu-id="358f7-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>  
  
 <span data-ttu-id="358f7-122">**X DO NOT** haben öffentliche Member, die entweder auslösen oder keine können basierend auf bestimmte Option.</span><span class="sxs-lookup"><span data-stu-id="358f7-122">**X DO NOT** have public members that can either throw or not based on some option.</span></span>  
  
 <span data-ttu-id="358f7-123">**X DO NOT** öffentliche Member, die zum Zurückgeben von Ausnahmen als Rückgabewert oder ein `out` Parameter.</span><span class="sxs-lookup"><span data-stu-id="358f7-123">**X DO NOT** have public members that return exceptions as the return value or an `out` parameter.</span></span>  
  
 <span data-ttu-id="358f7-124">Wenn Sie Ausnahmen aus öffentlichen APIs zurückgeben, anstatt sie auszulösen, werden viele der Vorteile der Ausnahme basierten Fehlerberichterstattung nicht mehr unterwirft.</span><span class="sxs-lookup"><span data-stu-id="358f7-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>  
  
 <span data-ttu-id="358f7-125">**✓ CONSIDER** Ausnahme-Generator-Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="358f7-125">**✓ CONSIDER** using exception builder methods.</span></span>  
  
 <span data-ttu-id="358f7-126">Es kommt häufig vor, dass die gleiche Ausnahme von unterschiedlichen Stellen ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="358f7-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="358f7-127">Um codebloat zu vermeiden, verwenden Sie Hilfsmethoden, die Ausnahmen erstellen und ihre Eigenschaften initialisieren.</span><span class="sxs-lookup"><span data-stu-id="358f7-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>  
  
 <span data-ttu-id="358f7-128">Außerdem werden Member, die Ausnahmen auslösen, nicht Inline angezeigt.</span><span class="sxs-lookup"><span data-stu-id="358f7-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="358f7-129">Wenn Sie die throw-Anweisung innerhalb des Generators verschieben, kann es vorkommen, dass der Member Inline ist.</span><span class="sxs-lookup"><span data-stu-id="358f7-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>  
  
 <span data-ttu-id="358f7-130">**X DO NOT** lösen Ausnahmen aus Ausnahmeblöcke-Filter.</span><span class="sxs-lookup"><span data-stu-id="358f7-130">**X DO NOT** throw exceptions from exception filter blocks.</span></span>  
  
 <span data-ttu-id="358f7-131">Wenn ein Ausnahme Filter eine Ausnahme auslöst, wird die Ausnahme von der CLR abgefangen, und der Filter gibt false zurück.</span><span class="sxs-lookup"><span data-stu-id="358f7-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="358f7-132">Dieses Verhalten kann nicht vom Filter unterschieden werden, der ausgeführt wird, und false explizit zurückgeben und daher sehr schwer zu Debuggen ist.</span><span class="sxs-lookup"><span data-stu-id="358f7-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>  
  
 <span data-ttu-id="358f7-133">**X AVOID** explizit Auslösen von Ausnahmen von finally-Blöcke.</span><span class="sxs-lookup"><span data-stu-id="358f7-133">**X AVOID** explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="358f7-134">Implizit ausgelöste Ausnahmen, die sich aus aufrufenden Methoden ergeben, die ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="358f7-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>  
  
 <span data-ttu-id="358f7-135">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="358f7-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="358f7-136">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="358f7-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="358f7-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="358f7-137">See also</span></span>

- [<span data-ttu-id="358f7-138">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="358f7-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="358f7-139">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="358f7-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
