---
title: "Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 348136a1feaf6e0a0824cf183a2eeec4e10b77fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="08ab9-102">Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="08ab9-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="08ab9-103">Dieses Beispiel zeigt, wie einen Ereignishandler mithilfe von Code ein Element hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="08ab9-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="08ab9-104">Wenn Sie einen Ereignishandler hinzufügen möchten eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Element, und die Markupseite, die das Element enthält, bereits geladen wurde, müssen Sie den Handler mithilfe von Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="08ab9-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="08ab9-105">Auch wenn Sie die Elementstruktur für eine Anwendung vollständig mithilfe von Code und keine Elemente mit deklarieren erstellen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie bestimmte Methoden zum Hinzufügen von Ereignishandlern zu die konstruierten Elementstruktur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="08ab9-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08ab9-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08ab9-106">Example</span></span>  
 <span data-ttu-id="08ab9-107">Im folgende Beispiel wird ein neues <xref:System.Windows.Controls.Button> auf eine Seite, die anfänglich in definiert ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08ab9-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="08ab9-108">Eine Code-Behind-Datei implementiert eine Ereignishandlermethode und fügt dann diese Methode als neuen Ereignishandler auf der <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="08ab9-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="08ab9-109">Die [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] Beispiel verwendet die `+=` Operator, um einen Handler, ein Ereignis zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="08ab9-109">The [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="08ab9-110">Dies ist der gleichen Operator, der verwendet wird, weisen Sie einen Handler im die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Modell für die Ereignisbehandlung.</span><span class="sxs-lookup"><span data-stu-id="08ab9-110">This is the same operator that is used to assign a handler in the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event handling model.</span></span> [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)]<span data-ttu-id="08ab9-111">unterstützt nicht diesen Operator als Mittel zum Hinzufügen von Ereignishandlern.</span><span class="sxs-lookup"><span data-stu-id="08ab9-111"> does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="08ab9-112">Es muss stattdessen eine der beiden folgenden Verfahren:</span><span class="sxs-lookup"><span data-stu-id="08ab9-112">It instead requires one of two techniques:</span></span>  
  
-   <span data-ttu-id="08ab9-113">Verwenden der <xref:System.Windows.UIElement.AddHandler%2A> -Methode, zusammen mit einem `AddressOf` -Operator, um auf die Ereignishandlerimplementierung verweisen.</span><span class="sxs-lookup"><span data-stu-id="08ab9-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
-   <span data-ttu-id="08ab9-114">Verwenden der `Handles` -Schlüsselwort als Teil der Definition des Ereignis-Handler.</span><span class="sxs-lookup"><span data-stu-id="08ab9-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="08ab9-115">Diese Technik ist hier nicht gezeigt; finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="08ab9-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="08ab9-116">Ein Ereignishandler hinzugefügt, der anfänglich analysierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite ist viel einfacher.</span><span class="sxs-lookup"><span data-stu-id="08ab9-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="08ab9-117">Fügen Sie in den Object-Element, in dem der Ereignishandler hinzugefügt werden sollen ein Attribut, das den Namen des Ereignisses übereinstimmt, die Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="08ab9-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="08ab9-118">Geben Sie den Wert dieses Attributs als Namen für die Ereignishandlermethode, die Sie in der CodeBehind-Datei definiert die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite.</span><span class="sxs-lookup"><span data-stu-id="08ab9-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="08ab9-119">Weitere Informationen finden Sie unter [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) oder [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="08ab9-119">For more information, see [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) or [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ab9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08ab9-120">See Also</span></span>  
 [<span data-ttu-id="08ab9-121">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="08ab9-121">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="08ab9-122">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="08ab9-122">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
