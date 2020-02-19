---
title: 'Gewusst wie: Erstellen einer kubischen Bézierkurve'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: c12bd84fcebb3acebb80bef5f4479ad535fd6691
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452109"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Gewusst wie: Erstellen einer kubischen Bézierkurve
In diesem Beispiel wird gezeigt, wie eine kubische Bezier-Kurve erstellt wird. Um eine kubische Bezier-Kurve zu erstellen, verwenden Sie die Klassen <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>und <xref:System.Windows.Media.BezierSegment>.  Verwenden Sie zum Anzeigen der resultierenden Geometrie ein <xref:System.Windows.Shapes.Path>-Element, oder verwenden Sie es mit einem <xref:System.Windows.Media.GeometryDrawing> oder einem <xref:System.Windows.Media.DrawingContext>. In den folgenden Beispielen wird eine kubische Bezier-Kurve zwischen (10, 100) und (300, 100) gezeichnet. Die Kurve hat Steuerungs Punkte (100, 0) und (200, 200).  
  
## <a name="example"></a>Beispiel  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]können Sie eine abgekürzte Markup Syntax verwenden, um einen Pfad zu beschreiben.  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 [xaml]  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie auch eine kubische Bezier-Kurve mithilfe von Objekt Tags zeichnen. Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen eines elliptischen Bogens](how-to-create-an-elliptical-arc.md)
- [Erstellen eines LineSegment in einer PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [Erstellen Sie eine kubische Bezier-Kurve.](how-to-create-a-cubic-bezier-curve.md)
- [Erstellen einer quadratischen Bezier-Kurve](how-to-create-a-quadratic-bezier-curve.md)
