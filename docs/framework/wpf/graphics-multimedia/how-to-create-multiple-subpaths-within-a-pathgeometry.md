---
title: "Gewusst wie: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry | Microsoft Docs"
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
  - "Klassen, PathGeometry"
  - "Grafiken [WPF], Untergeordnete Pfade"
  - "Mehrere untergeordnete Pfade"
  - "PathGeometry-Klasse"
  - "Untergeordnete Pfade"
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry
In diesem Beispiel wird das Erstellen von mehreren untergeordneten Pfaden in einer <xref:System.Windows.Media.PathGeometry> dargestellt.  Um mehrere untergeordnete Pfade zu erstellen, muss für jeden dieser Pfade eine <xref:System.Windows.Media.PathFigure> erstellt werden.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei untergeordnete Pfade erstellt, wobei jeder ein Dreieck darstellt.  
  
 [!code-xml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 Im folgenden Beispiel wird das Erstellen von mehreren untergeordneten Pfaden mithilfe von <xref:System.Windows.Shapes.Path> und der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Attributsyntax dargestellt.  Jedes `M` erstellt einen neuen untergeordneten Pfad. Somit werden in dem Beispiel zwei untergeordnete Pfade erstellt, die jeweils ein Dreieck zeichnen.  
  
 [!code-xml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 \(Beachten Sie, dass mithilfe dieser Attributsyntax eigentlich eine <xref:System.Windows.Media.StreamGeometry> erstellt wird, bei der es sich um eine vereinfachte Version von <xref:System.Windows.Media.PathGeometry> handelt.  Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).\)  
  
## Siehe auch  
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)