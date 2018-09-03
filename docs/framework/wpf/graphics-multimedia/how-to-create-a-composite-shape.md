---
title: 'Gewusst wie: Erstellen einer zusammengesetzten Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: 9892120d13a067586dbf6472a6873b6a52c2d8b4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43457082"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="c87ce-102">Gewusst wie: Erstellen einer zusammengesetzten Form</span><span class="sxs-lookup"><span data-stu-id="c87ce-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="c87ce-103">Dieses Beispiel zeigt, wie Sie zusammengesetzte Formen erstellen <xref:System.Windows.Media.Geometry> Objekte und zeigen Sie sie mithilfe einer <xref:System.Windows.Shapes.Path> Element.</span><span class="sxs-lookup"><span data-stu-id="c87ce-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="c87ce-104">Im folgenden Beispiel eine <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, und ein <xref:System.Windows.Media.RectangleGeometry> werden verwendet, mit einem <xref:System.Windows.Media.GeometryGroup> zum Erstellen einer zusammengesetzten Form.</span><span class="sxs-lookup"><span data-stu-id="c87ce-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="c87ce-105">Die Geometrie gezeichnet Klicken Sie dann mit einem <xref:System.Windows.Shapes.Path> Element.</span><span class="sxs-lookup"><span data-stu-id="c87ce-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c87ce-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c87ce-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="c87ce-107">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.</span><span class="sxs-lookup"><span data-stu-id="c87ce-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="c87ce-108">![Eine zusammengesetzte Geometrie, die mit einer GeometryGroup erstellt](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="c87ce-108">![A composite geometry created using a GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="c87ce-109">Zusammengesetzte Geometrie</span><span class="sxs-lookup"><span data-stu-id="c87ce-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="c87ce-110">Komplexere Formen, wie z. B. Polygone und Formen mit Kurvensegmente, können erstellt werden, mithilfe einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="c87ce-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="c87ce-111">Ein Beispiel zur Vorgehensweise: Erstellen einer Form mithilfe einer <xref:System.Windows.Media.PathGeometry>, finden Sie unter [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="c87ce-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="c87ce-112">Obwohl dieses Beispiel eine Form mit dem Bildschirm gerendert wird. eine <xref:System.Windows.Shapes.Path> Element <xref:System.Windows.Media.Geometry> Objekte können auch verwendet werden, um den Inhalt zu beschreiben eine <xref:System.Windows.Media.GeometryDrawing> oder <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="c87ce-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="c87ce-113">Sie können auch zum Ausschneiden und Treffertests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c87ce-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="c87ce-114">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="c87ce-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>
