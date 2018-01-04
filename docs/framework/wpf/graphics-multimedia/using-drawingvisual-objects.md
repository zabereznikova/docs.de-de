---
title: Verwenden von DrawingVisual-Objekten
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
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a33e56b69a357694a1d1a23d5cd3c887c88cea37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-drawingvisual-objects"></a><span data-ttu-id="d7134-102">Verwenden von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="d7134-102">Using DrawingVisual Objects</span></span>
<span data-ttu-id="d7134-103">Dieses Thema bietet einen Überblick zum Verwenden <xref:System.Windows.Media.DrawingVisual> Objekte in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visueller Ebene.</span><span class="sxs-lookup"><span data-stu-id="d7134-103">This topic provides an overview of how to use <xref:System.Windows.Media.DrawingVisual> objects in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visual layer.</span></span>  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a><span data-ttu-id="d7134-104">DrawingVisual-Objekt</span><span class="sxs-lookup"><span data-stu-id="d7134-104">DrawingVisual Object</span></span>  
 <span data-ttu-id="d7134-105">Die <xref:System.Windows.Media.DrawingVisual> ist eine einfache zeichnen-Klasse, die zum Rendern von Formen, Bildern oder Text verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7134-105">The <xref:System.Windows.Media.DrawingVisual> is a lightweight drawing class that is used to render shapes, images, or text.</span></span> <span data-ttu-id="d7134-106">Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Leistung gesteigert.</span><span class="sxs-lookup"><span data-stu-id="d7134-106">This class is considered lightweight because it does not provide layout or event handling, which improves its performance.</span></span> <span data-ttu-id="d7134-107">Aus diesem Grund sind Zeichnungen für Hintergründe und ClipArt ideal.</span><span class="sxs-lookup"><span data-stu-id="d7134-107">For this reason, drawings are ideal for backgrounds and clip art.</span></span>  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a><span data-ttu-id="d7134-108">DrawingVisual-Hostcontainer</span><span class="sxs-lookup"><span data-stu-id="d7134-108">DrawingVisual Host Container</span></span>  
 <span data-ttu-id="d7134-109">Um verwenden <xref:System.Windows.Media.DrawingVisual> -Objekte, müssen Sie einen Hostcontainer für die Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7134-109">In order to use <xref:System.Windows.Media.DrawingVisual> objects, you need to create a host container for the objects.</span></span> <span data-ttu-id="d7134-110">Leiten die Host-Container-Objekt aus der <xref:System.Windows.FrameworkElement> -Klasse, die das Layout und Ereignisbehandlung zu unterstützen, stellt die <xref:System.Windows.Media.DrawingVisual> Klasse besitzt.</span><span class="sxs-lookup"><span data-stu-id="d7134-110">The host container object must derive from the <xref:System.Windows.FrameworkElement> class, which provides the layout and event handling support that the <xref:System.Windows.Media.DrawingVisual> class lacks.</span></span> <span data-ttu-id="d7134-111">Das Hostcontainerobjekt zeigt keine sichtbaren Eigenschaften, da seine Hauptfunktion die Aufnahme untergeordneter Objekte ist.</span><span class="sxs-lookup"><span data-stu-id="d7134-111">The host container object does not display any visible properties, since its main purpose is to contain child objects.</span></span> <span data-ttu-id="d7134-112">Allerdings die <xref:System.Windows.UIElement.Visibility%2A> -Eigenschaft des Hostcontainers muss festgelegt werden, um <xref:System.Windows.Visibility.Visible>ist, andernfalls keines der untergeordneten Elemente werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7134-112">However, the <xref:System.Windows.UIElement.Visibility%2A> property of the host container must be set to <xref:System.Windows.Visibility.Visible>; otherwise, none of its child elements will be visible.</span></span>  
  
 <span data-ttu-id="d7134-113">Wenn Sie einen Host-Container-Objekt, für visuelle Objekte erstellen, müssen Sie zum Speichern der visuellen Objektverweisen in einem <xref:System.Windows.Media.VisualCollection>.</span><span class="sxs-lookup"><span data-stu-id="d7134-113">When you create a host container object for visual objects, you need to store the visual object references in a <xref:System.Windows.Media.VisualCollection>.</span></span> <span data-ttu-id="d7134-114">Verwenden der <xref:System.Windows.Media.VisualCollection.Add%2A> Methode, um ein visuelles Objekt auf den Hostcontainer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d7134-114">Use the <xref:System.Windows.Media.VisualCollection.Add%2A> method to add a visual object to the host container.</span></span> <span data-ttu-id="d7134-115">Im folgenden Beispiel wird ein Hostobjekt für den Container erstellt und drei visuelle Objekte werden hinzugefügt, um seine <xref:System.Windows.Media.VisualCollection>.</span><span class="sxs-lookup"><span data-stu-id="d7134-115">In the following example, a host container object is created, and three visual objects are added to its <xref:System.Windows.Media.VisualCollection>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  <span data-ttu-id="d7134-116">Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="d7134-116">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).</span></span>  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a><span data-ttu-id="d7134-117">Erstellen von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="d7134-117">Creating DrawingVisual Objects</span></span>  
 <span data-ttu-id="d7134-118">Beim Erstellen einer <xref:System.Windows.Media.DrawingVisual> Objekt, er hat keine Zeichnungsinhalt.</span><span class="sxs-lookup"><span data-stu-id="d7134-118">When you create a <xref:System.Windows.Media.DrawingVisual> object, it has no drawing content.</span></span> <span data-ttu-id="d7134-119">Sie können Text, Grafiken oder Bildinhalt hinzufügen, indem des Objekts abrufen <xref:System.Windows.Media.DrawingContext> und die Zeichnung.</span><span class="sxs-lookup"><span data-stu-id="d7134-119">You can add text, graphics, or image content by retrieving the object's <xref:System.Windows.Media.DrawingContext> and drawing into it.</span></span> <span data-ttu-id="d7134-120">Ein <xref:System.Windows.Media.DrawingContext> wird zurückgegeben, indem die <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> Methode von einem <xref:System.Windows.Media.DrawingVisual> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7134-120">A <xref:System.Windows.Media.DrawingContext> is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span>  
  
 <span data-ttu-id="d7134-121">Zeichnen Sie ein Rechteck in der <xref:System.Windows.Media.DrawingContext>, verwenden die <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> Methode der <xref:System.Windows.Media.DrawingContext> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7134-121">To draw a rectangle into the <xref:System.Windows.Media.DrawingContext>, use the <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> method of the <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="d7134-122">Ähnliche Methoden sind für andere Arten von Inhalten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d7134-122">Similar methods exist for drawing other types of content.</span></span> <span data-ttu-id="d7134-123">Sie danach Zeichnungsinhalt in der <xref:System.Windows.Media.DrawingContext>, rufen Sie die <xref:System.Windows.Media.DrawingContext.Close%2A> Methode zum Schließen der <xref:System.Windows.Media.DrawingContext> und den Inhalt beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="d7134-123">When you are finished drawing content into the <xref:System.Windows.Media.DrawingContext>, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the <xref:System.Windows.Media.DrawingContext> and persist the content.</span></span>  
  
 <span data-ttu-id="d7134-124">Im folgenden Beispiel ein <xref:System.Windows.Media.DrawingVisual> Objekt wird erstellt, und ein Rechteck gezeichnet, in dessen <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="d7134-124">In the following example, a <xref:System.Windows.Media.DrawingVisual> object is created, and a rectangle is drawn into its <xref:System.Windows.Media.DrawingContext>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a><span data-ttu-id="d7134-125">Erstellen von Überschreibungen für Elemente von FrameworkElement</span><span class="sxs-lookup"><span data-stu-id="d7134-125">Creating Overrides for FrameworkElement Members</span></span>  
 <span data-ttu-id="d7134-126">Der Hostcontainerobjekt ist für die Verwaltung seiner Auflistung von visuellen Objekten zuständig.</span><span class="sxs-lookup"><span data-stu-id="d7134-126">The host container object is responsible for managing its collection of visual objects.</span></span> <span data-ttu-id="d7134-127">Dies erfordert, dass der Hostcontainer Member Außerkraftsetzungen für die abgeleitete implementieren <xref:System.Windows.FrameworkElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d7134-127">This requires that the host container implement member overrides for the derived <xref:System.Windows.FrameworkElement> class.</span></span>  
  
 <span data-ttu-id="d7134-128">Die folgende Liste beschreibt die zwei Elemente, die Sie überschreiben müssen:</span><span class="sxs-lookup"><span data-stu-id="d7134-128">The following list describes the two members you must override:</span></span>  
  
