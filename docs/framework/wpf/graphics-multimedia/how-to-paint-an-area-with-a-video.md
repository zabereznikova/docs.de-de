---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem Video'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: d2ca0f8b70abf6e895ea275d2a47eb4a6dd4bfe4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-paint-an-area-with-a-video"></a>Gewusst wie: Zeichnen eines Bereichs mit einem Video
In diesem Beispiel wird gezeigt, wie einen Bereich mit Medien gezeichnet wird. Eine Möglichkeit zum Zeichnen eines Bereichs mit Medien ist die Verwendung einer <xref:System.Windows.Controls.MediaElement> zusammen mit einem <xref:System.Windows.Media.VisualBrush>. Verwenden der <xref:System.Windows.Controls.MediaElement> zum Laden und Wiedergeben der Medien und Verwendung zur Festlegung der <xref:System.Windows.Media.VisualBrush.Visual%2A> Eigenschaft von der <xref:System.Windows.Media.VisualBrush>. Anschließend können Sie die <xref:System.Windows.Media.VisualBrush> um einen Bereich mit den geladenen Medien zu zeichnen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.MediaElement> und ein <xref:System.Windows.Media.VisualBrush> zum Zeichnen der <xref:System.Windows.Controls.TextBlock.Foreground%2A> des ein <xref:System.Windows.Controls.TextBlock> -Steuerelement mit Video. In diesem Beispiel wird die <xref:System.Windows.Controls.MediaElement.IsMuted%2A> Eigenschaft von der <xref:System.Windows.Controls.MediaElement> auf `true` , damit es kein Sound erzeugt.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a>Beispiel  
 Da <xref:System.Windows.Media.VisualBrush> erbt von der <xref:System.Windows.Media.TileBrush> -Klasse stellt verschiedene Modi für Tiling bereit. Durch Festlegen der <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft eine <xref:System.Windows.Media.VisualBrush> auf <xref:System.Windows.Media.TileMode.Tile> festlegen und die <xref:System.Windows.Media.TileBrush.Viewport%2A> -Eigenschaft auf einen Wert kleiner als der Bereich, der zu zeichnenden sind, können Sie ein gekacheltes Muster erstellen.  
  
 Im folgende Beispiel ist identisch mit dem vorherigen Beispiel, außer dass die <xref:System.Windows.Media.VisualBrush> ein Muster aus dem Video generiert.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 Informationen zur Vorgehensweise beim Hinzufügen einer Inhaltsdatei ein, z. B. eine Mediendatei an Ihre Anwendung finden Sie unter [Anwendungsressource WPF-Inhalt und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md). Wenn Sie eine Mediendatei hinzufügen, müssen Sie es als eine Datei mit Inhalt und nicht als eine Ressourcendatei hinzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.VisualBrush>  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Übersicht über TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [Übersicht über Multimedia](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
