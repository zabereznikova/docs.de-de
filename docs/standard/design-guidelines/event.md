---
title: Ereignisentwurf
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a07392ba805b5f2a3913b01a15dd0e1668f0ccf7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="event-design"></a><span data-ttu-id="f0db0-102">Ereignisentwurf</span><span class="sxs-lookup"><span data-stu-id="f0db0-102">Event Design</span></span>
<span data-ttu-id="f0db0-103">Ereignisse werden am häufigsten verwendete Form von Rückrufen (Konstrukte, die das Framework zum Aufrufen von Benutzercode zu ermöglichen).</span><span class="sxs-lookup"><span data-stu-id="f0db0-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="f0db0-104">Andere Rückrufmechanismen enthalten Elemente und Delegaten, virtuelle Member und schnittstellenbasierten-Plug-ins. Daten aus der Verwendbarkeit Studien anzugeben, dass die meisten Entwickler sind nachrichtenorientierten Ereignisse verwenden, als sie die anderen Rückrufmechanismen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0db0-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="f0db0-105">Ereignisse sind gut mit Visual Studio und vielen Sprachen integriert.</span><span class="sxs-lookup"><span data-stu-id="f0db0-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="f0db0-106">Es ist wichtig zu beachten, dass es zwei Gruppen von Ereignisse gibt: Ereignisse, die ausgelöst wird, bevor ein Status des Systems ändert, aufgerufen wird, vorab auch Ereignisse, die ausgelöst wird, nachdem ein Zustand ändert, sogenannte nach der Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="f0db0-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="f0db0-107">Ein Beispiel eines Ereignisses vor wäre `Form.Closing`, der Fehler wird ausgelöst, bevor ein Formular geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="f0db0-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="f0db0-108">Ein Beispiel für ein Ereignis nach der wäre `Form.Closed`, der Fehler wird ausgelöst, nachdem ein Formular geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="f0db0-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="f0db0-109">**Führen Sie ✓** verwenden Sie den Begriff "Auslösen" Ereignisse anstatt "Feuer" oder "Auslösen" an.</span><span class="sxs-lookup"><span data-stu-id="f0db0-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="f0db0-110">**Führen Sie ✓** verwenden <xref:System.EventHandler%601?displayProperty=nameWithType> statt Sie manuell neue Delegaten als Ereignishandler verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0db0-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="f0db0-111">**✓ GGF.** verwenden eine Unterklasse von <xref:System.EventArgs> als Ereignisargument, es sei denn, Sie sicher, dass das Ereignis nie zur Übertragung von Daten an die Ereignisbehandlungsmethode müssen sind in diesem Fall können Sie die `EventArgs` direkt eingeben.</span><span class="sxs-lookup"><span data-stu-id="f0db0-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="f0db0-112">Wenn Sie eine API mit liefern `EventArgs` direkt, Sie werden nie mehr Daten mit dem Ereignis ausgeführt werden, ohne Unterbrechung der Kompatibilität hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f0db0-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="f0db0-113">Wenn Sie eine Unterklasse verwenden, auch wenn anfänglich vollständig leer ist, die Unterklasse bei Bedarf Eigenschaften hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f0db0-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="f0db0-114">**Führen Sie ✓** verwenden Sie eine geschützte virtuelle Methode jedes Ereignis ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0db0-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="f0db0-115">Dies gilt nur für nicht statische Ereignisse für nicht versiegelte Klassen, nicht für Strukturen, versiegelte Klassen oder statische Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="f0db0-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="f0db0-116">Der Zweck der Methode ist eine Möglichkeit für eine abgeleitete Klasse für die Ereignisbehandlung mit einer Außerkraftsetzung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f0db0-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="f0db0-117">Überschreiben ist eine flexiblere, schnellere und besser Möglichkeit zum Basisklassenereignissen in abgeleiteten Klassen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f0db0-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="f0db0-118">Gemäß der Konvention werden der Name der Methode sollte mit "On" beginnen und mit dem Namen des Ereignisses folgen.</span><span class="sxs-lookup"><span data-stu-id="f0db0-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="f0db0-119">Die abgeleitete Klasse können nicht die grundlegende Implementierung der Methode in der Überschreibung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f0db0-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="f0db0-120">Für diesen vorbereitet werden, ausgenommen Verarbeitungen in der Methode, die für die Basisklasse ordnungsgemäß funktioniert erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f0db0-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="f0db0-121">**Führen Sie ✓** akzeptieren einen Parameter für die geschützte Methode, die ein Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="f0db0-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="f0db0-122">Der Parameter heißen `e` und sollten als Ereignisargumentklasse eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f0db0-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="f0db0-123">**X nicht** übergeben Sie null als Sender an, wenn eine nicht statische Ereignis durch das auslösen.</span><span class="sxs-lookup"><span data-stu-id="f0db0-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="f0db0-124">**Führen Sie ✓** übergeben Sie null als Sender an, wenn ein statisches Ereignis auslösen.</span><span class="sxs-lookup"><span data-stu-id="f0db0-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="f0db0-125">**X nicht** übergeben Sie null als Parameter für das Daten, beim Auslösen eines Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="f0db0-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="f0db0-126">Übergeben Sie `EventArgs.Empty` Wenn keine Daten an die Ereignisbehandlungsmethode übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0db0-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="f0db0-127">Entwickler erwarten, dass dieser Parameter nicht null sein.</span><span class="sxs-lookup"><span data-stu-id="f0db0-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="f0db0-128">**✓ GGF.** Auslösen von Ereignissen, die der Endbenutzer abbrechen können.</span><span class="sxs-lookup"><span data-stu-id="f0db0-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="f0db0-129">Dies gilt nur für Ereignisse vor.</span><span class="sxs-lookup"><span data-stu-id="f0db0-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="f0db0-130">Verwendung <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> oder seiner Unterklasse als das Ereignisargument für die Endbenutzer zum Abbrechen von Ereignissen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f0db0-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="f0db0-131">Entwurf benutzerdefinierter Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="f0db0-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="f0db0-132">Es gibt Fälle, in denen `EventHandler<T>` kann nicht verwendet werden, z. B. wenn das Framework benötigt Arbeit mit früheren Versionen der CLR, Generika nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f0db0-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="f0db0-133">In solchen Fällen müssen Sie möglicherweise entwerfen und entwickeln einen benutzerdefinierten Ereignishandler-Delegaten.</span><span class="sxs-lookup"><span data-stu-id="f0db0-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="f0db0-134">**Führen Sie ✓** verwenden Sie den Rückgabetyp "void" für den Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="f0db0-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="f0db0-135">Ein Ereignishandler kann mehrere Methoden, die möglicherweise bei mehreren Objekten für die Ereignisbehandlung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f0db0-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="f0db0-136">Ereignisbehandlung Methoden zugelassen wird, einen Wert zurückzugeben, wäre mehrere Rückgabewerte für jeden Aufruf des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="f0db0-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="f0db0-137">**Führen Sie ✓** verwenden `object` als Typ des ersten Parameters der Ereignishandler, und rufen sie `sender`.</span><span class="sxs-lookup"><span data-stu-id="f0db0-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="f0db0-138">**✓ FÜHREN** verwenden <xref:System.EventArgs?displayProperty=nameWithType> oder seiner Unterklasse als Typ des zweiten Parameters der Ereignishandler, und nennen Sie es `e`.</span><span class="sxs-lookup"><span data-stu-id="f0db0-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="f0db0-139">**X nicht** verfügen über mehr als zwei Parameter auf Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="f0db0-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="f0db0-140">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="f0db0-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f0db0-141">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="f0db0-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0db0-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0db0-142">See Also</span></span>  
 [<span data-ttu-id="f0db0-143">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="f0db0-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="f0db0-144">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f0db0-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
