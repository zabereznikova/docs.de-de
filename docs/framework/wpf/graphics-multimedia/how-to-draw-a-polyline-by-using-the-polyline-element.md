---
title: "Gewusst wie: Zeichnen einer Polylinie mithilfe des Polylinien-Elements | Microsoft Docs"
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
  - "Verbundene Linien"
  - "Zeichnen, Polylinien"
  - "Grafiken [WPF], Polylinien"
  - "Linien, Verbunden (siehe Polylinien)"
  - "Polylinien, Zeichnen"
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Zeichnen einer Polylinie mithilfe des Polylinien-Elements
In diesem Beispiel wird veranschaulicht, wie Sie mithilfe des <xref:System.Windows.Shapes.Polyline>\-Elements eine Polylinie zeichnen. Eine Polylinie besteht aus mehreren verbundenen Linien.  
  
 Erstellen Sie zum Zeichnen einer Polylinie ein <xref:System.Windows.Shapes.Polyline>\-Element. Verwenden Sie dessen <xref:System.Windows.Shapes.Polyline.Points%2A>\-Eigenschaft, um die Eckpunkte der Form anzugeben.  Beschreiben Sie abschließend mithilfe der <xref:System.Windows.Shapes.Shape.Stroke%2A>\-Eigenschaft und der <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>\-Eigenschaft die Kontur der Polylinie, da eine Linie ohne einen Strich nicht sichtbar ist.  
  
> [!NOTE]
>  Da es sich bei dem <xref:System.Windows.Shapes.Polyline>\-Element nicht um eine geschlossene Form handelt, hat die <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft auch dann keine Auswirkungen, wenn Sie die Formkontur absichtlich schließen.  Wenn Sie mithilfe der <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft, eine geschlossene Form erstellen möchten, müssen Sie ein <xref:System.Windows.Shapes.Polygon>\-Element verwenden.  
  
 In folgendem Beispiel werden zwei <xref:System.Windows.Shapes.Polyline>\-Elemente innerhalb eines <xref:System.Windows.Controls.Canvas> gezeichnet.  
  
## Beispiel  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ist die gültige Syntax für Punkte eine durch Leerzeichen getrennte Liste von x\- und y\-Koordinatenpaaren, die durch Trennzeichen getrennt sind.  
  
 [!code-xml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Obwohl in diesem Beispiel ein <xref:System.Windows.Controls.Canvas> als Container für die Polylinien verwendet wird, können Polylinien\-Elemente \(sowie alle anderen Formelemente\) mit allen <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> verwendet werden, die Inhalte unterstützen, bei denen es sich nicht um Text handelt.  
  
 Dieses Beispiel gehört zu einem größeren Beispiel. Das vollständige Beispiel finden Sie unter [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## Siehe auch  
 <xref:System.Windows.Shapes.Polyline>   
 <xref:System.Windows.Shapes.Polygon>   
 <xref:System.Windows.Shapes.Shape>   
 [Beispiel für Formelemente](http://go.microsoft.com/fwlink/?LinkID=160037)   
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)