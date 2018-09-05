---
title: 'Gewusst wie: Erstellen einer Form mithilfe von PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: 4c9cd7a1af921a0a547c7dec3afc5f69b29e6aed
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748579"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Gewusst wie: Erstellen einer Form mithilfe von PathGeometry
In diesem Beispiel wird gezeigt, wie zum Erstellen einer Form mithilfe der <xref:System.Windows.Media.PathGeometry> Klasse. <xref:System.Windows.Media.PathGeometry> Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten; jedes <xref:System.Windows.Media.PathFigure> stellt eine andere "Abbildung" oder Form dar. Jede <xref:System.Windows.Media.PathFigure> selbst besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, von denen jedes einen verknüpften Abschnitt der Figur oder Form darstellt. Segmenttypen beinhalten <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, und <xref:System.Windows.Media.BezierSegment>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.PathGeometry> ein Dreieck erstellen. Die <xref:System.Windows.Media.PathGeometry> nutzt eine <xref:System.Windows.Shapes.Path> Element.  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![Eine PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "Wcpsdk_graphicsmm_pathgeometry_triangle")  
Ein Dreieck mit PathGeometry erstellt  
  
 Im vorherigen Beispiel wurde gezeigt, wie eine relativ einfache Form, ein Dreieck zu bilden. Ein <xref:System.Windows.Media.PathGeometry> kann auch verwendet werden, um komplexere Formen, einschließlich Bögen und Kurven zu erstellen. Beispiele finden Sie in [Erstellen eines elliptischen Bogens](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [erstellen Sie eine kubische Bezier-Kurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), und [Erstellen einer quadratischen Bezier-Kurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Beispiele zu Geometrie](https://go.microsoft.com/fwlink/?LinkID=159989)
