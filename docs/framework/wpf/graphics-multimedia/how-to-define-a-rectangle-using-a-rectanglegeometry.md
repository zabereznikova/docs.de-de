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
ms.openlocfilehash: bd42aca2541d67469173f63655ada18a12eb692c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352502"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>Vorgehensweise: Definieren eines Rechtecks mit RectangleGeometry
In diesem Beispiel wird beschrieben, wie Sie mit der <xref:System.Windows.Media.RectangleGeometry> Klasse, um ein Rechteck beschrieben.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Erstellen und Rendern einer <xref:System.Windows.Media.RectangleGeometry>.  Die relative Position und den Abmessungen des Rechtecks definieren, indem eine <xref:System.Windows.Rect> Struktur. Die relative Position `50,50` und die Höhe und Breite sind beide `25` ein Quadrat zu erstellen. Das Innere des Rechtecks gezeichnet wird eine <xref:System.Windows.Media.Brushes.LemonChiffon%2A> Pinsel und seine Kontur gezeichnet wird eine <xref:System.Windows.Media.Brushes.Black%2A> Stärke von `1`.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![Eine RectangleGeometry](./media/graphicsmm-rectangle.gif "Graphicsmm_rectangle")  
RectangleGeometry  
  
 Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Shapes.Path> das zu rendernde Element der <xref:System.Windows.Media.RectangleGeometry>, es gibt viele andere Möglichkeiten, verwenden Sie <xref:System.Windows.Media.RectangleGeometry> Objekte. Z. B. eine <xref:System.Windows.Media.RectangleGeometry> kann verwendet werden, um anzugeben der <xref:System.Windows.UIElement.Clip%2A> von einer <xref:System.Windows.UIElement> oder <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> von eine <xref:System.Windows.Media.GeometryDrawing>.  
  
 Andere Klassen der einfachen Geometrie sind <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.EllipseGeometry>. Diese Geometrien, als auch eine komplexere, kann auch erstellt werden mit einem <xref:System.Windows.Media.PathGeometry> oder <xref:System.Windows.Media.StreamGeometry>.  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Geometrien](geometry-overview.md)
- [Erstellen einer zusammengesetzten Form](how-to-create-a-composite-shape.md)
- [Erstellen einer Form mithilfe von PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
