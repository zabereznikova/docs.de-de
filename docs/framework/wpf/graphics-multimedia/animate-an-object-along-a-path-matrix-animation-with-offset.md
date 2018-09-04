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
ms.openlocfilehash: 1d3b74ede9cde1928138d4d8625e8625354f5748
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522755"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="a2e10-102">Gewusst wie: Animieren eines Objekts auf einem Pfad (Matrixanimation mit Offsetakkumulation)</span><span class="sxs-lookup"><span data-stu-id="a2e10-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="a2e10-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> -Klasse zum Animieren eines Objekts entlang eines Pfads und der Animation den Offset-Werte sowie die Akkumulation.</span><span class="sxs-lookup"><span data-stu-id="a2e10-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2e10-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2e10-104">Example</span></span>  
 <span data-ttu-id="a2e10-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu animierende Objekt die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform> auf eine Schaltfläche angewendet.</span><span class="sxs-lookup"><span data-stu-id="a2e10-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="a2e10-106">Das Ergebnis ist eine Schaltfläche, die entlang eines gekrümmten Pfads verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="a2e10-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="a2e10-107">Darüber hinaus im Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> Eigenschaft `true`, sodass der Offset der animierten Matrix bei jeder Wiederholung der Animation akkumuliert.</span><span class="sxs-lookup"><span data-stu-id="a2e10-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="a2e10-108">Durch die Offsetakkumulation bewegt sich die Schaltfläche bei Wiederholung der Animation weiter über den Bildschirm und wird nicht auf die Startposition zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a2e10-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="a2e10-109">Beachten Sie, dass, obwohl die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> -Eigenschaft bewirkt, dass Offsetwerten bei Wiederholungen kumuliert werden, es nicht dazu, dass die Rotation von Werten für "accumulate".</span><span class="sxs-lookup"><span data-stu-id="a2e10-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="a2e10-110">Drehwinkel akkumuliert legen fest, um der Animation <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> und <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> Eigenschaften `true`.</span><span class="sxs-lookup"><span data-stu-id="a2e10-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="a2e10-111">Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="a2e10-111">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="a2e10-112">Ein Beispiel für das Animieren einer <xref:System.Windows.Media.Matrix> entlang eines Pfads ohne Offsetakkumulation-Wert, finden Sie unter [animieren Sie ein Objekt auf einem Pfad (Matrixanimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="a2e10-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e10-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2e10-113">See Also</span></span>  
 [<span data-ttu-id="a2e10-114">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="a2e10-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="a2e10-115">Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)</span><span class="sxs-lookup"><span data-stu-id="a2e10-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
