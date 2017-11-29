---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einer Zeichnung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1db788ae0fabdfd27cf215bfcf466c41df19c637
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-drawing"></a>Gewusst wie: Zeichnen eines Bereichs mit einer Zeichnung
Dieses Beispiel zeigt, wie Sie einen Bereich mit einer Zeichnung zeichnen. Um einen Bereich mit einer Zeichnung zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.DrawingBrush> und eine oder mehrere <xref:System.Windows.Media.Drawing> Objekte.   Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingBrush> ein Objekt mit einer Zeichnung von zwei Ellipsen Paint-Ereignis.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![Ausgabe eines DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "Graphicsmm_drawingbrush_simple")  
  
 (Die Mitte der Form ist weiß [steuern die Füllung für eine zusammengesetzte Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md).)  
  
 Durch Festlegen einer <xref:System.Windows.Media.DrawingBrush> des Objekts <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaften, Sie können ein sich wiederholendes Muster erstellen. Im folgenden Beispiel wird ein Objekt mit einem aus einer Zeichnung von zwei Ellipsen erstellten Muster gezeichnet.  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 Die folgende Abbildung zeigt die nebeneinander <xref:System.Windows.Media.DrawingBrush> Ausgabe.  
  
 ![Ausgabe eines DrawingBrush in Kachelform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "Graphicsmm_drawingbrush_tiled")  
  
 Weitere Informationen zu zeichnen Pinsel, finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md). Weitere Informationen zu <xref:System.Windows.Media.Drawing> anzuzeigen, die [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).
