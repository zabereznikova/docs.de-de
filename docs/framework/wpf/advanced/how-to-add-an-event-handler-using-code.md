---
title: 'Vorgehensweise: Hinzufügen eines Ereignishandlers mithilfe von Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 10f8e0899e61d5d54589c910bdcbcd92d8ee947c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129355"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="481fb-102">Vorgehensweise: Hinzufügen eines Ereignishandlers mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="481fb-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="481fb-103">Dieses Beispiel zeigt, wie ein Element mithilfe von Code einen Ereignishandler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="481fb-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="481fb-104">Wenn Sie einen Ereignishandler hinzufügen möchten eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Element, und die Markupseite, die das Element enthält, bereits geladen wurde, müssen Sie den Handler, die mithilfe von Code.</span><span class="sxs-lookup"><span data-stu-id="481fb-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="481fb-105">Sie können auch bei der Erstellung die Elementstruktur für eine Anwendung vollständig mithilfe von Code, und deklarieren keine Elemente mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie bestimmte Methoden zum Hinzufügen von Ereignishandlern an die Struktur der konstruierte Element aufrufen.</span><span class="sxs-lookup"><span data-stu-id="481fb-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="481fb-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="481fb-106">Example</span></span>  
 <span data-ttu-id="481fb-107">Im folgenden Beispiel wird ein neues <xref:System.Windows.Controls.Button> zu einer vorhandenen Seite, die anfänglich in definiert ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="481fb-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="481fb-108">Eine Code-Behind-Datei implementiert eine Ereignishandlermethode, und fügt diese Methode als einen neuen Ereignishandler für die <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="481fb-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="481fb-109">Die C# Beispiel verwendet die `+=` Operator, um ein Ereignis einen Handler zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="481fb-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="481fb-110">Dies ist der gleiche Operator, der verwendet wird, weisen Sie einen Handler im der [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Modell für die Ereignisbehandlung.</span><span class="sxs-lookup"><span data-stu-id="481fb-110">This is the same operator that is used to assign a handler in the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event handling model.</span></span> <span data-ttu-id="481fb-111">Microsoft Visual Basic unterstützt diesen Operator nicht als Mittel zum Hinzufügen von Ereignishandlern.</span><span class="sxs-lookup"><span data-stu-id="481fb-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="481fb-112">Es muss stattdessen eine der beiden Methoden:</span><span class="sxs-lookup"><span data-stu-id="481fb-112">It instead requires one of two techniques:</span></span>  
  
-   <span data-ttu-id="481fb-113">Verwenden der <xref:System.Windows.UIElement.AddHandler%2A> -Methode zusammen mit einer `AddressOf` -Operator, um auf die Implementierung des Handlers zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="481fb-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
-   <span data-ttu-id="481fb-114">Verwenden der `Handles` -Schlüsselwort als Teil der Definition des Ereignis-Handler.</span><span class="sxs-lookup"><span data-stu-id="481fb-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="481fb-115">Diese Technik ist hier nicht gezeigt; finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="481fb-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="481fb-116">Hinzufügen eines ereignishandlers, der anfänglich analysierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite ist viel einfacher.</span><span class="sxs-lookup"><span data-stu-id="481fb-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="481fb-117">Fügen Sie in der Object-Element, in dem Sie den Ereignishandler hinzufügen möchten ein Attribut, das mit dem Namen des Ereignisses übereinstimmt, die Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="481fb-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="481fb-118">Geben Sie den Wert dieses Attributs als Namen für die Ereignishandlermethode, die Sie in der CodeBehind-Datei definiert die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite.</span><span class="sxs-lookup"><span data-stu-id="481fb-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="481fb-119">Weitere Informationen finden Sie unter [XAML Overview (WPF)](xaml-overview-wpf.md) oder [Übersicht über Routingereignisse](routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="481fb-119">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="481fb-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="481fb-120">See also</span></span>

- [<span data-ttu-id="481fb-121">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="481fb-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="481fb-122">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="481fb-122">How-to Topics</span></span>](events-how-to-topics.md)
