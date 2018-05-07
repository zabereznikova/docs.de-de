---
title: 'Gewusst wie: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 5b129b1bacb5dc2cba87376e8df70e115a5ebd72
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>Gewusst wie: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry
In diesem Beispiel wird gezeigt, wie mehrere Pfade im Erstellen einer <xref:System.Windows.Media.PathGeometry>. Um mehrere Pfade zu erstellen, erstellen Sie eine <xref:System.Windows.Media.PathFigure> für jeden untergeordneten Pfad.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei Pfade, die jeweils einem Dreieck gekennzeichnet.  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 Im folgende Beispiel wird gezeigt, wie erstellen Sie mehrere Pfade mithilfe einer <xref:System.Windows.Shapes.Path> und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attributsyntax. Jede `M` erstellt einen neuen untergeordneten so, dass im Beispiel werden zwei Pfade erstellt, jeweils ein Dreieck gezeichnet wird.  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (Beachten Sie, die diese Attributsyntax tatsächlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, einer helleren Gewichtung-Version von einer <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
