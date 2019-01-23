---
title: 'Vorgehensweise: Definieren eines Rechtecks mit RectangleGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 9c57f1536065af0bca1f3752179547daa502c066
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511645"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="a9df1-102">Vorgehensweise: Definieren eines Rechtecks mit RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="a9df1-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="a9df1-103">In diesem Beispiel wird beschrieben, wie Sie mit der <xref:System.Windows.Media.RectangleGeometry> Klasse, um ein Rechteck beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9df1-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9df1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9df1-104">Example</span></span>  
 <span data-ttu-id="a9df1-105">Das folgende Beispiel zeigt das Erstellen und Rendern einer <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="a9df1-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="a9df1-106">Die relative Position und den Abmessungen des Rechtecks definieren, indem eine <xref:System.Windows.Rect> Struktur.</span><span class="sxs-lookup"><span data-stu-id="a9df1-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="a9df1-107">Die relative Position `50,50` und die Höhe und Breite sind beide `25` ein Quadrat zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9df1-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="a9df1-108">Das Innere des Rechtecks gezeichnet wird eine <xref:System.Windows.Media.Brushes.LemonChiffon%2A> Pinsel und seine Kontur gezeichnet wird eine <xref:System.Windows.Media.Brushes.Black%2A> Stärke von `1`.</span><span class="sxs-lookup"><span data-stu-id="a9df1-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="a9df1-109">![Eine RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "Graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="a9df1-109">![A RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="a9df1-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="a9df1-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="a9df1-111">Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Shapes.Path> das zu rendernde Element der <xref:System.Windows.Media.RectangleGeometry>, es gibt viele andere Möglichkeiten, verwenden Sie <xref:System.Windows.Media.RectangleGeometry> Objekte.</span><span class="sxs-lookup"><span data-stu-id="a9df1-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="a9df1-112">Z. B. eine <xref:System.Windows.Media.RectangleGeometry> kann verwendet werden, um anzugeben der <xref:System.Windows.UIElement.Clip%2A> von einer <xref:System.Windows.UIElement> oder <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> von eine <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="a9df1-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="a9df1-113">Andere Klassen der einfachen Geometrie sind <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="a9df1-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="a9df1-114">Diese Geometrien, als auch eine komplexere, kann auch erstellt werden mit einem <xref:System.Windows.Media.PathGeometry> oder <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="a9df1-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9df1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9df1-115">See also</span></span>
- [<span data-ttu-id="a9df1-116">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="a9df1-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [<span data-ttu-id="a9df1-117">Erstellen einer zusammengesetzten Form</span><span class="sxs-lookup"><span data-stu-id="a9df1-117">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [<span data-ttu-id="a9df1-118">Erstellen einer Form mithilfe von PathGeometry</span><span class="sxs-lookup"><span data-stu-id="a9df1-118">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
