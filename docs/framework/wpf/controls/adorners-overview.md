---
title: Übersicht über Adorner
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: 94075189d82e5d446b3058b944c789a4288c26ca
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634530"
---
# <a name="adorners-overview"></a><span data-ttu-id="85112-102">Übersicht über Adorner</span><span class="sxs-lookup"><span data-stu-id="85112-102">Adorners Overview</span></span>
<span data-ttu-id="85112-103">Adorner sind eine besondere Art von <xref:System.Windows.FrameworkElement>verwendet, um visuelle Hinweise zu einem Benutzer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="85112-103">Adorners are a special type of <xref:System.Windows.FrameworkElement>, used to provide visual cues to a user.</span></span> <span data-ttu-id="85112-104">Adorner können unter anderem verwendet werden, um Elementen funktionale Ziehpunkte hinzuzufügen oder Zustandsinformationen über Steuerelemente bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="85112-104">Among other uses, Adorners can be used to add functional handles to elements or provide state information about a control.</span></span>  
  
  
  
<a name="about_Adorners"></a>   
## <a name="about-adorners"></a><span data-ttu-id="85112-105">Informationen über Adorner</span><span class="sxs-lookup"><span data-stu-id="85112-105">About Adorners</span></span>  
 <span data-ttu-id="85112-106">Ein <xref:System.Windows.Documents.Adorner> ist eine benutzerdefinierte <xref:System.Windows.FrameworkElement> Bindung an eine <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="85112-106">An <xref:System.Windows.Documents.Adorner> is a custom <xref:System.Windows.FrameworkElement> that is bound to a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="85112-107">Adorner gerendert werden, eine <xref:System.Windows.Documents.AdornerLayer>, d.h. eine Renderingoberfläche, die immer über dem verzierten Element oder eine Auflistung von verzierten Elemente ist.</span><span class="sxs-lookup"><span data-stu-id="85112-107">Adorners are rendered in an <xref:System.Windows.Documents.AdornerLayer>, which is a rendering surface that is always on top of the adorned element or a collection of adorned elements.</span></span> <span data-ttu-id="85112-108">Rendering eines Adorners erfolgt unabhängig vom Rendering aus, der die <xref:System.Windows.UIElement> , das der Adorner gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="85112-108">Rendering of an adorner is independent from rendering of the <xref:System.Windows.UIElement> that the adorner is bound to.</span></span> <span data-ttu-id="85112-109">Ein Adorner wird in der Regel relativ zum Element positioniert, an das er gebunden ist. Dazu wird ein 2D-Standardkoordinatenursprung verwendet, der sich in der oberen linken Ecke des verzierten Elements befindet.</span><span class="sxs-lookup"><span data-stu-id="85112-109">An adorner is typically positioned relative to the element to which it is bound, using the standard 2-D coordinate origin located at the upper-left of the adorned element.</span></span>  
  
 <span data-ttu-id="85112-110">Adorner finden eine breite Anwendung in folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="85112-110">Common applications for adorners include:</span></span>  
  
-   <span data-ttu-id="85112-111">Hinzufügen funktionaler Ziehpunkte zu einem <xref:System.Windows.UIElement> , mit denen einen Benutzer das Element auf irgendeine Weise (Größe ändern, drehen, neu positionieren, usw.) zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="85112-111">Adding functional handles to a <xref:System.Windows.UIElement> that enable a user to manipulate the element in some way (resize, rotate, reposition, etc.).</span></span>  
  
-   <span data-ttu-id="85112-112">Bereitstellen von visuellem Feedback, um verschiedene Zustände anzugeben oder auf verschiedene Ereignisse zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="85112-112">Provide visual feedback to indicate various states, or in response to various events.</span></span>  
  
