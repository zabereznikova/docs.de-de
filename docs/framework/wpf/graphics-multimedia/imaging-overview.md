---
title: Übersicht über die Bildverarbeitung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- metadata [WPF], images
- displaying images [WPF]
- Imaging API [WPF]
- image metadata [WPF]
- converting images [WPF]
- encoding image formats [WPF]
- format decoding for images [WPF]
- painting with images [WPF]
- stretching images [WPF]
- images [WPF], about imaging
- format encoding for images [WPF]
- cropping images [WPF]
- decoding image formats [WPF]
- rotating images [WPF]
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
ms.openlocfilehash: 6cb389cd0458d1c9e7af94586c394764f01e4bab
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665185"
---
# <a name="imaging-overview"></a>Übersicht über die Bildverarbeitung
Dieses Thema enthält eine Einführung in die [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)]. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] ermöglicht es Entwicklern, Bilder anzuzeigen, zu transformieren und zu formatieren.  

<a name="_wpfImaging"></a>   
## <a name="wpf-imaging-component"></a>WPF Imaging-Komponente  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] ermöglicht signifikante Verbesserungen der Bildverarbeitungsfunktionen in [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]. Bildverarbeitugnsfunktionen, z.B. die Anzeige einer Bitmap oder die Verwendung eines Bilds in einem allgemeinen Steuerelement, basierten in der Vergangenheit auf [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)]- oder [!INCLUDE[TLA#tla_gdiplus](../../../../includes/tlasharptla-gdiplus-md.md)]-Bibliotheken. Diese [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] stellen Baseline-Bildverarbeitungsfunktionen bereit, verfügen aber nicht über Features wie die Unterstützung für Codec-Erweiterbarkeit und hochwertige Bilder. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] wurde entworfen, um die Nachteile von [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] und [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)] zu beheben und einen neuen Satz von [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] bereitzustellen, die Bilder in Ihren Anwendung anzeigen und verwenden.  
  
 Es gibt zwei Zugriffsmöglichkeiten auf die [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]: eine verwaltete Komponente und eine nicht verwaltete Komponente. Die nicht verwaltete Komponente stellt die folgenden Features bereit.  
  
- Erweiterbarkeitsmodell für neue oder proprietäre Bildformate.  
  
