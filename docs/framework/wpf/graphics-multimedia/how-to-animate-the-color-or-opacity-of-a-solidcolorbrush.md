---
title: 'Gewusst wie: Animieren der Farbe oder der Durchlässigkeit von SolidColorBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452882"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="7aef2-102">Gewusst wie: Animieren der Farbe oder der Durchlässigkeit von SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="7aef2-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="7aef2-103">Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> eines <xref:System.Windows.Media.SolidColorBrush>animieren.</span><span class="sxs-lookup"><span data-stu-id="7aef2-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7aef2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7aef2-104">Example</span></span>  
 <span data-ttu-id="7aef2-105">Im folgenden Beispiel werden drei Animationen verwendet, um die <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> eines <xref:System.Windows.Media.SolidColorBrush>zu animieren.</span><span class="sxs-lookup"><span data-stu-id="7aef2-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
- <span data-ttu-id="7aef2-106">Die erste Animation, eine <xref:System.Windows.Media.Animation.ColorAnimation>, ändert die Farbe des Pinsels in <xref:System.Windows.Media.Colors.Gray%2A>, wenn die Maus in das Rechteck gelangt.</span><span class="sxs-lookup"><span data-stu-id="7aef2-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
- <span data-ttu-id="7aef2-107">Die nächste Animation, eine weitere <xref:System.Windows.Media.Animation.ColorAnimation>, ändert die Farbe des Pinsels in <xref:System.Windows.Media.Colors.Orange%2A>, wenn der Mauszeiger das Rechteck verlässt.</span><span class="sxs-lookup"><span data-stu-id="7aef2-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
- <span data-ttu-id="7aef2-108">Die abschließende Animation, eine <xref:System.Windows.Media.Animation.DoubleAnimation>, ändert die Deckkraft des Pinsels in 0,0, wenn die linke Maustaste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="7aef2-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="7aef2-109">Ein ausführeres Beispiel, das zeigt, wie Sie verschiedene Arten von Pinseln animieren, finden Sie im [Beispiel Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="7aef2-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="7aef2-110">Weitere Informationen zur Animation finden Sie unter [Übersicht über Animationen](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7aef2-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="7aef2-111">Aus Gründen der Konsistenz mit anderen Animations Beispielen wird in den Code Versionen dieses Beispiels ein <xref:System.Windows.Media.Animation.Storyboard> Objekt verwendet, um Ihre Animationen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7aef2-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="7aef2-112">Beim Anwenden einer einzelnen Animation im Code ist es jedoch einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>-Methode zu verwenden, anstatt eine <xref:System.Windows.Media.Animation.Storyboard>zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7aef2-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="7aef2-113">Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="7aef2-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aef2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7aef2-114">See also</span></span>

- [<span data-ttu-id="7aef2-115">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="7aef2-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="7aef2-116">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="7aef2-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="7aef2-117">Beispiel für Pinsel</span><span class="sxs-lookup"><span data-stu-id="7aef2-117">Brushes Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
