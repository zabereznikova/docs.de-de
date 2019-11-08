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
ms.openlocfilehash: b60f2871062a12d3bee91a9c6d9883222b3034f4
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733565"
---
# <a name="imaging-overview"></a>Übersicht über die Bildverarbeitung
Dieses Thema enthält eine Einführung in die Microsoft Windows Presentation Foundation Imaging-Komponente. WPF-Imaging ermöglicht Entwicklern das anzeigen, Transformieren und Formatieren von Bildern.  

## <a name="wpf-imaging-component"></a>WPF Imaging-Komponente  
 WPF-Imaging bietet deutliche Verbesserungen bei den Abbild Funktionen von Microsoft Windows. Abbild Erstellungs Funktionen, wie z. b. das Anzeigen einer Bitmap oder die Verwendung eines Bilds auf einem allgemeinen Steuerelement, waren zuvor auf die Microsoft Windows Graphics Device Interface-oder Microsoft Windows-GDI+-Bibliotheken angewiesen. Diese API stellt grundlegende Abbild Erstellungs Funktionen bereit, verfügt jedoch nicht über Features wie die Unterstützung von Codec-Erweiterbarkeit und qualitativ hochwertige Bildunterstützung. WPF Imaging ist so konzipiert, dass die Mängel von GDI und GDI+ umgangen werden und eine neue API zum Anzeigen und Verwenden von Bildern in Ihren Anwendungen bereitgestellt wird.  
  
 Es gibt zwei Möglichkeiten für den Zugriff auf die WPF Imaging-API, eine verwaltete Komponente und eine nicht verwaltete Komponente. Die nicht verwaltete Komponente stellt die folgenden Features bereit.  
  
- Erweiterbarkeitsmodell für neue oder proprietäre Bildformate.  
  
- Verbesserte Leistung und Sicherheit bei nativen Abbild Formaten, einschließlich Bitmap (BMP), Joint Photographics Experts Group (JPEG), Portable Network Graphics (PNG), Tagged Image File Format (TIFF), Microsoft Windows Media Photo, Graphics Interchange Format (GIF), und Symbol (. ico).  
  
- Beibehaltung von Bilddaten mit hoher Bittiefe von bis zu 8 Bits pro Kanal (32 Bits pro Pixel).  
  
- Nicht destruktive Bildskalieren, Zuschneiden und Drehungen.  
  
- Vereinfachte Farbverwaltung.  
  
- Unterstützung für in der Datei enthaltene proprietäre Metadaten.  
  
