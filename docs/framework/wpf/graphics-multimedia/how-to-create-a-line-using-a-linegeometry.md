---
title: 'Gewusst wie: Erstellen einer Linie mit einer LineGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: 8db33fc5c611dcbcae50c71ada1c6b6f9fd9bd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560468"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="d8a88-102">Gewusst wie: Erstellen einer Linie mit einer LineGeometry</span><span class="sxs-lookup"><span data-stu-id="d8a88-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="d8a88-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.LineGeometry> Klasse, um eine Zeile zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d8a88-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="d8a88-104">Ein <xref:System.Windows.Media.LineGeometry> wird durch die Anfangs- und Endpunkte definiert.</span><span class="sxs-lookup"><span data-stu-id="d8a88-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8a88-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d8a88-105">Example</span></span>  
 <span data-ttu-id="d8a88-106">Das folgende Beispiel zeigt das Erstellen und Rendern einer <xref:System.Windows.Media.LineGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d8a88-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="d8a88-107">Ein <xref:System.Windows.Shapes.Path> Element wird verwendet, um die Zeile zu rendern.</span><span class="sxs-lookup"><span data-stu-id="d8a88-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="d8a88-108">Da eine Linie keinen Bereich aufweist der <xref:System.Windows.Shapes.Path> des Objekts <xref:System.Windows.Shapes.Shape.Fill%2A> nicht angegeben ist; stattdessen die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8a88-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="d8a88-109">![Eine LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "Graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="d8a88-109">![A LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="d8a88-110">Eine LineGeometry, gezeichnet von (10,20) bis (100,130)</span><span class="sxs-lookup"><span data-stu-id="d8a88-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="d8a88-111">Andere Klassen einfache Geometrie sind <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d8a88-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="d8a88-112">Diese Geometrien sowie komplexere können auch erstellt werden mithilfe einer <xref:System.Windows.Media.PathGeometry> oder <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d8a88-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="d8a88-113">Weitere Informationen finden Sie unter der [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8a88-113">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a88-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8a88-114">See Also</span></span>  
 [<span data-ttu-id="d8a88-115">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="d8a88-115">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="d8a88-116">Erstellen einer zusammengesetzten Form</span><span class="sxs-lookup"><span data-stu-id="d8a88-116">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="d8a88-117">Erstellen einer Form mithilfe von PathGeometry</span><span class="sxs-lookup"><span data-stu-id="d8a88-117">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
