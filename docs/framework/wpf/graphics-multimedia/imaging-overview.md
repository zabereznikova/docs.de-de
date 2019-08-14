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
ms.openlocfilehash: fcf5e8e68492f4d1ff75221384b08ffad2b939f3
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971951"
---
# <a name="imaging-overview"></a>Übersicht über die Bildverarbeitung
Dieses Thema enthält eine Einführung in die [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)]. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] ermöglicht es Entwicklern, Bilder anzuzeigen, zu transformieren und zu formatieren.  

## <a name="wpf-imaging-component"></a>WPF Imaging-Komponente  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] ermöglicht signifikante Verbesserungen der Bildverarbeitungsfunktionen in [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]. Abbild Erstellungs Funktionen, wie z. b. das Anzeigen einer Bitmap oder die Verwendung eines Bilds auf einem allgemeinen Steuerelement, waren zuvor auf die Microsoft Windows Graphics Device Interface-oder Microsoft Windows-GDI+-Bibliotheken angewiesen. Diese API stellt grundlegende Abbild Erstellungs Funktionen bereit, verfügt jedoch nicht über Features wie die Unterstützung von Codec-Erweiterbarkeit und qualitativ hochwertige Bildunterstützung. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]wurde entworfen, um die Unzulänglichkeiten von GDI und GDI+ zu überwinden und eine neue API zum Anzeigen und Verwenden von Bildern in Ihren Anwendungen bereitzustellen.  
  
 Es gibt zwei Möglichkeiten für den Zugriff [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] auf die API, eine verwaltete Komponente und eine nicht verwaltete Komponente. Die nicht verwaltete Komponente stellt die folgenden Features bereit.  
  
- Erweiterbarkeitsmodell für neue oder proprietäre Bildformate.  
  
- Verbesserte Leistung und Sicherheit bei nativen Image Formaten wie Bitmap (BMP), Joint Photographics Experts Group (JPEG) [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)], [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)],,, Graphics Interchange Format (GIF) und Symbol (. ico).  
  
- Beibehaltung von Bilddaten mit hoher Bittiefe von bis zu 8 Bits pro Kanal (32 Bits pro Pixel).  
  
- Nicht destruktive Bildskalieren, Zuschneiden und Drehungen.  
  
- Vereinfachte Farbverwaltung.  
  
- Unterstützung für in der Datei enthaltene proprietäre Metadaten.  
  
