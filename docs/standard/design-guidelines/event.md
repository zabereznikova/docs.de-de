---
title: Ereignisentwurf
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b257da73d33fae54ef464e9dd69906316b87fd88
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353852"
---
# <a name="event-design"></a><span data-ttu-id="cc31f-102">Ereignisentwurf</span><span class="sxs-lookup"><span data-stu-id="cc31f-102">Event Design</span></span>
<span data-ttu-id="cc31f-103">Ereignisse sind am häufigsten verwendeten Form von Rückrufen (Konstrukte, die das Framework für den Aufruf von Benutzercode zu ermöglichen).</span><span class="sxs-lookup"><span data-stu-id="cc31f-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="cc31f-104">Andere Rückrufmechanismen enthalten Elemente, die die Delegaten, virtuelle Member und schnittstellenbasierter-Plug-ins. Daten aus Umfragen zur benutzerfreundlichkeit haben anzugeben, dass die meisten Entwickler sind wohler, Ereignisse, als sie die anderen Rückrufmechanismen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc31f-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="cc31f-105">Ereignisse sind in Visual Studio und vielen Sprachen gut integriert.</span><span class="sxs-lookup"><span data-stu-id="cc31f-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="cc31f-106">Es ist wichtig zu beachten, dass es zwei Gruppen von Ereignisse gibt: Ereignisse, die ausgelöst wird, bevor ein Status des Systems geändert wird, wird aufgerufen, Pre-Ereignisse sowie Ereignisse ausgelöst, nachdem ein Zustand ändert, wird nach der Ereignisse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="cc31f-107">Ein Beispiel für ein Ereignis vor `Form.Closing`, der Fehler wird ausgelöst, bevor ein Formular geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="cc31f-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="cc31f-108">Ein Beispiel für ein Ereignis nach der `Form.Closed`, der Fehler wird ausgelöst, nachdem ein Formular geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="cc31f-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="cc31f-109">**✓ DO** verwenden Sie den Begriff "Auslösen" Ereignisse anstatt "Feuer" oder "Auslösen" an.</span><span class="sxs-lookup"><span data-stu-id="cc31f-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="cc31f-110">**✓ DO** verwenden <xref:System.EventHandler%601?displayProperty=nameWithType> statt Sie manuell neue Delegaten als Ereignishandler verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cc31f-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="cc31f-111">**✓ CONSIDER** verwenden eine Unterklasse von <xref:System.EventArgs> als Ereignisargument, es sei denn, Sie sicher, dass das Ereignis nie zur Übertragung von Daten an die Ereignisbehandlungsmethode müssen sind in diesem Fall können Sie die `EventArgs` direkt eingeben.</span><span class="sxs-lookup"><span data-stu-id="cc31f-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="cc31f-112">Wenn Sie schicken eine API mit `EventArgs` direkt, Sie werden nie Daten mit dem Ereignis ausgeführt werden, ohne wichtige Kompatibilität hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="cc31f-113">Wenn Sie eine Unterklasse verwenden, auch wenn Anfangs vollständig leer ist, Sie Eigenschaften in die Unterklasse, die bei Bedarf hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="cc31f-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="cc31f-114">**✓ DO** verwenden Sie eine geschützte virtuelle Methode jedes Ereignis ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="cc31f-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="cc31f-115">Dies gilt nur für nicht statischen Ereignisse, die für nicht versiegelte Klassen nicht statischen Ereignisse, versiegelte Klassen oder Strukturen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="cc31f-116">Der Zweck der Methode ist eine Möglichkeit für eine abgeleitete Klasse zum Behandeln des Ereignisses, das mit einer Außerkraftsetzung.</span><span class="sxs-lookup"><span data-stu-id="cc31f-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="cc31f-117">Überschreiben ist eine flexiblere, schneller und natürliche Möglichkeit, Behandeln von Basisklassenereignissen in abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="cc31f-118">Gemäß der Konvention der Namen der Methode muss mit "On" beginnen und mit dem Namen des Ereignisses folgen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="cc31f-119">Die abgeleitete Klasse können nicht die grundlegende Implementierung der Methode in der Überschreibung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="cc31f-120">Für dieses vorbereitet werden, dazu eine Verarbeitung nicht in der Methode, die für die Basisklasse ordnungsgemäß ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="cc31f-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="cc31f-121">**✓ DO** akzeptieren einen Parameter für die geschützte Methode, die ein Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="cc31f-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="cc31f-122">Der Parameter heißen `e` und soll als die Ereignisargumentklasse eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cc31f-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="cc31f-123">**X DO NOT** übergeben Sie null als Sender an, wenn eine nicht statische Ereignis durch das auslösen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="cc31f-124">**✓ DO** übergeben Sie null als Sender an, wenn ein statisches Ereignis auslösen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="cc31f-125">**X DO NOT** übergeben Sie null als Parameter für das Daten, beim Auslösen eines Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="cc31f-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="cc31f-126">Übergeben Sie `EventArgs.Empty` Wenn keine Daten an die Ereignisbehandlungsmethode übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="cc31f-127">Entwickler erwarten, dass dieser Parameter nicht null sein.</span><span class="sxs-lookup"><span data-stu-id="cc31f-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="cc31f-128">**✓ CONSIDER** Auslösen von Ereignissen, die der Endbenutzer abbrechen können.</span><span class="sxs-lookup"><span data-stu-id="cc31f-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="cc31f-129">Dies gilt nur für vorherige Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="cc31f-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="cc31f-130">Verwendung <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> oder die Unterklasse als das Ereignisargument, das dem Endbenutzer Ereignisse ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="cc31f-131">Entwurf benutzerdefinierter Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="cc31f-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="cc31f-132">Es gibt Fälle, in denen `EventHandler<T>` kann nicht verwendet werden, z. B. wenn das Framework muss mit früheren Versionen der CLR arbeiten, dem keine Generika unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cc31f-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="cc31f-133">In solchen Fällen müssen Sie möglicherweise zum Entwerfen und entwickeln ein benutzerdefiniertes Ereignis-Handler-Delegat.</span><span class="sxs-lookup"><span data-stu-id="cc31f-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="cc31f-134">**✓ DO** verwenden Sie den Rückgabetyp "void" für den Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="cc31f-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="cc31f-135">Ein Ereignishandler kann mehrere Methoden, die möglicherweise auf mehrere Objekte für die Ereignisbehandlung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cc31f-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="cc31f-136">Wenn Ereignisbehandlung Methoden zum Zurückgeben eines Werts zulässig wäre, würde Rückgabe mehrerer Werte für jeden Aufruf des Ereignisses vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="cc31f-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="cc31f-137">**✓ DO** verwenden `object` als Typ des ersten Parameters der Ereignishandler, und rufen sie `sender`.</span><span class="sxs-lookup"><span data-stu-id="cc31f-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="cc31f-138">**✓ DO** verwenden <xref:System.EventArgs?displayProperty=nameWithType> oder seiner Unterklasse als Typ des zweiten Parameters der Ereignishandler, und nennen Sie es `e`.</span><span class="sxs-lookup"><span data-stu-id="cc31f-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="cc31f-139">**X DO NOT** verfügen über mehr als zwei Parameter auf Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="cc31f-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="cc31f-140">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="cc31f-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="cc31f-141">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="cc31f-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc31f-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc31f-142">See also</span></span>

- [<span data-ttu-id="cc31f-143">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="cc31f-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="cc31f-144">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="cc31f-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
