---
title: 'Gewusst wie: Erstellen eines elliptischen Bogens'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: 7ca7d06aa25f8dfae648d8c54c8b95cc277ffbf9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087436"
---
# <a name="how-to-create-an-elliptical-arc"></a>Gewusst wie: Erstellen eines elliptischen Bogens
Dieses Beispiel zeigt, wie Sie einen elliptischen Bogen zu zeichnen. Verwenden Sie zum Erstellen eines elliptischen Bogens der <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.ArcSegment> Klassen.  
  
## <a name="example"></a>Beispiel  
 In den folgenden Beispielen wird ein elliptischen Bogens nach (200,100) von (10,100) gezeichnet. Der Bogen verfügt über eine <xref:System.Windows.Media.ArcSegment.Size%2A> von 100 x 50 geräteunabhängige Pixel, ein <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> von 45 Grad ein <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> Festlegen der `true`, und ein <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> von <xref:System.Windows.Media.SweepDirection.Counterclockwise>.  
  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können zum Beschreiben eines Pfads Attributsyntax verwenden.  
  
 [!code-xaml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 [xaml]  
  
 (Beachten Sie, die dieser Attributsyntax eigentlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, eine schlankere-Version von einem <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch einen elliptischen Bogen zeichnen, verwenden Sie hierzu explizit Objekttags. Im folgenden finden Sie im vorhergehenden Abschnitt entspricht [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup.  
  
 [!code-xaml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter den [Beispiele zu Geometrie](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer quadratischen Bezier-Kurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)  
 [Erstellen Sie eine kubische Bezier-Kurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