- Die verwaltete Komponente nutzt die nicht verwaltete Infrastruktur, um die nahtlose Integration von Bildern mit anderen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Funktionen, z.B. [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], Animation und Grafiken, bereitzustellen. Die verwaltete Komponente profitiert auch vom Windows Presentation Foundation (WPF) Imaging Codec Erweiterbarkeit Model (WPF), das die automatische Erkennung neuer Bildformate in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen ermöglicht.  
  
 Der Großteil der verwalteten WPF-Imaging-API befindet sich im <xref:System.Windows.Media.Imaging?displayProperty=nameWithType>-Namespace, obwohl mehrere wichtige Typen, z. b. <xref:System.Windows.Media.ImageBrush> und <xref:System.Windows.Media.ImageDrawing> sich im <xref:System.Windows.Media?displayProperty=nameWithType>-Namespace befinden und <xref:System.Windows.Controls.Image> sich im <xref:System.Windows.Controls?displayProperty=nameWithType>-Namespace befinden.  
  
 Dieses Thema enthält zusätzliche Informationen über die verwaltete Komponente. Weitere Informationen zur nicht verwalteten API finden Sie in der Dokumentation zur [nicht verwalteten WPF-Imaging-Komponente](/windows/desktop/wic/-wic-lh) .  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>WPF-Bildformate  

 Ein Codec wird zum Decodieren und Codieren eines bestimmten Medienformats verwendet. WPF Imaging umfasst einen Codec für BMP-, JPEG-, PNG-, TIFF-, Windows Media-Foto-, GIF-und Symbolbild Formate. Anhand jedes einzelnen Codecs können Anwendungen das entsprechende Bildformat decodieren und, mit Ausnahme von ICON, Codieren.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> ist eine wichtige Klasse, die beim Decodieren und Codieren von Bildern verwendet wird. Dabei handelt es sich um den grundlegenden Baustein der WPF-Abbild Pipeline, der einen einzelnen konstanten Satz von Pixeln mit einer bestimmten Größe und Auflösung darstellt. Bei einem <xref:System.Windows.Media.Imaging.BitmapSource> kann es sich um einen einzelnen Frame eines Bilds mit mehreren Frames handeln, oder es kann sich um das Ergebnis einer Transformation handeln, die auf einem <xref:System.Windows.Media.Imaging.BitmapSource>ausgeführt wird. Es ist das übergeordnete Element von vielen der primären Klassen, die in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Abbild Erstellung wie <xref:System.Windows.Media.Imaging.BitmapFrame>verwendet werden.  
  
 Ein <xref:System.Windows.Media.Imaging.BitmapFrame> wird zum Speichern der eigentlichen Bitmapdaten eines Bildformats verwendet. Viele Bildformate unterstützen nur ein einzelnes <xref:System.Windows.Media.Imaging.BitmapFrame>, obwohl Formate wie GIF und TIFF mehrere Frames pro Bild unterstützen. Rahmen werden von Decodern als Eingabedaten verwendet und zur Erstellung der Bilddateien an Encoder übergeben.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Media.Imaging.BitmapFrame> aus einem <xref:System.Windows.Media.Imaging.BitmapSource> erstellt und dann einem TIFF-Bild hinzugefügt wird.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Decodieren von Bildformaten  
 Beim Decodieren von Bildern wird das Bildformat in Bilddaten übersetzt, die vom System verwendet werden können. Die Bilddaten können dann verwendet werden, um das Bild anzuzeigen und zu verarbeiten oder um es in ein anderes Format zu codieren. Die Decoderauswahl basiert auf dem Bildformat. Der Codec wird automatisch ausgewählt, wenn kein bestimmter Decoder angegeben wird. Die Beispiele im Abschnitt [Anzeigen von Bildern in WPF](#_displayingimages) veranschaulichen die automatische Decodierung. Benutzerdefinierte Formatierungs Schnittstellen, die mit den nicht verwalteten WPF-Abbild Erstellungs Schnittstellen entwickelt und beim System registriert sind, nehmen automatisch an der Decoderauswahl Dadurch können benutzerdefinierte Formate, automatisch in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen angezeigt werden.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bitmap-Decoder zum Decodieren eines BMP-Format Bilds verwendet wird.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Codieren von Bildformaten  
 Bei der Bildcodierung werden Bilddaten in ein bestimmten Bildformat übersetzt. Die codierten Bilddaten können dann zum Erstellen neuer Bilddateien verwendet werden. Die WPF-Abbild Erstellung stellt Encoder für jedes der oben beschriebenen Bildformate bereit.  
  
 Das folgende Beispiel veranschaulicht die Verwendung eines Encoders, um ein neu erstelltes Bitmapbild zu speichern.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## <a name="displaying-images-in-wpf"></a>Anzeigen von Bildern in WPF  
 Es gibt mehrere Möglichkeiten, ein Bild in einer Windows Presentation Foundation (WPF)-Anwendung anzuzeigen. Bilder können mithilfe eines <xref:System.Windows.Controls.Image>-Steuer Elements angezeigt, mithilfe einer <xref:System.Windows.Media.ImageBrush>auf einem visuellen Element gezeichnet oder mithilfe eines <xref:System.Windows.Media.ImageDrawing>gezeichnet werden.  
  
### <a name="using-the-image-control"></a>Verwenden des Image-Steuerelements  
 <xref:System.Windows.Controls.Image> ist ein Framework-Element und die primäre Methode, Bilder in Anwendungen anzuzeigen. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können <xref:System.Windows.Controls.Image> auf zwei Arten verwendet werden: Attribut Syntax oder Eigenschaften Syntax. Im folgenden Beispiel wird veranschaulicht, wie ein Bild auf eine Breite von 200 Pixeln mit Attributsyntax und Eigenschaftensyntax gerendert wird. Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 In vielen der Beispiele wird ein <xref:System.Windows.Media.Imaging.BitmapImage> Objekt verwendet, um auf eine Bilddatei zu verweisen. <xref:System.Windows.Media.Imaging.BitmapImage> ist eine spezialisierte <xref:System.Windows.Media.Imaging.BitmapSource>, die für das Laden von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] optimiert ist und eine einfache Möglichkeit zum Anzeigen von Bildern als <xref:System.Windows.Controls.Image.Source%2A> eines <xref:System.Windows.Controls.Image> Steuer Elements ist.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bild mithilfe von Code auf eine Breite von 200 Pixel gerendert wird.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage> implementiert die <xref:System.ComponentModel.ISupportInitialize> Schnittstelle, um die Initialisierung für mehrere Eigenschaften zu optimieren. Eigenschaftenänderungen können nur während der Objektinitialisierung erfolgen. <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A>, um zu signalisieren, dass die Initialisierung begonnen hat, und <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A>, um zu signalisieren, dass die Initialisierung abgeschlossen wurde. Nach der Initialisierung werden Eigenschaftenänderungen Eigenschaften ignoriert.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Drehen, Konvertieren und Zuschneiden von Bildern  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ermöglicht es Benutzern, Bilder mithilfe der Eigenschaften von <xref:System.Windows.Media.Imaging.BitmapImage> oder mithilfe zusätzlicher <xref:System.Windows.Media.Imaging.BitmapSource> Objekte wie <xref:System.Windows.Media.Imaging.CroppedBitmap> oder <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>umzuwandeln. Diese Bildtransformationen können Bilder skalieren oder drehen, das Pixelformat eines Bilds ändern oder ein Bild zuschneiden.  
  
 Bild Drehungen werden mithilfe der <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A>-Eigenschaft von <xref:System.Windows.Media.Imaging.BitmapImage>ausgeführt. Drehungen können nur in 90-Grad-Schritten erfolgen. Im folgenden Beispiel wird ein Bild um 90 Grad gedreht.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Die Umstellung eines Bilds in ein anderes Pixel Format, wie z. b. Graustufen, erfolgt mithilfe <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. In den folgenden Beispielen wird ein Bild in <xref:System.Windows.Media.PixelFormats.Gray4%2A>konvertiert.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Zum Zuschneiden eines Bilds kann entweder die <xref:System.Windows.UIElement.Clip%2A>-Eigenschaft von <xref:System.Windows.Controls.Image> oder <xref:System.Windows.Media.Imaging.CroppedBitmap> verwendet werden. Wenn Sie nur einen Teil eines Bilds anzeigen möchten, sollten Sie in der Regel <xref:System.Windows.UIElement.Clip%2A> verwenden. Wenn Sie ein abgeschnittenes Bild codieren und speichern müssen, sollten Sie das <xref:System.Windows.Media.Imaging.CroppedBitmap> verwenden. Im folgenden Beispiel wird ein Bild mithilfe der Clip-Eigenschaft mithilfe eines <xref:System.Windows.Media.EllipseGeometry>zugeschnitten.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Dehnen von Bildern  
 Die <xref:System.Windows.Controls.Image.Stretch%2A>-Eigenschaft steuert, wie ein Bild gestreckt wird, um den Container auszufüllen. Die <xref:System.Windows.Controls.Image.Stretch%2A>-Eigenschaft akzeptiert die folgenden Werte, die durch die <xref:System.Windows.Media.Stretch>-Enumeration definiert werden:  
  
