---
title: 'Vorgehensweise: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 0b57d0441c1aa9d5972af1f1c6b989aacba7f87f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353366"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>Vorgehensweise: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry
Dieses Beispiel zeigt, wie Sie mehrere Pfade im Erstellen einer <xref:System.Windows.Media.PathGeometry>. Um mehrere Pfade zu erstellen, erstellen Sie eine <xref:System.Windows.Media.PathFigure> für jeden untergeordneten Pfad.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei Pfade, die jeweils ein Dreieck.  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 Das folgende Beispiel zeigt, wie zum Erstellen von mehreren untergeordneten Pfaden mithilfe einer <xref:System.Windows.Shapes.Path> und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attributsyntax. Jede `M` erstellt einen neuen untergeordneten, so, dass im Beispiel werden zwei Pfade erstellt, jeweils ein Dreieck gezeichnet wird.  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (Beachten Sie, die dieser Attributsyntax eigentlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, eine schlankere-Version von einem <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](path-markup-syntax.md).)  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Geometrien](geometry-overview.md)
