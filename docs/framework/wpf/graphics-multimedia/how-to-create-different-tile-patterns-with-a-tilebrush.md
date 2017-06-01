---
title: "Gewusst wie: Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush | Microsoft Docs"
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
  - "Erstellen, Kachelmuster mit TileBrush"
  - "Kachelmuster, Erstellen"
  - "TileBrush, Erstellen von Kachelmustern"
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush
In diesem Beispiel ist dargestellt, wie die <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Eigenschaft eines <xref:System.Windows.Media.TileBrush> verwendet wird, um ein Muster zu erstellen.  
  
 Mit der <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Eigenschaft können Sie festlegen, wie der Inhalt eines <xref:System.Windows.Media.TileBrush> wiederholt, d. h. wie "gekachelt" wird, um einen Ausgabebereich auszufüllen.  Legen Sie den <xref:System.Windows.Media.TileBrush.TileMode%2A> auf <xref:System.Windows.Media.TileMode>, <xref:System.Windows.Media.TileMode>, <xref:System.Windows.Media.TileMode> oder <xref:System.Windows.Media.TileMode> fest, um ein Muster zu erstellen.  Sie müssen den <xref:System.Windows.Media.TileBrush.Viewport%2A> des <xref:System.Windows.Media.TileBrush> außerdem so festlegen, dass er kleiner ist als der zu zeichnende Bereich, andernfalls wird nur eine einzige Kachel erstellt, unabhängig von der verwendeten <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Einstellung.  
  
## Beispiel  
 Im folgenden Beispiel werden fünf <xref:System.Windows.Media.DrawingBrush>\-Objekte erstellt, für die jeweils eine eigene <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Einstellung festgelegt wird und die anschließend zum Zeichnen von fünf Rechtecken verwendet werden.  In diesem Beispiel wird die <xref:System.Windows.Media.DrawingBrush>\-Klasse verwendet, um das <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Verhalten zu veranschaulichen. Die <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Eigenschaft kann für alle <xref:System.Windows.Media.TileBrush>\-Objekte, d. h. für <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush> und <xref:System.Windows.Media.DrawingBrush> auf die gleiche Weise verwendet werden.  
  
 In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![TileBrush&#45;Kachelbeispiel&#45;Ausgabe](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm\_DrawingBrushTileModeExample")  
Mit der TileMode\-Eigenschaft erstellte Kachelmuster  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## Siehe auch  
 [Festlegen der Kachelgröße für ein TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)