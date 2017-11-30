---
title: "Übersicht über TileBrush"
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
- TileBrush [WPF]
- brushes [WPF], TileBrush
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f759a56233e8cf2b1c1d39862706be518fefe43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="tilebrush-overview"></a>Übersicht über TileBrush
<xref:System.Windows.Media.TileBrush>-Objekte ermöglichen den steuern, wie ein Bereich mit einem Bild gezeichnet wird mit einer hohen <xref:System.Windows.Media.Drawing>, oder <xref:System.Windows.Media.Visual>. Dieses Thema beschreibt, wie <xref:System.Windows.Media.TileBrush> Funktionen erhalten Sie besser steuern, wie ein <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, oder <xref:System.Windows.Media.VisualBrush> zeichnet einen Bereich.  
  
  
<a name="prerequisite"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, ist es hilfreich zu verstehen, wie Sie die grundlegenden Funktionen von der <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, oder <xref:System.Windows.Media.VisualBrush> Klasse. Eine Einführung zu diesen Typen finden Sie unter der [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="tilebrush"></a>   
## <a name="painting-an-area-with-tiles"></a>Zeichnen eines Bereichs mit Kacheln  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, sind <xref:System.Windows.Media.VisualBrush> Typen von <xref:System.Windows.Media.TileBrush> Objekte. Kacheleffekte bieten Ihnen gute Steuerungsmöglichkeiten für das Malen eines Bilds, einer Zeichnung oder eines visuellen Objekts in einem Bereich. Sie können beispielsweise zum Zeichnen eines Bereichs anstelle eines einzelnen gestreckten Bilds eine Reihe von Bildkacheln verwenden, die ein Muster ergeben.  
  
 Beim Zeichnen eines Bereichs mit einem Kacheleffekt spielen drei Komponenten eine Rolle: Inhalt, Basiskachel und Ausgabebereich.  
  
 ![TileBrush-Komponenten](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Komponenten eines TileBrush mit einer einzelnen Kachel  
  
 ![Komponenten eines gekachelten TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "Graphicsmm_tiledprojection")  
Komponenten eines TileBrush mit einer TileMode-Kachel  
  
 Ausgabebereich ist der Bereich gezeichnet wird, wie z. B. die <xref:System.Windows.Shapes.Shape.Fill%2A> des ein <xref:System.Windows.Shapes.Ellipse> oder die <xref:System.Windows.Controls.Control.Background%2A> von einer <xref:System.Windows.Controls.Button>. In den nächsten Abschnitten wird beschrieben, die anderen beiden Komponenten der eine <xref:System.Windows.Media.TileBrush>.  
  
<a name="brushcontent"></a>   
## <a name="brush-content"></a>Pinselinhalt  
 Es gibt drei verschiedene Typen von <xref:System.Windows.Media.TileBrush> und jeder Zeichnet mit einem anderen Typ des Inhalts.  
  
-   Wenn der Pinsel eine <xref:System.Windows.Media.ImageBrush>, dieser Inhalt ist ein Bild der <xref:System.Windows.Media.ImageBrush.ImageSource%2A> Eigenschaft gibt den Inhalt der <xref:System.Windows.Media.ImageBrush>.  
  
-   Wenn der Pinsel eine <xref:System.Windows.Media.DrawingBrush>, diesen Inhalt ist eine Zeichnung. Die <xref:System.Windows.Media.DrawingBrush.Drawing%2A> Eigenschaft gibt den Inhalt der <xref:System.Windows.Media.DrawingBrush>.  
  
-   Wenn der Pinsel eine <xref:System.Windows.Media.VisualBrush>, diesen Inhalt ist ein visuelles Element. Die <xref:System.Windows.Media.VisualBrush.Visual%2A> Eigenschaft gibt den Inhalt der <xref:System.Windows.Media.VisualBrush>.  
  
 Sie können angeben, die Position und Abmessungen des <xref:System.Windows.Media.TileBrush> Inhalt mithilfe der <xref:System.Windows.Media.TileBrush.Viewbox%2A> -Eigenschaft, jedoch verlassen der <xref:System.Windows.Media.TileBrush.Viewbox%2A> auf seinen Standardwert festgelegt. Wird standardmäßig die <xref:System.Windows.Media.TileBrush.Viewbox%2A> konfiguriert ist, um den Inhalt des Pinsels vollständig enthalten. Weitere Informationen zum Konfigurieren der <xref:System.Windows.Controls.Viewbox>, finden Sie unter der <xref:System.Windows.Controls.Viewbox> Eigenschaftenseite.  
  
<a name="thebasetile"></a>   
## <a name="the-base-tile"></a>Basiskachel  
 Ein <xref:System.Windows.Media.TileBrush> dessen Inhalt auf einem Basiskachel projiziert. Die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaftensteuerelemente wie <xref:System.Windows.Media.TileBrush> Inhalt wird gestreckt, um die Basiskachel auszufüllen. Die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft akzeptiert die folgenden Werte, die definiert, indem Sie die <xref:System.Windows.Media.Stretch> Enumeration:  
  
-   <xref:System.Windows.Media.Stretch.None>: Der Inhalt des Pinsels ist nicht gestreckt, um die Kachel auszufüllen.  
  
-   <xref:System.Windows.Media.Stretch.Fill>: Der Inhalt des Pinsels wird skaliert, um die Kachel passt. Da Höhe und Breite des Inhalts unabhängig voneinander skaliert werden, wird das ursprüngliche Seitenverhältnis des Inhalts möglicherweise nicht beibehalten. Der Inhalt des Pinsels wird möglicherweise verzerrt, um die Ausgabekachel vollständig auszufüllen.  
  
-   <xref:System.Windows.Media.Stretch.Uniform>: Der Inhalt des Pinsels wird skaliert, sodass er vollständig innerhalb der Kachel passt. Das Seitenverhältnis des Inhalts wird beibehalten.  
  
-   <xref:System.Windows.Media.Stretch.UniformToFill>: Der Inhalt des Pinsels wird so skaliert, dass es vollständig Ausgabebereich füllt, während des Inhalts ursprüngliche Seitenverhältnis beibehalten.  
  
 Das folgende Bild zeigt die verschiedenen <xref:System.Windows.Media.TileBrush.Stretch%2A> Einstellungen.  
  
 ![Unterschiedliche TileBrush-Dehneinstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 Im folgenden Beispiel den Inhalt einer <xref:System.Windows.Media.ImageBrush> festgelegt ist, sodass er nicht gestreckt wird, um den Ausgabebereich ausfüllen.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 Wird standardmäßig ein <xref:System.Windows.Media.TileBrush> generiert eine einzige Kachel (die Basiskachel) und streckt diese Kachel, um den Ausgabebereich vollständig auszufüllen. Sie können die Größe und Position der Basiskachel ändern, durch Festlegen der <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaften.  
  
<a name="basetilesize"></a>   
### <a name="base-tile-size"></a>Größe der Basiskachel  
 Die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft bestimmt die Größe und Position der Basiskachel, und die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaft bestimmt, ob die <xref:System.Windows.Media.TileBrush.Viewport%2A> unter Verwendung der absolute oder relativer Koordinaten angegeben wird. Wenn die Koordinaten relativ sind, sind sie relativ zur Größe des Ausgabebereichs. Der Punkt (0,0) stellt die obere linke Ecke des Ausgabebereichs und (1,1) stellt die untere rechte Ecke des Ausgabebereichs dar. Angeben, dass die <xref:System.Windows.Media.TileBrush.Viewport%2A> -Eigenschaft absolute Koordinaten verwendet, legen Sie die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaft <xref:System.Windows.Media.BrushMappingMode.Absolute>.  
  
 Die folgende Abbildung zeigt den Unterschied in der Ausgabe zwischen einem <xref:System.Windows.Media.TileBrush> mit relativen und absoluten <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>. Beachten Sie, dass in den Abbildungen ein Kachelmuster angezeigt wird. Im nächsten Abschnitt wird beschrieben, wie Kachelmuster angegeben werden.  
  
 ![Absolute und relative Viewport-Einheiten](../../../../docs/framework/wpf/graphics-multimedia/media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 Im folgenden Beispiel wird ein Bild verwendet, um eine Kachel zu erstellen, deren Breite und Höhe 50% ist. Die Basiskachel befindet sich bei (0,0) des Ausgabebereichs.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 Im nächsten Beispiel wird die Kacheln von einem <xref:System.Windows.Media.ImageBrush> auf 25 von 25 geräteunabhängige Pixel. Da die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> absolut ist, werden die <xref:System.Windows.Media.ImageBrush> Kacheln sind immer 25 von 25 Pixel, unabhängig von der Größe des Clientbereichs gezeichnet wird.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>   
### <a name="tiling-behavior"></a>Kachelverhalten  
 Ein <xref:System.Windows.Media.TileBrush> ein gekacheltes Muster erzeugt, wenn die Basiskachel den Ausgabebereich und ein anderer dann nicht vollständig gefüllt wird <xref:System.Windows.Media.TileMode.None> angegeben ist. Wenn eines Kacheleffekts Kachel nicht vollständig den Ausgabebereich ausfüllen der <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft gibt an, ob die Basiskachel dupliziert werden soll, um den Ausgabebereich ausfüllen, und wenn dies der Fall ist, wie die Basiskachel dupliziert werden soll. Die <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft akzeptiert die folgenden Werte, die definiert, indem Sie die <xref:System.Windows.Media.TileMode> Enumeration:  
  
-   <xref:System.Windows.Media.TileMode.None>: Nur die Basiskachel wird gezeichnet.  
  
-   <xref:System.Windows.Media.TileMode.Tile>: Die Basiskachel wird gezeichnet, und der verbleibende Bereich wird durch die Wiederholung der Basiskachel, dass dem rechten Rand einer Kachel neben dem linken Rand der nächsten und wird auf ähnliche Weise für die untere und obere ausgefüllt.  
  
-   <xref:System.Windows.Media.TileMode.FlipX>: Identisch mit <xref:System.Windows.Media.TileMode.Tile>, aber Kachelspalte horizontal gekippt werden.  
  
-   <xref:System.Windows.Media.TileMode.FlipY>: Identisch mit <xref:System.Windows.Media.TileMode.Tile>, aber kachelreihe vertikal gekippt werden.  
  
-   <xref:System.Windows.Media.TileMode.FlipXY>: Eine Kombination von <xref:System.Windows.Media.TileMode.FlipX> und <xref:System.Windows.Media.TileMode.FlipY>.  
  
 Die folgende Abbildung zeigt die unterschiedlichen Kachelmodi.  
  
 ![Unterschiedliche TileBrush-TileMode-Einstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 Im folgenden Beispiel wird ein Bild verwendet, um ein Rechteck zu zeichnen, das 100 Pixel breit und 100 Pixel hoch ist. Durch Festlegen des Pinsels <xref:System.Windows.Media.TileBrush.Viewport%2A> vorsieht, 0,0,0.25,0.25, erfolgt die Basiskachel 1/4 des Ausgabebereichs verhält. Des Pinsels <xref:System.Windows.Media.TileBrush.TileMode%2A> festgelegt ist, um <xref:System.Windows.Media.TileMode.FlipXY>. sodass er das Rechteck mit Kachelreihen ausfüllt.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 <xref:System.Windows.Media.TileBrush>  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)  
 [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [ImageBrush-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160005)  
 [VisualBrush-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160049)
