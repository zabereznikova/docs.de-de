---
title: 'Gewusst wie: Animieren eines Objekts entlang eines Pfads (PointAnimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452895"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="396bc-102">Gewusst wie: Animieren eines Objekts entlang eines Pfads (PointAnimation)</span><span class="sxs-lookup"><span data-stu-id="396bc-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="396bc-103">Dieses Beispiel zeigt, wie ein <xref:System.Windows.Media.Animation.PointAnimationUsingPath>-Objekt verwendet wird, um eine <xref:System.Windows.Point> entlang eines gekrümmten Pfads zu animieren.</span><span class="sxs-lookup"><span data-stu-id="396bc-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="396bc-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="396bc-104">Example</span></span>  
 <span data-ttu-id="396bc-105">Im folgenden Beispiel wird eine <xref:System.Windows.Media.EllipseGeometry> entlang eines durch einen <xref:System.Windows.Media.PathGeometry>definierten Pfads verschoben.</span><span class="sxs-lookup"><span data-stu-id="396bc-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="396bc-106">Die <xref:System.Windows.Media.EllipseGeometry.Center%2A>-Eigenschaft der Ellipse, die einen <xref:System.Windows.Point> Wert annimmt, gibt die Position an. zum Verschieben der Ellipse-Geometrie animieren Sie die <xref:System.Windows.Media.EllipseGeometry.Center%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="396bc-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="396bc-107">Im Beispiel wird eine <xref:System.Windows.Media.Animation.PointAnimationUsingPath> verwendet, um die <xref:System.Windows.Media.EllipseGeometry.Center%2A>-Eigenschaft des <xref:System.Windows.Media.EllipseGeometry>-Objekts zu animieren.</span><span class="sxs-lookup"><span data-stu-id="396bc-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="396bc-108">Das komplette Beispiel finden Sie unter [Beispiel für Pfad Animation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="396bc-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="396bc-109">In der Code Version des vorangehenden Beispiels wurde ein <xref:System.Windows.Media.Animation.Storyboard> zum Animieren des <xref:System.Windows.Media.EllipseGeometry>verwendet, obwohl nur eine Animation angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="396bc-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="396bc-110">Eine <xref:System.Windows.Media.Animation.Storyboard> ist oft die einfachste Möglichkeit, mehrere Animationen anzuwenden, da diese Animationen durch denselben <xref:System.Windows.Media.Animation.Storyboard>gesteuert werden können.</span><span class="sxs-lookup"><span data-stu-id="396bc-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="396bc-111">Eine einfachere Möglichkeit, eine einzelne Animation auf eine Eigenschaft anzuwenden, wenn Sie Code verwenden, ist jedoch die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="396bc-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="396bc-112">Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="396bc-112">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="396bc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="396bc-113">See also</span></span>

- [<span data-ttu-id="396bc-114">Beispiel zu Textanimation</span><span class="sxs-lookup"><span data-stu-id="396bc-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="396bc-115">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="396bc-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="396bc-116">Gewusst-wie-Themen zur Pfadanimation</span><span class="sxs-lookup"><span data-stu-id="396bc-116">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
