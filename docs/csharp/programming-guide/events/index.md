---
title: Ereignisse – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 55fe0e8f94d9b350305b634cabb90011e173b572
ms.sourcegitcommit: 882a2f56bf6afdcb40d468e4ae9371296822b68c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2018
ms.locfileid: "53451143"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="5a9d5-102">Ereignisse (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="5a9d5-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="5a9d5-103">Ereignisse aktivieren eine [Klasse](../../../csharp/language-reference/keywords/class.md) oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="5a9d5-104">Die Klasse, die das Ereignis sendet (oder *auslöst*), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder *behandeln*), werden als *Abonnenten*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="5a9d5-105">In einer typischen C#-Windows Forms oder Web-Anwendung abonnieren Sie Ereignisse, die von Steuerelementen wie Schaltflächen und Listenfelder ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="5a9d5-106">Sie können die integrierte Entwicklungsumgebung (IDE) von Visual C# zum Durchsuchen der Ereignisse verwenden, die ein Steuerelement auslöst, und diejenigen wählen, die Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="5a9d5-107">Mithilfe der IDE können eine leere Ereignishandlermethode und der Code ganz einfach automatisch zu den Abonnenten des Ereignisses hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-107">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="5a9d5-108">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="5a9d5-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="5a9d5-109">Übersicht über Ereignisse</span><span class="sxs-lookup"><span data-stu-id="5a9d5-109">Events Overview</span></span>  
 <span data-ttu-id="5a9d5-110">Ereignisse verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="5a9d5-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="5a9d5-111">Der Herausgeber wird bestimmt, wenn ein Ereignis ausgelöst wird. Die Abonnenten bestimmen, welche Aktion als Reaktion auf das Ereignis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="5a9d5-112">Ein Ereignis kann mehrere Abonnenten haben.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="5a9d5-113">Ein Abonnent kann mehrere Ereignisse von mehreren Herausgebern behandeln.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="5a9d5-114">Ereignisse, die keine Abonnenten haben, werden nie ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="5a9d5-115">Ereignisse werden in der Regel verwendet, um Benutzeraktionen wie Mausklicks oder Menüauswahlen in GUI-Schnittstellen zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="5a9d5-116">Wenn ein Ereignis mehrere Abonnenten hat, werden die Ereignishandler synchron aufgerufen, wenn ein Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="5a9d5-117">Informationen zum asynchronen Aufrufen von Ereignissen finden Sie unter [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="5a9d5-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
-   <span data-ttu-id="5a9d5-118">In der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] -Klassenbibliothek basieren Ereignisse auf dem <xref:System.EventHandler> -Delegaten und der <xref:System.EventArgs> -Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5a9d5-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="5a9d5-119">Related Sections</span></span>  
 <span data-ttu-id="5a9d5-120">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="5a9d5-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="5a9d5-121">Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements</span><span class="sxs-lookup"><span data-stu-id="5a9d5-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="5a9d5-122">Vorgehensweise: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen</span><span class="sxs-lookup"><span data-stu-id="5a9d5-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="5a9d5-123">Vorgehensweise: Auslösen von Basisklassenereignissen in abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="5a9d5-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="5a9d5-124">Vorgehensweise:  Implementieren von Schnittstellenereignissen</span><span class="sxs-lookup"><span data-stu-id="5a9d5-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="5a9d5-125">Vorgehensweise: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen</span><span class="sxs-lookup"><span data-stu-id="5a9d5-125">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="5a9d5-126">Vorgehensweise: Implementieren von benutzerdefinierten Ereigniszugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="5a9d5-126">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="5a9d5-127">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="5a9d5-127">C# Language Specification</span></span>  

<span data-ttu-id="5a9d5-128">Weitere Informationen erhalten Sie unter [Ereignisse](~/_csharplang/spec/classes.md#events) in der [C#-Sprachspezifikation](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="5a9d5-128">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="5a9d5-129">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="5a9d5-129">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="5a9d5-130">Enthaltene Buchkapitel</span><span class="sxs-lookup"><span data-stu-id="5a9d5-130">Featured Book Chapters</span></span>  
 <span data-ttu-id="5a9d5-131">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegaten, Ereignisse und Lambda-Ausdrücke) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (C# 3.0-Cookbook, 3. Auflage: Mehr als 250 Lösungen für C# 3.0-Programmierer)</span><span class="sxs-lookup"><span data-stu-id="5a9d5-131">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="5a9d5-132">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) (Delegaten und Ereignisse) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29) (Erlernen von C# 3.0: Die Grundlagen von C# 3.0)</span><span class="sxs-lookup"><span data-stu-id="5a9d5-132">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a9d5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a9d5-133">See Also</span></span>

- <xref:System.EventHandler>  
- [<span data-ttu-id="5a9d5-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5a9d5-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5a9d5-135">Delegaten</span><span class="sxs-lookup"><span data-stu-id="5a9d5-135">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="5a9d5-136">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a9d5-136">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
