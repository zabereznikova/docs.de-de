---
title: "Gewusst wie: Definieren eines Rechtecks mit RectangleGeometry | Microsoft Docs"
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
  - "Klassen, RectangleGeometry"
  - "Grafiken [WPF], Rechtecke"
  - "RectangleGeometry-Klasse"
  - "Rechtecke, Erstellen mit RectangleGeometry-Klasse"
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Definieren eines Rechtecks mit RectangleGeometry
In diesem Beispiel wird beschrieben, wie mit der <xref:System.Windows.Media.RectangleGeometry>\-Klasse ein Rechteck beschrieben wird.  
  
## Beispiel  
 Im folgenden Beispiel wird das Erstellen und Rendern einer <xref:System.Windows.Media.RectangleGeometry> veranschaulicht.  Die relative Position und die Abmessungen des Rechtecks werden durch eine <xref:System.Windows.Rect>\-Struktur definiert.  Die relative Position lautet `50,50`. Die Höhe und die Breite betragen jeweils `25`, wodurch ein Quadrat erstellt wird.  Das Innere des Rechtecks wird mit einem <xref:System.Windows.Media.Brushes.LemonChiffon%2A>\-Pinsel und die Kontur mit einem <xref:System.Windows.Media.Brushes.Black%2A>\-Strich der Stärke `1` gezeichnet.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![Eine RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.png "graphicsmm\_rectangle")  
RectangleGeometry  
  
 Zwar wird in diesem Beispiel <xref:System.Windows.Media.RectangleGeometry> mithilfe eines <xref:System.Windows.Shapes.Path>\-Elements gerendert, Sie können die <xref:System.Windows.Media.RectangleGeometry>\-Objekte jedoch auf viele verschiedene Arten verwenden.  Beispielsweise kann <xref:System.Windows.Media.RectangleGeometry> verwendet werden, um den <xref:System.Windows.UIElement.Clip%2A> eines <xref:System.Windows.UIElement> oder die <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> einer <xref:System.Windows.Media.GeometryDrawing> anzugeben.  
  
 Andere Klassen der einfachen Geometrie sind <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.EllipseGeometry>.  Diese und auch komplexere Geometrien können auch mit <xref:System.Windows.Media.PathGeometry> oder <xref:System.Windows.Media.StreamGeometry> erstellt werden.  
  
## Siehe auch  
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)