- Verbesserte Leistung und Sicherheit auf nativen Bildformate wie [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)], [!INCLUDE[TLA#tla_jpegorg](../../../../includes/tlasharptla-jpegorg-md.md)], [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)], [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)], [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)], [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] und die Symboldatei (.ICO).  
  
- Beibehaltung von Bilddaten mit hoher Bittiefe von bis zu 8 Bits pro Kanal (32 Bits pro Pixel).  
  
- Nicht destruktive Bildskalieren, Zuschneiden und Drehungen.  
  
- Vereinfachte Farbverwaltung.  
  
- Unterstützung für in der Datei enthaltene proprietäre Metadaten.  
  
- Die verwaltete Komponente nutzt die nicht verwaltete Infrastruktur, um die nahtlose Integration von Bildern mit anderen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Funktionen, z.B. [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], Animation und Grafiken, bereitzustellen. Die verwaltete Komponente profitiert ebenfalls von der Windows Presentation Foundation (WPF) zum Erstellen von Abbildern Codec-Erweiterbarkeitsmodell die automatische Erkennung neuer Bildformate in ermöglicht [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen.  
  
 Der Großteil der verwalteten [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] befinden sich in der <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> -Namespace, obwohl einige wichtigen Typen, z. B. <xref:System.Windows.Media.ImageBrush> und <xref:System.Windows.Media.ImageDrawing> befinden sich in der <xref:System.Windows.Media?displayProperty=nameWithType> Namespace und <xref:System.Windows.Controls.Image> befindet sich in der <xref:System.Windows.Controls?displayProperty=nameWithType> Namespace.  
  
 Dieses Thema enthält zusätzliche Informationen über die verwaltete Komponente. Weitere Informationen über die nicht verwaltete [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] finden Sie in der Dokumentation [Nicht verwaltete WPF Imaging-Komponente](/windows/desktop/wic/-wic-lh).  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>WPF-Bildformate  
 Ein Codec wird zum Decodieren und Codieren eines bestimmten Medienformats verwendet. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] enthält einen Codec für [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)], [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)], [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)], [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)], [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)], [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] und ICON-Bildformate. Anhand jedes einzelnen Codecs können Anwendungen das entsprechende Bildformat decodieren und, mit Ausnahme von ICON, Codieren.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> eine wichtige Klasse wird das Decodieren und Codieren von Bildern verwendet werden. Sie ist der grundlegende Baustein der [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]-Pipeline und stellt einen einzelnen konstanten Satz von Pixeln mit einer bestimmten Größe und Auflösung dar. Ein <xref:System.Windows.Media.Imaging.BitmapSource> kann ein einzelner Rahmen eines Bilds mit mehreren Rahmen, oder sie eine Transformation ausgeführt werden kann eine <xref:System.Windows.Media.Imaging.BitmapSource>. Es ist das übergeordnete Element vieler primären Klassen verwendet, die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] wie z. B. imaging <xref:System.Windows.Media.Imaging.BitmapFrame>.  
  
 Ein <xref:System.Windows.Media.Imaging.BitmapFrame> wird verwendet, um die tatsächlichen Bitmapdaten eines Bildformats zu speichern. Viele Bildformate unterstützen lediglich einen einzelnen <xref:System.Windows.Media.Imaging.BitmapFrame>, obwohl Formate wie [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] und [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] mehrere Rahmen pro Bild unterstützen. Rahmen werden von Decodern als Eingabedaten verwendet und zur Erstellung der Bilddateien an Encoder übergeben.  
  
 Im folgende Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Media.Imaging.BitmapFrame> aus erstellt eine <xref:System.Windows.Media.Imaging.BitmapSource> und anschließend hinzugefügt eine [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] Image.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Decodieren von Bildformaten  
 Beim Decodieren von Bildern wird das Bildformat in Bilddaten übersetzt, die vom System verwendet werden können. Die Bilddaten können dann verwendet werden, um das Bild anzuzeigen und zu verarbeiten oder um es in ein anderes Format zu codieren. Die Decoderauswahl basiert auf dem Bildformat. Der Codec wird automatisch ausgewählt, wenn kein bestimmter Decoder angegeben wird. Die Beispiele im Abschnitt [Anzeigen von Bildern in WPF](#_displayingimages) veranschaulichen die automatische Decodierung. Decoder für benutzerdefinierte Formate, die mithilfe der nicht verwalteten [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]-Schnittstellen entwickelt und im System registriert sind, werden automatisch in die Decoderauswahl eingebunden. Dadurch können benutzerdefinierte Formate, automatisch in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen angezeigt werden.  
  
 Das folgende Beispiel veranschaulicht die Verwendung eines Bitmapdecoders, um ein Bild im [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]-Format zu decodieren.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Codieren von Bildformaten  
 Bei der Bildcodierung werden Bilddaten in ein bestimmten Bildformat übersetzt. Die codierten Bilddaten können dann zum Erstellen neuer Bilddateien verwendet werden. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] stellt Encoder für jedes der oben beschriebenen Bildformate bereit.  
  
 Das folgende Beispiel veranschaulicht die Verwendung eines Encoders, um ein neu erstelltes Bitmapbild zu speichern.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## <a name="displaying-images-in-wpf"></a>Anzeigen von Bildern in WPF  
 Es gibt mehrere Möglichkeiten, ein Bild in einer Windows Presentation Foundation (WPF)-Anwendung anzuzeigen. Bilder können angezeigt werden, mithilfe von ein <xref:System.Windows.Controls.Image> Steuerelement gezeichnet, die in einer Visualisierung mit ein <xref:System.Windows.Media.ImageBrush>, oder mit einer <xref:System.Windows.Media.ImageDrawing>.  
  
