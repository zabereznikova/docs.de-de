---
title: "Gewusst wie: Erstellen einer quadratischen B&#233;zierkurve | Microsoft Docs"
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
  - "Bezier-Kurven, Erstellen"
  - "Grafiken [WPF], Quadratische Bézierkurven"
  - "Quadratische Bézierkurven, Erstellen"
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Erstellen einer quadratischen B&#233;zierkurve
Dieses Beispiel zeigt, wie Sie eine quadratische Bézierkurve erstellen.  Um eine quadratische Bézierkurve zu erstellen, verwenden Sie die Klassen <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> und <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
## Beispiel  
 In den folgenden Beispielen wird von den Koordinaten \(10,100\) bis \(300,100\) eine quadratische Bézierkurve gezeichnet.  Die Kurve verfügt bei \(200,200\) über einen Kontrollpunkt.  
  
 \[xaml\]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie zum Beschreiben eines Pfads die Attributsyntax verwenden.  
  
 [!code-xml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 \[xaml\]  
  
 \(Beachten Sie, dass mithilfe dieser Attributsyntax eigentlich eine <xref:System.Windows.Media.StreamGeometry> erstellt wird, bei der es sich um eine vereinfachte Version von <xref:System.Windows.Media.PathGeometry> handelt.  Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).\)  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie eine quadratische Bézierkurve auch zeichnen, indem Sie die Objektelementsyntax verwenden.  Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Beispiel.  
  
 [!code-xml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Dieses Beispiel gehört zu einem größeren Beispiel. Das vollständige Beispiel finden Sie unter [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## Siehe auch  
 [Erstellen eines elliptischen Bogens](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)   
 [Erstellen einer kubischen Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)