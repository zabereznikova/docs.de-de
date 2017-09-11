---
title: Ereignisse (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6a913a615de8185bb358376def1e2a051bdaa951
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="events-c-programming-guide"></a><span data-ttu-id="4ebf0-102">Ereignisse (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4ebf0-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="4ebf0-103">Ereignisse aktivieren eine [Klasse](../../../csharp/language-reference/keywords/class.md) oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="4ebf0-104">Die Klasse, die das Ereignis sendet (oder *auslöst*), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder *behandeln*), werden als *Abonnenten*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="4ebf0-105">In einer typischen C#-Windows Forms oder Web-Anwendung abonnieren Sie Ereignisse, die von Steuerelementen wie Schaltflächen und Listenfelder ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="4ebf0-106">Sie können die [!INCLUDE[csprcs](~/includes/csprcs-md.md)] -integrierte Entwicklungsumgebung (IDE) zum Durchsuchen der Ereignisse verwenden, die ein Steuerelement auslöst, und diejenigen wählen, die Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-106">You can use the [!INCLUDE[csprcs](~/includes/csprcs-md.md)] integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="4ebf0-107">Die IDE fügt automatisch eine leere Ereignishandlermethode und den Code zum Abonnieren des Ereignisses hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-107">The IDE automatically adds an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="4ebf0-108">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="4ebf0-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="4ebf0-109">Übersicht über Ereignisse</span><span class="sxs-lookup"><span data-stu-id="4ebf0-109">Events Overview</span></span>  
 <span data-ttu-id="4ebf0-110">Ereignisse verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="4ebf0-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="4ebf0-111">Der Herausgeber wird bestimmt, wenn ein Ereignis ausgelöst wird. Die Abonnenten bestimmen, welche Aktion als Reaktion auf das Ereignis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="4ebf0-112">Ein Ereignis kann mehrere Abonnenten haben.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="4ebf0-113">Ein Abonnent kann mehrere Ereignisse von mehreren Herausgebern behandeln.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="4ebf0-114">Ereignisse, die keine Abonnenten haben, werden nie ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="4ebf0-115">Ereignisse werden in der Regel verwendet, um Benutzeraktionen wie Mausklicks oder Menüauswahlen in GUI-Schnittstellen zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="4ebf0-116">Wenn ein Ereignis mehrere Abonnenten hat, werden die Ereignishandler synchron aufgerufen, wenn ein Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="4ebf0-117">Informationen zum asynchronen Aufrufen von Ereignissen finden Sie unter [Calling Synchronous Methods Asynchronously](https://msdn.microsoft.com/library/2e08f6yc).</span><span class="sxs-lookup"><span data-stu-id="4ebf0-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](https://msdn.microsoft.com/library/2e08f6yc).</span></span>  
  
-   <span data-ttu-id="4ebf0-118">In der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] -Klassenbibliothek basieren Ereignisse auf dem <xref:System.EventHandler> -Delegaten und der <xref:System.EventArgs> -Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="4ebf0-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4ebf0-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4ebf0-119">Related Sections</span></span>  
 <span data-ttu-id="4ebf0-120">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="4ebf0-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="4ebf0-121">Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements</span><span class="sxs-lookup"><span data-stu-id="4ebf0-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="4ebf0-122">Gewusst wie: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen</span><span class="sxs-lookup"><span data-stu-id="4ebf0-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="4ebf0-123">Gewusst wie: Auslösen von Basisklassenereignissen in abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="4ebf0-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="4ebf0-124">Gewusst wie: Implementieren von Schnittstellenereignissen</span><span class="sxs-lookup"><span data-stu-id="4ebf0-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="4ebf0-125">Threadsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="4ebf0-125">Thread Synchronization</span></span>](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [<span data-ttu-id="4ebf0-126">Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen</span><span class="sxs-lookup"><span data-stu-id="4ebf0-126">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="4ebf0-127">Gewusst wie: Implementieren benutzerdefinierter Ereigniszugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="4ebf0-127">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="4ebf0-128">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="4ebf0-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="4ebf0-129">Enthaltene Buchkapitel</span><span class="sxs-lookup"><span data-stu-id="4ebf0-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="4ebf0-130">[Delegaten, Ereignisse und Lambda-Ausdrücke](http://go.microsoft.com/fwlink/?LinkId=195395) im [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="4ebf0-130">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
 <span data-ttu-id="4ebf0-131">[Delegaten und Ereignisse](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span><span class="sxs-lookup"><span data-stu-id="4ebf0-131">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebf0-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ebf0-132">See Also</span></span>  
 <span data-ttu-id="4ebf0-133"><xref:System.EventHandler></span><span class="sxs-lookup"><span data-stu-id="4ebf0-133"><xref:System.EventHandler></span></span>   
 <span data-ttu-id="4ebf0-134">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4ebf0-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4ebf0-135">[Delegaten](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="4ebf0-135">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="4ebf0-136">[Erstellen von Ereignishandlern in Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx) </span><span class="sxs-lookup"><span data-stu-id="4ebf0-136">[Creating Event Handlers in Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx) </span></span>  
 [<span data-ttu-id="4ebf0-137">Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster</span><span class="sxs-lookup"><span data-stu-id="4ebf0-137">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](https://msdn.microsoft.com/library/hkasytyf)

