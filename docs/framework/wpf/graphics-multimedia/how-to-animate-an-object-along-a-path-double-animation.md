---
title: 'Vorgehensweise: Verschieben eines Objekts auf einem Pfad (Doppelanimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 54f345bbe6b513e3593cbf45ba190d4a44228424
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101444"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="9b8c1-102">Vorgehensweise: Verschieben eines Objekts auf einem Pfad (Doppelanimation)</span><span class="sxs-lookup"><span data-stu-id="9b8c1-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="9b8c1-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Klasse, um ein Objekt entlang eines Pfads durch Verschieben einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="9b8c1-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b8c1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b8c1-104">Example</span></span>  
 <span data-ttu-id="9b8c1-105">Das folgende Beispiel verwendet zwei <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Objekte ein Rechteck entlang eines geometrischen Pfads verschoben:</span><span class="sxs-lookup"><span data-stu-id="9b8c1-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
-   <span data-ttu-id="9b8c1-106">Die erste <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert die <xref:System.Windows.Media.TranslateTransform.X%2A> von der <xref:System.Windows.Media.TranslateTransform> auf das Rechteck angewendet.</span><span class="sxs-lookup"><span data-stu-id="9b8c1-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="9b8c1-107">Das Rechteck wird hierdurch horizontal am Pfad entlang verschoben.</span><span class="sxs-lookup"><span data-stu-id="9b8c1-107">It makes the rectangle move horizontally along the path.</span></span>  
  
-   <span data-ttu-id="9b8c1-108">Die zweite <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert die <xref:System.Windows.Media.TranslateTransform.Y%2A> von der <xref:System.Windows.Media.TranslateTransform> auf das Rechteck angewendet.</span><span class="sxs-lookup"><span data-stu-id="9b8c1-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="9b8c1-109">Das Rechteck wird hierdurch vertikal am Pfad entlang verschoben.</span><span class="sxs-lookup"><span data-stu-id="9b8c1-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="9b8c1-110">Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="9b8c1-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="9b8c1-111">Eine weitere Möglichkeit zum Verschieben eines Objekts mithilfe eines geometrischen Pfads ist die Verwendung einer <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Objekt.</span><span class="sxs-lookup"><span data-stu-id="9b8c1-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="9b8c1-112">Ein Beispiel finden Sie unter [animieren Sie ein Objekt auf einem Pfad (Matrixanimation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="9b8c1-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8c1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b8c1-113">See also</span></span>

- [<span data-ttu-id="9b8c1-114">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="9b8c1-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="9b8c1-115">Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)</span><span class="sxs-lookup"><span data-stu-id="9b8c1-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
