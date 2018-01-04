---
title: 'Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts'
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
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c5a72d5df9d7ff9cdd90d6e09a7dab574e2caaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="71000-102">Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts</span><span class="sxs-lookup"><span data-stu-id="71000-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="71000-103">In diesem Beispiel wird gezeigt, wie zum Animieren der <xref:System.Windows.Media.GradientStop.Color%2A> und <xref:System.Windows.Media.GradientStop.Offset%2A> von <xref:System.Windows.Media.GradientStop> Objekte.</span><span class="sxs-lookup"><span data-stu-id="71000-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71000-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="71000-104">Example</span></span>  
 <span data-ttu-id="71000-105">Das folgende Beispiel erstellt eine Animation drei Farbverlaufsstopps innerhalb einer <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="71000-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="71000-106">Das Beispiel verwendet drei Animationen, von die jedes einen anderen Farbverlaufsstopps animiert.</span><span class="sxs-lookup"><span data-stu-id="71000-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
-   <span data-ttu-id="71000-107">Die erste Animation eine <xref:System.Windows.Media.Animation.DoubleAnimation>, erstellt eine Animation des ersten Farbverlaufsstopps <xref:System.Windows.Media.GradientStop.Offset%2A> von 0,0 bis 1,0, und klicken Sie dann auf 0,0 sichern.</span><span class="sxs-lookup"><span data-stu-id="71000-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="71000-108">Daher die erste im Farbverlauf verändert sich von der linken Seite auf die rechte Seite des Rechtecks-Farbe aus, und klicken Sie dann auf die linke Seite zurück.</span><span class="sxs-lookup"><span data-stu-id="71000-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
-   <span data-ttu-id="71000-109">Die zweite Animation eine <xref:System.Windows.Media.Animation.ColorAnimation>, erstellt eine Animation des zweiten Farbverlaufsstopps <xref:System.Windows.Media.GradientStop.Color%2A> aus <xref:System.Windows.Media.Colors.Purple%2A> auf <xref:System.Windows.Media.Colors.Yellow%2A> und dann zurück in <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="71000-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="71000-110">Daher ändert sich die mittlere Farbe im Verlauf von Violett, Gelb und zurück in Violett.</span><span class="sxs-lookup"><span data-stu-id="71000-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
-   <span data-ttu-id="71000-111">Die dritte Animation, eine andere <xref:System.Windows.Media.Animation.ColorAnimation>, wird die Durchlässigkeit des dritten Farbverlaufsstopps des <xref:System.Windows.Media.GradientStop.Color%2A> mit-1 und dann wieder.</span><span class="sxs-lookup"><span data-stu-id="71000-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="71000-112">Daher wird die dritte Farbe im Farbverlauf ausgeblendet, und klicken Sie dann erneut wird nicht transparent.</span><span class="sxs-lookup"><span data-stu-id="71000-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="71000-113">Obwohl in diesem Beispiel verwendet eine <xref:System.Windows.Media.LinearGradientBrush>, der Prozess entspricht dem für die Animation <xref:System.Windows.Media.GradientStop> Objekte innerhalb einer <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="71000-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="71000-114">Weitere Beispiele finden Sie unter der [Pinsel Beispiel](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="71000-114">For additional examples, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71000-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71000-115">See Also</span></span>  
 <xref:System.Windows.Media.GradientStop>  
 [<span data-ttu-id="71000-116">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="71000-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="71000-117">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="71000-117">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
