---
title: 'Gewusst wie: Erstellen eines elliptischen Bogens'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: d0fffbb25f3c5aaceb2cd80af4f1093e44111200
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453064"
---
# <a name="how-to-create-an-elliptical-arc"></a>Gewusst wie: Erstellen eines elliptischen Bogens
In diesem Beispiel wird gezeigt, wie ein elliptischer Bogen gezeichnet wird. Verwenden Sie zum Erstellen eines elliptischen Bogens die Klassen <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>und <xref:System.Windows.Media.ArcSegment>.  
  
## <a name="example"></a>Beispiel  
 In den folgenden Beispielen wird ein elliptischer Bogen von (10.100) zu (200.100) gezeichnet. Der Bogen verfügt über eine <xref:System.Windows.Media.ArcSegment.Size%2A> von 100 bis 50 geräteunabhängigen Pixeln, eine <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 Grad, eine <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> Einstellung `true`und eine <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> <xref:System.Windows.Media.SweepDirection.Counterclockwise>.  
  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]können Sie die Attribut Syntax verwenden, um einen Pfad zu beschreiben.  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 [xaml]  
  
 (Beachten Sie, dass diese Attribut Syntax tatsächlich einen <xref:System.Windows.Media.StreamGeometry>erstellt, eine hellere Version einer <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](path-markup-syntax.md).)  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie auch einen elliptischen Bogen zeichnen, indem Sie explizit Objekt Tags verwenden. Folgendes entspricht dem vorangehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup.  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das komplette Beispiel finden Sie im [Beispiel zu Geometry](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen einer quadratischen Bezier-Kurve](how-to-create-a-quadratic-bezier-curve.md)
- [Erstellen Sie eine kubische Bezier-Kurve.](how-to-create-a-cubic-bezier-curve.md)
