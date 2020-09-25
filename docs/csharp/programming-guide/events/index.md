---
title: Ereignisse – C#-Programmierhandbuch
description: Hier erfahren Sie mehr über Ereignisse. Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 14c18006e393dece5d32d30c2a727d797515c779
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167456"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="30cbd-104">Ereignisse (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="30cbd-104">Events (C# Programming Guide)</span></span>

<span data-ttu-id="30cbd-105">Ereignisse aktivieren eine [Klasse](../../language-reference/keywords/class.md) oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="30cbd-105">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="30cbd-106">Die Klasse, die das Ereignis sendet (oder *auslöst*), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder *behandeln*), werden als *Abonnenten*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="30cbd-106">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="30cbd-107">In einer typischen C#-Windows Forms oder Web-Anwendung abonnieren Sie Ereignisse, die von Steuerelementen wie Schaltflächen und Listenfelder ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="30cbd-107">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="30cbd-108">Sie können die integrierte Entwicklungsumgebung (IDE) von Visual C# zum Durchsuchen der Ereignisse verwenden, die ein Steuerelement auslöst, und diejenigen wählen, die Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="30cbd-108">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="30cbd-109">Mithilfe der IDE können eine leere Ereignishandlermethode und der Code ganz einfach automatisch zu den Abonnenten des Ereignisses hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="30cbd-109">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="30cbd-110">Weitere Informationen finden Sie unter [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="30cbd-110">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="30cbd-111">Übersicht über Ereignisse</span><span class="sxs-lookup"><span data-stu-id="30cbd-111">Events Overview</span></span>  

 <span data-ttu-id="30cbd-112">Ereignisse verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="30cbd-112">Events have the following properties:</span></span>  
  
- <span data-ttu-id="30cbd-113">Der Herausgeber wird bestimmt, wenn ein Ereignis ausgelöst wird. Die Abonnenten bestimmen, welche Aktion als Reaktion auf das Ereignis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="30cbd-113">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="30cbd-114">Ein Ereignis kann mehrere Abonnenten haben.</span><span class="sxs-lookup"><span data-stu-id="30cbd-114">An event can have multiple subscribers.</span></span> <span data-ttu-id="30cbd-115">Ein Abonnent kann mehrere Ereignisse von mehreren Herausgebern behandeln.</span><span class="sxs-lookup"><span data-stu-id="30cbd-115">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="30cbd-116">Ereignisse, die keine Abonnenten haben, werden nie ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="30cbd-116">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="30cbd-117">Ereignisse werden in der Regel verwendet, um Benutzeraktionen wie Mausklicks oder Menüauswahlen in GUI-Schnittstellen zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="30cbd-117">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="30cbd-118">Wenn ein Ereignis mehrere Abonnenten hat, werden die Ereignishandler synchron aufgerufen, wenn ein Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="30cbd-118">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="30cbd-119">Informationen zum asynchronen Aufrufen von Ereignissen finden Sie unter [Asynchrones Aufrufen von synchronen Methoden](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="30cbd-119">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="30cbd-120">In der .NET-Klassenbibliothek basieren Ereignisse auf dem Delegaten <xref:System.EventHandler> und der Basisklasse <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="30cbd-120">In the .NET class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="30cbd-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="30cbd-121">Related Sections</span></span>  

 <span data-ttu-id="30cbd-122">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="30cbd-122">For more information, see:</span></span>  
  
- [<span data-ttu-id="30cbd-123">Abonnieren von Ereignissen und Kündigen von Ereignisabonnements</span><span class="sxs-lookup"><span data-stu-id="30cbd-123">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="30cbd-124">Veröffentlichen von Ereignissen, die den .NET-Richtlinien entsprechen</span><span class="sxs-lookup"><span data-stu-id="30cbd-124">How to publish events that conform to .NET Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="30cbd-125">Auslösen von Basisklassenereignissen in abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="30cbd-125">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="30cbd-126">Implementieren von Schnittstellenereignissen</span><span class="sxs-lookup"><span data-stu-id="30cbd-126">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="30cbd-127">Implementieren benutzerdefinierter Ereignisaccessoren</span><span class="sxs-lookup"><span data-stu-id="30cbd-127">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="30cbd-128">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="30cbd-128">C# Language Specification</span></span>  

<span data-ttu-id="30cbd-129">Weitere Informationen erhalten Sie unter [Ereignisse](~/_csharplang/spec/classes.md#events) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="30cbd-129">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="30cbd-130">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="30cbd-130">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="30cbd-131">Enthaltene Buchkapitel</span><span class="sxs-lookup"><span data-stu-id="30cbd-131">Featured Book Chapters</span></span>  

 <span data-ttu-id="30cbd-132">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) (Delegaten, Ereignisse und Lambda-Ausdrücke) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10)) (C# 3.0-Cookbook, 3. Auflage: Mehr als 250 Lösungen für C# 3.0-Programmierer)</span><span class="sxs-lookup"><span data-stu-id="30cbd-132">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span></span>  
  
 <span data-ttu-id="30cbd-133">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) (Delegaten und Ereignisse) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10)) (Erlernen von C# 3.0: Die Grundlagen von C# 3.0)</span><span class="sxs-lookup"><span data-stu-id="30cbd-133">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) in [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30cbd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30cbd-134">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="30cbd-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="30cbd-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="30cbd-136">Delegaten</span><span class="sxs-lookup"><span data-stu-id="30cbd-136">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="30cbd-137">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30cbd-137">Creating Event Handlers in Windows Forms</span></span>](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms)
