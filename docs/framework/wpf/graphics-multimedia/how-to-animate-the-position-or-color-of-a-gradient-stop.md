---
title: 'Vorgehensweise: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts'
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
ms.openlocfilehash: eeaea4732855155bf711912644f2f5b3f5a4f8d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134809"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="a1a38-102">Vorgehensweise: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts</span><span class="sxs-lookup"><span data-stu-id="a1a38-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="a1a38-103">Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.GradientStop.Color%2A> und <xref:System.Windows.Media.GradientStop.Offset%2A> von <xref:System.Windows.Media.GradientStop> Objekte.</span><span class="sxs-lookup"><span data-stu-id="a1a38-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1a38-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1a38-104">Example</span></span>  
 <span data-ttu-id="a1a38-105">Das folgende Beispiel erstellt eine Animation drei Farbverlaufstopps in einem <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="a1a38-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="a1a38-106">Im Beispiel werden drei Animationen, von die jede eine unterschiedliche Farbverlaufsunterbrechungspunkte verwendet:</span><span class="sxs-lookup"><span data-stu-id="a1a38-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
-   <span data-ttu-id="a1a38-107">Der ersten Animation, einer <xref:System.Windows.Media.Animation.DoubleAnimation>, erstellt eine Animation die ersten Farbverlaufsstopps <xref:System.Windows.Media.GradientStop.Offset%2A> von 0,0 bis 1,0 und wieder auf 0,0 setzen.</span><span class="sxs-lookup"><span data-stu-id="a1a38-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="a1a38-108">Daher wird die erste Farbe im Farbverlauf verändert sich von der linken Seite auf die rechte Seite des Rechtecks, und klicken Sie dann auf der linken Seite zurück.</span><span class="sxs-lookup"><span data-stu-id="a1a38-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
-   <span data-ttu-id="a1a38-109">Die zweite Animation, einer <xref:System.Windows.Media.Animation.ColorAnimation>, des zweiten Farbverlaufsstopps animiert <xref:System.Windows.Media.GradientStop.Color%2A> aus <xref:System.Windows.Media.Colors.Purple%2A> zu <xref:System.Windows.Media.Colors.Yellow%2A> und dann zurück zur <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="a1a38-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="a1a38-110">Daher ändert sich die mittlere Farbe im Farbverlauf von Violett, Gelb und zurück in Violett.</span><span class="sxs-lookup"><span data-stu-id="a1a38-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
-   <span data-ttu-id="a1a38-111">Der dritte Animation, einer anderen <xref:System.Windows.Media.Animation.ColorAnimation>, wird die Durchlässigkeit des des dritten Farbverlaufsstopps <xref:System.Windows.Media.GradientStop.Color%2A> durch 1 und anschließend wieder.</span><span class="sxs-lookup"><span data-stu-id="a1a38-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="a1a38-112">Daher wird die dritte Farbe im Farbverlauf verblasst, und klicken Sie dann erneut wird nicht transparent.</span><span class="sxs-lookup"><span data-stu-id="a1a38-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="a1a38-113">Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Media.LinearGradientBrush>, der Prozess ist identisch für die Animation <xref:System.Windows.Media.GradientStop> Objekte innerhalb einer <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="a1a38-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="a1a38-114">Weitere Beispiele finden Sie unter den [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="a1a38-114">For additional examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a38-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1a38-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="a1a38-116">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="a1a38-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a1a38-117">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="a1a38-117">Storyboards Overview</span></span>](storyboards-overview.md)
