---
title: 'Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads'
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
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e4963d174f889ac51087356b042bc5b06990593
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="d41aa-102">Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads</span><span class="sxs-lookup"><span data-stu-id="d41aa-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="d41aa-103">In diesem Beispiel wird gezeigt, wie zum Drehen ein Objekt entlang eines geometrischen Pfads, der durch definiert ist ein <xref:System.Windows.Media.PathGeometry> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d41aa-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d41aa-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d41aa-104">Example</span></span>  
 <span data-ttu-id="d41aa-105">Das folgende Beispiel verwendet drei <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Objekte ein Rechteck entlang eines geometrischen Pfads verschoben.</span><span class="sxs-lookup"><span data-stu-id="d41aa-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
-   <span data-ttu-id="d41aa-106">Die erste <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert eine <xref:System.Windows.Media.RotateTransform> , für das Rechteck angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d41aa-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="d41aa-107">Die Animation generiert Winkelwerte.</span><span class="sxs-lookup"><span data-stu-id="d41aa-107">The animation generates angle values.</span></span> <span data-ttu-id="d41aa-108">Das Rechteck dreht (schwenkt) sich entlang der Pfadkonturen.</span><span class="sxs-lookup"><span data-stu-id="d41aa-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
-   <span data-ttu-id="d41aa-109">Die anderen beiden Objekte animieren der <xref:System.Windows.Media.TranslateTransform.X%2A> und <xref:System.Windows.Media.TranslateTransform.Y%2A> Werte eine <xref:System.Windows.Media.TranslateTransform> , für das Rechteck angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d41aa-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="d41aa-110">Sie verschieben das Rechteck horizontal und vertikal entlang des Pfads.</span><span class="sxs-lookup"><span data-stu-id="d41aa-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="d41aa-111">Eine weitere Möglichkeit zum Drehen eines Objekts mithilfe eines geometrischen Pfads ist die Verwendung einer <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Objekt, und seine <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="d41aa-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="d41aa-112">Weitere Informationen und ein Beispiel finden Sie unter [Drehen eines Objekts mithilfe eines geometrischen Pfads (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="d41aa-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="d41aa-113">Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="d41aa-113">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d41aa-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d41aa-114">See Also</span></span>  
 [<span data-ttu-id="d41aa-115">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="d41aa-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="d41aa-116">Beispiel zu Textanimation</span><span class="sxs-lookup"><span data-stu-id="d41aa-116">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="d41aa-117">Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)</span><span class="sxs-lookup"><span data-stu-id="d41aa-117">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
