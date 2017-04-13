---
title: "Gewusst wie: Zeichnen eines Bereichs mit einer Zeichnung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Pinsel, Zeichnen mit Zeichnungen"
  - "Zeichnungen, Zeichnen mit"
  - "Zeichnen, Mit Zeichnungen"
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Zeichnen eines Bereichs mit einer Zeichnung
Dieses Beispiel zeigt, wie Sie einen Bereich mit einer Zeichnung zeichnen.  Um einen Bereich mit einer Zeichnung zu zeichnen, verwenden Sie einen <xref:System.Windows.Media.DrawingBrush> und ein oder mehrere <xref:System.Windows.Media.Drawing>\-Objekte.  Im folgenden Beispiel wird ein <xref:System.Windows.Media.DrawingBrush> verwendet, um ein Objekt mit einer Zeichnung zweier Ellipsen zu zeichnen.  
  
## Beispiel  
 [!code-xml[drawingbrush_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![Ausgabe von einem DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "graphicsmm\_drawingbrush\_simple")  
  
 \(Die Mitte der Form ist weiß. Die Gründe dafür sind unter [Steuern des Ausfüllens einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md) beschrieben.\)  
  
 Sie können ein sich wiederholendes Muster erstellen, indem Sie die Eigenschaften <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.TileMode%2A> eines <xref:System.Windows.Media.DrawingBrush>\-Objekts festlegen.  Im folgenden Beispiel wird ein Objekt mit einem aus einer Zeichnung von zwei Ellipsen erstellten Muster gezeichnet.  
  
 [!code-xml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 Die folgende Abbildung zeigt die <xref:System.Windows.Media.DrawingBrush>\-Ausgabe in Kachelform.  
  
 ![Gekachelte Ausgabe von einem DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "graphicsmm\_drawingbrush\_tiled")  
  
 Weitere Informationen zu Zeichenpinseln finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  Weitere Informationen zu <xref:System.Windows.Media.Drawing>\-Objekten finden Sie unter [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).