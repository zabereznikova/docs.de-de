---
title: 'Vorgehensweise: Drehen eines Objekts mithilfe eines geometrischen Pfads'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: 3e35169da7297ec62e0114ab21f4ba81c0a656ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651245"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="89a46-102">Vorgehensweise: Drehen eines Objekts mithilfe eines geometrischen Pfads</span><span class="sxs-lookup"><span data-stu-id="89a46-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="89a46-103">In diesem Beispiel wird gezeigt, wie zum Drehen ein Objekts entlang eines geometrischen Pfads, der durch definiert ist eine <xref:System.Windows.Media.PathGeometry> Objekt.</span><span class="sxs-lookup"><span data-stu-id="89a46-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89a46-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89a46-104">Example</span></span>  
 <span data-ttu-id="89a46-105">Das folgende Beispiel verwendet drei <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Objekte ein Rechteck entlang eines geometrischen Pfads verschoben.</span><span class="sxs-lookup"><span data-stu-id="89a46-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
- <span data-ttu-id="89a46-106">Die erste <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert ein <xref:System.Windows.Media.RotateTransform> , die auf das Rechteck angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="89a46-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="89a46-107">Die Animation generiert Winkelwerte.</span><span class="sxs-lookup"><span data-stu-id="89a46-107">The animation generates angle values.</span></span> <span data-ttu-id="89a46-108">Das Rechteck dreht (schwenkt) sich entlang der Pfadkonturen.</span><span class="sxs-lookup"><span data-stu-id="89a46-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
- <span data-ttu-id="89a46-109">Die anderen beiden Objekte animieren das <xref:System.Windows.Media.TranslateTransform.X%2A> und <xref:System.Windows.Media.TranslateTransform.Y%2A> Werte eine <xref:System.Windows.Media.TranslateTransform> , die auf das Rechteck angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="89a46-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="89a46-110">Sie verschieben das Rechteck horizontal und vertikal entlang des Pfads.</span><span class="sxs-lookup"><span data-stu-id="89a46-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="89a46-111">Eine weitere Möglichkeit zum Drehen eines Objekts mithilfe eines geometrischen Pfads ist die Verwendung einer <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Objekt, und legen dessen <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="89a46-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="89a46-112">Weitere Informationen und ein Beispiel finden Sie unter [Drehen eines Objekts mithilfe eines geometrischen Pfads (Matrixanimation)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="89a46-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="89a46-113">Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="89a46-113">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a46-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89a46-114">See also</span></span>

- [<span data-ttu-id="89a46-115">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="89a46-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="89a46-116">Beispiel zu Textanimation</span><span class="sxs-lookup"><span data-stu-id="89a46-116">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="89a46-117">Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)</span><span class="sxs-lookup"><span data-stu-id="89a46-117">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