- Die verwaltete Komponente nutzt die nicht verwaltete Infrastruktur, um die nahtlose Integration von Bildern mit anderen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Funktionen, z.B. [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], Animation und Grafiken, bereitzustellen. Die verwaltete Komponente profitiert auch vom Windows Presentation Foundation (WPF) Imaging Codec Erweiterbarkeit Model (WPF), das die automatische Erkennung neuer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Bildformate in Anwendungen ermöglicht.  
  
 Der Großteil [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] der verwalteten API befindet sich <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> im-Namespace, obwohl mehrere <xref:System.Windows.Media.ImageBrush> wichtige Typen, z. b <xref:System.Windows.Media.ImageDrawing> . und, <xref:System.Windows.Media?displayProperty=nameWithType> sich im- <xref:System.Windows.Controls.Image> Namespace befinden <xref:System.Windows.Controls?displayProperty=nameWithType> und sich im Namespace.  
  
 Dieses Thema enthält zusätzliche Informationen über die verwaltete Komponente. Weitere Informationen zur nicht verwalteten API finden Sie in der Dokumentation zur [nicht verwalteten WPF-Imaging-Komponente](/windows/desktop/wic/-wic-lh) .  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>WPF-Bildformate  
 Ein Codec wird zum Decodieren und Codieren eines bestimmten Medienformats verwendet. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]beinhaltet einen Codec für BMP-, [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)]JPEG [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)]-,-,-, GIF-und Symbolbild Formate. Anhand jedes einzelnen Codecs können Anwendungen das entsprechende Bildformat decodieren und, mit Ausnahme von ICON, Codieren.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource>ist eine wichtige Klasse, die beim Decodieren und Codieren von Bildern verwendet wird. Sie ist der grundlegende Baustein der [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]-Pipeline und stellt einen einzelnen konstanten Satz von Pixeln mit einer bestimmten Größe und Auflösung dar. Ein <xref:System.Windows.Media.Imaging.BitmapSource> kann ein einzelner Rahmen eines Bilds mit mehreren Frames sein, oder es kann das Ergebnis einer Transformation sein, die auf <xref:System.Windows.Media.Imaging.BitmapSource>einem ausgeführt wird. Es ist das übergeordnete Element vieler der in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] der Abbild Erstellung verwendeten primären Klassen, <xref:System.Windows.Media.Imaging.BitmapFrame>z. b.  
  
 Eine <xref:System.Windows.Media.Imaging.BitmapFrame> wird verwendet, um die tatsächlichen Bitmapdaten eines Bildformats zu speichern. Viele Bildformate unterstützen nur ein <xref:System.Windows.Media.Imaging.BitmapFrame>einzelnes, obwohl Formate, wie z [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] . b. gif, mehrere Frames pro Bild unterstützen. Rahmen werden von Decodern als Eingabedaten verwendet und zur Erstellung der Bilddateien an Encoder übergeben.  
  
 Im folgenden Beispiel wird veranschaulicht, <xref:System.Windows.Media.Imaging.BitmapFrame> wie ein aus einer <xref:System.Windows.Media.Imaging.BitmapSource> erstellt und anschließend einem [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] Bild hinzugefügt wird.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Decodieren von Bildformaten  
 Beim Decodieren von Bildern wird das Bildformat in Bilddaten übersetzt, die vom System verwendet werden können. Die Bilddaten können dann verwendet werden, um das Bild anzuzeigen und zu verarbeiten oder um es in ein anderes Format zu codieren. Die Decoderauswahl basiert auf dem Bildformat. Der Codec wird automatisch ausgewählt, wenn kein bestimmter Decoder angegeben wird. Die Beispiele im Abschnitt [Anzeigen von Bildern in WPF](#_displayingimages) veranschaulichen die automatische Decodierung. Decoder für benutzerdefinierte Formate, die mithilfe der nicht verwalteten [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]-Schnittstellen entwickelt und im System registriert sind, werden automatisch in die Decoderauswahl eingebunden. Dadurch können benutzerdefinierte Formate, automatisch in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen angezeigt werden.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bitmap-Decoder zum Decodieren eines BMP-Format Bilds verwendet wird.  
  
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
 Es gibt mehrere Möglichkeiten, ein Bild in einer Windows Presentation Foundation (WPF)-Anwendung anzuzeigen. Bilder können mithilfe eines <xref:System.Windows.Controls.Image> -Steuer Elements angezeigt, in einem visuellen Element mithilfe eines <xref:System.Windows.Media.ImageBrush>gezeichnet oder mithilfe eines <xref:System.Windows.Media.ImageDrawing>gezeichnet werden.  
  
### <a name="using-the-image-control"></a>Verwenden des Image-Steuerelements  
 <xref:System.Windows.Controls.Image>ist ein FrameworkElement und die primäre Methode zum Anzeigen von Bildern in Anwendungen. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]kannaufzwei Artenverwendetwerden:AttributSyntaxoderEigenschaftsSyntax.<xref:System.Windows.Controls.Image> Im folgenden Beispiel wird veranschaulicht, wie ein Bild auf eine Breite von 200 Pixeln mit Attributsyntax und Eigenschaftensyntax gerendert wird. Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 In vielen der Beispiele wird ein <xref:System.Windows.Media.Imaging.BitmapImage> -Objekt verwendet, um auf eine Bilddatei zu verweisen. <xref:System.Windows.Media.Imaging.BitmapImage>ist eine spezialisierte <xref:System.Windows.Media.Imaging.BitmapSource> , die für [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] das Laden optimiert ist und eine einfache Möglichkeit <xref:System.Windows.Controls.Image.Source%2A> zum Anzeigen von <xref:System.Windows.Controls.Image> Bildern als eines-Steuer Elements ist.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bild mithilfe von Code auf eine Breite von 200 Pixel gerendert wird.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Imaging.BitmapImage>implementiert die <xref:System.ComponentModel.ISupportInitialize> -Schnittstelle, um die Initialisierung für mehrere Eigenschaften zu optimieren. Eigenschaftenänderungen können nur während der Objektinitialisierung erfolgen. Wird <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> aufgerufen, um zu signalisieren, dass die <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> Initialisierung begonnen hat, und signalisiert, dass die Initialisierung abgeschlossen wurde. Nach der Initialisierung werden Eigenschaftenänderungen Eigenschaften ignoriert.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Drehen, Konvertieren und Zuschneiden von Bildern  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]ermöglicht es Benutzern, Bilder mithilfe von Eigenschaften von <xref:System.Windows.Media.Imaging.BitmapImage> oder mit zusätzlichen <xref:System.Windows.Media.Imaging.BitmapSource> Objekten wie <xref:System.Windows.Media.Imaging.CroppedBitmap> oder <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>zu transformieren. Diese Bildtransformationen können Bilder skalieren oder drehen, das Pixelformat eines Bilds ändern oder ein Bild zuschneiden.  
  
 Bild Drehungen werden mithilfe der <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> -Eigenschaft von <xref:System.Windows.Media.Imaging.BitmapImage>ausgeführt. Drehungen können nur in 90-Grad-Schritten erfolgen. Im folgenden Beispiel wird ein Bild um 90 Grad gedreht.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Die Umstellung eines Bilds in ein anderes Pixel Format, wie z. b <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. Graustufen, erfolgt mithilfe von. In den folgenden Beispielen wird ein Bild in konvertiert <xref:System.Windows.Media.PixelFormats.Gray4%2A>.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Zum Zuschneiden eines Bilds kann <xref:System.Windows.UIElement.Clip%2A> entweder die <xref:System.Windows.Controls.Image> - <xref:System.Windows.Media.Imaging.CroppedBitmap> Eigenschaft von oder verwendet werden. Wenn Sie nur einen Teil eines Bilds anzeigen möchten, <xref:System.Windows.UIElement.Clip%2A> sollte in der Regel verwendet werden. Wenn Sie ein abgeschnittenes Bild codieren und speichern müssen, <xref:System.Windows.Media.Imaging.CroppedBitmap> sollte verwendet werden. Im folgenden Beispiel wird ein Bild mithilfe der Clip-Eigenschaft mithilfe <xref:System.Windows.Media.EllipseGeometry>von zugeschnitten.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Dehnen von Bildern  
 Die <xref:System.Windows.Controls.Image.Stretch%2A> -Eigenschaft steuert, wie ein Bild gestreckt wird, um den Container auszufüllen. Die <xref:System.Windows.Controls.Image.Stretch%2A> -Eigenschaft akzeptiert die folgenden Werte, die durch <xref:System.Windows.Media.Stretch> die-Enumeration definiert werden:  
  
