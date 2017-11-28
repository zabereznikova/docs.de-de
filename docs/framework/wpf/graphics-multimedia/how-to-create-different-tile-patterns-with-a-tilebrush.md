---
title: 'Gewusst wie: Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush'
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
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6247f6a16cd8ab7be683d0d4d33aac021f3a2b32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a>Gewusst wie: Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush
Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft eine <xref:System.Windows.Media.TileBrush> um ein Muster zu erstellen.  
  
 Die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft können Sie angeben, wie die Inhalts des eine <xref:System.Windows.Media.TileBrush> wird wiederholt, d. h., gekachelt, um einen Ausgabebereich ausfüllen. Um ein Muster zu erstellen, Sie legen die <xref:System.Windows.Media.TileBrush.TileMode%2A> auf <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, oder <xref:System.Windows.Media.TileMode.FlipXY>. Müssen Sie auch Festlegen der <xref:System.Windows.Media.TileBrush.Viewport%2A> von der <xref:System.Windows.Media.TileBrush> , damit es kleiner ist als der Bereich handelt, die zu zeichnenden; hingegen nur eine einzige Kachel wird erzeugt, unabhängig davon die <xref:System.Windows.Media.TileBrush.TileMode%2A> Einstellung, die Sie verwenden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt fünf <xref:System.Windows.Media.DrawingBrush> Objekte, erhalten sie jede ein anderes <xref:System.Windows.Media.TileBrush.TileMode%2A> festlegen und verwendet sie zum Zeichnen von fünf Rechtecken. Obwohl in diesem Beispiel verwendet die <xref:System.Windows.Media.DrawingBrush> Klasse zur Veranschaulichung der Funktion <xref:System.Windows.Media.TileBrush.TileMode%2A> Verhalten, die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft funktioniert genauso wie für alle der <xref:System.Windows.Media.TileBrush> Objekte aufweist, d. h. für <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, und <xref:System.Windows.Media.DrawingBrush>.  
  
 In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![TileBrush Kacheln Beispielausgabe](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "Graphicsmm_DrawingBrushTileModeExample")  
Kachel-Muster, die mit der TileMode-Eigenschaft erstellt  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen der Kachelgröße für ein TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