- <xref:System.Windows.Media.Stretch.None>: das Bild wird nicht gestreckt, um den Ausgabebereich auszufüllen. Wenn das Bild größer als der Ausgabebereich ist, wird das Bild in den Ausgabebereich gezogen, und alle überstehenden Bereiche werden abgeschnitten.  
  
- <xref:System.Windows.Media.Stretch.Fill>: das Bild wird so skaliert, dass es in den Ausgabebereich passt. Da Höhe und Breite des Bilds unabhängig voneinander skaliert werden, wird das ursprüngliche Seitenverhältnis des Bilds möglicherweise nicht beibehalten. Dies bedeutet, dass das Bild möglicherweise verzerrt wird, um den Ausgabecontainer vollständig auszufüllen.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: das Bild wird so skaliert, dass es vollständig in den Ausgabebereich passt. Das Seitenverhältnis des Inhalts wird beibehalten.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: das Bild wird so skaliert, dass es den Ausgabebereich vollständig ausfüllt, während das ursprüngliche Seitenverhältnis des Bilds beibehalten wird.  
  
 Im folgenden Beispiel wird jede der verfügbaren <xref:System.Windows.Media.Stretch> Enumerationen auf einen <xref:System.Windows.Controls.Image>angewendet.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispiels und zeigt, welche Auswirkungen die verschiedenen <xref:System.Windows.Controls.Image.Stretch%2A> Einstellungen haben, wenn Sie auf ein Bild angewendet werden.  
  
 ![Unterschiedliche TileBrush-Dehneinstellungen](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Unterschiedliche Dehneinstellungen  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Zeichnen mit Bildern  
 Bilder können auch in einer Anwendung angezeigt werden, indem Sie mit einem <xref:System.Windows.Media.Brush>zeichnen. Mithilfe von Pinseln können Sie [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Objekte, angefangen von einfachen Objekten, über Objekte in Volltonfarbe bis hin zu Objekten mit komplexen von Mustern und Bildern, zeichnen. Verwenden Sie zum Zeichnen mit Bildern einen <xref:System.Windows.Media.ImageBrush>. Eine <xref:System.Windows.Media.ImageBrush> ist ein <xref:System.Windows.Media.TileBrush>, der ihren Inhalt als Bitmapbild definiert. Ein <xref:System.Windows.Media.ImageBrush> zeigt ein einzelnes Bild an, das von seiner <xref:System.Windows.Media.ImageBrush.ImageSource%2A>-Eigenschaft angegeben wird. Sie können steuern, wie das Bild gedehnt, angeordnet und gekachelt wird. Auf diese Weise können Sie Zerrungen verhindern und Muster und andere Effekte herstellen. Die folgende Abbildung zeigt einige Effekte, die mit einem <xref:System.Windows.Media.ImageBrush>erzielt werden können.  
  
 ![ImageBrush-Ausgabebeispiele](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Bildpinsel können Formen, Steuerelemente, Text usw. füllen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie der Hintergrund einer Schaltfläche mit einem Bild mithilfe eines-<xref:System.Windows.Media.ImageBrush>gezeichnet wird.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Weitere Informationen zum <xref:System.Windows.Media.ImageBrush> und zum Zeichnen von Bildern finden Sie [unterzeichnen mit Bildern, Zeichnungen und visuellen](painting-with-images-drawings-and-visuals.md)Elementen.  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>Bildmetadaten  
 Einige Bilddateien enthalten Metadaten, die den Inhalt oder die Eigenschaften der Datei beschreiben. Die meisten Digitalkameras erstellen z.B. Bilder, die Metadaten zum Fabrikat und Modell der Kamera enthalten, mit der das Bild aufgenommen wurde. Jedes Bildformat verarbeitet Metadaten anders, aber WPF-Imaging bietet eine einheitliche Möglichkeit zum Speichern und Abrufen von Metadaten für jedes unterstützte Bildformat.  
  
 Der Zugriff auf Metadaten wird durch die <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>-Eigenschaft eines <xref:System.Windows.Media.Imaging.BitmapSource> Objekts bereitgestellt. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> gibt ein <xref:System.Windows.Media.Imaging.BitmapMetadata> Objekt zurück, das alle im Bild enthaltenen Metadaten enthält. Diese Daten können in einem Metadatenschema oder einer Kombination aus unterschiedlichen Schemas vorliegen. Die WPF-Abbild Erstellung unterstützt die folgenden Bild Metadatenschemas: austauschbare Bilddatei (EXIF), Text (PNG-Textdaten), das Image Dateiverzeichnis (IFD), International Press Telekommunikations Council (IPTC) und erweiterbare metadatenplattform (XMP).  
  
 Um den Prozess des Lesens von Metadaten zu vereinfachen, stellt <xref:System.Windows.Media.Imaging.BitmapMetadata> mehrere benannte Eigenschaften bereit, auf die leicht zugegriffen werden kann, z. b. <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>und <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>. Viele dieser benannten Eigenschaften können auch verwendet werden, um Metadaten zu schreiben. Zusätzliche Unterstützung für das Lesen von Metadaten wird vom Metadaten-Abfragereader bereitgestellt. Die <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A>-Methode wird zum Abrufen eines Metadatenabfrage-Readers verwendet, indem eine Zeichen folgen Abfrage wie *"/app1/exif/"* bereitgestellt wird. Im folgenden Beispiel wird <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> verwendet, um den am Speicherort *"/Text/Description"* gespeicherten Text abzurufen.  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Zum Schreiben von Metadaten wird ein Metadaten-Abfragewriter verwendet. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> Ruft den Abfragewriter ab und legt den gewünschten Wert fest. Im folgenden Beispiel wird <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> verwendet, um den am Speicherort *"/Text/Description"* gespeicherten Text zu schreiben.  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>Code-Erweiterbarkeit  
 Ein Kern Feature von WPF Imaging ist das Erweiterbarkeits Modell für neue Bild Codecs. Diese nicht verwalteten Schnittstellen können Codec-Entwickler Codecs in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integrieren, damit neue Bildformate automatisch von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen verwendet werden können.  
  
 Ein Beispiel für die Erweiterbarkeits-API finden Sie im [Win32-Beispielcodec](https://go.microsoft.com/fwlink/?LinkID=160052). In diesem Beispiel wird veranschaulicht, wie ein Decoder und Encoder für ein benutzerdefiniertes Bildformat erstellt werden.  
  
> [!NOTE]
> Der Codec muss digital signiert werden, damit das System ihn erkennt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Win32 Sample Codec](https://go.microsoft.com/fwlink/?LinkID=160052)