- <xref:System.Windows.Media.Stretch.None>: Das Bild wird nicht gestreckt, um den Ausgabebereich auszufüllen. Wenn das Bild größer als der Ausgabebereich ist, wird das Bild in den Ausgabebereich gezogen, und alle überstehenden Bereiche werden abgeschnitten.  
  
- <xref:System.Windows.Media.Stretch.Fill>: Das Bild wird so skaliert, dass es in den Ausgabebereich passt. Da Höhe und Breite des Bilds unabhängig voneinander skaliert werden, wird das ursprüngliche Seitenverhältnis des Bilds möglicherweise nicht beibehalten. Dies bedeutet, dass das Bild möglicherweise verzerrt wird, um den Ausgabecontainer vollständig auszufüllen.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: Das Bild wird so skaliert, dass es vollständig in den Ausgabebereich passt. Das Seitenverhältnis des Inhalts wird beibehalten.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: Das Bild wird so skaliert, dass es den Ausgabebereich vollständig ausfüllt, während das ursprüngliche Seitenverhältnis des Bilds beibehalten wird.  
  
 Im folgenden Beispiel wird jede der verfügbaren <xref:System.Windows.Media.Stretch> Enumerationen auf eine <xref:System.Windows.Controls.Image>angewendet.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispiels und zeigt die Auswirkung der verschiedenen <xref:System.Windows.Controls.Image.Stretch%2A> Einstellungen auf ein Bild.  
  
 ![Unterschiedliche TileBrush-Dehneinstellungen](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Unterschiedliche Dehneinstellungen  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Zeichnen mit Bildern  
 Bilder können auch in einer Anwendung angezeigt werden, indem Sie mit <xref:System.Windows.Media.Brush>einem zeichnen. Mithilfe von Pinseln können Sie [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Objekte, angefangen von einfachen Objekten, über Objekte in Volltonfarbe bis hin zu Objekten mit komplexen von Mustern und Bildern, zeichnen. Um mit Bildern zu zeichnen, verwenden <xref:System.Windows.Media.ImageBrush>Sie eine. Ein <xref:System.Windows.Media.ImageBrush> ist ein Typ von <xref:System.Windows.Media.TileBrush> , der seinen Inhalt als Bitmapbild definiert. Ein <xref:System.Windows.Media.ImageBrush> zeigt ein einzelnes Bild an, das durch die <xref:System.Windows.Media.ImageBrush.ImageSource%2A> -Eigenschaft angegeben wird. Sie können steuern, wie das Bild gedehnt, angeordnet und gekachelt wird. Auf diese Weise können Sie Zerrungen verhindern und Muster und andere Effekte herstellen. Die folgende Abbildung zeigt einige Effekte, die mit einem <xref:System.Windows.Media.ImageBrush>erreicht werden können.  
  
 ![ImageBrush-Ausgabe Beispiele](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Bildpinsel können Formen, Steuerelemente, Text usw. füllen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie den Hintergrund einer Schaltfläche mit einem Bild mithilfe <xref:System.Windows.Media.ImageBrush>eines zeichnen können.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.ImageBrush> und zum Zeichnen von Bildern finden Sie [unterzeichnen mit Bildern, Zeichnungen und visuellen](painting-with-images-drawings-and-visuals.md)Elementen.  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>Bildmetadaten  
 Einige Bilddateien enthalten Metadaten, die den Inhalt oder die Eigenschaften der Datei beschreiben. Die meisten Digitalkameras erstellen z.B. Bilder, die Metadaten zum Fabrikat und Modell der Kamera enthalten, mit der das Bild aufgenommen wurde. Jedes Bildformat behandelt Metadaten unterschiedlich, aber [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] bietet eine einheitliche Möglichkeit zum Speichern und Abrufen von Metadaten für jedes unterstützte Bildformat.  
  
 Der Zugriff auf Metadaten wird durch die <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> -Eigenschaft <xref:System.Windows.Media.Imaging.BitmapSource> eines-Objekts bereitgestellt. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>Gibt ein <xref:System.Windows.Media.Imaging.BitmapMetadata> -Objekt zurück, das alle im Bild enthaltenen Metadaten enthält. Diese Daten können in einem Metadatenschema oder einer Kombination aus unterschiedlichen Schemas vorliegen. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]unterstützt die folgenden bildmetadatenschemas: Austauschbare Bilddatei (EXIF), Text (PNG-Textdaten), das Bild Datei Verzeichnis (IFD), der internationale Press-Telekommunikations-Rat [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)](IPTC) und.  
  
 Um den Prozess des Lesens von Metadaten zu vereinfachen, <xref:System.Windows.Media.Imaging.BitmapMetadata> stellt mehrere benannte Eigenschaften bereit, auf die leicht zugegriffen werden <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>kann <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>, wie <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>z. b., und. Viele dieser benannten Eigenschaften können auch verwendet werden, um Metadaten zu schreiben. Zusätzliche Unterstützung für das Lesen von Metadaten wird vom Metadaten-Abfragereader bereitgestellt. Die <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> -Methode wird zum Abrufen eines Metadatenabfrage-Readers verwendet, indem eine Zeichen folgen Abfrage wie *"/app1/exif/"* bereitgestellt wird. Im folgenden Beispiel wird verwendet <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> , um den am Speicherort *"/Text/Description"* gespeicherten Text abzurufen.  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Zum Schreiben von Metadaten wird ein Metadaten-Abfragewriter verwendet. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>Ruft den Abfragewriter ab und legt den gewünschten Wert fest. Im folgenden Beispiel wird verwendet <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> , um den am Speicherort *"/Text/Description"* gespeicherten Text zu schreiben.  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>Code-Erweiterbarkeit  
 Ein Hauptmerkmal des [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] ist das Erweiterbarkeitsmodell für neue Bildcodecs. Diese nicht verwalteten Schnittstellen können Codec-Entwickler Codecs in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integrieren, damit neue Bildformate automatisch von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen verwendet werden können.  
  
 Ein Beispiel für die Erweiterbarkeits-API finden Sie im [Win32](https://go.microsoft.com/fwlink/?LinkID=160052)-Beispielcodec. In diesem Beispiel wird veranschaulicht, wie ein Decoder und Encoder für ein benutzerdefiniertes Bildformat erstellt werden.  
  
> [!NOTE]
>  Der Codec muss digital signiert werden, damit das System ihn erkennt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Win32 Sample Codec](https://go.microsoft.com/fwlink/?LinkID=160052)
