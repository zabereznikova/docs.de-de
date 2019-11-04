---
title: 'Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 457b8cf5c68096b20df7fe39f1cc3f40358f34d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460441"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="33324-102">Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="33324-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="33324-103">In diesem Beispiel wird gezeigt, wie einem Element mithilfe von Code ein Ereignishandler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="33324-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="33324-104">Wenn Sie einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Element einen Ereignishandler hinzufügen möchten und die Markup Seite, die das-Element enthält, bereits geladen wurde, müssen Sie den Handler mithilfe von Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="33324-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="33324-105">Wenn Sie die Elementstruktur für eine Anwendung vollständig mit Code und ohne Deklaration von Elementen mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]aufbauen, können Sie auch bestimmte Methoden zum Hinzufügen von Ereignis Handlern zur konstruierten Elementstruktur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="33324-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33324-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="33324-106">Example</span></span>  
 <span data-ttu-id="33324-107">Im folgenden Beispiel wird einer vorhandenen Seite, die anfänglich in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]definiert ist, ein neues <xref:System.Windows.Controls.Button> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="33324-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="33324-108">Eine Code Behind-Datei implementiert eine Ereignishandlermethode und fügt diese Methode dann als neuen Ereignishandler auf dem <xref:System.Windows.Controls.Button>hinzu.</span><span class="sxs-lookup"><span data-stu-id="33324-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="33324-109">Im C# Beispiel wird der `+=`-Operator verwendet, um einem Ereignis einen Handler zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="33324-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="33324-110">Dabei handelt es sich um denselben Operator, der verwendet wird, um einen Handler im Ereignis Behandlungsmodell Common Language Runtime (CLR) zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="33324-110">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="33324-111">Microsoft Visual Basic unterstützt diesen Operator nicht als Mittel zum Hinzufügen von Ereignis Handlern.</span><span class="sxs-lookup"><span data-stu-id="33324-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="33324-112">Stattdessen ist eine von zwei Methoden erforderlich:</span><span class="sxs-lookup"><span data-stu-id="33324-112">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="33324-113">Verwenden Sie die <xref:System.Windows.UIElement.AddHandler%2A>-Methode sowie einen `AddressOf`-Operator, um auf die Ereignishandlerimplementierung zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="33324-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="33324-114">Verwenden Sie das `Handles`-Schlüsselwort als Teil der Ereignishandlerdefinition.</span><span class="sxs-lookup"><span data-stu-id="33324-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="33324-115">Diese Technik wird hier nicht angezeigt. siehe [Visual Basic und WPF-Ereignis Behandlung](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="33324-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="33324-116">Das Hinzufügen eines Ereignis Handlers in der anfänglich analysierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite ist viel einfacher.</span><span class="sxs-lookup"><span data-stu-id="33324-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="33324-117">Fügen Sie innerhalb des Objekt Elements, dem Sie den Ereignishandler hinzufügen möchten, ein Attribut hinzu, das dem Namen des Ereignisses entspricht, das Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="33324-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="33324-118">Geben Sie dann den Wert dieses Attributs als Namen der Ereignishandlermethode an, die Sie in der Code-Behind-Datei der Seite "[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]" definiert haben.</span><span class="sxs-lookup"><span data-stu-id="33324-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="33324-119">Weitere Informationen finden Sie unter [Übersicht über](routed-events-overview.md) [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) oder Routing Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="33324-119">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33324-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33324-120">See also</span></span>

- [<span data-ttu-id="33324-121">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="33324-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="33324-122">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="33324-122">How-to Topics</span></span>](events-how-to-topics.md)
