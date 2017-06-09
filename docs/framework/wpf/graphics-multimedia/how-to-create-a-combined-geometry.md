---
title: "Gewusst wie: Erstellen von kombinierten Geometrien | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Kombinieren von Geometrien"
  - "Geometrien, Kombinieren"
  - "Grafiken, Kombinieren von Geometrien"
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Erstellen von kombinierten Geometrien
Dieses Beispiel zeigt, wie Sie Geometrien kombinieren.  Um zwei Geometrien zu kombinieren, verwenden Sie ein <xref:System.Windows.Media.CombinedGeometry>\-Objekt.  Legen Sie die <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>\-Eigenschaft und die <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>\-Eigenschaft des Objekts auf die zu kombinierenden Geometrien fest, und definieren Sie die <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>\-Eigenschaft, um anzugeben, wie die Geometrien kombiniert werden sollen: `Union`, `Intersect`, `Exclude` oder `Xor`.  
  
 Um eine kombinierte Geometrie aus zwei oder mehr Geometrien zu erstellen, verwenden Sie eine <xref:System.Windows.Media.GeometryGroup>.  
  
## Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.CombinedGeometry> definiert, wobei der Kombinationsmodus auf `Exclude` festgelegt ist.  Sowohl <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> als auch <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius definiert, deren Mittelpunkte jedoch um den Wert 50 versetzt sind.  
  
 [!code-xml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Ergebnisse des Exclude&#45;Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.png "mil\_task\_combined\_geometry\_exclude")  
Kombinierte Geometrie – Exclude  
  
 Im folgenden Markup wird eine <xref:System.Windows.Media.CombinedGeometry> definiert, wobei der Kombinationsmodus auf `Intersect` festgelegt ist.  Sowohl <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> als auch <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius definiert, deren Mittelpunkte jedoch um den Wert 50 versetzt sind.  
  
 [!code-xml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Ergebnisse des Intersect&#45;Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.png "mil\_task\_combined\_geometry\_intersect")  
Kombinierte Geometrie – Intersect  
  
 Im folgenden Markup wird eine <xref:System.Windows.Media.CombinedGeometry> definiert, wobei der Kombinationsmodus auf `Union` festgelegt ist.  Sowohl <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> als auch <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius definiert, deren Mittelpunkte jedoch um den Wert 50 versetzt sind.  
  
 [!code-xml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Ergebnisse des Union&#45;Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.png "mil\_task\_combined\_geometry\_union")  
Kombinierte Geometrie – Union  
  
 Im folgenden Markup wird eine <xref:System.Windows.Media.CombinedGeometry> definiert, wobei der Kombinationsmodus auf `Xor` festgelegt ist.  Sowohl <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> als auch <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius definiert, deren Mittelpunkte jedoch um den Wert 50 versetzt sind.  
  
 [!code-xml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Ergebnisse des Xor&#45;Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.png "mil\_task\_combined\_geometry\_xor")  
Kombinierte Geometrie – Xor