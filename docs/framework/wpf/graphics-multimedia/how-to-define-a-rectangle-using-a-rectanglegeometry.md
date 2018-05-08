---
title: 'Gewusst wie: Definieren eines Rechtecks mit RectangleGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 5d2ec6aec1eea8528ea6b43f72f4820b8bc19a37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>Gewusst wie: Definieren eines Rechtecks mit RectangleGeometry
Dieses Beispiel beschreibt, wie die <xref:System.Windows.Media.RectangleGeometry> Klasse, um ein Rechteck beschrieben.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Erstellen und Rendern einer <xref:System.Windows.Media.RectangleGeometry>.  Die relative Position und die Dimensionen des Rechtecks definieren, indem eine <xref:System.Windows.Rect> Struktur. Die relative Position ist `50,50` und die Höhe und Breite werden beide `25` erstellen ein Quadrat. Das Innere des Rechtecks gezeichnet wird, mit einem <xref:System.Windows.Media.Brushes.LemonChiffon%2A> Pinsel und seine Kontur mit gezeichnet wird eine <xref:System.Windows.Media.Brushes.Black%2A> Stärke der `1`.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![Eine RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "Graphicsmm_rectangle")  
RectangleGeometry  
  
 Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Shapes.Path> Element zum Rendern der <xref:System.Windows.Media.RectangleGeometry>, es gibt viele andere Methoden verwenden <xref:System.Windows.Media.RectangleGeometry> Objekte. Z. B. eine <xref:System.Windows.Media.RectangleGeometry> kann verwendet werden, um anzugeben der <xref:System.Windows.UIElement.Clip%2A> von einer <xref:System.Windows.UIElement> oder die <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> des eine <xref:System.Windows.Media.GeometryDrawing>.  
  
 Andere Klassen einfache Geometrie sind <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.EllipseGeometry>. Diese Geometrien sowie komplexere können auch erstellt werden mithilfe einer <xref:System.Windows.Media.PathGeometry> oder <xref:System.Windows.Media.StreamGeometry>.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
