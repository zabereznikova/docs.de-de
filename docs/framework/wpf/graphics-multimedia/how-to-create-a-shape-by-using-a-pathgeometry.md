---
title: 'Gewusst wie: Erstellen einer Form mithilfe von PathGeometry'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31f77f0921bb018317834077f70e4623c47a4f7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Gewusst wie: Erstellen einer Form mithilfe von PathGeometry
In diesem Beispiel wird gezeigt, wie ein Shape erstellt die <xref:System.Windows.Media.PathGeometry> Klasse. <xref:System.Windows.Media.PathGeometry>Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten; jedes <xref:System.Windows.Media.PathFigure> einen anderen "Abbildung" oder eine Form darstellt. Jede <xref:System.Windows.Media.PathFigure> selbst besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, die jeweils einen verknüpften Bereich der Abbildung oder Form darstellen. Segment Anweisungstypen <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, und <xref:System.Windows.Media.BezierSegment>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.PathGeometry> ein Dreieck erstellen. Die <xref:System.Windows.Media.PathGeometry> wird angezeigt, mit einem <xref:System.Windows.Shapes.Path> Element.  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![Eine PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "Wcpsdk_graphicsmm_pathgeometry_triangle")  
Ein Dreieck mit einem PathGeometry erstellt  
  
 Im vorherige Beispiel wurde gezeigt, wie eine relativ einfache Form, ein Dreieck zu erstellen. Ein <xref:System.Windows.Media.PathGeometry> kann auch verwendet werden, um komplexere Formen, einschließlich Bögen und Kurven zu erstellen. Beispiele finden Sie unter [Erstellen eines elliptischen Bogens](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [erstellen Sie eine kubische Bézier-Kurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), und [erstellen Sie eine quadratische Bézier-Kurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Geometrien-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159989)