### <a name="using-the-image-control"></a>Verwenden des Image-Steuerelements  
 <xref:System.Windows.Controls.Image> ist ein FrameworkElement und der einfachste Weg zum Anzeigen von Bildern in Anwendungen. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], <xref:System.Windows.Controls.Image> kann in zwei Arten Attributsyntax oder Eigenschaftensyntax verwendet werden. Im folgenden Beispiel wird veranschaulicht, wie ein Bild auf eine Breite von 200 Pixeln mit Attributsyntax und Eigenschaftensyntax gerendert wird. Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Viele der Beispiele verwenden eine <xref:System.Windows.Media.Imaging.BitmapImage> Objekt, das eine Bilddatei verweist. <xref:System.Windows.Media.Imaging.BitmapImage> ist ein spezielles <xref:System.Windows.Media.Imaging.BitmapSource> , ist optimiert für [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] laden und ist eine einfache Möglichkeit zum Anzeigen von Bildern als die <xref:System.Windows.Controls.Image.Source%2A> von einer <xref:System.Windows.Controls.Image> Steuerelement.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bild mithilfe von Code auf eine Breite von 200 Pixel gerendert wird.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Imaging.BitmapImage> implementiert die <xref:System.ComponentModel.ISupportInitialize> Schnittstelle, um die Initialisierung für mehrere Eigenschaften zu optimieren. Eigenschaftenänderungen können nur während der Objektinitialisierung erfolgen. Rufen Sie <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> um zu signalisieren, dass die Initialisierung begonnen hat und <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> um zu signalisieren, dass die Initialisierung abgeschlossen wurde. Nach der Initialisierung werden Eigenschaftenänderungen Eigenschaften ignoriert.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Drehen, Konvertieren und Zuschneiden von Bildern  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ermöglicht es Benutzern, Bilder zu transformieren, indem Sie mit den Eigenschaften des <xref:System.Windows.Media.Imaging.BitmapImage> oder durch die Verwendung zusätzlicher <xref:System.Windows.Media.Imaging.BitmapSource> Objekte, z. B. <xref:System.Windows.Media.Imaging.CroppedBitmap> oder <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. Diese Bildtransformationen können Bilder skalieren oder drehen, das Pixelformat eines Bilds ändern oder ein Bild zuschneiden.  
  
 Drehen von Bildern erfolgen über die <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> Eigenschaft <xref:System.Windows.Media.Imaging.BitmapImage>. Drehungen können nur in 90-Grad-Schritten erfolgen. Im folgenden Beispiel wird ein Bild um 90 Grad gedreht.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Konvertieren von Bildern in ein anderes Pixelformat, wie z. B. Graustufe, erfolgt mit <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. In den folgenden Beispielen wird ein Bild in konvertiert <xref:System.Windows.Media.PixelFormats.Gray4%2A>.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Ein Bild zuschneiden, entweder von der <xref:System.Windows.UIElement.Clip%2A> Eigenschaft <xref:System.Windows.Controls.Image> oder <xref:System.Windows.Media.Imaging.CroppedBitmap> kann verwendet werden. In der Regel, wenn Sie nur einen Teil eines Bilds anzeigen möchten <xref:System.Windows.UIElement.Clip%2A> verwendet werden soll. Wenn Sie codieren und speichern ein zugeschnittenes Bild enthält, müssen die <xref:System.Windows.Media.Imaging.CroppedBitmap> verwendet werden soll. Im folgenden Beispiel wird ein Bild zugeschnitten, mithilfe der Clip-Eigenschaft mit einem <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Dehnen von Bildern  
 Die <xref:System.Windows.Controls.Image.Stretch%2A> -Eigenschaft steuert, wie ein Bild auf den Füllbereich seines Containers ausgedehnt wird. Die <xref:System.Windows.Controls.Image.Stretch%2A> Eigenschaft akzeptiert die folgenden Werte, die von definiert die <xref:System.Windows.Media.Stretch> Enumeration:  
  
- <xref:System.Windows.Media.Stretch.None>: Das Bild wird nicht gestreckt, um den Ausgabebereich auszufüllen. Wenn das Bild größer als der Ausgabebereich ist, wird das Bild in den Ausgabebereich gezogen, und alle überstehenden Bereiche werden abgeschnitten.  
  
