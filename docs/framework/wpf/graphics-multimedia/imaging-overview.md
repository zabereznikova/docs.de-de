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
ms.openlocfilehash: 3365c35e3e7b7fe5c0be48a65d7a14da0882c90e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186697"
---
# <a name="imaging-overview"></a>Übersicht über die Bildverarbeitung
Dieses Thema enthält eine Einführung in die Microsoft Windows Presentation Foundation Imaging-Komponente. WPF Imaging ermöglicht Entwicklern das Anzeigen, Transformieren und Formatieren von Bildern.  

## <a name="wpf-imaging-component"></a>WPF Imaging-Komponente  
 WPF Imaging bietet erhebliche Verbesserungen bei den Imaging-Funktionen in Microsoft Windows. Imaging-Funktionen, z. B. das Anzeigen einer Bitmap oder die Verwendung eines Bildes in einem gemeinsamen Steuerelement, waren zuvor auf die GDI-Bibliotheken (Microsoft Windows Graphics Device Interface) oder Microsoft Windows GDI+-Bibliotheken angewiesen. Diese API bietet grundlegende Imaging-Funktionalität, aber es fehlen Funktionen wie Unterstützung für Codec-Erweiterbarkeit und Unterstützung für Bildunterstützung mit hoher Genauigkeit. WPF Imaging wurde entwickelt, um die Mängel von GDI und GDI+ zu beheben und einen neuen SATZ von API zur Anzeige und Verwendung von Bildern in Ihren Anwendungen bereitzustellen.  
  
 Es gibt zwei Möglichkeiten, auf die WPF Imaging-API zuzugreifen, eine verwaltete Komponente und eine nicht verwaltete Komponente. Die nicht verwaltete Komponente stellt die folgenden Features bereit.  
  
- Erweiterbarkeitsmodell für neue oder proprietäre Bildformate.  
  
- Verbesserte Leistung und Sicherheit bei nativen Bildformaten, einschließlich Bitmap (BMP), Joint Photographics Experts Group (JPEG), Portable Network Graphics (PNG), Tagged Image File Format (TIFF), Microsoft Windows Media Photo, Graphics Interchange Format (GIF), und Symbol (.ico).  
  
- Beibehaltung von Bilddaten mit hoher Bittiefe von bis zu 8 Bits pro Kanal (32 Bits pro Pixel).  
  
- Nicht destruktive Bildskalieren, Zuschneiden und Drehungen.  
  
- Vereinfachte Farbverwaltung.  
  
- Unterstützung für in der Datei enthaltene proprietäre Metadaten.  
  
- Die verwaltete Komponente nutzt die nicht verwaltete Infrastruktur, um eine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]nahtlose Integration von Bildern mit anderen WPF-Features wie , Animationen und Grafiken zu ermöglichen. Die verwaltete Komponente profitiert auch vom Windows Presentation Foundation (WPF)-Imaging-Codec-Erweiterbarkeitsmodell, das die automatische Erkennung neuer Bildformate in WPF-Anwendungen ermöglicht.  
  
 Der Großteil der verwalteten WPF <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> Imaging-API befindet sich im <xref:System.Windows.Media.ImageBrush> Namespace, obwohl sich mehrere wichtige Typen, z. B. <xref:System.Windows.Media.ImageDrawing> im <xref:System.Windows.Media?displayProperty=nameWithType> Namespace, befinden und <xref:System.Windows.Controls.Image> sich im <xref:System.Windows.Controls?displayProperty=nameWithType> Namespace befinden.  
  
 Dieses Thema enthält zusätzliche Informationen über die verwaltete Komponente. Weitere Informationen zur nicht verwalteten API finden Sie in der Dokumentation zu [nicht verwalteten WPF Imaging Component.](/windows/desktop/wic/-wic-lh)  
  
