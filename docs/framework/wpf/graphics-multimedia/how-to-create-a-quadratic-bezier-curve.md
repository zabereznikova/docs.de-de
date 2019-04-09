---
title: 'Vorgehensweise: Erstellen einer quadratischen Bézierkurve'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: a0b2145b4a5bba11186419fe680f2eca41949d6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134872"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a>Vorgehensweise: Erstellen einer quadratischen Bézierkurve
Dieses Beispiel zeigt, wie Sie eine quadratische Bezierkurve zu erstellen.  Verwenden Sie zum Erstellen einer quadratischen Bezierkurve der <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.QuadraticBezierSegment> Klassen.  
  
## <a name="example"></a>Beispiel  
 In den folgenden Beispielen wird eine quadratische Bezierkurve (300,100) von (10,100) positioniert. Die Kurve hat ein Steuerungspunkts für bei (200,200) enthält.  
  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können zum Beschreiben eines Pfads Attributsyntax verwenden.  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 [xaml]  
  
 (Beachten Sie, die dieser Attributsyntax eigentlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, eine schlankere-Version von einem <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](path-markup-syntax.md).)  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch eine quadratische Bezier-Kurve, die mithilfe von Objektelementsyntax zeichnen. Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen eines elliptischen Bogens](how-to-create-an-elliptical-arc.md)
- [Erstellen einer kubischen Bézierkurve](how-to-create-a-cubic-bezier-curve.md)
