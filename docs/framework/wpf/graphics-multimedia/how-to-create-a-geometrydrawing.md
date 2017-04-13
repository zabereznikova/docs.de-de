---
title: "Gewusst wie: Erstellen einer GeometryDrawing | Microsoft Docs"
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
  - "Klassen, GeometryDrawing"
  - "GeometryDrawing-Klasse"
  - "Grafiken, GeometryDrawing-Klasse"
  - "Formen zum Rendern"
  - "Formen, Zum Rendern"
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Erstellen einer GeometryDrawing
In diesem Beispiel wird gezeigt, wie eine <xref:System.Windows.Media.GeometryDrawing> erstellt und angezeigt wird.  Mit einer <xref:System.Windows.Media.GeometryDrawing> können Sie eine ausgefüllte Form mit einem Rand erstellen, indem Sie <xref:System.Windows.Media.Pen> und <xref:System.Windows.Media.Brush> einer <xref:System.Windows.Media.Geometry> zuordnen.  Die <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> beschreibt die Struktur, der <xref:System.Windows.Media.GeometryDrawing.Brush%2A> beschreibt die Füllung und der <xref:System.Windows.Media.GeometryDrawing.Pen%2A> beschreibt den Rand der Form.  
  
## Beispiel  
 Im folgenden Beispiel wird mithilfe einer <xref:System.Windows.Media.GeometryDrawing> eine Form gerendert.  Die Form wird von einer <xref:System.Windows.Media.GeometryGroup> und zwei <xref:System.Windows.Media.EllipseGeometry>\-Objekten beschrieben.  Das Innere der Form wird mit einem <xref:System.Windows.Media.LinearGradientBrush>, die Kontur mit einem <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen> gezeichnet.  Die <xref:System.Windows.Media.GeometryDrawing> wird mithilfe eines <xref:System.Windows.Media.ImageDrawing>\- und eines <xref:System.Windows.Controls.Image>\-Elements angezeigt.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 In der folgenden Abbildung ist die resultierende <xref:System.Windows.Media.GeometryDrawing> dargestellt.  
  
 ![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
  
 Mit einer <xref:System.Windows.Media.DrawingGroup> können Sie komplexere Zeichnungen erstellen und mehrere Zeichnungsobjekte zu einer einzigen zusammengesetzten Zeichnung zusammenfassen.  
  
## Siehe auch  
 <xref:System.Windows.Media.DrawingGroup>   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Erstellen einer zusammengesetzten Zeichnung](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)