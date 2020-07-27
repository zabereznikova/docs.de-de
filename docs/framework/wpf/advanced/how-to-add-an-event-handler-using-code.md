---
title: 'Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code'
description: Verwenden Sie dieses Beispiel, um zu erfahren, wie Sie einem Element in Windows Presentation Foundation einen Ereignishandler hinzufügen, indem Sie Code verwenden, anstatt ihn mithilfe von XAML zu deklarieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: b36969f7a65ccbf6c9d03b22767d9eacdc177ad1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166362"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="81aac-103">Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="81aac-103">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="81aac-104">In diesem Beispiel wird gezeigt, wie einem Element mithilfe von Code ein Ereignishandler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="81aac-104">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="81aac-105">Wenn Sie einem-Element einen Ereignishandler hinzufügen möchten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und die Markup Seite, die das-Element enthält, bereits geladen wurde, müssen Sie den Handler mithilfe von Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="81aac-105">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="81aac-106">Wenn Sie die Elementstruktur für eine Anwendung, die vollständig Code verwendet, und keine Elemente mithilfe von deklarieren [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , können Sie alternativ bestimmte Methoden zum Hinzufügen von Ereignis Handlern zur konstruierten Elementstruktur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="81aac-106">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81aac-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81aac-107">Example</span></span>  
 <span data-ttu-id="81aac-108">Im folgenden Beispiel <xref:System.Windows.Controls.Button> wird einer vorhandenen Seite, die anfänglich in definiert ist, ein neues hinzugefügt [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81aac-108">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="81aac-109">Eine Code Behind-Datei implementiert eine Ereignishandlermethode und fügt diese Methode dann als neuen Ereignishandler für hinzu <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="81aac-109">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="81aac-110">Im c#-Beispiel wird der- `+=` Operator verwendet, um einem Ereignis einen Handler zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="81aac-110">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="81aac-111">Dabei handelt es sich um denselben Operator, der verwendet wird, um einen Handler im Ereignis Behandlungsmodell Common Language Runtime (CLR) zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="81aac-111">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="81aac-112">Microsoft Visual Basic unterstützt diesen Operator nicht als Mittel zum Hinzufügen von Ereignis Handlern.</span><span class="sxs-lookup"><span data-stu-id="81aac-112">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="81aac-113">Stattdessen ist eine von zwei Methoden erforderlich:</span><span class="sxs-lookup"><span data-stu-id="81aac-113">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="81aac-114">Verwenden Sie die- <xref:System.Windows.UIElement.AddHandler%2A> Methode und einen- `AddressOf` Operator, um auf die Ereignishandlerimplementierung zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="81aac-114">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="81aac-115">Verwenden Sie das- `Handles` Schlüsselwort als Teil der Ereignishandlerdefinition.</span><span class="sxs-lookup"><span data-stu-id="81aac-115">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="81aac-116">Diese Technik wird hier nicht angezeigt. siehe [Visual Basic und WPF-Ereignis Behandlung](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="81aac-116">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="81aac-117">Das Hinzufügen eines Ereignis Handlers in der anfänglich analysierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite ist viel einfacher.</span><span class="sxs-lookup"><span data-stu-id="81aac-117">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="81aac-118">Fügen Sie innerhalb des Objekt Elements, dem Sie den Ereignishandler hinzufügen möchten, ein Attribut hinzu, das dem Namen des Ereignisses entspricht, das Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="81aac-118">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="81aac-119">Geben Sie dann den Wert dieses Attributs als Namen der Ereignishandlermethode an, die Sie in der Code Behind-Datei der Seite definiert haben [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81aac-119">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="81aac-120">Weitere Informationen finden Sie unter [Übersicht über](routed-events-overview.md) [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) oder Routing Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="81aac-120">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81aac-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81aac-121">See also</span></span>

- [<span data-ttu-id="81aac-122">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="81aac-122">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="81aac-123">Artikel zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="81aac-123">How-to Topics</span></span>](events-how-to-topics.md)
