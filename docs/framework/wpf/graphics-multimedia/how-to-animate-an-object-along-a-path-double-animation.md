---
title: 'Gewusst wie: Verschieben eines Objekts auf einem Pfad (DoubleAnimation)'
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
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a461b741675a18ac1e3544b17a9bbe9a8d18547
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="e92b7-102">Gewusst wie: Verschieben eines Objekts auf einem Pfad (DoubleAnimation)</span><span class="sxs-lookup"><span data-stu-id="e92b7-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="e92b7-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Klasse, um ein Objekt entlang eines Pfads, definiert durch Verschieben einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="e92b7-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e92b7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e92b7-104">Example</span></span>  
 <span data-ttu-id="e92b7-105">Das folgende Beispiel verwendet zwei <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Objekte ein Rechteck entlang eines geometrischen Pfads verschoben:</span><span class="sxs-lookup"><span data-stu-id="e92b7-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
-   <span data-ttu-id="e92b7-106">Die erste <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> eine Animation der <xref:System.Windows.Media.TranslateTransform.X%2A> von der <xref:System.Windows.Media.TranslateTransform> auf das Rechteck angewendet.</span><span class="sxs-lookup"><span data-stu-id="e92b7-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="e92b7-107">Das Rechteck wird hierdurch horizontal am Pfad entlang verschoben.</span><span class="sxs-lookup"><span data-stu-id="e92b7-107">It makes the rectangle move horizontally along the path.</span></span>  
  
-   <span data-ttu-id="e92b7-108">Die zweite <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> eine Animation der <xref:System.Windows.Media.TranslateTransform.Y%2A> von der <xref:System.Windows.Media.TranslateTransform> auf das Rechteck angewendet.</span><span class="sxs-lookup"><span data-stu-id="e92b7-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="e92b7-109">Das Rechteck wird hierdurch vertikal am Pfad entlang verschoben.</span><span class="sxs-lookup"><span data-stu-id="e92b7-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="e92b7-110">Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="e92b7-110">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="e92b7-111">Eine weitere Möglichkeit zum Verschieben eines Objekts mithilfe eines geometrischen Pfads ist die Verwendung einer <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Objekt.</span><span class="sxs-lookup"><span data-stu-id="e92b7-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="e92b7-112">Ein Beispiel finden Sie unter [animieren ein Objekt entlang eines Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="e92b7-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92b7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e92b7-113">See Also</span></span>  
 [<span data-ttu-id="e92b7-114">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="e92b7-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="e92b7-115">Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)</span><span class="sxs-lookup"><span data-stu-id="e92b7-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
