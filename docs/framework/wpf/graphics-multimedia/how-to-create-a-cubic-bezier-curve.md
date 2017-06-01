---
title: "Gewusst wie: Erstellen einer kubischen B&#233;zierkurve | Microsoft Docs"
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
  - "Bezier-Kurven, Kubisch"
  - "Erstellen, Kubische Bezier-Kurven"
  - "Kubische Bezier-Kurven"
  - "Kurven, Kubische Bezier-Kurven"
  - "Grafiken, Kubische Bezier-Kurven"
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Erstellen einer kubischen B&#233;zierkurve
Dieses Beispiel zeigt, wie Sie eine kubische Bézierkurve erstellen.  Um eine kubische Bézierkurve zu erstellen, verwenden Sie die Klassen <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.BezierSegment>.  Um die resultierende Geometrie anzuzeigen, verwenden Sie ein <xref:System.Windows.Shapes.Path>\-Element, oder verwenden Sie eine <xref:System.Windows.Media.GeometryDrawing> oder einen <xref:System.Windows.Media.DrawingContext>.  In den folgenden Beispielen wird von den Koordinaten \(10, 100\) bis \(300, 100\) eine kubische Bézierkurve gezeichnet.  Die Kurve verfügt bei \(100, 0\) und \(200, 200\) über Kontrollpunkte.  
  
## Beispiel  
 \[xaml\]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie abgekürzte Markupsyntax verwenden, um einen Pfad zu beschreiben.  
  
 [!code-xml[GeometrySample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 \[xaml\]  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie auch mit Objekttags eine kubische Bézierkurve zeichnen.  Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Beispiel.  
  
 [!code-xml[GeometrySample#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Dieses Beispiel gehört zu einem größeren Beispiel. Das vollständige Beispiel finden Sie unter [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## Siehe auch  
 [Erstellen eines elliptischen Bogens](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)   
 [Erstellen eines LineSegment in einer PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)   
 [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)   
 [Erstellen einer quadratischen Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)