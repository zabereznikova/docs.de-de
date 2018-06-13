---
title: Ereignisse (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 5b844b20ac62b4cbc2a73931eecab95f22b4b1de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339916"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="53774-102">Ereignisse (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="53774-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="53774-103">Ereignisse aktivieren eine [Klasse](../../../csharp/language-reference/keywords/class.md) oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="53774-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="53774-104">Die Klasse, die das Ereignis sendet (oder *auslöst*), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder *behandeln*), werden als *Abonnenten*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="53774-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="53774-105">In einer typischen C#-Windows Forms oder Web-Anwendung abonnieren Sie Ereignisse, die von Steuerelementen wie Schaltflächen und Listenfelder ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="53774-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="53774-106">Sie können die integrierte Entwicklungsumgebung (IDE) von Visual C# zum Durchsuchen der Ereignisse verwenden, die ein Steuerelement auslöst, und diejenigen wählen, die Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="53774-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="53774-107">Die IDE fügt automatisch eine leere Ereignishandlermethode und den Code zum Abonnieren des Ereignisses hinzu.</span><span class="sxs-lookup"><span data-stu-id="53774-107">The IDE automatically adds an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="53774-108">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="53774-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="53774-109">Übersicht über Ereignisse</span><span class="sxs-lookup"><span data-stu-id="53774-109">Events Overview</span></span>  
 <span data-ttu-id="53774-110">Ereignisse verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="53774-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="53774-111">Der Herausgeber wird bestimmt, wenn ein Ereignis ausgelöst wird. Die Abonnenten bestimmen, welche Aktion als Reaktion auf das Ereignis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="53774-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="53774-112">Ein Ereignis kann mehrere Abonnenten haben.</span><span class="sxs-lookup"><span data-stu-id="53774-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="53774-113">Ein Abonnent kann mehrere Ereignisse von mehreren Herausgebern behandeln.</span><span class="sxs-lookup"><span data-stu-id="53774-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="53774-114">Ereignisse, die keine Abonnenten haben, werden nie ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="53774-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="53774-115">Ereignisse werden in der Regel verwendet, um Benutzeraktionen wie Mausklicks oder Menüauswahlen in GUI-Schnittstellen zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="53774-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="53774-116">Wenn ein Ereignis mehrere Abonnenten hat, werden die Ereignishandler synchron aufgerufen, wenn ein Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="53774-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="53774-117">Informationen zum asynchronen Aufrufen von Ereignissen finden Sie unter [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="53774-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
-   <span data-ttu-id="53774-118">In der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] -Klassenbibliothek basieren Ereignisse auf dem <xref:System.EventHandler> -Delegaten und der <xref:System.EventArgs> -Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="53774-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="53774-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="53774-119">Related Sections</span></span>  
 <span data-ttu-id="53774-120">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="53774-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="53774-121">Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements</span><span class="sxs-lookup"><span data-stu-id="53774-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="53774-122">Gewusst wie: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen</span><span class="sxs-lookup"><span data-stu-id="53774-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="53774-123">Gewusst wie: Auslösen von Basisklassenereignissen in abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="53774-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="53774-124">Gewusst wie: Implementieren von Schnittstellenereignissen</span><span class="sxs-lookup"><span data-stu-id="53774-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="53774-125">Threadsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="53774-125">Thread Synchronization</span></span>](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [<span data-ttu-id="53774-126">Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen</span><span class="sxs-lookup"><span data-stu-id="53774-126">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="53774-127">Gewusst wie: Implementieren benutzerdefinierter Ereigniszugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="53774-127">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="53774-128">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="53774-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="53774-129">Enthaltene Buchkapitel</span><span class="sxs-lookup"><span data-stu-id="53774-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="53774-130">[Delegaten, Ereignisse und Lambda-Ausdrücke](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) im [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="53774-130">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
 <span data-ttu-id="53774-131">[Delegaten und Ereignisse](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="53774-131">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53774-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53774-132">See Also</span></span>  
 <xref:System.EventHandler>  
 [<span data-ttu-id="53774-133">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="53774-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="53774-134">Delegaten</span><span class="sxs-lookup"><span data-stu-id="53774-134">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="53774-135">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53774-135">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="53774-136">Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster</span><span class="sxs-lookup"><span data-stu-id="53774-136">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
