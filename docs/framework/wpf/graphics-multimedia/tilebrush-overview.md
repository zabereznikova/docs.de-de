---
title: Übersicht über TileBrush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF]
- brushes [WPF], TileBrush
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
ms.openlocfilehash: 99bcc8695206030a381d71df2dda495867d3e9c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187100"
---
# <a name="tilebrush-overview"></a>Übersicht über TileBrush
<xref:System.Windows.Media.TileBrush>Objekte geben Ihnen eine große Kontrolle darüber, wie ein <xref:System.Windows.Media.Drawing>Bereich <xref:System.Windows.Media.Visual>mit einem Bild, oder gemalt wird. In diesem Thema <xref:System.Windows.Media.TileBrush> wird beschrieben, wie Features <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>verwendet <xref:System.Windows.Media.VisualBrush> werden, um mehr Kontrolle darüber zu erlangen, wie ein , oder ein Bereich gezeichnet wird.  

<a name="prerequisite"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Um dieses Thema zu verstehen, ist es hilfreich zu <xref:System.Windows.Media.ImageBrush>verstehen, wie die grundlegenden Features der , <xref:System.Windows.Media.DrawingBrush>oder <xref:System.Windows.Media.VisualBrush> Klasse verwendet werden. Eine Einführung in diese Typen finden Sie im [Thema Malerei mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md).  
  
