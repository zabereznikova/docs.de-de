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
ms.openlocfilehash: 00b12d9dc25e0704eb73d8bc727ae6647493f494
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401167"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="63e03-102">Vorgehensweise: Hinzufügen eines Ereignishandlers mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="63e03-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="63e03-103">In diesem Beispiel wird gezeigt, wie einem Element mithilfe von Code ein Ereignishandler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="63e03-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="63e03-104">Wenn Sie einem- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Element einen Ereignishandler hinzufügen möchten und die Markup Seite, die das-Element enthält, bereits geladen wurde, müssen Sie den Handler mithilfe von Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="63e03-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="63e03-105">Wenn Sie die Elementstruktur für eine Anwendung, die vollständig Code verwendet, und keine Elemente mithilfe [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]von deklarieren, können Sie alternativ bestimmte Methoden zum Hinzufügen von Ereignis Handlern zur konstruierten Elementstruktur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="63e03-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63e03-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63e03-106">Example</span></span>  
 <span data-ttu-id="63e03-107">Im folgenden Beispiel wird einer vorhandenen <xref:System.Windows.Controls.Button> Seite, die anfänglich in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]definiert ist, ein neues hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63e03-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="63e03-108">Eine Code Behind-Datei implementiert eine Ereignishandlermethode und fügt diese Methode dann als neuen Ereignishandler für <xref:System.Windows.Controls.Button>hinzu.</span><span class="sxs-lookup"><span data-stu-id="63e03-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="63e03-109">Im C# Beispiel wird der `+=` -Operator verwendet, um einem Ereignis einen Handler zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="63e03-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="63e03-110">Dabei handelt es sich um denselben Operator, der verwendet wird, um einen Handler im Ereignis Behandlungsmodell Common Language Runtime (CLR) zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="63e03-110">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="63e03-111">Microsoft Visual Basic unterstützt diesen Operator nicht als Mittel zum Hinzufügen von Ereignis Handlern.</span><span class="sxs-lookup"><span data-stu-id="63e03-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="63e03-112">Stattdessen ist eine von zwei Methoden erforderlich:</span><span class="sxs-lookup"><span data-stu-id="63e03-112">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="63e03-113">Verwenden Sie <xref:System.Windows.UIElement.AddHandler%2A> die-Methode und einen `AddressOf` -Operator, um auf die Ereignishandlerimplementierung zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="63e03-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="63e03-114">Verwenden Sie `Handles` das-Schlüsselwort als Teil der Ereignishandlerdefinition.</span><span class="sxs-lookup"><span data-stu-id="63e03-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="63e03-115">Diese Technik wird hier nicht angezeigt. siehe [Visual Basic und WPF-Ereignis Behandlung](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="63e03-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="63e03-116">Das Hinzufügen eines Ereignis Handlers in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anfänglich analysierten Seite ist viel einfacher.</span><span class="sxs-lookup"><span data-stu-id="63e03-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="63e03-117">Fügen Sie innerhalb des Objekt Elements, dem Sie den Ereignishandler hinzufügen möchten, ein Attribut hinzu, das dem Namen des Ereignisses entspricht, das Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="63e03-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="63e03-118">Geben Sie dann den Wert dieses Attributs als Namen der Ereignishandlermethode an, die Sie in der Code Behind-Datei [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der Seite definiert haben.</span><span class="sxs-lookup"><span data-stu-id="63e03-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="63e03-119">Weitere Informationen finden Sie unter [Übersicht über](routed-events-overview.md) [XAML (WPF)](xaml-overview-wpf.md) oder Routing Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="63e03-119">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e03-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63e03-120">See also</span></span>

- [<span data-ttu-id="63e03-121">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="63e03-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="63e03-122">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="63e03-122">How-to Topics</span></span>](events-how-to-topics.md)
