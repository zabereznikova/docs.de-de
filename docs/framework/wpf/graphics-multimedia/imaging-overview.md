---
title: "&#220;bersicht &#252;ber die Bildverarbeitung | Microsoft Docs"
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
  - "Bildkonvertierung"
  - "Zuschneiden von Bildern"
  - "Decodieren von Bildformaten"
  - "Anzeigen von Bildern"
  - "Codieren von Bildformaten"
  - "Formatdecodierung von Bildern"
  - "Formatcodierung von Bildern"
  - "Bildmetadaten"
  - "Bilder, Informationen über Bildverarbeitung"
  - "Imaging-API"
  - "Metadaten, Bilder"
  - "Zeichnen mit Bildern"
  - "Drehen von Bildern"
  - "Dehnen von Bildern"
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# &#220;bersicht &#252;ber die Bildverarbeitung
Dieses Thema bietet eine Einführung in [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)].  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] ermöglicht Entwicklern, Bilder anzuzeigen, zu transformieren und zu formatieren.  
  
   
  
<a name="_wpfImaging"></a>   
## WPF Imaging\-Komponente  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] stellt erheblich erweiterte Bildverarbeitungsfunktionen in [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] bereit.  Bildverarbeitungsfunktionen, wie z. B. die Anzeige einer Bitmap oder die Verwendung eines Bilds in einem allgemeinen Steuerelement, basierten in der Vergangenheit auf der [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] oder auf [!INCLUDE[TLA#tla_gdiplus](../../../../includes/tlasharptla-gdiplus-md.md)]\-Bibliotheken.  Diese [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]s stellen Baseline\-Bildverarbeitungsfunktionen bereit, verfügen jedoch nicht über Features wie die Unterstützung von Codec\-Erweiterbarkeit und hochwertigen Bildern.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] wurde entworfen, um die Nachteile von [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] und [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)] zu beheben und einen neuen Satz von [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]s bereitzustellen, um Bilder in den Anwendungen anzuzeigen und zu verwenden.  
  
 Für den Zugriff auf die [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] stehen zwei Möglichkeiten zur Verfügung: eine verwaltete Komponente und eine nicht verwaltete Komponente.  Die nicht verwaltete Komponente stellt die folgenden Features bereit.  
  
-   Erweiterbarkeitsmodell für neue oder proprietäre Bildformate.  
  