<a name="tilebrush"></a>
## <a name="painting-an-area-with-tiles"></a>Zeichnen eines Bereichs mit Kacheln  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>sind <xref:System.Windows.Media.VisualBrush> <xref:System.Windows.Media.TileBrush> Objekttypen. Kacheleffekte bieten Ihnen gute Steuerungsmöglichkeiten für das Malen eines Bilds, einer Zeichnung oder eines visuellen Objekts in einem Bereich. Sie können beispielsweise zum Zeichnen eines Bereichs anstelle eines einzelnen gestreckten Bilds eine Reihe von Bildkacheln verwenden, die ein Muster ergeben.  
  
 Beim Zeichnen eines Bereichs mit einem Kacheleffekt spielen drei Komponenten eine Rolle: Inhalt, Basiskachel und Ausgabebereich.  
  
 ![TileBrush-Komponenten](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Komponenten eines TileBrush mit einer einzelnen Kachel  
  
 ![Komponenten eines gekachelten TileBrush-Elements](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Komponenten eines TileBrush mit einer TileMode-Kachel  
  
 Der Ausgabebereich ist der Bereich, <xref:System.Windows.Shapes.Shape.Fill%2A> der <xref:System.Windows.Shapes.Ellipse> lackiert <xref:System.Windows.Controls.Control.Background%2A> wird, <xref:System.Windows.Controls.Button>z. B. der von einem oder der eines . In den nächsten Abschnitten werden <xref:System.Windows.Media.TileBrush>die beiden anderen Komponenten einer beschrieben.  
  
<a name="brushcontent"></a>
## <a name="brush-content"></a>Pinselinhalt  
 Es gibt drei <xref:System.Windows.Media.TileBrush> verschiedene Arten von und jede Farbe mit einem anderen Inhaltstyp.  
  
- Wenn der Pinsel <xref:System.Windows.Media.ImageBrush>ein ist, ist <xref:System.Windows.Media.ImageBrush.ImageSource%2A> dieser Inhalt ein <xref:System.Windows.Media.ImageBrush>Bild Die Eigenschaft gibt den Inhalt der an.  
  
- Wenn es sich <xref:System.Windows.Media.DrawingBrush>bei dem Pinsel um einen handelt, handelt es sich bei diesem Inhalt um eine Zeichnung. Die <xref:System.Windows.Media.DrawingBrush.Drawing%2A> Eigenschaft gibt den <xref:System.Windows.Media.DrawingBrush>Inhalt der an.  
  
- Wenn es sich <xref:System.Windows.Media.VisualBrush>bei dem Pinsel um einen handelt, handelt es sich bei diesem Inhalt um ein visuelles Element. Die <xref:System.Windows.Media.VisualBrush.Visual%2A> Eigenschaft gibt den <xref:System.Windows.Media.VisualBrush>Inhalt der an.  
  
 Sie können die Position <xref:System.Windows.Media.TileBrush> und die <xref:System.Windows.Media.TileBrush.Viewbox%2A> Dimensionen des Inhalts mithilfe der <xref:System.Windows.Media.TileBrush.Viewbox%2A> Eigenschaft angeben, obwohl es üblich ist, den Satz auf den Standardwert zu belassen. Standardmäßig ist <xref:System.Windows.Media.TileBrush.Viewbox%2A> der so konfiguriert, dass er den Inhalt des Pinsels vollständig enthält. Weitere Informationen zum <xref:System.Windows.Controls.Viewbox>Konfigurieren der <xref:System.Windows.Controls.Viewbox> finden Sie auf der Eigenschaftenseite.  
  
<a name="thebasetile"></a>
## <a name="the-base-tile"></a>Basiskachel  
 Ein <xref:System.Windows.Media.TileBrush> projiziert seinen Inhalt auf eine Basiskachel. Die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft <xref:System.Windows.Media.TileBrush> steuert, wie der Inhalt gestreckt wird, um die Basiskachel zu füllen. Die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft akzeptiert die folgenden <xref:System.Windows.Media.Stretch> Werte, die durch die Enumeration definiert sind:  
  
- <xref:System.Windows.Media.Stretch.None>: Der Inhalt des Pinsels wird nicht gedehnt, um die Kachel zu füllen.  
  
- <xref:System.Windows.Media.Stretch.Fill>: Der Inhalt des Pinsels wird so skaliert, dass er an die Kachel passt. Da Höhe und Breite des Inhalts unabhängig voneinander skaliert werden, wird das ursprüngliche Seitenverhältnis des Inhalts möglicherweise nicht beibehalten. Der Inhalt des Pinsels wird möglicherweise verzerrt, um die Ausgabekachel vollständig auszufüllen.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: Der Inhalt des Pinsels wird so skaliert, dass er vollständig in die Kachel passt. Das Seitenverhältnis des Inhalts wird beibehalten.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: Der Inhalt des Pinsels wird so skaliert, dass er den Ausgabebereich vollständig ausfüllt, während das ursprüngliche Seitenverhältnis des Inhalts beibehalten wird.  
  
 Die folgende Abbildung veranschaulicht <xref:System.Windows.Media.TileBrush.Stretch%2A> die verschiedenen Einstellungen.  
  
 ![Unterschiedliche TileBrush-Dehneinstellungen](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 Im folgenden Beispiel wird der <xref:System.Windows.Media.ImageBrush> Inhalt eines so eingestellt, dass er sich nicht erstreckt, um den Ausgabebereich zu füllen.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 Standardmäßig generiert <xref:System.Windows.Media.TileBrush> a eine einzelne Kachel (die Basiskachel) und dehnt diese Kachel, um den Ausgabebereich vollständig zu füllen. Sie können die Größe und Position der <xref:System.Windows.Media.TileBrush.Viewport%2A> Basiskachel ändern, indem Sie die und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> die Eigenschaften festlegen.  
  
<a name="basetilesize"></a>
### <a name="base-tile-size"></a>Größe der Basiskachel  
 Die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft bestimmt die Größe und Position <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> der Basiskachel, und die Eigenschaft bestimmt, ob die <xref:System.Windows.Media.TileBrush.Viewport%2A> mit absoluten oder relativen Koordinaten angegeben wird. Wenn die Koordinaten relativ sind, sind sie relativ zur Größe des Ausgabebereichs. Der Punkt (0,0) stellt die obere linke Ecke des Ausgabebereichs und (1,1) stellt die untere rechte Ecke des Ausgabebereichs dar. Um anzugeben, <xref:System.Windows.Media.TileBrush.Viewport%2A> dass die Eigenschaft <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> absolute <xref:System.Windows.Media.BrushMappingMode.Absolute>Koordinaten verwendet, legen Sie die Eigenschaft auf fest.  
  
 Die folgende Abbildung zeigt den <xref:System.Windows.Media.TileBrush> Unterschied in <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>der Ausgabe zwischen einem mit relativen und absoluten . Beachten Sie, dass in den Abbildungen ein Kachelmuster angezeigt wird. Im nächsten Abschnitt wird beschrieben, wie Kachelmuster angegeben werden.  
  
 ![Absolute und relative Viewport-Einheiten](./media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 Im folgenden Beispiel wird ein Bild verwendet, um eine Kachel zu erstellen, deren Breite und Höhe 50% ist. Die Basiskachel befindet sich bei (0,0) des Ausgabebereichs.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 Im nächsten Beispiel werden <xref:System.Windows.Media.ImageBrush> die Kacheln von einem auf 25 mal 25 geräteunabhängige Pixel festgelegt. Da <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> die absolut <xref:System.Windows.Media.ImageBrush> sind, sind die Kacheln immer 25 x 25 Pixel, unabhängig von der Größe des zu malenden Bereichs.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>
### <a name="tiling-behavior"></a>Kachelverhalten  
 A <xref:System.Windows.Media.TileBrush> erzeugt ein gekacheltes Muster, wenn seine Basiskachel den Ausgabebereich nicht vollständig ausfüllt und ein anderer Kachelmodus angegeben <xref:System.Windows.Media.TileMode.None> wird. Wenn die Kachel eines Kachelpinsels den Ausgabebereich <xref:System.Windows.Media.TileBrush.TileMode%2A> nicht vollständig ausfüllt, gibt seine Eigenschaft an, ob die Basiskachel dupliziert werden soll, um den Ausgabebereich auszufüllen, und wenn ja, wie die Basiskachel dupliziert werden soll. Die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft akzeptiert die folgenden <xref:System.Windows.Media.TileMode> Werte, die durch die Enumeration definiert sind:  
  
- <xref:System.Windows.Media.TileMode.None>: Es wird nur die Basiskachel gezeichnet.  
  
- <xref:System.Windows.Media.TileMode.Tile>: Die Basiskachel wird gezeichnet, und der verbleibende Bereich wird gefüllt, indem die Basiskachel so wiederholt wird, dass der rechte Rand einer Kachel neben dem linken Rand der nächsten Kachel und ähnlich für unten und oben ist.  
  
- <xref:System.Windows.Media.TileMode.FlipX>: Das <xref:System.Windows.Media.TileMode.Tile>gleiche wie , aber alternative Spalten von Kacheln werden horizontal gekippt.  
  
- <xref:System.Windows.Media.TileMode.FlipY>: Das <xref:System.Windows.Media.TileMode.Tile>gleiche wie , aber alternative Zeilen von Kacheln werden vertikal gekippt.  
  
- <xref:System.Windows.Media.TileMode.FlipXY>: Eine <xref:System.Windows.Media.TileMode.FlipX> Kombination <xref:System.Windows.Media.TileMode.FlipY>aus und .  
  
 Die folgende Abbildung zeigt die unterschiedlichen Kachelmodi.  
  
 ![Unterschiedliche TileBrush-TileMode-Einstellungen](./media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 Im folgenden Beispiel wird ein Bild verwendet, um ein Rechteck zu zeichnen, das 100 Pixel breit und 100 Pixel hoch ist. Durch Festlegen der <xref:System.Windows.Media.TileBrush.Viewport%2A> Einstellung des Pinsels auf 0,0,0.25,0.25 wird die Basiskachel des Pinsels auf 1/4 des Ausgabebereichs festgelegt. Der Pinsel <xref:System.Windows.Media.TileBrush.TileMode%2A> ist auf <xref:System.Windows.Media.TileMode.FlipXY>gesetzt. sodass er das Rechteck mit Kachelreihen ausfüllt.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [How-to-Themen](brushes-how-to-topics.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
- [Beispiel zu ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
