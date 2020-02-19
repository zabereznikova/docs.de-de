---
title: 'Gewusst wie: Erstellen einer quadratischen Bézierkurve'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: caaf967b7cb5447d86dd031beeb16195413b0393
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452070"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a>Gewusst wie: Erstellen einer quadratischen Bézierkurve
In diesem Beispiel wird gezeigt, wie eine quadratische Bezier-Kurve erstellt wird.  Um eine quadratische Bezier-Kurve zu erstellen, verwenden Sie die Klassen <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>und <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
## <a name="example"></a>Beispiel  
 In den folgenden Beispielen wird eine quadratische Bezier-Kurve von (10.100) bis (300.100) gezeichnet. Die Kurve weist einen Kontrollpunkt von (200.200) auf.  
  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]können Sie die Attribut Syntax verwenden, um einen Pfad zu beschreiben.  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 [xaml]  
  
 (Beachten Sie, dass diese Attribut Syntax tatsächlich einen <xref:System.Windows.Media.StreamGeometry>erstellt, eine hellere Version einer <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](path-markup-syntax.md).)  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie auch eine quadratische Bezier-Kurve mithilfe der Objekt Element Syntax zeichnen. Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen eines elliptischen Bogens](how-to-create-an-elliptical-arc.md)
- [Erstellen Sie eine kubische Bezier-Kurve.](how-to-create-a-cubic-bezier-curve.md)
