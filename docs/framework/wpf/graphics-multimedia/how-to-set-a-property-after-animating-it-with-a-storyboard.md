---
title: 'Vorgehensweise: Festlegen einer Eigenschaft nach einer Storyboard-Animation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: e150a576ed6edb365e9e1468becc1a9e55b5aacc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532778"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="605d4-102">Vorgehensweise: Festlegen einer Eigenschaft nach einer Storyboard-Animation</span><span class="sxs-lookup"><span data-stu-id="605d4-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="605d4-103">In einigen Fällen kann es so aussehen, dass Sie den Wert einer Eigenschaft ändern können, nachdem sie animiert wurde.</span><span class="sxs-lookup"><span data-stu-id="605d4-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="605d4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="605d4-104">Example</span></span>  
 <span data-ttu-id="605d4-105">Im folgenden Beispiel eine <xref:System.Windows.Media.Animation.Storyboard> wird verwendet, um die Farbe des Animieren einer <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="605d4-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="605d4-106">Das Storyboard wird ausgelöst, wenn die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="605d4-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="605d4-107">Die <xref:System.Windows.Media.Animation.Timeline.Completed> -Ereignis behandelt, damit die Anwendung benachrichtigt wird, wenn die <xref:System.Windows.Media.Animation.ColorAnimation> abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="605d4-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="605d4-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="605d4-108">Example</span></span>  
 <span data-ttu-id="605d4-109">Nach der <xref:System.Windows.Media.Animation.ColorAnimation> abgeschlossen ist, versucht das Programm, das die Farbe des Pinsels in Blau zu ändern.</span><span class="sxs-lookup"><span data-stu-id="605d4-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="605d4-110">Der vorherige Code nicht angezeigt werden, nichts weiter tun: Pinsel bleibt die Gelb, das den Wert angegeben wird, indem die <xref:System.Windows.Media.Animation.ColorAnimation> , die den Pinsel animiert.</span><span class="sxs-lookup"><span data-stu-id="605d4-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="605d4-111">Der zugrunde liegende Eigenschaftswert (der Basiswert) ist tatsächlich Blau geändert.</span><span class="sxs-lookup"><span data-stu-id="605d4-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="605d4-112">Der effektive bzw. der aktuelle Wert bleibt jedoch gelben da die <xref:System.Windows.Media.Animation.ColorAnimation> noch den Basiswert überschreibt.</span><span class="sxs-lookup"><span data-stu-id="605d4-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="605d4-113">Wenn Sie den Basiswert der effektive Wert erneut werden möchten, müssen Sie die Animation einen Einfluss auf die Eigenschaft beenden.</span><span class="sxs-lookup"><span data-stu-id="605d4-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="605d4-114">Es gibt drei Möglichkeiten, dies mit der Storyboard-Animationen umzusetzen:</span><span class="sxs-lookup"><span data-stu-id="605d4-114">There are three ways to do this with storyboard animations:</span></span>  
  
-   <span data-ttu-id="605d4-115">Festlegen der Animation <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="605d4-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
-   <span data-ttu-id="605d4-116">Entfernen Sie das gesamte Storyboard an.</span><span class="sxs-lookup"><span data-stu-id="605d4-116">Remove the entire Storyboard.</span></span>  
  
-   <span data-ttu-id="605d4-117">Entfernen Sie die Animation, aus der jeweiligen Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="605d4-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="605d4-118">Festlegen von FillBehavior-Eigenschaft der Animation beendet</span><span class="sxs-lookup"><span data-stu-id="605d4-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="605d4-119">Durch Festlegen von <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> zu <xref:System.Windows.Media.Animation.FillBehavior.Stop>, Sie erkennen, dass die Animation beendet wird, auf die Zieleigenschaft, nachdem das Ende des aktiven Zeitraums erreicht.</span><span class="sxs-lookup"><span data-stu-id="605d4-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="605d4-120">Entfernen Sie das gesamte storyboard</span><span class="sxs-lookup"><span data-stu-id="605d4-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="605d4-121">Mithilfe einer <xref:System.Windows.Media.Animation.RemoveStoryboard> Trigger oder die <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> -Methode, teilen Sie die Storyboard-Animationen, um Auswirkungen auf deren Zieleigenschaften zu beenden.</span><span class="sxs-lookup"><span data-stu-id="605d4-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="605d4-122">Der Unterschied zwischen diesem Ansatz und die Einstellung der <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft ist, dass Sie das Storyboard entfernen können jederzeit und an zwar die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft hat nur Auswirkungen, wenn die Animation das Ende des aktiven Zeitraums erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="605d4-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="605d4-123">Entfernen einer Animation aus einer einzelnen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="605d4-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="605d4-124">Ein anderes Verfahren zum Beenden einer Animation Auswirkungen auf eine Eigenschaft ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> -Methode des animierten Objekts.</span><span class="sxs-lookup"><span data-stu-id="605d4-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="605d4-125">Geben Sie die zu animierende Eigenschaft als ersten Parameter und `null` als das zweite.</span><span class="sxs-lookup"><span data-stu-id="605d4-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="605d4-126">Dieses Verfahren funktioniert auch für nicht-Storyboard-Animationen.</span><span class="sxs-lookup"><span data-stu-id="605d4-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="605d4-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="605d4-127">See also</span></span>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [<span data-ttu-id="605d4-128">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="605d4-128">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="605d4-129">Übersicht über die Verfahren zur Animation von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="605d4-129">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