-   <span data-ttu-id="85112-113">Überlagerung von visuellen Dekorationen auf einem <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="85112-113">Overlay visual decorations on a <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="85112-114">Visuelles Maskieren oder überschreiben oder teilweise ein <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="85112-114">Visually mask or override part or all of a <xref:System.Windows.UIElement>.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="85112-115">stellt ein grundlegendes Framework zum Verzieren von visuellen Elementen bereit.</span><span class="sxs-lookup"><span data-stu-id="85112-115">provides a basic framework for adorning visual elements.</span></span> <span data-ttu-id="85112-116">In der folgenden Tabelle sind die zum Verzieren von Objekten verwendeten primären Typen samt deren Zweck aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="85112-116">The following table lists the primary types used when adorning objects, and their purpose.</span></span> <span data-ttu-id="85112-117">Es folgen mehrere Verwendungsbeispiele.</span><span class="sxs-lookup"><span data-stu-id="85112-117">Several usage examples follow.</span></span>  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|<span data-ttu-id="85112-118">Eine abstrakte Basisklasse, von der alle einzelnen Adornerimplementierungen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="85112-118">An abstract base class from which all concrete adorner implementations inherit.</span></span>|  
|<xref:System.Windows.Documents.AdornerLayer>|<span data-ttu-id="85112-119">Eine Klasse, die eine Rendering-Ebene für den (die) Adorner eines oder mehrerer verzierten Elementen darstellt.</span><span class="sxs-lookup"><span data-stu-id="85112-119">A class representing a rendering layer for the adorner(s) of one or more adorned elements.</span></span>|  
|<xref:System.Windows.Documents.AdornerDecorator>|<span data-ttu-id="85112-120">Eine Klasse, mit der eine Adorner-Ebene einer Auflistung von Elementen zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="85112-120">A class that enables an adorner layer to be associated with a collection of elements.</span></span>|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a><span data-ttu-id="85112-121">Implementierung eines benutzerdefinierten Adorners</span><span class="sxs-lookup"><span data-stu-id="85112-121">Implementing a Custom Adorner</span></span>  
 <span data-ttu-id="85112-122">Das von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellte Adorner-Framework dient in erster Linie der Unterstützung beim Erstellen benutzerdefinierter Adorner.</span><span class="sxs-lookup"><span data-stu-id="85112-122">The adorners framework provided by [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is intended primarily to support the creation of custom adorners.</span></span> <span data-ttu-id="85112-123">Ein benutzerdefinierter Adorner wird erstellt, durch die Implementierung einer Klasse, die von der abstrakten erbt <xref:System.Windows.Documents.Adorner> Klasse.</span><span class="sxs-lookup"><span data-stu-id="85112-123">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85112-124">Das übergeordnete Element einer <xref:System.Windows.Documents.Adorner> ist die <xref:System.Windows.Documents.AdornerLayer> , rendert die <xref:System.Windows.Documents.Adorner>, nicht das Element, das gestaltet wird.</span><span class="sxs-lookup"><span data-stu-id="85112-124">The parent of an <xref:System.Windows.Documents.Adorner> is the <xref:System.Windows.Documents.AdornerLayer> that renders the <xref:System.Windows.Documents.Adorner>, not the element being adorned.</span></span>  
  
 <span data-ttu-id="85112-125">Im folgenden Beispiel wird eine Klasse dargestellt, in der ein einfacher Adorner implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="85112-125">The following example shows a class that implements a simple adorner.</span></span> <span data-ttu-id="85112-126">Der Beispiel-Adorner verziert einfach die Ecken einer <xref:System.Windows.UIElement> mit Kreisen.</span><span class="sxs-lookup"><span data-stu-id="85112-126">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 <span data-ttu-id="85112-127">Die folgende Abbildung zeigt die SimpleCircleAdorner angewendet werden, um eine <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="85112-127">The following image shows the SimpleCircleAdorner applied to a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 ![Screenshot mit einem ein Textfeld.](./media/adorners-overview/simplecircleadorner-textbox.png)  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a><span data-ttu-id="85112-129">Renderingverhalten der Adorner</span><span class="sxs-lookup"><span data-stu-id="85112-129">Rendering Behavior for Adorners</span></span>  
 <span data-ttu-id="85112-130">Beachten Sie, dass für Adorner kein Renderingverhalten festgelegt ist. Damit wird sichergestellt, dass für das Rendering die Adorner-Implementierung verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="85112-130">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="85112-131">Eine gängige Methode, der Renderingverhalten zu implementieren ist, überschreiben die <xref:System.Windows.UIElement.OnRender%2A> -Methode und eine oder mehrere <xref:System.Windows.Media.DrawingContext> Objekte, um die Darstellung des Adorners nach Bedarf (wie im Beispiel oben gezeigt) zu rendern.</span><span class="sxs-lookup"><span data-stu-id="85112-131">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in the example above).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85112-132">Sämtliche Elemente auf der Adorner-Ebene werden vor allen anderen Stilen gerendert, die Sie festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="85112-132">Anything placed in the adorner layer is rendered on top of the rest of any styles you have set.</span></span> <span data-ttu-id="85112-133">Anders gesagt, befinden sich Adorner visuell stets im Vordergrund und können in der Z-Reihenfolge nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="85112-133">In other words, adorners are always visually on top and cannot be overridden using z-order.</span></span>  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a><span data-ttu-id="85112-134">Ereignisse und Treffertests</span><span class="sxs-lookup"><span data-stu-id="85112-134">Events and Hit Testing</span></span>  
 <span data-ttu-id="85112-135">Adorner empfangen Eingabeereignisse wie jedes andere <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="85112-135">Adorners receive input events just like any other <xref:System.Windows.FrameworkElement>.</span></span>  <span data-ttu-id="85112-136">Da ein Adorner immer höhere Z-Reihenfolge als das Element, er verziert verfügt, empfängt der Adorner Eingabeereignisse (z. B. <xref:System.Windows.UIElement.Drop> oder <xref:System.Windows.UIElement.MouseMove>), die für die zugrunde liegende Element Verzierte vorgesehen werden kann.</span><span class="sxs-lookup"><span data-stu-id="85112-136">Because an adorner always has a higher z-order than the element it adorns, the adorner receives input events (such as <xref:System.Windows.UIElement.Drop> or <xref:System.Windows.UIElement.MouseMove>) that may be intended for the underlying adorned element.</span></span>  <span data-ttu-id="85112-137">Ein Adorner kann bestimmte Eingabeereignisse überwachen und diese durch erneutes Auslösen des Ereignisses an das zugrunde liegende verzierte Element weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="85112-137">An adorner can listen for certain input events and pass these on to the underlying adorned element by re-raising the event.</span></span>  
  
 <span data-ttu-id="85112-138">Um Pass-Through-Treffertests von Elementen unter einem Adorner zu aktivieren, legen Sie den Treffertest <xref:System.Windows.UIElement.IsHitTestVisible%2A> Eigenschaft **"false"** für den Adorner.</span><span class="sxs-lookup"><span data-stu-id="85112-138">To enable pass-through hit testing of elements under an adorner, set the hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to **false** on the adorner.</span></span>  <span data-ttu-id="85112-139">Weitere Informationen zu Treffertests finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="85112-139">For more information about hit testing, see</span></span>  
  
 <span data-ttu-id="85112-140">[Treffertests in der visuellen Ebene](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span><span class="sxs-lookup"><span data-stu-id="85112-140">[Hit Testing in the Visual Layer](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span></span>  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a><span data-ttu-id="85112-141">Verzieren eines einzelnen UIElement-Elements</span><span class="sxs-lookup"><span data-stu-id="85112-141">Adorning a Single UIElement</span></span>  
 <span data-ttu-id="85112-142">Zum Binden eines Adorners an ein bestimmtes <xref:System.Windows.UIElement>, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="85112-142">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="85112-143">Rufen Sie die statische Methode <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> zum Abrufen einer <xref:System.Windows.Documents.AdornerLayer> -Objekt für die <xref:System.Windows.UIElement> verziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="85112-143">Call the static method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="85112-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> durchläuft die visuelle Struktur, beginnend am angegebenen <xref:System.Windows.UIElement>, und gibt die erste Adornerebene gefundenen zurück.</span><span class="sxs-lookup"><span data-stu-id="85112-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified <xref:System.Windows.UIElement>, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="85112-145">(Falls keine Adorner-Ebenen gefunden werden, gibt die Methode NULL zurück.)</span><span class="sxs-lookup"><span data-stu-id="85112-145">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="85112-146">Rufen Sie die <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode, um den Adorner an das Ziel binden <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="85112-146">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target <xref:System.Windows.UIElement>.</span></span>  
  
 <span data-ttu-id="85112-147">Im folgende Beispiel wird ein SimpleCircleAdorner, die (siehe oben), um eine <xref:System.Windows.Controls.TextBox> mit dem Namen *MyTextBox*.</span><span class="sxs-lookup"><span data-stu-id="85112-147">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="85112-148">Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85112-148">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a><span data-ttu-id="85112-149">Verzieren der untergeordneten Elemente eines Panels</span><span class="sxs-lookup"><span data-stu-id="85112-149">Adorning the Children of a Panel</span></span>  
 <span data-ttu-id="85112-150">Zum Binden eines Adorners an die untergeordneten Elemente ein <xref:System.Windows.Controls.Panel>, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="85112-150">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="85112-151">Rufen Sie die `static` Methode <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> eine Adornerebene für das Element gefunden, dessen untergeordnete Elemente zu verzieren sind.</span><span class="sxs-lookup"><span data-stu-id="85112-151">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="85112-152">Blättern Sie durch die untergeordneten Elemente des übergeordneten Elements, und rufen die <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode, um einen Adorner an jedes untergeordnete Element binden.</span><span class="sxs-lookup"><span data-stu-id="85112-152">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="85112-153">Im folgende Beispiel wird ein SimpleCircleAdorner (siehe oben) an die untergeordneten Elemente gebunden. eine <xref:System.Windows.Controls.StackPanel> mit dem Namen *MyStackPanel*.</span><span class="sxs-lookup"><span data-stu-id="85112-153">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a><span data-ttu-id="85112-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85112-154">See also</span></span>
- <xref:System.Windows.Media.AdornerHitTestResult>
- [<span data-ttu-id="85112-155">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="85112-155">Shapes and Basic Drawing in WPF Overview</span></span>](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="85112-156">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="85112-156">Painting with Images, Drawings, and Visuals</span></span>](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="85112-157">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="85112-157">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="85112-158">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="85112-158">How-to Topics</span></span>](adorners-how-to-topics.md)
