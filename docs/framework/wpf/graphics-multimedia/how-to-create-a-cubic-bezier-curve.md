---
title: "Gewusst wie: Erstellen einer kubischen Bézierkurve"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35d4fad0634586d5d0c6ea85f276d6e76edb3f63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Gewusst wie: Erstellen einer kubischen Bézierkurve
Dieses Beispiel zeigt, wie Sie eine kubische Bézier-Kurve zu erstellen. Um eine kubische Bézier-Kurve zu erstellen, verwenden Sie die <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.BezierSegment> Klassen.  Verwenden Sie zum Anzeigen der resultierenden Geometrie eine <xref:System.Windows.Shapes.Path> Element, oder verwenden sie eine <xref:System.Windows.Media.GeometryDrawing> oder eine <xref:System.Windows.Media.DrawingContext>. In den folgenden Beispielen wird eine kubische Bézier-Kurve von gezeichnet (10, 100), (300, 100). Die Kurve hat Steuerpunkte von (100, 0) und (200, 200).  
  
## <a name="example"></a>Beispiel  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können abgekürzte Markupsyntax verwenden, um einen Pfad zu beschreiben.  
  
 [!code-xaml[GeometrySample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 [xaml]  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch eine kubische Bézier-Kurve Objekttags zeichnen. Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.  
  
 [!code-xaml[GeometrySample#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines elliptischen Bogens](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [Erstellen eines LineSegment in einer PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)  
 [Erstellen einer kubischen Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)  
 [Erstellen einer quadratischen Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)
