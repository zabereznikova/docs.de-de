---
title: "Gewusst wie: Animieren der Farbe oder der Durchlässigkeit von SolidColorBrush"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4bac3ae90fa0fa2229e236f46b8884c942b99bef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="09321-102">Gewusst wie: Animieren der Farbe oder der Durchlässigkeit von SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="09321-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="09321-103">In diesem Beispiel wird gezeigt, wie zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> von einem <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="09321-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09321-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="09321-104">Example</span></span>  
 <span data-ttu-id="09321-105">Das folgende Beispiel verwendet drei Animationen zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> von einem <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="09321-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
-   <span data-ttu-id="09321-106">Die erste Animation eine <xref:System.Windows.Media.Animation.ColorAnimation>, ändert sich die Farbe des Pinsels zum <xref:System.Windows.Media.Colors.Gray%2A> Wenn der Mauszeiger in das Rechteck eintritt.</span><span class="sxs-lookup"><span data-stu-id="09321-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
-   <span data-ttu-id="09321-107">Die nächste Animation, eine andere <xref:System.Windows.Media.Animation.ColorAnimation>, ändert sich die Farbe des Pinsels zum <xref:System.Windows.Media.Colors.Orange%2A> Wenn die Maus das Rechteck verlässt.</span><span class="sxs-lookup"><span data-stu-id="09321-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
-   <span data-ttu-id="09321-108">Die endgültige Animation eine <xref:System.Windows.Media.Animation.DoubleAnimation>, ändert sich die Durchlässigkeit des Pinsels in 0,0, wenn die linke Maustaste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="09321-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="09321-109">Ein ausführlicheres Beispiel, das zeigt, wie verschiedene Typen von Pinsel animiert, finden Sie unter der [Pinsel Beispiel](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="09321-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="09321-110">Weitere Informationen zur Animation finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="09321-110">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="09321-111">Aus Gründen der Konsistenz mit anderen Animation Beispiele für die Codeversionen der in diesem Beispiel verwenden eine <xref:System.Windows.Media.Animation.Storyboard> Objekt, das ihre Animationen angewendet.</span><span class="sxs-lookup"><span data-stu-id="09321-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="09321-112">Beim Anwenden einer Animation im Code ist es jedoch einfacher zu verwenden, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode anstelle einer <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="09321-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="09321-113">Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="09321-113">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09321-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09321-114">See Also</span></span>  
 [<span data-ttu-id="09321-115">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="09321-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="09321-116">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="09321-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="09321-117">Beispiel für Pinsel</span><span class="sxs-lookup"><span data-stu-id="09321-117">Brushes Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159973)
