---
title: 'Vorgehensweise: Animieren eines Objekts auf einem Pfad (MatrixAnimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 836f61e062b921c7e51166a35d8169f903fcbab9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738299"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="8b1e1-102">Vorgehensweise: Animieren eines Objekts auf einem Pfad (MatrixAnimation)</span><span class="sxs-lookup"><span data-stu-id="8b1e1-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="8b1e1-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Klasse, um ein Objekt entlang eines Pfads zu animieren, die von definiert ist eine <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="8b1e1-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b1e1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b1e1-104">Example</span></span>  
 <span data-ttu-id="8b1e1-105">In diesem Beispiel wird Folgendes ausgeführt, um ein Objekt entlang eines Pfads zu animieren:</span><span class="sxs-lookup"><span data-stu-id="8b1e1-105">The following example animates an object along a path by doing the following:</span></span>  
  
-   <span data-ttu-id="8b1e1-106">Wendet eine <xref:System.Windows.Media.MatrixTransform> auf das Objekt, um es zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="8b1e1-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
-   <span data-ttu-id="8b1e1-107">Definiert den Pfad mit einem <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="8b1e1-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
-   <span data-ttu-id="8b1e1-108">Erstellt eine <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> und wird verwendet, um das Animieren der <xref:System.Windows.Media.Matrix> Eigenschaft der <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="8b1e1-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="8b1e1-109">Die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> nimmt die <xref:System.Windows.Media.PathGeometry> und verwendet sie zum Generieren von <xref:System.Windows.Media.Matrix> Werte.</span><span class="sxs-lookup"><span data-stu-id="8b1e1-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="8b1e1-110">Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="8b1e1-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="8b1e1-111">Weitere Informationen zu geometrischen Pfaden finden Sie unter den [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8b1e1-111">For more information about geometric paths, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b1e1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b1e1-112">See also</span></span>
- [<span data-ttu-id="8b1e1-113">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="8b1e1-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="8b1e1-114">Beispiel zu Textanimation</span><span class="sxs-lookup"><span data-stu-id="8b1e1-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="8b1e1-115">Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)</span><span class="sxs-lookup"><span data-stu-id="8b1e1-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