-   Leistungsverbesserung und erhöhte Sicherheit für systemeigene Bildformate, einschließlich [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)], [!INCLUDE[TLA#tla_jpegorg](../../../../includes/tlasharptla-jpegorg-md.md)], [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)], [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)], [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)], [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] und Symbol \(.ico\).  
  
-   Erhaltung von Bilddaten mit einer hohen Bittiefe von bis zu 8 Bits pro Kanal \(32 Bits pro Pixel\).  
  
-   Nicht destruktives Bildskalieren, Zuschneiden und Drehungen.  
  
-   Vereinfachte Farbverwaltung.  
  
-   Unterstützung für in der Datei enthaltene proprietäre Metadaten.  
  
-   Die verwaltete Komponente nutzt die nicht verwaltete Infrastruktur, um eine nahtlose Integration von Bildern mit anderen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Funktionen, z. B. [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], Animation und Grafiken, bereitzustellen.  Die verwaltete Komponente profitiert außerdem vom Codec\-Erweiterbarkeitsmodell der Bildverarbeitung in [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], was eine automatische Erkennung von neuen Bildformaten in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen ermöglicht.  
  
 Der Großteil der verwalteten [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] befindet sich im <xref:System.Windows.Media.Imaging?displayProperty=fullName>\-Namespace, auch wenn einige wichtigen Typen, z. B. <xref:System.Windows.Media.ImageBrush> und <xref:System.Windows.Media.ImageDrawing>, im <xref:System.Windows.Media?displayProperty=fullName>\-Namespace enthalten sind und <xref:System.Windows.Controls.Image> sich im <xref:System.Windows.Controls?displayProperty=fullName>\-Namespace befindet.  
  
 Dieses Thema enthält zusätzliche Informationen über die verwaltete Komponente.  Weitere Informationen über die nicht verwaltete [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] finden Sie in der Dokumentation [Nicht verwaltete WPF Imaging\-Komponente](_wic_lh).  
  
<a name="_imageformats"></a>   
## WPF\-Bildformate  
 Ein Codec wird zum Decodieren und Codieren eines bestimmten Medienformats verwendet.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] enthält einen Codec für die Bildformate [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)], [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)], [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)], [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)], [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)], [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] und ICON.  Anhand eines jeden einzelnen Codecs können Anwendungen das entsprechende Bildformat decodieren und \(mit Ausnahme von ICON\) codieren.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> ist für das Decodieren und Codieren von Bildern eine wichtige Klasse.  Sie ist der grundlegende Baustein der [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]\-Pipeline und stellt einen einzelnen konstanten Satz von Pixeln mit einer bestimmten Größe und Auflösung dar.  Eine <xref:System.Windows.Media.Imaging.BitmapSource> kann ein einzelner Rahmen eines Bilds mit mehreren Rahmen oder das Ergebnis einer Transformation sein, die auf eine <xref:System.Windows.Media.Imaging.BitmapSource> ausgeführt wurde.  Sie stellt die übergeordnete Klasse für viele der primären Klassen dar, die in der Bildverarbeitung von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet werden, z. B. <xref:System.Windows.Media.Imaging.BitmapFrame>.  
  
 Ein <xref:System.Windows.Media.Imaging.BitmapFrame> wird verwendet, um die tatsächlichen Bitmapdaten eines Bildformats zu speichern.  Viele Bildformate unterstützen lediglich einen einzelnen <xref:System.Windows.Media.Imaging.BitmapFrame>, wenngleich Formate wie [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] und [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] mehrere Rahmen pro Bild unterstützen.  Rahmen werden von Decodern als Eingabedaten verwendet und zur Erstellung der Bilddateien an die Encoder übergeben.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Media.Imaging.BitmapFrame> aus einer <xref:System.Windows.Media.Imaging.BitmapSource> erstellt und einem Bild im [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)]\-Format hinzugefügt wird.  
  
 [!code-csharp[BitmapFrameExample#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### Decodieren von Bildformaten  
 Beim Decodieren von Bildern wird das Bildformat in Bilddaten übersetzt, die vom System verwendet werden können.  Die Bilddaten können dann verwendet werden, um das Bild anzuzeigen und zu verarbeiten oder um es in ein anderes Format zu codieren.  Die Decoderauswahl basiert auf dem Bildformat.  Der Codec wird automatisch ausgewählt, wenn kein bestimmter Decoder angegeben wird.  Die Beispiele im Abschnitt [Anzeigen von Bildern in WPF](#_displayingimages) veranschaulichen die automatische Decodierung.  Decoder für benutzerdefinierte Formate, die mithilfe der nicht verwalteten [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]\-Schnittstellen entwickelt wurden und im System registriert sind, werden automatisch in die Decoderauswahl eingebunden.  Auf diese Weise können benutzerdefinierte Formate automatisch in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen angezeigt werden.  
  
 Im folgenden Beispiel wird die Verwendung eines Bitmapdecoders veranschaulicht, um ein Bild im [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]\-Format zu decodieren.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### Codieren von Bildformaten  
 Bei der Bildcodierung werden Bilddaten in ein bestimmtes Bildformat übersetzt.  Die codierten Bilddaten können dann zur Erstellung neuer Bilddateien verwendet werden.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] stellt Encoder für jedes der oben beschriebenen Bildformate bereit.  
  
 Im folgenden Beispiel wird die Verwendung eines Encoders veranschaulicht, um ein neu erstelltes Bitmapbild zu speichern.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## Anzeigen von Bildern in WPF  
 Es gibt mehrere Möglichkeiten, um in einer [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Anwendung ein Bild anzuzeigen.  Bilder können mit einem <xref:System.Windows.Controls.Image>\-Steuerelement angezeigt, mit einem <xref:System.Windows.Media.ImageBrush> auf ein visuelles Element gemalt oder mit <xref:System.Windows.Media.ImageDrawing> gezeichnet werden.  
  
### Verwenden des Image\-Steuerelements  
 <xref:System.Windows.Controls.Image> ist ein Frameworkelement und das Hauptverfahren zur Anzeige von Bildern in Anwendungen.  In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] kann <xref:System.Windows.Controls.Image> auf zwei Arten verwendet werden, mit Attributsyntax oder Eigenschaftensyntax.  Das folgende Beispiel zeigt, wie ein Bild auf eine Breite von 200 Pixel gerendert wird. Dabei wird sowohl die Attribut\- als auch die Eigenschaftensyntax verwendet.  Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Viele der Beispiele verwenden ein <xref:System.Windows.Media.Imaging.BitmapImage>\-Objekt, um auf eine Bilddatei zu verweisen.  <xref:System.Windows.Media.Imaging.BitmapImage> ist eine spezielle <xref:System.Windows.Media.Imaging.BitmapSource>, die für das Laden von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] optimiert wurde und eine einfache Möglichkeit bietet, Bilder als <xref:System.Windows.Controls.Image.Source%2A> eines <xref:System.Windows.Controls.Image>\-Steuerelements anzuzeigen.  
  
 Das folgende Beispiel zeigt, wie ein Bild auf eine Breite von 200 Pixel mithilfe von Code gerendert wird.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Imaging.BitmapImage> implementiert die <xref:System.ComponentModel.ISupportInitialize>\-Schnittstelle, um die Initialisierung für mehrere Eigenschaften zu optimieren.  Eigenschaftenänderungen können nur während der Objektinitialisierung erfolgen.  Rufen Sie <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> auf, um zu signalisieren, dass die Initialisierung begonnen wurde, und rufen Sie <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> auf, um zu signalisieren, dass die Initialisierung abgeschlossen wurde.  Nach der Initialisierung durchgeführte Eigenschaftenänderungen werden ignoriert.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### Drehen, Konvertieren und Zuschneiden von Bildern  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ermöglicht es den Benutzern, Bilder mithilfe der Eigenschaften von <xref:System.Windows.Media.Imaging.BitmapImage> oder durch die Verwendung zusätzlicher <xref:System.Windows.Media.Imaging.BitmapSource>\-Objekte, z. B. <xref:System.Windows.Media.Imaging.CroppedBitmap> oder <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>, zu transformieren.  Diese Bildtransformationen skalieren und drehen Bilder, ändern das Pixelformat von Bildern oder schneiden ein Bild zu.  
  
 Das Drehen von Bildern wird mithilfe der <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A>\-Eigenschaft von <xref:System.Windows.Media.Imaging.BitmapImage> ausgeführt.  Drehungen können nur in 90\-Grad\-Schritten vorgenommen werden.  Im folgenden Beispiel wird ein Bild um 90 Grad gedreht.  
  
 [!code-xml[ImageElementExample#TransformedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Die Bildkonvertierung in ein anderes Pixelformat, z. B. in eine Graustufe, erfolgt mit <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>.  In den folgenden Beispielen wird ein Bild in die Graustufe <xref:System.Windows.Media.PixelFormats.Gray4%2A> konvertiert.  
  
 [!code-xml[ImageElementExample_snip#ConvertedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Um ein Bild zuzuschneiden, kann entweder die <xref:System.Windows.UIElement.Clip%2A>\-Eigenschaft von <xref:System.Windows.Controls.Image> oder <xref:System.Windows.Media.Imaging.CroppedBitmap> verwendet werden.  Wenn Sie nur einen Bildbereich anzeigen möchten, sollte in der Regel <xref:System.Windows.UIElement.Clip%2A> verwendet werden.  Wenn Sie ein zugeschnittenes Bild codieren und speichern müssen, sollte <xref:System.Windows.Media.Imaging.CroppedBitmap> verwendet werden.  Im folgenden Beispiel wird mithilfe der Clip\-Eigenschaft und einer <xref:System.Windows.Media.EllipseGeometry> ein Bild zugeschnitten.  
  
 [!code-xml[ImageElementExample_snip#CroppedXAMLUsingClip1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### Dehnen von Bildern  
 Die <xref:System.Windows.Controls.Image.Stretch%2A>\-Eigenschaft steuert, wie ein Bild auf den Füllbereich seines Containers ausgedehnt wird.  Die <xref:System.Windows.Controls.Image.Stretch%2A>\-Eigenschaft akzeptiert die folgenden Werte, die von der <xref:System.Windows.Media.Stretch>\-Enumeration definiert werden:  
  
-   <xref:System.Windows.Media.Stretch>: Das Bild wird nicht auf den möglichen Füllbereich des Ausgabebereichs ausgedehnt.  Wenn das Bild größer als der Ausgabebereich ist, wird es in den Ausgabebereich gezogen, und alle überstehenden Bereiche werden abgeschnitten.  
  
-   <xref:System.Windows.Media.Stretch>: Das Bild wird auf die Größe des Ausgabebereichs skaliert.  Da die Bildhöhe und \-breite unabhängig voneinander skaliert werden, wird das ursprüngliche Seitenverhältnis des Bilds möglicherweise nicht beibehalten.  Dies bedeutet, dass das Bild möglicherweise verzerrt wird, um den Ausgabecontainer vollständig auszufüllen.  
  
-   <xref:System.Windows.Media.Stretch>: Das Bild wird so skaliert, dass es im Ausgabebereich komplett angezeigt werden kann.  Das Seitenverhältnis des Bilds wird beibehalten.  
  
-   <xref:System.Windows.Media.Stretch>: Das Bild wird so skaliert, dass es den Ausgabebereich vollständig ausfüllt. Das ursprüngliche Seitenverhältnis wird dabei beibehalten.  
  
 Im folgenden Beispiel wird jede der verfügbaren <xref:System.Windows.Media.Stretch>\-Enumerationen auf ein <xref:System.Windows.Controls.Image> angewendet.  
  
 Das folgende Bild zeigt die Ausgabe des Beispiels und veranschaulicht, wie sich die verschiedenen <xref:System.Windows.Controls.Image.Stretch%2A>\-Einstellungen auf ein Bild auswirken, wenn sie angewendet werden.  
  
 ![Unterschiedliche TileBrush&#45;Dehneinstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.png "img\_mmgraphics\_stretchenum")  
  
        Unterschiedliche Stretch\-Einstellungen  
  
 [!code-xml[ImageElementExample_snip#ImageStretchExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### Zeichnen mit Bildern  
 Bilder können auch in einer Anwendung angezeigt werden, indem man sie mit einem <xref:System.Windows.Media.Brush> zeichnet.  Mithilfe von Pinseln können Sie [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Objekte, angefangen von einfachen Objekten, über Objekte in Volltonfarbe bis hin zu Objekten mit komplexen Mustern und Bildern, zeichnen.  Um mit Bildern zu zeichnen, verwenden Sie einen <xref:System.Windows.Media.ImageBrush>.  Ein <xref:System.Windows.Media.ImageBrush> ist ein <xref:System.Windows.Media.TileBrush>\-Typ, der seinen Inhalt als Bitmapbild definiert.  Mit <xref:System.Windows.Media.ImageBrush> wird ein einzelnes Bild angezeigt, das über die <xref:System.Windows.Media.ImageBrush.ImageSource%2A>\-Eigenschaft angegeben wird.  Sie können steuern, wie das Bild gedehnt, angeordnet und gekachelt wird. Auf diese Weise können Sie Zerrungen verhindern und Muster sowie andere Effekte herstellen.  Die folgende Abbildung zeigt einige Effekte, die mit einem <xref:System.Windows.Media.ImageBrush> erreicht werden können.  
  
 ![ImageBrush&#45;Ausgabebeispiele](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.png "wcpsdk\_mmgraphics\_imagebrushexamples")  
  
        Bildpinsel können u. a. Formen, Steuerelemente und Text ausfüllen  
  
 Im folgenden Beispiel wird gezeigt, wie mit einem <xref:System.Windows.Media.ImageBrush> ein Bild als Hintergrund einer Schaltfläche gezeichnet wird.  
  
 [!code-xml[UsingImageBrush#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Weitere Informationen über <xref:System.Windows.Media.ImageBrush> und das Zeichnen von Bildern finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>   
## Metadaten von Bildern  
 Einige Bilddateien enthalten Metadaten, die den Inhalt oder die Eigenschaften der Datei beschreiben.  Beispielsweise erstellen die meisten digitalen Kameras Bilder, die Metadaten zum Fabrikat und zum Modell der Kamera enthalten, mit der das Bild aufgenommen wurde.  Jedes Bildformat behandelt Metadaten auf eine andere Weise. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] bietet hingegen eine einheitliche Möglichkeit, um Metadaten für jedes unterstützte Bildformat zu speichern und abzurufen.  
  
 Der Zugriff auf Metadaten wird durch die <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>\-Eigenschaft eines <xref:System.Windows.Media.Imaging.BitmapSource>\-Objekts bereitgestellt.  <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> gibt ein <xref:System.Windows.Media.Imaging.BitmapMetadata>\-Objekt zurück, das alle im Bild enthaltenen Metadaten enthält.  Diese Daten können in einem Metadatenschema oder in einer Kombination aus unterschiedlichen Schemas vorliegen.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] unterstützt die folgenden Schemas für Bildmetadaten: [!INCLUDE[TLA#tla_exif](../../../../includes/tlasharptla-exif-md.md)], tEXt \(PNG\-Textdaten\), [!INCLUDE[TLA#tla_ifd](../../../../includes/tlasharptla-ifd-md.md)], [!INCLUDE[TLA#tla_iptc](../../../../includes/tlasharptla-iptc-md.md)] und [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)].  
  
 Um den Vorgang zum Lesen von Metadaten zu vereinfachen, stellt <xref:System.Windows.Media.Imaging.BitmapMetadata> mehrere benannte und einfach abzurufende Eigenschaften bereit, dazu gehören <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A> und <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>.  Viele dieser benannten Eigenschaften können auch zum Schreiben von Metadaten verwendet werden.  Zusätzliche Unterstützung zum Lesen von Metadaten bietet der Metadaten\-Abfragereader.  Die <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A>\-Methode wird zum Aufrufen eines Metadaten\-Abfragereaders verwendet, indem eine Zeichenfolgenabfrage, z. B. *"\/app1\/exif\/"* bereitgestellt wird.  Im folgenden Beispiel wird <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> verwendet, um den unter *"\/Text\/Description"* gespeicherten Text abzufragen.  
  
 [!code-cpp[BitmapMetadata#GetQuery](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Zum Schreiben von Metadaten wird ein Metadaten\-Abfragewriter verwendet.  <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> ruft den Abfragewriter ab und legt den gewünschten Wert fest.  Im folgenden Beispiel wird <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> verwendet, um den unter *"\/Text\/Description"* gespeicherten Text zu schreiben.  
  
 [!code-cpp[BitmapMetadata#SetQuery](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## Erweiterbarkeit der Codecs  
 Ein Kernfeature von [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] ist das Erweiterbarkeitsmodell für neue Bildcodecs.  Mit diesen nicht verwalteten Schnittstellen können Codec\-Entwickler den Codec in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integrieren, sodass neue Bildformate von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen automatisch verwendet werden können.  
  
 Ein Beispiel für die Erweiterbarkeits\-[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] finden Sie unter [Win32\-Beispielcodec](http://go.microsoft.com/fwlink/?LinkID=160052).  In diesem Beispiel wird veranschaulicht, wie ein Decoder und ein Encoder für ein benutzerdefiniertes Bildformat erstellt werden.  
  
> [!NOTE]
>  Der Codec muss digital signiert werden, damit das System ihn erkennt.  
  
## Siehe auch  
 <xref:System.Windows.Media.Imaging.BitmapSource>   
 <xref:System.Windows.Media.Imaging.BitmapImage>   
 <xref:System.Windows.Controls.Image>   
 <xref:System.Windows.Media.Imaging.BitmapMetadata>   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Win32\-Beispielcodec](http://go.microsoft.com/fwlink/?LinkID=160052)