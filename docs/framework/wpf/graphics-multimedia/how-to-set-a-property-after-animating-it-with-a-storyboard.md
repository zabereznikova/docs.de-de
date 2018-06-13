---
title: 'Gewusst wie: Festlegen einer Eigenschaft nach einer Storyboard-Animation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: b8e9c08075b13f8d6f701d5ac6ae4f8ea8949184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562262"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="3fa64-102">Gewusst wie: Festlegen einer Eigenschaft nach einer Storyboard-Animation</span><span class="sxs-lookup"><span data-stu-id="3fa64-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="3fa64-103">In einigen Fällen könnte es scheinen, dass Sie den Wert einer Eigenschaft ändern können, nachdem sie animiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3fa64-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fa64-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fa64-104">Example</span></span>  
 <span data-ttu-id="3fa64-105">Im folgenden Beispiel ein <xref:System.Windows.Media.Animation.Storyboard> wird verwendet, um die Farbe des Animieren einer <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="3fa64-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="3fa64-106">Das Storyboard wird ausgelöst, wenn die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="3fa64-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="3fa64-107">Die <xref:System.Windows.Media.Animation.Timeline.Completed> -Ereignis behandelt wird, damit das Programm benachrichtigt wird, wenn die <xref:System.Windows.Media.Animation.ColorAnimation> abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3fa64-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="3fa64-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fa64-108">Example</span></span>  
 <span data-ttu-id="3fa64-109">Nach der <xref:System.Windows.Media.Animation.ColorAnimation> abgeschlossen ist, versucht das Programm, das die Farbe des Pinsels in Blau zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3fa64-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="3fa64-110">Der vorherige Code ist scheinbar nicht nichts zu tun: die Pinsel bleibt gelb, das den Wert von bereitgestellten der <xref:System.Windows.Media.Animation.ColorAnimation> , der den Pinsel animiert.</span><span class="sxs-lookup"><span data-stu-id="3fa64-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="3fa64-111">Die zugrunde liegende Eigenschaftswert (Preis) ist tatsächlich Blau geändert.</span><span class="sxs-lookup"><span data-stu-id="3fa64-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="3fa64-112">Der effektive bzw. der aktuelle Wert bleibt jedoch Gelb da die <xref:System.Windows.Media.Animation.ColorAnimation> ist den Basiswert noch überschreiben.</span><span class="sxs-lookup"><span data-stu-id="3fa64-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="3fa64-113">Gegebenenfalls den Basiswert der effektive Wert erneut zu, müssen Sie die Animation aus Schätzung vor bzw. beeinflusst die Eigenschaft beenden.</span><span class="sxs-lookup"><span data-stu-id="3fa64-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="3fa64-114">Es gibt drei Möglichkeiten, dies mit Storyboard-Animationen umzusetzen:</span><span class="sxs-lookup"><span data-stu-id="3fa64-114">There are three ways to do this with storyboard animations:</span></span>  
  
-   <span data-ttu-id="3fa64-115">Legen Sie der Animation <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="3fa64-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
-   <span data-ttu-id="3fa64-116">Entfernen Sie das gesamte Storyboard.</span><span class="sxs-lookup"><span data-stu-id="3fa64-116">Remove the entire Storyboard.</span></span>  
  
-   <span data-ttu-id="3fa64-117">Entfernen Sie die Animation aus der jeweiligen Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="3fa64-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="3fa64-118">Legen Sie die Animation FillBehavior-Eigenschaft auf Beenden</span><span class="sxs-lookup"><span data-stu-id="3fa64-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="3fa64-119">Durch Festlegen von <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> zu <xref:System.Windows.Media.Animation.FillBehavior.Stop>, teilen Sie die Animation zum Beenden von ihrer Zieleigenschaft beeinflussen, nachdem das Ende des aktiven Zeitraums erreicht.</span><span class="sxs-lookup"><span data-stu-id="3fa64-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="3fa64-120">Entfernen Sie das gesamte storyboard</span><span class="sxs-lookup"><span data-stu-id="3fa64-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="3fa64-121">Mithilfe einer <xref:System.Windows.Media.Animation.RemoveStoryboard> Trigger oder die <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> -Methode, teilen Sie die Storyboard-Animationen, beenden Sie die Auswirkungen auf die Zieleigenschaften.</span><span class="sxs-lookup"><span data-stu-id="3fa64-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="3fa64-122">Der Unterschied zwischen diesem Ansatz und dem Festlegen der <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft ist, Sie das Storyboard entfernen while-jederzeit und auf die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft ist nur wirksam, wenn die Animation das Ende ihres aktiven Zeitraums erreicht.</span><span class="sxs-lookup"><span data-stu-id="3fa64-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="3fa64-123">Entfernen einer Animation aus einer einzelnen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3fa64-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="3fa64-124">Ein anderes Verfahren zum Beenden einer Animation Auswirkungen auf eine Eigenschaft ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> -Methode des zu animierenden Objekts.</span><span class="sxs-lookup"><span data-stu-id="3fa64-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="3fa64-125">Geben Sie die Eigenschaft als erster Parameter animierten und `null` als das zweite.</span><span class="sxs-lookup"><span data-stu-id="3fa64-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="3fa64-126">Dieses Verfahren kann auch für nicht-Storyboard-Animationen.</span><span class="sxs-lookup"><span data-stu-id="3fa64-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa64-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fa64-127">See Also</span></span>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.Animation.RemoveStoryboard>  
 [<span data-ttu-id="3fa64-128">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="3fa64-128">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="3fa64-129">Übersicht über die Verfahren zur Animation von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3fa64-129">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
