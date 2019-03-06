---
title: 'Vorgehensweise: Zeichnen eines Bereichs mit einer Zeichnung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371558"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a><span data-ttu-id="76235-102">Vorgehensweise: Zeichnen eines Bereichs mit einer Zeichnung</span><span class="sxs-lookup"><span data-stu-id="76235-102">How to: Paint an Area with a Drawing</span></span>
<span data-ttu-id="76235-103">Dieses Beispiel zeigt, wie Sie einen Bereich mit einer Zeichnung zeichnen.</span><span class="sxs-lookup"><span data-stu-id="76235-103">This example shows how to paint an area with a drawing.</span></span> <span data-ttu-id="76235-104">Um einen Bereich mit einer Zeichnung zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.DrawingBrush> und einem oder mehreren <xref:System.Windows.Media.Drawing> Objekte.</span><span class="sxs-lookup"><span data-stu-id="76235-104">To paint an area with a drawing, you use a <xref:System.Windows.Media.DrawingBrush> and one or more <xref:System.Windows.Media.Drawing> objects.</span></span>   <span data-ttu-id="76235-105">Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingBrush> um ein Objekt mit einer Zeichnung zweier Ellipsen zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="76235-105">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint an object with a drawing of two ellipses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76235-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76235-106">Example</span></span>  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 <span data-ttu-id="76235-107">Die folgende Abbildung zeigt die Ausgabe des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="76235-107">The following illustration shows the example's output.</span></span>  
  
 <span data-ttu-id="76235-108">![Ausgabe eines DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "Graphicsmm_drawingbrush_simple")</span><span class="sxs-lookup"><span data-stu-id="76235-108">![Output from a DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span></span>  
  
 <span data-ttu-id="76235-109">(Die Mitte der Form ist weiß [Steuern des Ausfüllens einer zusammengesetzten Form](how-to-control-the-fill-of-a-composite-shape.md).)</span><span class="sxs-lookup"><span data-stu-id="76235-109">(The center of the shape is white for reasons described in     [Control the Fill of a Composite Shape](how-to-control-the-fill-of-a-composite-shape.md).)</span></span>  
  
 <span data-ttu-id="76235-110">Durch Festlegen einer <xref:System.Windows.Media.DrawingBrush> des Objekts <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaften, Sie können ein sich wiederholendes Muster erstellen.</span><span class="sxs-lookup"><span data-stu-id="76235-110">By setting a <xref:System.Windows.Media.DrawingBrush> object's <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties, you can create a repeating pattern.</span></span> <span data-ttu-id="76235-111">Im folgenden Beispiel wird ein Objekt mit einem aus einer Zeichnung von zwei Ellipsen erstellten Muster gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="76235-111">The following example paints an object with a pattern created from a drawing of two ellipses.</span></span>  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 <span data-ttu-id="76235-112">Die folgende Abbildung zeigt die nebeneinander <xref:System.Windows.Media.DrawingBrush> Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="76235-112">The following illustration shows the tiled <xref:System.Windows.Media.DrawingBrush> output.</span></span>  
  
 <span data-ttu-id="76235-113">![Ausgabe eines DrawingBrush in Kachelform](./media/graphicsmm-drawingbrush-tiled.png "Graphicsmm_drawingbrush_tiled")</span><span class="sxs-lookup"><span data-stu-id="76235-113">![Tiled output from a DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span></span>  
  
 <span data-ttu-id="76235-114">Weitere Informationen zu Zeichenpinseln finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="76235-114">For more information about drawing brushes, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span> <span data-ttu-id="76235-115">Weitere Informationen zu <xref:System.Windows.Media.Drawing> Objekten finden Sie die [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="76235-115">For more information about <xref:System.Windows.Media.Drawing> objects, see the [Drawing Objects Overview](drawing-objects-overview.md).</span></span>