<a name="_imageformats"></a>
## <a name="wpf-image-formats"></a>WPF-Bildformate  

 Ein Codec wird zum Decodieren und Codieren eines bestimmten Medienformats verwendet. WPF Imaging enthält einen Codec für BMP-, JPEG-, PNG-, TIFF-, Windows Media Photo-, GIF- und ICON-Bildformate. Anhand jedes einzelnen Codecs können Anwendungen das entsprechende Bildformat decodieren und, mit Ausnahme von ICON, Codieren.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource>ist eine wichtige Klasse, die bei der Dekodierung und Codierung von Bildern verwendet wird. Es ist der grundlegende Baustein der WPF Imaging-Pipeline und stellt einen einzelnen, konstanten Satz von Pixeln mit einer bestimmten Größe und Auflösung dar. A <xref:System.Windows.Media.Imaging.BitmapSource> kann ein einzelner Frame eines Mehrfachbilds sein, oder es kann <xref:System.Windows.Media.Imaging.BitmapSource>das Ergebnis einer Transformation sein, die auf einem durchgeführt wird. Es ist das übergeordnete Element vieler primärer Klassen, <xref:System.Windows.Media.Imaging.BitmapFrame>die in der WPF-Bildgebung verwendet werden, z. B. .  
  
 A <xref:System.Windows.Media.Imaging.BitmapFrame> wird verwendet, um die tatsächlichen Bitmapdaten eines Bildformats zu speichern. Viele Bildformate unterstützen <xref:System.Windows.Media.Imaging.BitmapFrame>nur eine einzelne , obwohl Formate wie GIF und TIFF mehrere Frames pro Bild unterstützen. Rahmen werden von Decodern als Eingabedaten verwendet und zur Erstellung der Bilddateien an Encoder übergeben.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Imaging.BitmapFrame> wird veranschaulicht, <xref:System.Windows.Media.Imaging.BitmapSource> wie ein aus einem erstellt und dann einem TIFF-Bild hinzugefügt wird.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Decodieren von Bildformaten  
 Beim Decodieren von Bildern wird das Bildformat in Bilddaten übersetzt, die vom System verwendet werden können. Die Bilddaten können dann verwendet werden, um das Bild anzuzeigen und zu verarbeiten oder um es in ein anderes Format zu codieren. Die Decoderauswahl basiert auf dem Bildformat. Der Codec wird automatisch ausgewählt, wenn kein bestimmter Decoder angegeben wird. Die Beispiele im Abschnitt [Anzeigen von Bildern in WPF](#_displayingimages) veranschaulichen die automatische Decodierung. Benutzerdefinierte Formatdecoder, die mit den nicht verwalteten WPF Imaging-Schnittstellen entwickelt und beim System registriert wurden, nehmen automatisch an der Decoderauswahl teil. Dadurch können benutzerdefinierte Formate automatisch in WPF-Anwendungen angezeigt werden.  
  
 Im folgenden Beispiel wird die Verwendung eines Bitmapdecoders zum Decodieren eines BMP-Formatbilds veranschaulicht.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Codieren von Bildformaten  
 Bei der Bildcodierung werden Bilddaten in ein bestimmten Bildformat übersetzt. Die codierten Bilddaten können dann zum Erstellen neuer Bilddateien verwendet werden. WPF Imaging stellt Encoder für jedes der oben beschriebenen Bildformate bereit.  
  
 Das folgende Beispiel veranschaulicht die Verwendung eines Encoders, um ein neu erstelltes Bitmapbild zu speichern.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>
## <a name="displaying-images-in-wpf"></a>Anzeigen von Bildern in WPF  
 Es gibt mehrere Möglichkeiten, ein Bild in einer Windows Presentation Foundation (WPF)-Anwendung anzuzeigen. Bilder können mit <xref:System.Windows.Controls.Image> einem Steuerelement angezeigt, auf <xref:System.Windows.Media.ImageBrush>einem visuellen <xref:System.Windows.Media.ImageDrawing>mit einem gezeichnet oder mit einem gezeichnet werden.  
  
### <a name="using-the-image-control"></a>Verwenden des Image-Steuerelements  
 <xref:System.Windows.Controls.Image>ist ein Framework-Element und die primäre Möglichkeit, Bilder in Anwendungen anzuzeigen. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.Image> kann auf zwei Arten verwendet werden; Attributsyntax oder Eigenschaftssyntax. Im folgenden Beispiel wird veranschaulicht, wie ein Bild auf eine Breite von 200 Pixeln mit Attributsyntax und Eigenschaftensyntax gerendert wird. Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Viele Beispiele verwenden <xref:System.Windows.Media.Imaging.BitmapImage> ein Objekt, um auf eine Bilddatei zu verweisen. <xref:System.Windows.Media.Imaging.BitmapImage>ist ein <xref:System.Windows.Media.Imaging.BitmapSource> Spezialist, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] der für das Laden optimiert ist <xref:System.Windows.Controls.Image.Source%2A> und <xref:System.Windows.Controls.Image> eine einfache Möglichkeit ist, Bilder als die eines Steuerelements anzuzeigen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bild mithilfe von Code auf eine Breite von 200 Pixel gerendert wird.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage>implementiert die <xref:System.ComponentModel.ISupportInitialize> Schnittstelle, um die Initialisierung für mehrere Eigenschaften zu optimieren. Eigenschaftenänderungen können nur während der Objektinitialisierung erfolgen. Aufruf, <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> um zu signalisieren, dass die Initialisierung begonnen hat, und <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> um zu signalisieren, dass die Initialisierung abgeschlossen ist. Nach der Initialisierung werden Eigenschaftenänderungen Eigenschaften ignoriert.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Drehen, Konvertieren und Zuschneiden von Bildern  
 WPF ermöglicht Benutzern das Transformieren <xref:System.Windows.Media.Imaging.BitmapImage> von Bildern <xref:System.Windows.Media.Imaging.BitmapSource> mithilfe <xref:System.Windows.Media.Imaging.CroppedBitmap> von <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>Eigenschaften oder mithilfe zusätzlicher Objekte wie oder . Diese Bildtransformationen können Bilder skalieren oder drehen, das Pixelformat eines Bilds ändern oder ein Bild zuschneiden.  
  
 Bildrotationen werden mit <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> der <xref:System.Windows.Media.Imaging.BitmapImage>Eigenschaft von durchgeführt. Drehungen können nur in 90-Grad-Schritten erfolgen. Im folgenden Beispiel wird ein Bild um 90 Grad gedreht.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Das Konvertieren eines Bildes in ein anderes Pixelformat, z. B. Graustufen, erfolgt mit <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. In den folgenden Beispielen wird <xref:System.Windows.Media.PixelFormats.Gray4%2A>ein Bild in konvertiert.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Um ein Bild zuzuschneiden, kann entweder die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft von <xref:System.Windows.Controls.Image> oder <xref:System.Windows.Media.Imaging.CroppedBitmap> verwendet werden. Wenn Sie nur einen Teil eines Bildes <xref:System.Windows.UIElement.Clip%2A> anzeigen möchten, sollten Sie in der Regel verwendet werden. Wenn Sie ein zugeschnittenes Bild codieren <xref:System.Windows.Media.Imaging.CroppedBitmap> und speichern müssen, sollte das verwendet werden. Im folgenden Beispiel wird ein Bild mit der <xref:System.Windows.Media.EllipseGeometry>Clip-Eigenschaft mit einer zugeschnitten.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Dehnen von Bildern  
 Die <xref:System.Windows.Controls.Image.Stretch%2A> Eigenschaft steuert, wie ein Bild gestreckt wird, um den Container zu füllen. Die <xref:System.Windows.Controls.Image.Stretch%2A> Eigenschaft akzeptiert die folgenden <xref:System.Windows.Media.Stretch> Werte, die durch die Enumeration definiert sind:  
  
