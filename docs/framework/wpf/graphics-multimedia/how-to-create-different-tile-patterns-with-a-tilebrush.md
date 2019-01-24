---
title: 'Vorgehensweise: Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: d6b6d4a20d43478131d3adb7c7d091214b3c5871
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721974"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a>Vorgehensweise: Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft eine <xref:System.Windows.Media.TileBrush> um ein Muster zu erstellen.  
  
 Die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft können Sie angeben, wie der Inhalt der ein <xref:System.Windows.Media.TileBrush> wird wiederholt, d. h., gekachelt, um einen Ausgabebereich auszufüllen. Um ein Muster zu erstellen, legen Sie die <xref:System.Windows.Media.TileBrush.TileMode%2A> zu <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, oder <xref:System.Windows.Media.TileMode.FlipXY>. Müssen Sie auch Festlegen der <xref:System.Windows.Media.TileBrush.Viewport%2A> von der <xref:System.Windows.Media.TileBrush> , damit er kleiner als der Bereich ist, die Sie zeichnen werden; andernfalls nur eine einzige Kachel wird erstellt, unabhängig davon die <xref:System.Windows.Media.TileBrush.TileMode%2A> Einstellung, die Sie verwenden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt fünf <xref:System.Windows.Media.DrawingBrush> Objekte, erhalten sie jeden eine andere <xref:System.Windows.Media.TileBrush.TileMode%2A> festlegen und zum Zeichnen von fünf Rechtecken verwendet. Obwohl dieses Beispiel verwendet die <xref:System.Windows.Media.DrawingBrush> Klasse zur Veranschaulichung <xref:System.Windows.Media.TileBrush.TileMode%2A> Verhalten der <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft funktioniert genauso wie für alle der <xref:System.Windows.Media.TileBrush> Objekte, d. h. für <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, und <xref:System.Windows.Media.DrawingBrush>.  
  
 In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![TileBrush-Beispielausgabe tiling](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "Graphicsmm_DrawingBrushTileModeExample")  
Kachelmuster mit der TileMode-Eigenschaft erstellt  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a>Siehe auch
- [Festlegen der Kachelgröße für ein TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