- <xref:System.Windows.Media.Stretch.Fill>: Das Bild wird skaliert, um die Größe des Ausgabebereichs. Da Höhe und Breite des Bilds unabhängig voneinander skaliert werden, wird das ursprüngliche Seitenverhältnis des Bilds möglicherweise nicht beibehalten. Dies bedeutet, dass das Bild möglicherweise verzerrt wird, um den Ausgabecontainer vollständig auszufüllen.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: Das Bild wird skaliert, sodass er vollständig in den Ausgabebereich passt. Das Seitenverhältnis des Inhalts wird beibehalten.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: Das Bild wird skaliert, sodass er den Ausgabebereich vollständig ausfüllt, und gleichzeitig das ursprüngliche Seitenverhältnis des.  
  
 Im folgenden Beispiel wird jede der verfügbaren <xref:System.Windows.Media.Stretch> Enumerationen zu einer <xref:System.Windows.Controls.Image>.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispiels und die Auswirkung der verschiedene <xref:System.Windows.Controls.Image.Stretch%2A> -Einstellungen zu einem Bild angewendet.  
  
 ![Unterschiedliche TileBrush-Dehneinstellungen](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Unterschiedliche Dehneinstellungen  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Zeichnen mit Bildern  
 Bilder können auch in einer Anwendung angezeigt werden, indem man Sie mit einem <xref:System.Windows.Media.Brush>. Mithilfe von Pinseln können Sie [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Objekte, angefangen von einfachen Objekten, über Objekte in Volltonfarbe bis hin zu Objekten mit komplexen von Mustern und Bildern, zeichnen. Um mit Images zu zeichnen, verwenden eine <xref:System.Windows.Media.ImageBrush>. Ein <xref:System.Windows.Media.ImageBrush> ist eine Art von <xref:System.Windows.Media.TileBrush> , dessen Inhalt als Bitmapbild definiert. Ein <xref:System.Windows.Media.ImageBrush> zeigt ein einzelnes Bild, das angegebenen seine <xref:System.Windows.Media.ImageBrush.ImageSource%2A> Eigenschaft. Sie können steuern, wie das Bild gedehnt, angeordnet und gekachelt wird. Auf diese Weise können Sie Zerrungen verhindern und Muster und andere Effekte herstellen. Die folgende Abbildung zeigt einige Effekte, die mit darstellbar ist ein <xref:System.Windows.Media.ImageBrush>.  
  
 !["ImageBrush" Ausgabe Beispiele](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "Wcpsdk_mmgraphics_imagebrushexamples")  
Bildpinsel können Formen, Steuerelemente, Text usw. füllen.  
  
 Im folgende Beispiel wird veranschaulicht, wie den Hintergrund einer Schaltfläche mit einem Bild gezeichnet ein <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.ImageBrush> und Zeichnen von Bildern finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>Bildmetadaten  
 Einige Bilddateien enthalten Metadaten, die den Inhalt oder die Eigenschaften der Datei beschreiben. Die meisten Digitalkameras erstellen z.B. Bilder, die Metadaten zum Fabrikat und Modell der Kamera enthalten, mit der das Bild aufgenommen wurde. Jedes Bildformat behandelt Metadaten unterschiedlich, aber [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] bietet eine einheitliche Möglichkeit zum Speichern und Abrufen von Metadaten für jedes unterstützte Bildformat.  
  
 Zugriff auf Metadaten erfolgt über die <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> Eigenschaft eine <xref:System.Windows.Media.Imaging.BitmapSource> Objekt. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> Gibt eine <xref:System.Windows.Media.Imaging.BitmapMetadata> -Objekt, das alle im Bild enthaltene Metadaten enthält. Diese Daten können in einem Metadatenschema oder einer Kombination aus unterschiedlichen Schemas vorliegen. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] unterstützt die folgenden Schemas für Bildmetadaten: [!INCLUDE[TLA#tla_exif](../../../../includes/tlasharptla-exif-md.md)], tEXt (PNG-Textdaten), [!INCLUDE[TLA#tla_ifd](../../../../includes/tlasharptla-ifd-md.md)], [!INCLUDE[TLA#tla_iptc](../../../../includes/tlasharptla-iptc-md.md)] und [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)].  
  
 Um den Prozess des Lesens von Metadaten zu vereinfachen <xref:System.Windows.Media.Imaging.BitmapMetadata> bietet mehrere benannte Eigenschaften, die z. B. einfach zugegriffen werden können <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>, und <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>. Viele dieser benannten Eigenschaften können auch verwendet werden, um Metadaten zu schreiben. Zusätzliche Unterstützung für das Lesen von Metadaten wird vom Metadaten-Abfragereader bereitgestellt. Die <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> Methode wird verwendet, um eine Metadatenabfrage-Readers zu abrufen, indem eine Zeichenfolgenabfrage, z. B. *"/ app1/Exif /"*. Im folgenden Beispiel <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> dient zum Abrufen des Texts, der in gespeicherten der *"/ Text/Description"* Speicherort.  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Zum Schreiben von Metadaten wird ein Metadaten-Abfragewriter verwendet. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> Ruft den Abfragewriter ab und legt den gewünschten Wert fest. Im folgenden Beispiel <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> wird verwendet, um das Schreiben von Text in gespeicherten der *"/ Text/Description"* Speicherort.  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>Code-Erweiterbarkeit  
 Ein Hauptmerkmal des [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] ist das Erweiterbarkeitsmodell für neue Bildcodecs. Diese nicht verwalteten Schnittstellen können Codec-Entwickler Codecs in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integrieren, damit neue Bildformate automatisch von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen verwendet werden können.  
  
 Ein Beispiel für die Erweiterbarkeits-[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] finden Sie unter [Win32 Sample Codec](https://go.microsoft.com/fwlink/?LinkID=160052). In diesem Beispiel wird veranschaulicht, wie ein Decoder und Encoder für ein benutzerdefiniertes Bildformat erstellt werden.  
  
> [!NOTE]
>  Der Codec muss digital signiert werden, damit das System ihn erkennt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Win32 Sample Codec](https://go.microsoft.com/fwlink/?LinkID=160052)
