---
title: 'Gewusst wie: Ändern des Endes einer Zeile oder eines Segments'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: e69f461d426fc6a587263cea7a18478da53b5b09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559836"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="1a78b-102">Gewusst wie: Ändern des Endes einer Zeile oder eines Segments</span><span class="sxs-lookup"><span data-stu-id="1a78b-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="1a78b-103">In diesem Beispiel wird gezeigt, wie so ändern Sie die Form am Anfang oder Ende eines offenen <xref:System.Windows.Shapes.Shape> Element.</span><span class="sxs-lookup"><span data-stu-id="1a78b-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="1a78b-104">So ändern Sie die Abdeckung am Anfang eines geöffneten <xref:System.Windows.Shapes.Shape>, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1a78b-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="1a78b-105">So ändern Sie die Abdeckung am Ende eines geöffneten <xref:System.Windows.Shapes.Shape>, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1a78b-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="1a78b-106">Um die verfügbaren Zeilenenden finden Sie unter der <xref:System.Windows.Media.PenLineCap> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="1a78b-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a78b-107">Diese Eigenschaft wirkt sich nur auf eine offene Form, wie z. B. eine <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, oder ein offenes <xref:System.Windows.Shapes.Path> Element.</span><span class="sxs-lookup"><span data-stu-id="1a78b-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="1a78b-108">Im folgende Beispiel zeichnet vier <xref:System.Windows.Shapes.Polyline> Elemente und einen anderen Satz von Shapes an den Enden der einzelnen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a78b-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a78b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a78b-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="1a78b-110">Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="1a78b-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a78b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a78b-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
