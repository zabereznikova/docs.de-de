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
ms.openlocfilehash: 8013bacf6c4d33ce89fc287e625ce8c8fb6c3ef0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369941"
---
# <a name="tilebrush-overview"></a>Übersicht über TileBrush
<xref:System.Windows.Media.TileBrush> -Objekte bieten Ihnen viel Kontrolle wie ein Bereich mit einem Bild, gezeichnet wird <xref:System.Windows.Media.Drawing>, oder <xref:System.Windows.Media.Visual>. In diesem Thema wird beschrieben, wie Sie mit <xref:System.Windows.Media.TileBrush> Funktionen erhalten Sie weitere steuern, wie ein <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, oder <xref:System.Windows.Media.VisualBrush> zeichnet einen Bereich.  
  
  
<a name="prerequisite"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 Um in diesem Thema zu verstehen, ist es hilfreich zu verstehen, wie Sie mit der grundlegenden Funktionen des die <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, oder <xref:System.Windows.Media.VisualBrush> Klasse. Eine Einführung in diese Datentypen, finden Sie unter den [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).  
  
<a name="tilebrush"></a>   
## <a name="painting-an-area-with-tiles"></a>Zeichnen eines Bereichs mit Kacheln  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, sind <xref:System.Windows.Media.VisualBrush> gibt Typen von <xref:System.Windows.Media.TileBrush> Objekte. Kacheleffekte bieten Ihnen gute Steuerungsmöglichkeiten für das Malen eines Bilds, einer Zeichnung oder eines visuellen Objekts in einem Bereich. Sie können beispielsweise zum Zeichnen eines Bereichs anstelle eines einzelnen gestreckten Bilds eine Reihe von Bildkacheln verwenden, die ein Muster ergeben.  
  
 Beim Zeichnen eines Bereichs mit einem Kacheleffekt spielen drei Komponenten eine Rolle: Inhalt, Basiskachel und Ausgabebereich.  
  
 ![TileBrush-Komponenten](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Komponenten eines TileBrush mit einer einzelnen Kachel  
  
 ![Komponenten eines gekachelten TileBrush](./media/graphicsmm-tiledprojection.png "Graphicsmm_tiledprojection")  
Komponenten eines TileBrush mit einer TileMode-Kachel  
  
 Der Ausgabebereich ist der gezeichnete Bereich, z. B. die <xref:System.Windows.Shapes.Shape.Fill%2A> des ein <xref:System.Windows.Shapes.Ellipse> oder <xref:System.Windows.Controls.Control.Background%2A> von einer <xref:System.Windows.Controls.Button>. Die nächsten Abschnitte beschreiben die beiden anderen Komponenten einer <xref:System.Windows.Media.TileBrush>.  
  
<a name="brushcontent"></a>   
## <a name="brush-content"></a>Pinselinhalt  
 Es gibt drei verschiedene Typen von <xref:System.Windows.Media.TileBrush> und jeder Zeichnet mit einem anderen Typ des Inhalts.  
  
-   Ist der Pinsel ein <xref:System.Windows.Media.ImageBrush>, dieser Inhalt ist ein Bild der <xref:System.Windows.Media.ImageBrush.ImageSource%2A> Eigenschaft gibt an, den Inhalt der <xref:System.Windows.Media.ImageBrush>.  
  
-   Wenn der Pinsel ein <xref:System.Windows.Media.DrawingBrush>, dieser Inhalt ist eine Zeichnung. Die <xref:System.Windows.Media.DrawingBrush.Drawing%2A> Eigenschaft gibt an, den Inhalt der <xref:System.Windows.Media.DrawingBrush>.  
  
-   Wenn der Pinsel ein <xref:System.Windows.Media.VisualBrush>, dieser Inhalt ist eine Visualisierung. Die <xref:System.Windows.Media.VisualBrush.Visual%2A> Eigenschaft gibt den Inhalt der <xref:System.Windows.Media.VisualBrush>.  
  
 Können Sie angeben, die Position und Abmessungen des <xref:System.Windows.Media.TileBrush> Inhalt mithilfe der <xref:System.Windows.Media.TileBrush.Viewbox%2A> Eigenschaft zwar üblich, lassen die <xref:System.Windows.Media.TileBrush.Viewbox%2A> auf seinen Standardwert festgelegt. In der Standardeinstellung die <xref:System.Windows.Media.TileBrush.Viewbox%2A> ist konfiguriert, dass der Inhalt des Pinsels vollständig enthalten. Weitere Informationen zum Konfigurieren der <xref:System.Windows.Controls.Viewbox>, finden Sie unter den <xref:System.Windows.Controls.Viewbox> Eigenschaftenseite.  
  
<a name="thebasetile"></a>   
## <a name="the-base-tile"></a>Basiskachel  
 Ein <xref:System.Windows.Media.TileBrush> projiziert seinen Inhalt auf eine Basiskachel. Die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft steuert wie <xref:System.Windows.Media.TileBrush> Inhalt wird gestreckt, um die Basiskachel auszufüllen. Die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft akzeptiert die folgenden Werte, die von definiert die <xref:System.Windows.Media.Stretch> Enumeration:  
  
-   <xref:System.Windows.Media.Stretch.None>: Der Inhalt des Pinsels wird nicht gestreckt, um die Kachel auszufüllen.  
  
-   <xref:System.Windows.Media.Stretch.Fill>: Der Inhalt des Pinsels wird skaliert, um die Kachel zu passen. Da Höhe und Breite des Inhalts unabhängig voneinander skaliert werden, wird das ursprüngliche Seitenverhältnis des Inhalts möglicherweise nicht beibehalten. Der Inhalt des Pinsels wird möglicherweise verzerrt, um die Ausgabekachel vollständig auszufüllen.  
  
-   <xref:System.Windows.Media.Stretch.Uniform>: Der Inhalt des Pinsels wird so skaliert, dass er vollständig innerhalb des Felds passt. Das Seitenverhältnis des Inhalts wird beibehalten.  
  
-   <xref:System.Windows.Media.Stretch.UniformToFill>: Der Inhalt des Pinsels wird skaliert, sodass er den Ausgabebereich vollständig ausfüllt, und gleichzeitig den Inhalt des ursprünglichen Seitenverhältnisse beizubehalten.  
  
 Die folgende Abbildung zeigt die verschiedenen <xref:System.Windows.Media.TileBrush.Stretch%2A> Einstellungen.  
  
 ![Unterschiedliche TileBrush-Dehneinstellungen](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 Im folgenden Beispiel den Inhalt einer <xref:System.Windows.Media.ImageBrush> wird festgelegt, damit er nicht gestreckt wird, um den Ausgabebereich auszufüllen.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 Standardmäßig eine <xref:System.Windows.Media.TileBrush> generiert eine einzige Kachel (die Basiskachel) und streckt die Kachel, um den Ausgabebereich vollständig ausfüllt. Sie können die Größe und Position der Basiskachel ändern, durch Festlegen der <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaften.  
  
<a name="basetilesize"></a>   
### <a name="base-tile-size"></a>Größe der Basiskachel  
 Die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft bestimmt die Größe und Position der Basiskachel, und die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaft bestimmt, ob die <xref:System.Windows.Media.TileBrush.Viewport%2A> mit absoluten oder relativen Koordinaten angegeben ist. Wenn die Koordinaten relativ sind, sind sie relativ zur Größe des Ausgabebereichs. Der Punkt (0,0) stellt die obere linke Ecke des Ausgabebereichs und (1,1) stellt die untere rechte Ecke des Ausgabebereichs dar. Um anzugeben, dass die <xref:System.Windows.Media.TileBrush.Viewport%2A> -Eigenschaft absolute Koordinaten verwendet, legen Sie die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaft, um <xref:System.Windows.Media.BrushMappingMode.Absolute>.  
  
 Die folgende Abbildung zeigt den Unterschied in der Ausgabe zwischen einem <xref:System.Windows.Media.TileBrush> mit relativen und absoluten <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>. Beachten Sie, dass in den Abbildungen ein Kachelmuster angezeigt wird. Im nächsten Abschnitt wird beschrieben, wie Kachelmuster angegeben werden.  
  
 ![Absolute und relative Viewport-Einheiten](./media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 Im folgenden Beispiel wird ein Bild verwendet, um eine Kachel zu erstellen, deren Breite und Höhe 50% ist. Die Basiskachel befindet sich bei (0,0) des Ausgabebereichs.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 Im nächsten Beispiel wird die Kacheln von einem <xref:System.Windows.Media.ImageBrush> auf 25 von 25 geräteunabhängige Pixel. Da die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> sind absolut, die <xref:System.Windows.Media.ImageBrush> Kacheln sind immer 25 von 25 Pixeln, unabhängig von der Größe des gezeichneten Bereichs.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>   
### <a name="tiling-behavior"></a>Kachelverhalten  
 Ein <xref:System.Windows.Media.TileBrush> erzeugt ein Kachelmuster, wenn die Basiskachel den Ausgabebereich ausfüllt und ein anderer Kachelmodus nicht vollständig ausfüllt wird <xref:System.Windows.Media.TileMode.None> angegeben ist. Wenn Sie eine Kachel kachelpinsels den Ausgabebereich nicht vollständig ausfüllt seine <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft gibt an, ob die Basiskachel dupliziert werden soll, um den Ausgabebereich auszufüllen, und wenn dies der Fall ist, wie die Basiskachel dupliziert werden soll. Die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft akzeptiert die folgenden Werte, die von definiert die <xref:System.Windows.Media.TileMode> Enumeration:  
  
-   <xref:System.Windows.Media.TileMode.None>: Nur die Basiskachel wird gezeichnet.  
  
-   <xref:System.Windows.Media.TileMode.Tile>: Die Basiskachel wird gezeichnet, und der verbleibende Bereich wird durch die Wiederholung der Basiskachel, dass die Rechte Kante einer Kachel neben bis zur linken Kante der nächsten und wird auf ähnliche Weise für die untere und obere Kante gefüllt.  
  
-   <xref:System.Windows.Media.TileMode.FlipX>: Identisch mit <xref:System.Windows.Media.TileMode.Tile>, aber Kachelspalte horizontal gekippt werden.  
  
-   <xref:System.Windows.Media.TileMode.FlipY>: Identisch mit <xref:System.Windows.Media.TileMode.Tile>, aber kachelreihe vertikal gekippt werden.  
  
-   <xref:System.Windows.Media.TileMode.FlipXY>: Die Kombination aus <xref:System.Windows.Media.TileMode.FlipX> und <xref:System.Windows.Media.TileMode.FlipY>.  
  
 Die folgende Abbildung zeigt die unterschiedlichen Kachelmodi.  
  
 ![Unterschiedliche TileBrush-TileMode-Einstellungen](./media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 Im folgenden Beispiel wird ein Bild verwendet, um ein Rechteck zu zeichnen, das 100 Pixel breit und 100 Pixel hoch ist. Durch Festlegen des Pinsels <xref:System.Windows.Media.TileBrush.Viewport%2A> wurde festgelegt auf 0,0,0.25,0.25, erfolgt die Basiskachel des Pinsels 1/4 des Ausgabebereichs verhält. Der des Pinsels <xref:System.Windows.Media.TileBrush.TileMode%2A> nastaven NA hodnotu <xref:System.Windows.Media.TileMode.FlipXY>. sodass er das Rechteck mit Kachelreihen ausfüllt.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Themen zu Vorgehensweisen](brushes-how-to-topics.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
- [Beispiel zu ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [VisualBrush-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160049)
