---
title: 'Vorgehensweise: Erstellen einer zusammengesetzten Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: de9f7972c7a51ea623c3630fe62bb48f6109317e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353490"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="39fa0-102">Vorgehensweise: Erstellen einer zusammengesetzten Form</span><span class="sxs-lookup"><span data-stu-id="39fa0-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="39fa0-103">Dieses Beispiel zeigt, wie Sie zusammengesetzte Formen erstellen <xref:System.Windows.Media.Geometry> Objekte und zeigen Sie sie mithilfe einer <xref:System.Windows.Shapes.Path> Element.</span><span class="sxs-lookup"><span data-stu-id="39fa0-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="39fa0-104">Im folgenden Beispiel eine <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, und ein <xref:System.Windows.Media.RectangleGeometry> werden verwendet, mit einem <xref:System.Windows.Media.GeometryGroup> zum Erstellen einer zusammengesetzten Form.</span><span class="sxs-lookup"><span data-stu-id="39fa0-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="39fa0-105">Die Geometrie gezeichnet Klicken Sie dann mit einem <xref:System.Windows.Shapes.Path> Element.</span><span class="sxs-lookup"><span data-stu-id="39fa0-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39fa0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39fa0-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="39fa0-107">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.</span><span class="sxs-lookup"><span data-stu-id="39fa0-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="39fa0-108">![Eine zusammengesetzte Geometrie, die mit einer GeometryGroup erstellt](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="39fa0-108">![A composite geometry created using a GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="39fa0-109">Zusammengesetzte Geometrie</span><span class="sxs-lookup"><span data-stu-id="39fa0-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="39fa0-110">Komplexere Formen, wie z. B. Polygone und Formen mit Kurvensegmente, können erstellt werden, mithilfe einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="39fa0-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="39fa0-111">Ein Beispiel zur Vorgehensweise: Erstellen einer Form mithilfe einer <xref:System.Windows.Media.PathGeometry>, finden Sie unter [Erstellen einer Form mithilfe von PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="39fa0-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="39fa0-112">Obwohl dieses Beispiel eine Form mit dem Bildschirm gerendert wird. eine <xref:System.Windows.Shapes.Path> Element <xref:System.Windows.Media.Geometry> Objekte können auch verwendet werden, um den Inhalt zu beschreiben eine <xref:System.Windows.Media.GeometryDrawing> oder <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="39fa0-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="39fa0-113">Sie können auch zum Ausschneiden und Treffertests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39fa0-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="39fa0-114">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="39fa0-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>
