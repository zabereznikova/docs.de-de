---
title: "Gewusst wie: Erstellen eines elliptischen Bogens | Microsoft Docs"
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
  - "Bögen, In Ellipsenform"
  - "Elliptische Bogen, Erstellen"
  - "Grafiken [WPF], Elliptische Bogen"
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen eines elliptischen Bogens
In diesem Beispiel wird veranschaulicht, wie ein elliptischer Bogen gezeichnet wird.  Verwenden Sie zum Erstellen eines elliptischen Bogens die Klassen <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> und <xref:System.Windows.Media.ArcSegment>.  
  
## Beispiel  
 In den folgenden Beispielen wird ein elliptischer Bogen von \(10,100\) nach \(200,100\) gezeichnet.  Der Bogen verfügt über die folgenden Merkmale: <xref:System.Windows.Media.ArcSegment.Size%2A> 100 mal 50 geräteunabhängige Pixel, <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 Grad, <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>\-Festlegung auf `true` und <xref:System.Windows.Media.ArcSegment.SweepDirection%2A>\-Festlegung auf <xref:System.Windows.Media.SweepDirection>.  
  
 \[xaml\]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie zum Beschreiben eines Pfads die Attributsyntax verwenden.  
  
 [!code-xml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 \[xaml\]  
  
 \(Beachten Sie, dass mithilfe dieser Attributsyntax eigentlich eine <xref:System.Windows.Media.StreamGeometry> erstellt wird, bei der es sich um eine vereinfachte Version von <xref:System.Windows.Media.PathGeometry> handelt.  Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).\)  
  
 Ein elliptischer Bogen kann in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ebenfalls explizit mithilfe der Objekttags gezeichnet werden.  Das Folgende entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup.  
  
 [!code-xml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Dieses Beispiel ist ein Teil eines umfangreicheren Beispiels.  Das vollständige Beispiel finden Sie unter [Beispiele zu Geometrie](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## Siehe auch  
 [Erstellen einer quadratischen Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)   
 [Erstellen einer kubischen Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)