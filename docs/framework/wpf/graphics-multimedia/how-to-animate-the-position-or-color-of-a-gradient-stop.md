---
title: 'Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452843"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="6922e-102">Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts</span><span class="sxs-lookup"><span data-stu-id="6922e-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="6922e-103">Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Media.GradientStop.Color%2A> und <xref:System.Windows.Media.GradientStop.Offset%2A> von <xref:System.Windows.Media.GradientStop> Objekten animieren.</span><span class="sxs-lookup"><span data-stu-id="6922e-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6922e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6922e-104">Example</span></span>  
 <span data-ttu-id="6922e-105">Im folgenden Beispiel werden drei Farbverlaufs Stopps in einer <xref:System.Windows.Media.LinearGradientBrush>animiert.</span><span class="sxs-lookup"><span data-stu-id="6922e-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="6922e-106">In diesem Beispiel werden drei Animationen verwendet, von denen jede einen anderen Farbverlaufs-halte Vorgang animiert:</span><span class="sxs-lookup"><span data-stu-id="6922e-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
- <span data-ttu-id="6922e-107">Die erste Animation, eine <xref:System.Windows.Media.Animation.DoubleAnimation>, animiert die <xref:System.Windows.Media.GradientStop.Offset%2A> des ersten Farbverlaufs Stopps von 0,0 auf 1,0 und dann zurück zu 0,0.</span><span class="sxs-lookup"><span data-stu-id="6922e-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="6922e-108">Folglich verschiebt sich die erste Farbe im Farbverlauf von der linken zum rechten Rand des Rechtecks und dann zurück zur linken Seite.</span><span class="sxs-lookup"><span data-stu-id="6922e-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
- <span data-ttu-id="6922e-109">Die zweite Animation, eine <xref:System.Windows.Media.Animation.ColorAnimation>, animiert die <xref:System.Windows.Media.GradientStop.Color%2A> des zweiten Farbverlaufs Stopps von <xref:System.Windows.Media.Colors.Purple%2A> bis <xref:System.Windows.Media.Colors.Yellow%2A> und dann zurück zu <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="6922e-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="6922e-110">Folglich wechselt die Mittel Farbe im Farbverlauf von lila in gelb und zurück zu Lila.</span><span class="sxs-lookup"><span data-stu-id="6922e-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
- <span data-ttu-id="6922e-111">Die dritte Animation, eine weitere <xref:System.Windows.Media.Animation.ColorAnimation>, animiert die Deckkraft des <xref:System.Windows.Media.GradientStop.Color%2A> des dritten Farbverlaufs Stopps durch-1 und dann zurück.</span><span class="sxs-lookup"><span data-stu-id="6922e-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="6922e-112">Folglich wird die dritte Farbe im Farbverlauf ausgeblendet und dann wieder transparent.</span><span class="sxs-lookup"><span data-stu-id="6922e-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="6922e-113">Obwohl in diesem Beispiel eine <xref:System.Windows.Media.LinearGradientBrush>verwendet wird, ist der Prozess für das Animieren <xref:System.Windows.Media.GradientStop> Objekten innerhalb einer <xref:System.Windows.Media.RadialGradientBrush>identisch.</span><span class="sxs-lookup"><span data-stu-id="6922e-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="6922e-114">Weitere Beispiele finden Sie im [Beispiel Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="6922e-114">For additional examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6922e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6922e-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="6922e-116">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="6922e-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6922e-117">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="6922e-117">Storyboards Overview</span></span>](storyboards-overview.md)
