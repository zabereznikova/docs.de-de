---
title: 'Vorgehensweise: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: d7b3d24f8d947d342a2af5484a6620c8379ac664
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638352"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>Vorgehensweise: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry
Dieses Beispiel zeigt, wie Sie mehrere Pfade im Erstellen einer <xref:System.Windows.Media.PathGeometry>. Um mehrere Pfade zu erstellen, erstellen Sie eine <xref:System.Windows.Media.PathFigure> für jeden untergeordneten Pfad.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei Pfade, die jeweils ein Dreieck.  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 Das folgende Beispiel zeigt, wie zum Erstellen von mehreren untergeordneten Pfaden mithilfe einer <xref:System.Windows.Shapes.Path> und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attributsyntax. Jede `M` erstellt einen neuen untergeordneten, so, dass im Beispiel werden zwei Pfade erstellt, jeweils ein Dreieck gezeichnet wird.  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (Beachten Sie, die dieser Attributsyntax eigentlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, eine schlankere-Version von einem <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
