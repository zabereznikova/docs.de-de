---
title: "Gewusst wie: Erstellen einer Form mithilfe von PathGeometry | Microsoft Docs"
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
  - "Grafiken [WPF], Formen"
  - "PathGeometry-Klasse"
  - "Formen, Erstellen mit PathGeometry-Klasse"
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erstellen einer Form mithilfe von PathGeometry
In diesem Beispiel wird gezeigt, wie eine Form mit der <xref:System.Windows.Media.PathGeometry>\-Klasse erstellt wird.  <xref:System.Windows.Media.PathGeometry>\-Objekte setzen sich aus einem oder mehreren <xref:System.Windows.Media.PathFigure>\-Objekten zusammen, wobei jedes <xref:System.Windows.Media.PathFigure>\-Objekt eine andere "Abbildung" oder Form darstellt.  Jedes <xref:System.Windows.Media.PathFigure>\-Objekt setzt sich wiederum aus einem oder mehreren <xref:System.Windows.Media.PathSegment>\-Objekten zusammen, die jeweils einen verknüpften Bereich der Abbildung oder Form darstellen.  Zu den Segmenttypen gehören <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, und <xref:System.Windows.Media.BezierSegment>.  
  
## Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.PathGeometry> verwendet, um ein Dreieck zu erstellen.  Die <xref:System.Windows.Media.PathGeometry> wird mit einem <xref:System.Windows.Shapes.Path>\-Element angezeigt.  
  
 [!code-xml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 In der folgenden Abbildung wird die im vorherigen Beispiel erstellte Form dargestellt.  
  
 ![Eine PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.png "wcpsdk\_graphicsmm\_pathgeometry\_triangle")  
Ein mit PathGeometry erstelltes Dreieck  
  
 Im vorherigen Beispiel wurde veranschaulicht, wie Sie eine relativ einfache Form, ein Dreieck, erstellen.  Mit <xref:System.Windows.Media.PathGeometry> können Sie auch komplexere Formen, einschließlich Bögen und Kurven, erstellen.  Beispiele finden Sie unter [Erstellen eines elliptischen Bogens](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Erstellen einer kubischen Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md) und [Erstellen einer quadratischen Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).  
  
 Dieses Beispiel gehört zu einem größeren Beispiel. Das vollständige Beispiel finden Sie unter [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## Siehe auch  
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.GeometryDrawing>   
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Beispiele zu Geometrie](http://go.microsoft.com/fwlink/?LinkID=159989)