- <xref:System.Windows.Media.Stretch.None>: Das Bild wird nicht gestreckt, um den Ausgabebereich zu füllen. Wenn das Bild größer als der Ausgabebereich ist, wird das Bild in den Ausgabebereich gezogen, und alle überstehenden Bereiche werden abgeschnitten.  
  
- <xref:System.Windows.Media.Stretch.Fill>: Das Bild wird so skaliert, dass es an den Ausgabebereich passt. Da Höhe und Breite des Bilds unabhängig voneinander skaliert werden, wird das ursprüngliche Seitenverhältnis des Bilds möglicherweise nicht beibehalten. Dies bedeutet, dass das Bild möglicherweise verzerrt wird, um den Ausgabecontainer vollständig auszufüllen.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: Das Bild wird so skaliert, dass es vollständig in den Ausgabebereich passt. Das Seitenverhältnis des Inhalts wird beibehalten.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: Das Bild wird so skaliert, dass es den Ausgabebereich vollständig ausfüllt, während das ursprüngliche Seitenverhältnis des Bildes beibehalten wird.  
  
 Im folgenden Beispiel werden <xref:System.Windows.Media.Stretch> alle verfügbaren Enumerationen auf eine <xref:System.Windows.Controls.Image>angewendet.  
  
 Die folgende Abbildung zeigt die Ausgabe aus dem <xref:System.Windows.Controls.Image.Stretch%2A> Beispiel und zeigt die Auswirkungen der verschiedenen Einstellungen, wenn sie auf ein Bild angewendet werden.  
  
 ![Unterschiedliche TileBrush-Dehneinstellungen](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Unterschiedliche Dehneinstellungen  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Zeichnen mit Bildern  
 Bilder können auch in einer Anwendung <xref:System.Windows.Media.Brush>angezeigt werden, indem sie mit einem malen. Mithilfe von Pinseln können Sie [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Objekte, angefangen von einfachen Objekten, über Objekte in Volltonfarbe bis hin zu Objekten mit komplexen von Mustern und Bildern, zeichnen. Um mit Bildern zu <xref:System.Windows.Media.ImageBrush>malen, verwenden Sie eine . Ein <xref:System.Windows.Media.ImageBrush> Typ von, der <xref:System.Windows.Media.TileBrush> seinen Inhalt als Bitmapbild definiert. Ein <xref:System.Windows.Media.ImageBrush> zeigt ein einzelnes Bild <xref:System.Windows.Media.ImageBrush.ImageSource%2A> an, das durch seine Eigenschaft angegeben wird. Sie können steuern, wie das Bild gedehnt, angeordnet und gekachelt wird. Auf diese Weise können Sie Zerrungen verhindern und Muster und andere Effekte herstellen. Die folgende Abbildung zeigt einige Effekte, <xref:System.Windows.Media.ImageBrush>die mit einem erreicht werden können.  
  
 ![ImageBrush-Ausgabebeispiele](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Bildpinsel können Formen, Steuerelemente, Text usw. füllen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie der Hintergrund <xref:System.Windows.Media.ImageBrush>einer Schaltfläche mit einem Bild mit einer gezeichnet wird.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Weitere Informationen <xref:System.Windows.Media.ImageBrush> zu Bildern und Demlackieren finden Sie [unter Malen mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>
## <a name="image-metadata"></a>Bildmetadaten  
 Einige Bilddateien enthalten Metadaten, die den Inhalt oder die Eigenschaften der Datei beschreiben. Die meisten Digitalkameras erstellen z.B. Bilder, die Metadaten zum Fabrikat und Modell der Kamera enthalten, mit der das Bild aufgenommen wurde. Jedes Bildformat verarbeitet Metadaten unterschiedlich, aber WPF Imaging bietet eine einheitliche Möglichkeit zum Speichern und Abrufen von Metadaten für jedes unterstützte Bildformat.  
  
 Der Zugriff auf Metadaten <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> wird <xref:System.Windows.Media.Imaging.BitmapSource> über die Eigenschaft eines Objekts bereitgestellt. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>gibt <xref:System.Windows.Media.Imaging.BitmapMetadata> ein Objekt zurück, das alle im Bild enthaltenen Metadaten enthält. Diese Daten können in einem Metadatenschema oder einer Kombination aus unterschiedlichen Schemas vorliegen. WPF Imaging unterstützt die folgenden Bildmetadatenschemata: Exchangeable Image File (Exif), tEXt (PNG Textual Data), Image File Directory (IFD), International Press Telecommunications Council (IPTC) und Extensible Metadata Platform (XMP).  
  
 Um das Lesen von Metadaten <xref:System.Windows.Media.Imaging.BitmapMetadata> zu vereinfachen, werden mehrere benannte <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A> <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>Eigenschaften <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>angezeigt, auf die leicht zugegriffen werden kann, z. B. , und . Viele dieser benannten Eigenschaften können auch verwendet werden, um Metadaten zu schreiben. Zusätzliche Unterstützung für das Lesen von Metadaten wird vom Metadaten-Abfragereader bereitgestellt. Die <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> Methode wird verwendet, um einen Metadatenabfrageleser abzurufen, indem eine Zeichenfolgenabfrage wie *"/app1/exif/"* bereitzustellen ist. Im folgenden Beispiel <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> wird verwendet, um den Text zu erhalten, der an der Position *"/Text/Beschreibung"* gespeichert ist.  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Zum Schreiben von Metadaten wird ein Metadaten-Abfragewriter verwendet. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>ruft den Abfrageschreiber ab und legt den gewünschten Wert fest. Im folgenden Beispiel <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> wird verwendet, um den Text zu schreiben, der an der Position *"/Text/Beschreibung"* gespeichert ist.  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>
## <a name="codec-extensibility"></a>Code-Erweiterbarkeit  
 Ein Kernmerkmal von WPF Imaging ist das Erweiterbarkeitsmodell für neue Bildcodecs. Diese nicht verwalteten Schnittstellen ermöglichen codec-Entwicklern die Integration von Codecs in WPF, sodass neue Bildformate automatisch von WPF-Anwendungen verwendet werden können.  
  
 Ein Beispiel für die Erweiterbarkeits-API finden Sie im [Win32-Beispielcodec](https://go.microsoft.com/fwlink/?LinkID=160052). In diesem Beispiel wird veranschaulicht, wie ein Decoder und Encoder für ein benutzerdefiniertes Bildformat erstellt werden.  
  
> [!NOTE]
> Der Codec muss digital signiert werden, damit das System ihn erkennt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Win32 Sample Codec](https://go.microsoft.com/fwlink/?LinkID=160052)
