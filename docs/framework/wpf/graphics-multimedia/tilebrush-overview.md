---
title: "&#220;bersicht &#252;ber TileBrush | Microsoft Docs"
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
  - "Pinsel, TileBrush"
  - "TileBrush"
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber TileBrush
<xref:System.Windows.Media.TileBrush>\-Objekte bieten Ihnen umfangreiche Steuerungsmöglichkeiten beim Zeichnen eines Bereichs mit einem Bild, einer <xref:System.Windows.Media.Drawing> oder einem <xref:System.Windows.Media.Visual>.  In diesem Thema wird die Verwendung der <xref:System.Windows.Media.TileBrush>\-Features beschrieben, um besser steuern zu können, wie ein <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> einen Bereich zeichnet.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisite"></a>   
## Vorbereitungsmaßnahmen  
 Für dieses Thema sollten Sie mit der Verwendung der grundlegenden Features der Klassen <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> vertraut sein.  Eine Einführung in diese Typen finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="tilebrush"></a>   
## Zeichnen eines Bereichs mit Kacheln  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush> sind Typen von <xref:System.Windows.Media.TileBrush>\-Objekten.  TileBrush\-Objekte bieten Ihnen umfangreiche Steuerungsmöglichkeiten beim Zeichnen eines Bereichs mit einem Bild, einer Zeichnung oder einem visuellen Element.  Sie können beispielsweise zum Zeichnen eines Bereichs anstelle eines einzelnen gestreckten Bilds eine Reihe von Bildkacheln verwenden, die ein Muster ergeben.  
  
 Wenn Sie einen Bereich mit einem TileBrush zeichnen, verwenden Sie drei Komponenten: Inhalt, Basiskachel und Ausgabebereich.  
  
 ![TileBrush&#45;Komponenten](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk\_mmgraphics\_defaultcontentprojection2")  
  
        Komponenten eines TileBrush mit einer einzelnen Kachel  
  
 ![Komponenten eines gekachelten TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm\_tiledprojection")  
  
        Komponenten eines TileBrush mit dem TileMode Tile  
  
 Der Ausgabebereich ist der gezeichnete Bereich, z. B. die <xref:System.Windows.Shapes.Shape.Fill%2A> einer <xref:System.Windows.Shapes.Ellipse> oder der <xref:System.Windows.Controls.Control.Background%2A> eines <xref:System.Windows.Controls.Button>\-Elements.  In den nächsten Abschnitten werden die anderen zwei Komponenten eines <xref:System.Windows.Media.TileBrush> beschrieben.  
  
<a name="brushcontent"></a>   
## Pinselinhalt  
 Es gibt drei verschiedene Typen von <xref:System.Windows.Media.TileBrush>, und jeder zeichnet mit einem anderen Inhaltstyp.  
  
-   Wenn der Pinsel ein <xref:System.Windows.Media.ImageBrush> ist, handelt es sich beim Inhalt um ein Bild. Die <xref:System.Windows.Media.ImageBrush.ImageSource%2A>\-Eigenschaft legt den Inhalt für den <xref:System.Windows.Media.ImageBrush> fest.  
  
-   Wenn der Pinsel ein <xref:System.Windows.Media.DrawingBrush> ist, handelt es sich beim Inhalt um eine Zeichnung.  Die <xref:System.Windows.Media.DrawingBrush.Drawing%2A>\-Eigenschaft gibt den Inhalt des <xref:System.Windows.Media.DrawingBrush> an.  
  
-   Wenn der Pinsel ein <xref:System.Windows.Media.VisualBrush> ist, handelt es sich beim Inhalt um ein visuelles Element.  Die <xref:System.Windows.Media.VisualBrush.Visual%2A>\-Eigenschaft gibt den Inhalt des <xref:System.Windows.Media.VisualBrush> an.  
  
 Mit der <xref:System.Windows.Media.TileBrush.Viewbox%2A>\-Eigenschaft können Sie Position und Abmessungen des <xref:System.Windows.Media.TileBrush>\-Inhalts angeben. Für <xref:System.Windows.Media.TileBrush.Viewbox%2A> wird jedoch in der Regel der Standardwert festgelegt.  Standardmäßig wird <xref:System.Windows.Media.TileBrush.Viewbox%2A> so konfiguriert, dass der Inhalt des Pinsels vollständig enthalten ist.  Weitere Informationen zum Konfigurieren von <xref:System.Windows.Controls.Viewbox> finden Sie auf der Eigenschaftenseite für <xref:System.Windows.Controls.Viewbox>.  
  
<a name="thebasetile"></a>   
## Basiskachel  
 Bei einem <xref:System.Windows.Media.TileBrush> wird der Inhalt auf einer Basiskachel aufgebaut.  Die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft steuert, wie der <xref:System.Windows.Media.TileBrush>\-Inhalt gestreckt wird, um die Basiskachel auszufüllen.  Die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft akzeptiert die folgenden Werte, die von der <xref:System.Windows.Media.Stretch>\-Enumeration definiert werden:  
  
-   <xref:System.Windows.Media.Stretch>: Der Inhalt des Pinsels wird nicht gestreckt, um die Kachel auszufüllen.  
  
-   <xref:System.Windows.Media.Stretch>: Der Inhalt des Pinsels wird skaliert und an die Kachel angepasst.  Da Höhe und Breite des Inhalts unabhängig voneinander skaliert werden, wird das ursprüngliche Seitenverhältnis des Inhalts möglicherweise nicht beibehalten.  Dies bedeutet, dass der Inhalt des Pinsels möglicherweise verzerrt wird, um die Ausgabekachel vollständig auszufüllen.  
  
-   <xref:System.Windows.Media.Stretch>: Der Inhalt des Pinsels wird skaliert, damit er vollständig in die Kachel passt.  Das Seitenverhältnis des Inhalts wird beibehalten.  
  
-   <xref:System.Windows.Media.Stretch>: Der Inhalt des Pinsels wird so skaliert, dass er den Ausgabebereich vollständig ausfüllt. Das ursprüngliche Seitenverhältnis wird jedoch beibehalten.  
  
 In der folgenden Abbildung werden die unterschiedlichen <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Einstellungen veranschaulicht.  
  
 ![Unterschiedliche TileBrush&#45;Dehneinstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.png "img\_mmgraphics\_stretchenum")  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush>\-Inhalt so festgelegt, dass er nicht gestreckt wird, um den Ausgabebereich auszufüllen.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 Standardmäßig erstellt ein <xref:System.Windows.Media.TileBrush> eine einzelne Kachel \(die Basiskachel\) und streckt diese Kachel, um den Ausgabebereich vollständig auszufüllen.  Sie können Größe und Position der Basiskachel ändern, indem Sie die Eigenschaften <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> festlegen.  
  
<a name="basetilesize"></a>   
### Größe der Basiskachel  
 Die <xref:System.Windows.Media.TileBrush.Viewport%2A>\-Eigenschaft bestimmt Größe und Position der Basiskachel, und die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>\-Eigenschaft bestimmt, ob <xref:System.Windows.Media.TileBrush.Viewport%2A> mit absoluten oder relativen Koordinaten angegeben wird.  Wenn die Koordinaten relativ sind, werden sie relativ zur Größe des Ausgabebereichs angegeben.  Der Punkt \(0,0\) stellt die obere linke Ecke des Ausgabebereichs dar, und \(1,1\) stellt die untere rechte Ecke des Ausgabebereichs dar.  Um anzugeben, dass die <xref:System.Windows.Media.TileBrush.Viewport%2A>\-Eigenschaft absolute Koordinaten verwendet, legen Sie die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>\-Eigenschaft auf <xref:System.Windows.Media.BrushMappingMode> fest.  
  
 Die folgende Abbildung zeigt den Unterschied in der Ausgabe zwischen einem <xref:System.Windows.Media.TileBrush> mit relativen und einem anderen mit absoluten <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> an.  Beachten Sie, dass in beiden Abbildungen ein gekacheltes Muster angezeigt wird. Im nächsten Abschnitt wird beschrieben, wie Kachelmuster angegeben werden.  
  
 ![Absolute und relative Viewport&#45;Einheiten](../../../../docs/framework/wpf/graphics-multimedia/media/absolute-and-relative-viewports.png "absolute\_and\_relative\_viewports")  
  
 Im folgenden Beispiel wird ein Bild zum Erstellen einer Kachel mit einer Breite und Höhe von 50 % verwendet.  Die Basiskachel befindet sich bei \(0,0\) des Ausgabebereichs.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 Im nächsten Beispiel werden die Kacheln von einem <xref:System.Windows.Media.ImageBrush> auf 25 mal 25 [geräteunabhängige Pixel](GTMT) festgelegt.  Da es sich bei <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> um absolute Werte handelt, haben die <xref:System.Windows.Media.ImageBrush>\-Kacheln unabhängig von der Größe des Bereichs, der gezeichnet wird, immer eine Größe von 25 mal 25 Pixel.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>   
### Kachelverhalten  
 Ein <xref:System.Windows.Media.TileBrush> erzeugt ein Kachelmuster, wenn die Basiskachel den Ausgabebereich nicht vollständig ausfüllt und ein anderer Kachelmodus als <xref:System.Windows.Media.TileMode> angegeben ist.  Wenn eine TileBrush\-Kachel den Ausgabebereich nicht vollständig ausfüllt, gibt seine <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Eigenschaft an, ob die Basiskachel dupliziert werden soll, um den Ausgabebereich auszufüllen, und wie die Basiskachel in diesem Fall dupliziert wird.  Die <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Eigenschaft akzeptiert die folgenden Werte, die von der <xref:System.Windows.Media.TileMode>\-Enumeration definiert werden:  
  
-   <xref:System.Windows.Media.TileMode>: Nur die Basiskachel wird gezeichnet.  
  
-   <xref:System.Windows.Media.TileMode>: Die Basiskachel wird gezeichnet, und der verbleibende Bereich wird ausgefüllt, indem die Basiskachel wiederholt wird, sodass die rechte Ecke einer Kachel an die linke Ecke der nächsten Kachel angrenzt. Das gleiche Prinzip gilt für oben und unten.  
  
-   <xref:System.Windows.Media.TileMode>: Wie <xref:System.Windows.Media.TileMode>, jedoch wird jede zweite Kachelspalte horizontal gekippt.  
  
-   <xref:System.Windows.Media.TileMode>: Wie <xref:System.Windows.Media.TileMode>, jedoch wird jede zweite Kachelzeile vertikal gekippt.  
  
-   <xref:System.Windows.Media.TileMode>: Eine Kombination von <xref:System.Windows.Media.TileMode> und <xref:System.Windows.Media.TileMode>.  
  
 In der folgenden Abbildung werden die unterschiedlichen Kachelmodi veranschaulicht.  
  
 ![Unterschiedliche TileBrush&#45;TileMode&#45;Einstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-tilemodes.png "img\_mmgraphics\_tilemodes")  
  
 Im folgenden Beispiel wird mithilfe eines Bilds ein Rechteck gezeichnet, das 100 Pixel breit und 100 Pixel hoch ist.  Wenn der <xref:System.Windows.Media.TileBrush.Viewport%2A> des Pinsels auf 0,0,0.25,0.25 festgelegt wurde, beträgt die Größe der Basiskachel 1\/4 des Ausgabebereichs.  Die <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Eigenschaft des Pinsels ist auf <xref:System.Windows.Media.TileMode> festgelegt,  sodass das Rechteck mit Kachelzeilen ausgefüllt wird.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## Siehe auch  
 <xref:System.Windows.Media.ImageBrush>   
 <xref:System.Windows.Media.DrawingBrush>   
 <xref:System.Windows.Media.VisualBrush>   
 <xref:System.Windows.Media.TileBrush>   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Beispiel zu ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005)   
 [Beispiel zu VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049)