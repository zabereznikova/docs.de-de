---
title: 'Gewusst wie: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a9a233df95f69a68c5410c5836dacd5ab2c239a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
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
