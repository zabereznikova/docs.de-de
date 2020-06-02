---
title: Ereignisentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: 852c99b1a41691911f7ae82d3b8104526811757d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289823"
---
# <a name="event-design"></a><span data-ttu-id="7219f-102">Ereignisentwurf</span><span class="sxs-lookup"><span data-stu-id="7219f-102">Event Design</span></span>
<span data-ttu-id="7219f-103">Ereignisse sind die am häufigsten verwendete Form von Rückrufe (-Konstrukte, die dem Framework das Aufrufen von Benutzercode ermöglichen).</span><span class="sxs-lookup"><span data-stu-id="7219f-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="7219f-104">Andere Rückruf Mechanismen beinhalten Member, die Delegaten, virtuelle Member und Schnittstellen basierte Plug-Ins verwenden. Daten aus Nutzbarkeits Studien zeigen an, dass die Mehrzahl der Entwickler die Verwendung von Ereignissen leichter machen, als Sie die anderen Rückruf Mechanismen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7219f-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="7219f-105">Ereignisse sind gut in Visual Studio und viele Sprachen integriert.</span><span class="sxs-lookup"><span data-stu-id="7219f-105">Events are nicely integrated with Visual Studio and many languages.</span></span>

 <span data-ttu-id="7219f-106">Es ist wichtig zu beachten, dass es zwei Gruppen von Ereignissen gibt: Ereignisse, die vor dem Systemwechsel ausgelöst werden, als präereignisse bezeichnet werden, und Ereignisse, die nach einem Zustands Wechsel ausgelöst werden, die als nach Ereignissen bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7219f-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="7219f-107">Ein Beispiel für ein präereignis wäre `Form.Closing` , das ausgelöst wird, bevor ein Formular geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="7219f-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="7219f-108">Ein Beispiel für ein Post-Ereignis wäre `Form.Closed` , das ausgelöst wird, nachdem ein Formular geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="7219f-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>

 <span data-ttu-id="7219f-109">✔️ Verwenden Sie anstelle von "Fire" oder "Trigger" den Begriff "Raise" für Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="7219f-109">✔️ DO use the term "raise" for events rather than "fire" or "trigger."</span></span>

 <span data-ttu-id="7219f-110">✔️ verwenden <xref:System.EventHandler%601?displayProperty=nameWithType> anstelle von Manuelles Erstellen neuer Delegaten, die als Ereignishandler verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7219f-110">✔️ DO use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>

 <span data-ttu-id="7219f-111">✔️ sollten Sie die Verwendung einer Unterklasse von <xref:System.EventArgs> als Ereignis Argument in Erwägung ziehen, es sei denn, Sie sind sicher, dass das Ereignis niemals Daten an die Ereignis Behandlungsmethode übertragen muss. in diesem Fall können Sie den `EventArgs` Typ direkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="7219f-111">✔️ CONSIDER using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>

 <span data-ttu-id="7219f-112">Wenn Sie eine API direkt mithilfe `EventArgs` von versenden, können Sie ohne Unterbrechung der Kompatibilität niemals Daten hinzufügen, die mit dem Ereignis übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="7219f-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="7219f-113">Wenn Sie eine Unterklasse verwenden, können Sie, auch wenn Sie anfänglich vollständig leer ist, bei Bedarf Eigenschaften zur Unterklasse hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7219f-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>

 <span data-ttu-id="7219f-114">✔️ eine geschützte virtuelle Methode verwenden, um jedes Ereignis zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="7219f-114">✔️ DO use a protected virtual method to raise each event.</span></span> <span data-ttu-id="7219f-115">Dies gilt nur für nicht statische Ereignisse in nicht versiegelten Klassen, nicht für Strukturen, versiegelte Klassen oder statische Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="7219f-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>

 <span data-ttu-id="7219f-116">Der Zweck der-Methode besteht darin, eine Methode bereitzustellen, mit der eine abgeleitete Klasse das Ereignis mithilfe einer außer Kraft Setzung behandeln kann.</span><span class="sxs-lookup"><span data-stu-id="7219f-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="7219f-117">Das Überschreiben ist eine flexiblere, schnellere und natürlichere Methode zum Verarbeiten von Basisklassen Ereignissen in abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="7219f-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="7219f-118">Gemäß der Konvention sollte der Name der Methode mit "on" beginnen und mit dem Namen des Ereignisses befolgt werden.</span><span class="sxs-lookup"><span data-stu-id="7219f-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>

 <span data-ttu-id="7219f-119">Die abgeleitete Klasse kann auswählen, dass die Basis Implementierung der Methode nicht in der Überschreibung aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7219f-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="7219f-120">Seien Sie darauf vorbereitet, indem Sie keine Verarbeitung in die-Methode einschließen, die erforderlich ist, damit die Basisklasse ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="7219f-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>

 <span data-ttu-id="7219f-121">✔️ einen Parameter an die geschützte Methode übernehmen, die ein Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="7219f-121">✔️ DO take one parameter to the protected method that raises an event.</span></span>

 <span data-ttu-id="7219f-122">Der-Parameter muss benannt werden `e` und als Ereignis Argument Klasse eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7219f-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>

 <span data-ttu-id="7219f-123">❌Übergeben Sie NULL nicht als Absender, wenn Sie ein nicht statisches Ereignis auslassen.</span><span class="sxs-lookup"><span data-stu-id="7219f-123">❌ DO NOT pass null as the sender when raising a nonstatic event.</span></span>

 <span data-ttu-id="7219f-124">✔️ bei der Erstellung eines statischen Ereignisses NULL als Absender übergeben.</span><span class="sxs-lookup"><span data-stu-id="7219f-124">✔️ DO pass null as the sender when raising a static event.</span></span>

 <span data-ttu-id="7219f-125">❌Übergeben Sie NULL nicht als Ereignisdaten Parameter, wenn Sie ein Ereignis aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7219f-125">❌ DO NOT pass null as the event data parameter when raising an event.</span></span>

 <span data-ttu-id="7219f-126">Sie sollten übergeben, `EventArgs.Empty` Wenn Sie keine Daten an die Ereignis Behandlungsmethode übergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="7219f-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="7219f-127">Entwickler erwarten, dass dieser Parameter nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="7219f-127">Developers expect this parameter not to be null.</span></span>

 <span data-ttu-id="7219f-128">✔️ sollten Ereignisse in Erwägung ziehen, die der Endbenutzer abbrechen kann.</span><span class="sxs-lookup"><span data-stu-id="7219f-128">✔️ CONSIDER raising events that the end user can cancel.</span></span> <span data-ttu-id="7219f-129">Dies gilt nur für präereignisse.</span><span class="sxs-lookup"><span data-stu-id="7219f-129">This only applies to pre-events.</span></span>

 <span data-ttu-id="7219f-130">Verwenden Sie oder die zugehörige <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> Unterklasse als Ereignis Argument, damit der Endbenutzer Ereignisse abbrechen kann.</span><span class="sxs-lookup"><span data-stu-id="7219f-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>

