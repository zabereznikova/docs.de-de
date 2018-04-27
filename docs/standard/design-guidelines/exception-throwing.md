---
title: Auslösen von Ausnahmen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 47c16ac94054fff193b1f5976fe7f04f10a39ecd
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="exception-throwing"></a><span data-ttu-id="be8ff-102">Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="be8ff-102">Exception Throwing</span></span>
<span data-ttu-id="be8ff-103">Ausnahme auslösende-Richtlinien, die in diesem Abschnitt beschriebenen erfordern eine gute Definition der Bedeutung der Ausführung ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="be8ff-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="be8ff-104">Fehler bei der Ausführung tritt auf, wenn es sich bei Mitglied nicht seiner Vorgehensweise (welche die Elementnamen impliziert) entwickelt.</span><span class="sxs-lookup"><span data-stu-id="be8ff-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="be8ff-105">Beispielsweise, wenn die `OpenFile` Methode kann nicht an den Aufrufer eine geöffnete Dateihandle zurückgeben, es werden Fehler bei der Ausführung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="be8ff-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>  
  
 <span data-ttu-id="be8ff-106">Die meisten Entwickler haben mit der Verwendung von Ausnahmen für Verwendungsfehler z. B. Division durch 0 (null) oder null-Verweise vertraut werden.</span><span class="sxs-lookup"><span data-stu-id="be8ff-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="be8ff-107">Ausnahmen werden in das Framework für alle fehlerbedingungen, einschließlich Fehler bei der Ausführung verwendet.</span><span class="sxs-lookup"><span data-stu-id="be8ff-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>  
  
 <span data-ttu-id="be8ff-108">**X nicht** Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="be8ff-108">**X DO NOT** return error codes.</span></span>  
  
 <span data-ttu-id="be8ff-109">Ausnahmen sind das primäre Mittel zum Melden von Fehlern in Frameworks.</span><span class="sxs-lookup"><span data-stu-id="be8ff-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>  
  
 <span data-ttu-id="be8ff-110">**Führen Sie ✓** Ausführungsfehler durch das Auslösen von Ausnahmen gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="be8ff-110">**✓ DO** report execution failures by throwing exceptions.</span></span>  
  
 <span data-ttu-id="be8ff-111">**✓ GGF.** Beenden des Prozesses durch Aufrufen von `System.Environment.FailFast` (Feature von .NET Framework 2.0) anstatt eine Ausnahme auszulösen, wenn Ihr Code eine Situation vorfindet, wo es unsicher, für die weitere Ausführung ist.</span><span class="sxs-lookup"><span data-stu-id="be8ff-111">**✓ CONSIDER** terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>  
  
 <span data-ttu-id="be8ff-112">**X nicht** verwenden Sie Ausnahmen für die normale ablaufsteuerung, falls möglich.</span><span class="sxs-lookup"><span data-stu-id="be8ff-112">**X DO NOT** use exceptions for the normal flow of control, if possible.</span></span>  
  
 <span data-ttu-id="be8ff-113">Mit Ausnahme von Systemfehlern und Vorgänge mit potenzielle Racebedingungen sollten Framework-Entwickler APIs entwerfen, damit Benutzer Code schreiben können, der keine Ausnahmen auslöst.</span><span class="sxs-lookup"><span data-stu-id="be8ff-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="be8ff-114">Sie können z. B. angeben, dass eine Möglichkeit zum Überprüfen von Vorbedingungen vor dem Mitglied aufrufen, damit Benutzer Code schreiben können, der keine Ausnahmen auslöst.</span><span class="sxs-lookup"><span data-stu-id="be8ff-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>  
  
 <span data-ttu-id="be8ff-115">Das Element zum Prüfen auf Vorbedingungen eines anderen Elements wird häufig als ein Tester bezeichnet, und der Member, der eigentliche Arbeit übernimmt einen Ausführer aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="be8ff-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>  
  
 <span data-ttu-id="be8ff-116">Es gibt Fälle, wenn der Tester-Ausführer-Muster ein inakzeptabler Leistung auswirken können.</span><span class="sxs-lookup"><span data-stu-id="be8ff-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="be8ff-117">In solchen Fällen sollte dem so genannten Try-Analyse Muster berücksichtigt werden (finden Sie unter [Ausnahmen und Leistungsfähigkeit](../../../docs/standard/design-guidelines/exceptions-and-performance.md) für Weitere Informationen).</span><span class="sxs-lookup"><span data-stu-id="be8ff-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>  
  
 <span data-ttu-id="be8ff-118">**✓ GGF.** Leistungseinbußen bei der Auslösen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="be8ff-118">**✓ CONSIDER** the performance implications of throwing exceptions.</span></span> <span data-ttu-id="be8ff-119">Throw-Raten über 100 pro Sekunde sind wahrscheinlich die Leistung der meisten Anwendung deutlich beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="be8ff-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>  
  
 <span data-ttu-id="be8ff-120">**Führen Sie ✓** Dokument alle Ausnahmen öffentlich aufrufbare Member aufgrund einer Verletzung des Elements (anstatt aufgrund eines Systemfehlers) Vertrag, und behandeln Sie sie als Bestandteil des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="be8ff-120">**✓ DO** document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>  
  
 <span data-ttu-id="be8ff-121">Ausnahmen, die Bestandteil des Vertrags sind sollten nicht von einer Version zur nächsten ändern (d. h. Ausnahmetyp nicht ändern sollten, und neue Ausnahmen nicht hinzugefügt werden sollen).</span><span class="sxs-lookup"><span data-stu-id="be8ff-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>  
  
 <span data-ttu-id="be8ff-122">**X nicht** haben öffentliche Member, die entweder auslösen oder keine können basierend auf bestimmte Option.</span><span class="sxs-lookup"><span data-stu-id="be8ff-122">**X DO NOT** have public members that can either throw or not based on some option.</span></span>  
  
 <span data-ttu-id="be8ff-123">**X nicht** öffentliche Member, die zum Zurückgeben von Ausnahmen als Rückgabewert oder ein `out` Parameter.</span><span class="sxs-lookup"><span data-stu-id="be8ff-123">**X DO NOT** have public members that return exceptions as the return value or an `out` parameter.</span></span>  
  
 <span data-ttu-id="be8ff-124">Zurückgeben von Ausnahmen von öffentlichen APIs, statt sie unterlaufen kann viele der Vorteile von Ausnahmen basierende-Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="be8ff-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>  
  
 <span data-ttu-id="be8ff-125">**✓ GGF.** Ausnahme-Generator-Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="be8ff-125">**✓ CONSIDER** using exception builder methods.</span></span>  
  
 <span data-ttu-id="be8ff-126">Es ist üblich, die von verschiedenen Positionen in die gleiche Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="be8ff-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="be8ff-127">Um Codeumfang zu vermeiden, verwenden Sie Hilfsmethoden, die Ausnahmen zu erstellen und initialisieren Sie ihre Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="be8ff-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>  
  
 <span data-ttu-id="be8ff-128">Außerdem werden Elemente, die Ausnahmen auslösen nicht abrufen Inlining.</span><span class="sxs-lookup"><span data-stu-id="be8ff-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="be8ff-129">Verschieben die Throw-Anweisung in der Generator lassen möglicherweise das Element inline zu setzen.</span><span class="sxs-lookup"><span data-stu-id="be8ff-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>  
  
 <span data-ttu-id="be8ff-130">**X nicht** lösen Ausnahmen aus Ausnahmeblöcke-Filter.</span><span class="sxs-lookup"><span data-stu-id="be8ff-130">**X DO NOT** throw exceptions from exception filter blocks.</span></span>  
  
 <span data-ttu-id="be8ff-131">Wenn ein Ausnahmefilter eine Ausnahme auslöst, wird die Ausnahme von der CLR und der Filter "false" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="be8ff-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="be8ff-132">Dieses Verhalten ist nicht von den Filter ausführen und explizit "false" zurückgeben und ist daher sehr schwer zu beheben.</span><span class="sxs-lookup"><span data-stu-id="be8ff-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>  
  
 <span data-ttu-id="be8ff-133">**X vermeiden** explizit Auslösen von Ausnahmen von finally-Blöcke.</span><span class="sxs-lookup"><span data-stu-id="be8ff-133">**X AVOID** explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="be8ff-134">Implizit ausgelöste Ausnahmen, Aufrufen von Methoden, die ausgelöst werden, sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="be8ff-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>  
  
 <span data-ttu-id="be8ff-135">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="be8ff-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="be8ff-136">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="be8ff-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be8ff-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be8ff-137">See Also</span></span>  
 [<span data-ttu-id="be8ff-138">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="be8ff-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="be8ff-139">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="be8ff-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
