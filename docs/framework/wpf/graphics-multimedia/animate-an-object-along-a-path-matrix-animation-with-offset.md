---
title: 'Gewusst wie: Animieren eines Objekts auf einem Pfad (Matrixanimation mit Offsetakkumulation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 77daf4efb913f2bc2606247178b6a6c4add29bd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556808"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="a8514-102">Gewusst wie: Animieren eines Objekts auf einem Pfad (Matrixanimation mit Offsetakkumulation)</span><span class="sxs-lookup"><span data-stu-id="a8514-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="a8514-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> -Klasse zum Animieren eines Objekts entlang eines Pfads und der Animation dem Offset-Werte, wie er wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="a8514-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8514-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a8514-104">Example</span></span>  
 <span data-ttu-id="a8514-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu animierende Objekt die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform> auf eine Schaltfläche angewendet.</span><span class="sxs-lookup"><span data-stu-id="a8514-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="a8514-106">Das Ergebnis ist eine Schaltfläche, die entlang eines gekrümmten Pfads verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="a8514-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="a8514-107">Darüber hinaus im Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> Eigenschaft `true`, dadurch wird den Offset der animierten Matrix bei jeder Wiederholung der Animation akkumuliert.</span><span class="sxs-lookup"><span data-stu-id="a8514-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="a8514-108">Durch die Offsetakkumulation bewegt sich die Schaltfläche bei Wiederholung der Animation weiter über den Bildschirm und wird nicht auf die Startposition zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a8514-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="a8514-109">Beachten Sie, dass, obwohl die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> -Eigenschaft bewirkt, dass Offset-Werte, die bei Wiederholungen kumuliert werden, es ist nicht dazu führen, dass Drehung Werte kumuliert.</span><span class="sxs-lookup"><span data-stu-id="a8514-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="a8514-110">Damit der Drehwinkel akkumuliert wird, legen Sie der Animation <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> und <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> Eigenschaften `true`.</span><span class="sxs-lookup"><span data-stu-id="a8514-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="a8514-111">Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="a8514-111">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="a8514-112">Ein Beispiel zum Animieren einer <xref:System.Windows.Media.Matrix> entlang eines Pfads ohne Offset Accumulation /-Wert, finden Sie unter [animieren ein Objekt entlang eines Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="a8514-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8514-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8514-113">See Also</span></span>  
 [<span data-ttu-id="a8514-114">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="a8514-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="a8514-115">Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)</span><span class="sxs-lookup"><span data-stu-id="a8514-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
