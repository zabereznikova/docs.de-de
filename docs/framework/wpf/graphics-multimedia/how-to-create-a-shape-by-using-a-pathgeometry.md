---
title: 'Vorgehensweise: Erstellen einer Form mithilfe einer PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: b0ab703596612524881ab892a1095b0f49cd1551
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159314"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Vorgehensweise: Erstellen einer Form mithilfe einer PathGeometry
In diesem Beispiel wird gezeigt, wie zum Erstellen einer Form mithilfe der <xref:System.Windows.Media.PathGeometry> Klasse. <xref:System.Windows.Media.PathGeometry> Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten; jedes <xref:System.Windows.Media.PathFigure> stellt eine andere "Abbildung" oder Form dar. Jede <xref:System.Windows.Media.PathFigure> selbst besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, von denen jedes einen verknüpften Abschnitt der Figur oder Form darstellt. Segmenttypen beinhalten <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, und <xref:System.Windows.Media.BezierSegment>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.PathGeometry> ein Dreieck erstellen. Die <xref:System.Windows.Media.PathGeometry> nutzt eine <xref:System.Windows.Shapes.Path> Element.  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![Eine PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "Wcpsdk_graphicsmm_pathgeometry_triangle")  
Ein Dreieck mit PathGeometry erstellt  
  
 Im vorherigen Beispiel wurde gezeigt, wie eine relativ einfache Form, ein Dreieck zu bilden. Ein <xref:System.Windows.Media.PathGeometry> kann auch verwendet werden, um komplexere Formen, einschließlich Bögen und Kurven zu erstellen. Beispiele finden Sie in [Erstellen eines elliptischen Bogens](how-to-create-an-elliptical-arc.md), [erstellen Sie eine kubische Bezier-Kurve](how-to-create-a-cubic-bezier-curve.md), und [Erstellen einer quadratischen Bezier-Kurve](how-to-create-a-quadratic-bezier-curve.md).  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Übersicht über die Geometrie](geometry-overview.md)
- [Beispiele zu Geometrie](https://go.microsoft.com/fwlink/?LinkID=159989)
