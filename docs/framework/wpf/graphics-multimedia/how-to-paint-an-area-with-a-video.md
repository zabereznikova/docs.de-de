---
title: 'Vorgehensweise: Zeichnen eines Bereichs mit einem Video'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: c5995359486bcc415b048256c772ec5012b066f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580199"
---
# <a name="how-to-paint-an-area-with-a-video"></a>Vorgehensweise: Zeichnen eines Bereichs mit einem Video
Dieses Beispiel zeigt, wie Sie das Zeichnen eines Bereichs mit Media. Eine Möglichkeit zum Zeichnen eines Bereichs mit Medien ist die Verwendung einer <xref:System.Windows.Controls.MediaElement> zusammen mit einem <xref:System.Windows.Media.VisualBrush>. Verwenden der <xref:System.Windows.Controls.MediaElement> laden und Wiedergeben der Medien und verwenden dieses dann zum Festlegen der <xref:System.Windows.Media.VisualBrush.Visual%2A> Eigenschaft der <xref:System.Windows.Media.VisualBrush>. Anschließend können Sie die <xref:System.Windows.Media.VisualBrush> zum Zeichnen eines Bereichs mit den geladenen Medien.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.MediaElement> und ein <xref:System.Windows.Media.VisualBrush> zum Zeichnen der <xref:System.Windows.Controls.TextBlock.Foreground%2A> von einer <xref:System.Windows.Controls.TextBlock> -Steuerelement mit Video. In diesem Beispiel wird die <xref:System.Windows.Controls.MediaElement.IsMuted%2A> Eigenschaft der <xref:System.Windows.Controls.MediaElement> zu `true` , damit es kein Sound abgespielt wird.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a>Beispiel  
 Da <xref:System.Windows.Media.VisualBrush> erbt von der <xref:System.Windows.Media.TileBrush> -Klasse stellt mehrere Kachelmodi bereit. Durch Festlegen der <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft eine <xref:System.Windows.Media.VisualBrush> zu <xref:System.Windows.Media.TileMode.Tile> und durch Festlegen der <xref:System.Windows.Media.TileBrush.Viewport%2A> -Eigenschaft auf einen Wert kleiner als der Bereich, der zu zeichnenden, Sie können ein Kachelmuster erstellen.  
  
 Im folgende Beispiel ist identisch mit dem vorherigen Beispiel, außer dass die <xref:System.Windows.Media.VisualBrush> ein Muster aus dem Video generiert.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 Informationen zur Vorgehensweise beim Hinzufügen einer Inhaltsdatei, z. B. eine Mediendatei an Ihre Anwendung finden Sie unter [WPF-Anwendungsressource, Inhalt und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md). Wenn Sie eine Mediendatei hinzufügen, müssen Sie es als eine Datei mit Inhalt und nicht als eine Ressourcendatei hinzufügen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.VisualBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Übersicht über TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)
- [Übersicht über Multimedia](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
