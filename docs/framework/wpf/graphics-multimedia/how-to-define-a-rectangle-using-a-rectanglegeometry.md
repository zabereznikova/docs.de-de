---
title: 'Gewusst wie: Definieren eines Rechtecks mit RectangleGeometry'
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
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a8254bd60da379d006bc50ab3a935cd83b83d0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="1d592-102">Gewusst wie: Definieren eines Rechtecks mit RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="1d592-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="1d592-103">Dieses Beispiel beschreibt, wie die <xref:System.Windows.Media.RectangleGeometry> Klasse, um ein Rechteck beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d592-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d592-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d592-104">Example</span></span>  
 <span data-ttu-id="1d592-105">Das folgende Beispiel zeigt das Erstellen und Rendern einer <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="1d592-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="1d592-106">Die relative Position und die Dimensionen des Rechtecks definieren, indem eine <xref:System.Windows.Rect> Struktur.</span><span class="sxs-lookup"><span data-stu-id="1d592-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="1d592-107">Die relative Position ist `50,50` und die Höhe und Breite werden beide `25` erstellen ein Quadrat.</span><span class="sxs-lookup"><span data-stu-id="1d592-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="1d592-108">Das Innere des Rechtecks gezeichnet wird, mit einem <xref:System.Windows.Media.Brushes.LemonChiffon%2A> Pinsel und seine Kontur mit gezeichnet wird eine <xref:System.Windows.Media.Brushes.Black%2A> Stärke der `1`.</span><span class="sxs-lookup"><span data-stu-id="1d592-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="1d592-109">![Eine RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "Graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="1d592-109">![A RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="1d592-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="1d592-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="1d592-111">Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Shapes.Path> Element zum Rendern der <xref:System.Windows.Media.RectangleGeometry>, es gibt viele andere Methoden verwenden <xref:System.Windows.Media.RectangleGeometry> Objekte.</span><span class="sxs-lookup"><span data-stu-id="1d592-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="1d592-112">Z. B. eine <xref:System.Windows.Media.RectangleGeometry> kann verwendet werden, um anzugeben der <xref:System.Windows.UIElement.Clip%2A> von einer <xref:System.Windows.UIElement> oder die <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> des eine <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="1d592-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="1d592-113">Andere Klassen einfache Geometrie sind <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="1d592-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="1d592-114">Diese Geometrien sowie komplexere können auch erstellt werden mithilfe einer <xref:System.Windows.Media.PathGeometry> oder <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="1d592-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d592-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d592-115">See Also</span></span>  
 [<span data-ttu-id="1d592-116">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="1d592-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="1d592-117">Erstellen einer zusammengesetzten Form</span><span class="sxs-lookup"><span data-stu-id="1d592-117">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="1d592-118">Erstellen einer Form mithilfe von PathGeometry</span><span class="sxs-lookup"><span data-stu-id="1d592-118">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
