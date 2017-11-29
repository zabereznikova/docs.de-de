---
title: 'Gewusst wie: Erstellen von kombinierten Geometrien'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2be0471f27d26b145cc29847a08bf3bc3b1d51ff
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-combined-geometry"></a>Gewusst wie: Erstellen von kombinierten Geometrien
In diesem Beispiel wird gezeigt, wie Geometrien kombiniert werden. Zum Kombinieren zweier Geometrien verwenden eine <xref:System.Windows.Media.CombinedGeometry> Objekt. Legen Sie seine <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> Eigenschaften mit den zwei Geometrien zu kombinieren, und legen Sie die <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> Eigenschaft, die bestimmt, wie die Geometrien kombiniert werden sollen, auf `Union`, `Intersect`, `Exclude`, oder `Xor`.  
  
 Um eine zusammengesetzte Geometrie aus mindestens zwei Geometrien zu erstellen, verwenden Sie eine <xref:System.Windows.Media.GeometryGroup>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel ein <xref:System.Windows.Media.CombinedGeometry> mit einem Kombinationsmodus definiert `Exclude`.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, jedoch mit Rechenzentren Offset von 50 definiert.  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Ergebnisse des Exclude-Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "Mil_task_combined_geometry_exclude")  
Kombinierte Geometrie ausschließen  
  
 Im folgenden Markup eine <xref:System.Windows.Media.CombinedGeometry> wird definiert, mit der Kombinationsmodus `Intersect`.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, jedoch mit Rechenzentren Offset von 50 definiert.  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Ergebnisse des Intersect-Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "Mil_task_combined_geometry_intersect")  
Intersect-kombinierte Geometrie  
  
 Im folgenden Markup eine <xref:System.Windows.Media.CombinedGeometry> wird definiert, mit der Kombinationsmodus `Union`.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, jedoch mit Rechenzentren Offset von 50 definiert.  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Ergebnisse des Union-Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "Mil_task_combined_geometry_union")  
Kombinierte Geomtrievereinigung  
  
 Im folgenden Markup eine <xref:System.Windows.Media.CombinedGeometry> wird definiert, mit der Kombinationsmodus `Xor`.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, jedoch mit Rechenzentren Offset von 50 definiert.  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Ergebnisse des Xor-Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "Mil_task_combined_geometry_xor")  
Kombinierte Geometrie Xor