-   <span data-ttu-id="d7134-129"><xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Gibt ein untergeordnetes Element am angegebenen Index aus der Auflistung von untergeordneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="d7134-129"><xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Returns a child at the specified index from the collection of child elements.</span></span>  
  
-   <span data-ttu-id="d7134-130"><xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Ruft die Anzahl der sichtbaren untergeordneten Elemente innerhalb dieses Elements ab.</span><span class="sxs-lookup"><span data-stu-id="d7134-130"><xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Gets the number of visual child elements within this element.</span></span>  
  
 <span data-ttu-id="d7134-131">Im folgenden Beispiel überschreibt, für die beiden <xref:System.Windows.FrameworkElement> Member implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="d7134-131">In the following example, overrides for the two <xref:System.Windows.FrameworkElement> members are implemented.</span></span>  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a><span data-ttu-id="d7134-132">Bereitstellen von Unterstützung für den Treffertest</span><span class="sxs-lookup"><span data-stu-id="d7134-132">Providing Hit Testing Support</span></span>  
 <span data-ttu-id="d7134-133">Das Hostobjekt für den Container bieten Ereignisbehandlung, auch wenn keine angezeigten Eigenschaften anzuzeigen, jedoch seine <xref:System.Windows.UIElement.Visibility%2A> Eigenschaft muss festgelegt werden, um <xref:System.Windows.Visibility.Visible>.</span><span class="sxs-lookup"><span data-stu-id="d7134-133">The host container object can provide event handling even if it does not display any visible properties—however, its <xref:System.Windows.UIElement.Visibility%2A> property must be set to <xref:System.Windows.Visibility.Visible>.</span></span> <span data-ttu-id="d7134-134">Dadurch können Sie eine Ereignisbehandlungsroutine für den Hostcontainer erstellen, die Mausereignisse, z.B. das Loslassen der linken Maustaste, auffangen kann.</span><span class="sxs-lookup"><span data-stu-id="d7134-134">This allows you to create an event handling routine for the host container that can trap mouse events, such as the release of the left mouse button.</span></span> <span data-ttu-id="d7134-135">Die Routine für die Ereignisbehandlung kann dann implementieren Treffertests durch Aufrufen der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="d7134-135">The event handling routine can then implement hit testing by invoking the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="d7134-136">Der Methode <xref:System.Windows.Media.HitTestResultCallback> Parameter verweist auf eine benutzerdefinierte Prozedur, die Sie verwenden können, um zu bestimmen, die sich ergebenden Aktion eines Treffertests.</span><span class="sxs-lookup"><span data-stu-id="d7134-136">The method's <xref:System.Windows.Media.HitTestResultCallback> parameter refers to a user-defined procedure that you can use to determine the resulting action of a hit test.</span></span>  
  
 <span data-ttu-id="d7134-137">Im folgenden Beispiel wird die Unterstützung für Treffertests für das Hostcontainerobjekt und seine untergeordneten Elemente implementiert.</span><span class="sxs-lookup"><span data-stu-id="d7134-137">In the following example, hit testing support is implemented for the host container object and its children.</span></span>  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="d7134-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7134-138">See Also</span></span>  
 <xref:System.Windows.Media.DrawingVisual>  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 [<span data-ttu-id="d7134-139">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="d7134-139">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="d7134-140">Treffertests in der visuellen Ebene</span><span class="sxs-lookup"><span data-stu-id="d7134-140">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