### <a name="custom-event-handler-design"></a><span data-ttu-id="7219f-131">Design des benutzerdefinierten Ereignis Handlers</span><span class="sxs-lookup"><span data-stu-id="7219f-131">Custom Event Handler Design</span></span>
 <span data-ttu-id="7219f-132">Es gibt Fälle, in denen nicht `EventHandler<T>` verwendet werden kann, z. b. wenn das Framework mit früheren Versionen der CLR arbeiten muss, die keine Generika unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7219f-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="7219f-133">In solchen Fällen müssen Sie möglicherweise einen benutzerdefinierten Ereignishandlerdelegaten entwerfen und entwickeln.</span><span class="sxs-lookup"><span data-stu-id="7219f-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>

 <span data-ttu-id="7219f-134">✔️ den Rückgabetyp "void" für Ereignishandler verwenden.</span><span class="sxs-lookup"><span data-stu-id="7219f-134">✔️ DO use a return type of void for event handlers.</span></span>

 <span data-ttu-id="7219f-135">Ein Ereignishandler kann mehrere Ereignis Verarbeitungsmethoden aufrufen, möglicherweise auf mehreren Objekten.</span><span class="sxs-lookup"><span data-stu-id="7219f-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="7219f-136">Wenn Ereignis Behandlungsmethoden einen Wert zurückgeben können, gibt es mehrere Rückgabewerte für jeden Ereignis Aufruf.</span><span class="sxs-lookup"><span data-stu-id="7219f-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>

 <span data-ttu-id="7219f-137">✔️ verwenden `object` Sie als Typ des ersten Parameters des Ereignis Handlers, und nennen Sie ihn `sender` .</span><span class="sxs-lookup"><span data-stu-id="7219f-137">✔️ DO use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>

 <span data-ttu-id="7219f-138">✔️ Verwenden Sie oder die zugehörige <xref:System.EventArgs?displayProperty=nameWithType> Unterklasse als Typ des zweiten Parameters des Ereignis Handlers, und nennen Sie Sie `e` .</span><span class="sxs-lookup"><span data-stu-id="7219f-138">✔️ DO use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>

 <span data-ttu-id="7219f-139">❌Für Ereignishandler sind nicht mehr als zwei Parameter vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7219f-139">❌ DO NOT have more than two parameters on event handlers.</span></span>

 <span data-ttu-id="7219f-140">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="7219f-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="7219f-141">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="7219f-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="7219f-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7219f-142">See also</span></span>

- [<span data-ttu-id="7219f-143">Entwurfs Richtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="7219f-143">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="7219f-144">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="7219f-144">Framework Design Guidelines</span></span>](index.md)
