---
title: "Gewusst wie: Erstellen einer Linie mit einer LineGeometry | Microsoft Docs"
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
  - "Klassen, LineGeometry"
  - "Grafiken [WPF], Linien"
  - "LineGeometry-Klasse"
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Erstellen einer Linie mit einer LineGeometry
In diesem Beispiel wird die Verwendung der <xref:System.Windows.Media.LineGeometry>\-Klasse zum Beschreiben einer Linie dargestellt.  Eine <xref:System.Windows.Media.LineGeometry> wird durch ihren Start\- und ihren Endpunkt definiert.  
  
## Beispiel  
 Im folgenden Beispiel wird das Erstellen und Rendern einer <xref:System.Windows.Media.LineGeometry> veranschaulicht.  Ein <xref:System.Windows.Shapes.Path>\-Element wird verwendet, um die Linie zu rendern.  Da eine Linie keinen Bereich aufweist, wird <xref:System.Windows.Shapes.Shape.Fill%2A> für das <xref:System.Windows.Shapes.Path>\-Objekt nicht festgelegt. Stattdessen werden die <xref:System.Windows.Shapes.Shape.Stroke%2A>\-Eigenschaft und die <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>\-Eigenschaft verwendet.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![Eine LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
  
        LineGeometry, gezeichnet von \(10,20\) bis \(100,130\)  
  
 Andere Klassen der einfachen Geometrie sind <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.EllipseGeometry>.  Diese und auch komplexere Geometrien können auch mit <xref:System.Windows.Media.PathGeometry> oder <xref:System.Windows.Media.StreamGeometry> erstellt werden.  Weitere Informationen finden Sie unter [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
## Siehe auch  
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)