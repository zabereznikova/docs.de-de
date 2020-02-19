---
title: 'Gewusst wie: Ändern des Endes einer Zeile oder eines Segments'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 5f755d7b4d1682755ea461121f91c0666d450ad1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452778"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="9be93-102">Gewusst wie: Ändern des Endes einer Zeile oder eines Segments</span><span class="sxs-lookup"><span data-stu-id="9be93-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="9be93-103">In diesem Beispiel wird gezeigt, wie die Form am Anfang oder Ende eines geöffneten <xref:System.Windows.Shapes.Shape> Elements geändert wird.</span><span class="sxs-lookup"><span data-stu-id="9be93-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="9be93-104">Um die Obergrenze am Anfang eines geöffneten <xref:System.Windows.Shapes.Shape>zu ändern, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9be93-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="9be93-105">Um die Obergrenze am Ende eines geöffneten <xref:System.Windows.Shapes.Shape>zu ändern, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9be93-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="9be93-106">Informationen zum Anzeigen der verfügbaren Zeilenenden finden Sie in der <xref:System.Windows.Media.PenLineCap>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="9be93-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9be93-107">Diese Eigenschaft wirkt sich nur auf eine geöffnete Form aus, z. b. eine <xref:System.Windows.Shapes.Line>, eine <xref:System.Windows.Shapes.Polyline>oder ein offenes <xref:System.Windows.Shapes.Path> Element.</span><span class="sxs-lookup"><span data-stu-id="9be93-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="9be93-108">Im folgenden Beispiel werden vier <xref:System.Windows.Shapes.Polyline> Elemente gezeichnet, und es wird ein anderer Satz von Formen an den Enden der einzelnen Elemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="9be93-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9be93-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9be93-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="9be93-110">Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="9be93-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be93-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9be93-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
