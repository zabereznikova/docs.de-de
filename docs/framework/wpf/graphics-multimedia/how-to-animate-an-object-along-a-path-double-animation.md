---
title: 'Gewusst wie: Verschieben eines Objekts auf einem Pfad (DoubleAnimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452856"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="7030a-102">Gewusst wie: Verschieben eines Objekts auf einem Pfad (DoubleAnimation)</span><span class="sxs-lookup"><span data-stu-id="7030a-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="7030a-103">In diesem Beispiel wird gezeigt, wie die <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>-Klasse verwendet wird, um ein Objekt entlang eines durch ein <xref:System.Windows.Media.PathGeometry>definierten Pfads zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="7030a-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7030a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7030a-104">Example</span></span>  
 <span data-ttu-id="7030a-105">Im folgenden Beispiel werden zwei <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>-Objekte verwendet, um ein Rechteck entlang eines geometrischen Pfads zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="7030a-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
- <span data-ttu-id="7030a-106">Der erste <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert die <xref:System.Windows.Media.TranslateTransform.X%2A> des <xref:System.Windows.Media.TranslateTransform>, das auf das Rechteck angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="7030a-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="7030a-107">Das Rechteck wird hierdurch horizontal am Pfad entlang verschoben.</span><span class="sxs-lookup"><span data-stu-id="7030a-107">It makes the rectangle move horizontally along the path.</span></span>  
  
- <span data-ttu-id="7030a-108">Der zweite <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert die <xref:System.Windows.Media.TranslateTransform.Y%2A> des <xref:System.Windows.Media.TranslateTransform>, das auf das Rechteck angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="7030a-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="7030a-109">Das Rechteck wird hierdurch vertikal am Pfad entlang verschoben.</span><span class="sxs-lookup"><span data-stu-id="7030a-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="7030a-110">Das komplette Beispiel finden Sie unter [Beispiel für Pfad Animation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="7030a-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="7030a-111">Eine andere Möglichkeit, ein Objekt mithilfe eines geometrischen Pfads zu verschieben, ist die Verwendung eines <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Objekts.</span><span class="sxs-lookup"><span data-stu-id="7030a-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="7030a-112">Ein Beispiel finden Sie unter [Animieren eines Objekts entlang eines Pfads (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="7030a-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7030a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7030a-113">See also</span></span>

- [<span data-ttu-id="7030a-114">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="7030a-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="7030a-115">Gewusst-wie-Themen zur Pfadanimation</span><span class="sxs-lookup"><span data-stu-id="7030a-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
