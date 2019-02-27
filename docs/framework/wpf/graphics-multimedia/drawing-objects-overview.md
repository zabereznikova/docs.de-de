---
title: Übersicht über Zeichnungsobjekte
ms.date: 03/30/2017
helpviewer_keywords:
- ImageDrawing objects [WPF]
- GlyphRunDrawing objects [WPF]
- GeometryDrawing objects [WPF]
- drawings [WPF], about drawings
- Drawing objects [WPF]
- DrawingGroup objects [WPF]
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
ms.openlocfilehash: edbb5521069caaa83dc24ca03af510d8e12f1b11
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836525"
---
# <a name="drawing-objects-overview"></a>Übersicht über Zeichnungsobjekte
In diesem Thema werden <xref:System.Windows.Media.Drawing> Objekte und beschreibt, wie Sie diese verwenden, um effizient Zeichnen von Formen, Bitmaps, Text und Medien. Verwenden Sie <xref:System.Windows.Media.Drawing> Zeichnen von Objekten, die bei der Erstellung von ClipArt-Objekt, mit einem <xref:System.Windows.Media.DrawingBrush>, oder verwenden Sie <xref:System.Windows.Media.Visual> Objekte.  
  
 
  
<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>Was ist ein Zeichnungsobjekt?  
 Ein <xref:System.Windows.Media.Drawing> -Objekt beschreibt sichtbaren Inhalt, z. B. eine Form, Bitmap, Video oder eine Textzeile. Verschiedene Arten von Zeichnungen beschreiben verschiedene Arten von Inhalten. Im Folgenden finden Sie eine Liste der unterschiedlichen Typen von Zeichnungsobjekten.  
  
-   <xref:System.Windows.Media.GeometryDrawing> – Zeichnet eine Form.  
  
-   <xref:System.Windows.Media.ImageDrawing> – Zeichnet ein Bild.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> – Zeichnet Text.  
  
-   <xref:System.Windows.Media.VideoDrawing> – Gibt eine Audio- oder Videodatei.  
  
-   <xref:System.Windows.Media.DrawingGroup> – Zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 <xref:System.Windows.Media.Drawing> -Objekte sind vielseitig. Es gibt viele Möglichkeiten, Sie können, eine <xref:System.Windows.Media.Drawing> Objekt.  
  
-   Sie können es als Bild anzeigen, indem Sie mit einem <xref:System.Windows.Media.DrawingImage> und <xref:System.Windows.Controls.Image> Steuerelement.  
  
-   Können Sie sie mit einer <xref:System.Windows.Media.DrawingBrush> auf ein Objekt zu zeichnen, z. B. die <xref:System.Windows.Controls.Page.Background%2A> von einer <xref:System.Windows.Controls.Page>.  
  
-   Sie können sie die Darstellung der beschreiben eine <xref:System.Windows.Media.DrawingVisual>.  
  
-   Sie können es verwenden, um den Inhalt der aufzulisten eine <xref:System.Windows.Media.Visual>.  
  
 WPF bietet andere Arten von Objekten, zeichnen Formen, Bitmaps, Text und Medien. Angenommen, Sie können auch <xref:System.Windows.Shapes.Shape> Objekte zum Zeichnen von Formen, und die <xref:System.Windows.Controls.MediaElement> Steuerelement bietet eine weitere Möglichkeit zum Hinzufügen von Videos für Ihre Anwendung. Wann also sollten Sie verwenden <xref:System.Windows.Media.Drawing> Objekte? Wenn Sie Frameworkfeatures auf Frameworkebene Leistungsvorteile Opfern können oder Sie müssen <xref:System.Windows.Freezable> Funktionen. Da <xref:System.Windows.Media.Drawing> Objekte unterstützen keine [Layout](../../../../docs/framework/wpf/advanced/layout.md), Eingabe und Fokus, bieten sie Leistungsvorteile, die sie sich hervorragend zum Beschreiben von Hintergründen, ClipArt und zum Zeichnen auf niedriger Ebene mit machen <xref:System.Windows.Media.Visual> Objekte.  
  
 Da sie einen Typ sind <xref:System.Windows.Freezable> Objekt <xref:System.Windows.Media.Drawing> erhalten-Objekte mehrere spezielle Features, einschließlich die folgenden: sie können als deklariert werden [Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)entscheiden, die von mehreren Objekten, die schreibgeschützt zur Verbesserung der gemeinsamen Leistung, geklont und threadsicher gemacht. Weitere Informationen zu den verschiedenen Funktionen von <xref:System.Windows.Freezable> Objekten finden Sie die [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Zeichnen einer Form  
 Um eine Form zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.GeometryDrawing>. Einer Geometrie-Zeichnung <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> Eigenschaft beschreibt die Form zu zeichnen, seine <xref:System.Windows.Media.GeometryDrawing.Brush%2A> Eigenschaft beschreibt, wie das Innere der Form gezeichnet werden soll, und die zugehörige <xref:System.Windows.Media.GeometryDrawing.Pen%2A> Eigenschaft beschreibt, wie die Kontur gezeichnet werden soll.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.GeometryDrawing> zeichnen eine Form. Die Form wird beschrieben, indem eine <xref:System.Windows.Media.GeometryGroup> und zwei <xref:System.Windows.Media.EllipseGeometry> Objekte. Das Innere der Form gezeichnet wird eine <xref:System.Windows.Media.LinearGradientBrush> und seine Kontur gezeichnet wird, mit einem <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.  
  
 In diesem Beispiel erstellt die folgenden <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")  
Eine GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Das vollständige Beispiel finden Sie unter [Erstellen einer GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-geometrydrawing.md).  
  
 Andere <xref:System.Windows.Media.Geometry> Klassen, z. B. <xref:System.Windows.Media.PathGeometry> ermöglichen es Ihnen, komplexere Formen zu erstellen, indem die Kurven und Bögen erstellen. Weitere Informationen zu <xref:System.Windows.Media.Geometry> Objekten finden Sie die [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 Weitere Informationen zu anderen Möglichkeiten zum Zeichnen von Formen, die keine verwenden <xref:System.Windows.Media.Drawing> Objekten finden Sie [Formen und Grundlegendes Zeichnen in WPF (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Zeichnen eines Bilds  
 Um ein Bild zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.ImageDrawing>. Ein <xref:System.Windows.Media.ImageDrawing> des Objekts <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> Eigenschaft beschreibt, das Bild zu zeichnen, und die zugehörige <xref:System.Windows.Media.ImageDrawing.Rect%2A> -Eigenschaft definiert den Bereich, in dem das Bild gezeichnet wird.  
  
 Im folgende Beispiel wird ein Bild in ein Rechteck bei (75,75) gezeichnet, das 100 x 100 Pixel groß ist. Die folgende Abbildung zeigt die <xref:System.Windows.Media.ImageDrawing> durch das Beispiel erstellt. Ein grauer Rahmen wurde hinzugefügt, um die Grenzen des zeigen die <xref:System.Windows.Media.ImageDrawing>.  
  
 ![Eine 100 x 100 ImageDrawing, gezeichnet bei &#40;75,75&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-imagedrawing-offset.png "Graphicsmm_simple_imagedrawing_offset")  
Eine ImageDrawing mit den Maßen 100 x 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Weitere Informationen zu Bildern finden Sie unter der [Überblick über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Wiedergeben von Medien (nur Code)  
  
> [!NOTE]
>  Sie können deklarieren eine <xref:System.Windows.Media.VideoDrawing> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können nur laden und Wiedergeben von Medien mithilfe von Code. Zum Wiedergeben des Videos in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], verwenden Sie eine <xref:System.Windows.Controls.MediaElement> stattdessen.  
  
 Um eine Audio- oder Videodatei wiederzugeben, die Sie verwenden eine <xref:System.Windows.Media.VideoDrawing> und <xref:System.Windows.Media.MediaPlayer>. Es gibt zwei Methoden zum Laden und Wiedergeben von Medien. Die erste ist die Verwendung einer <xref:System.Windows.Media.MediaPlayer> und ein <xref:System.Windows.Media.VideoDrawing> von selbst, und die zweite besteht darin, Ihre eigenen erstellen <xref:System.Windows.Media.MediaTimeline> mit der <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Wenn Sie Medien mit Ihrer Anwendung verteilen, können Sie keine Mediendatei als Ressource verwenden, wie Sie das mit einem Bild machen würden. In der Projektdatei müssen Sie stattdessen den Medientyp auf `Content` festlegen, und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always`.  
  
 Zum Abspielen von Medien ohne das Erstellen einer eigenen <xref:System.Windows.Media.MediaTimeline>, Sie die folgenden Schritte ausführen.  
  
1.  Erstellen eines <xref:System.Windows.Media.MediaPlayer>-Objekts  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2.  Verwenden der <xref:System.Windows.Media.MediaPlayer.Open%2A> Methode zum Laden der Mediendatei.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3.  Erstellen Sie eine <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4.  Geben Sie die Größe und Position zum Zeichnen der Medien durch Festlegen der <xref:System.Windows.Media.VideoDrawing.Rect%2A> Eigenschaft der <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5.  Legen Sie die <xref:System.Windows.Media.VideoDrawing.Player%2A> Eigenschaft der <xref:System.Windows.Media.VideoDrawing> mit der <xref:System.Windows.Media.MediaPlayer> Sie erstellt haben.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6.  Verwenden der <xref:System.Windows.Media.MediaPlayer.Play%2A> Methode der <xref:System.Windows.Media.MediaPlayer> zum Starten der Wiedergabe von Medien.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.VideoDrawing> und <xref:System.Windows.Media.MediaPlayer> , eine Videodatei wiederzugeben.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Um zeitlich steuern die Medien zu erhalten, verwenden Sie eine <xref:System.Windows.Media.MediaTimeline> mit der <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing> Objekte. Die <xref:System.Windows.Media.MediaTimeline> können Sie angeben, ob das Video wiederholt werden soll. Verwenden einer <xref:System.Windows.Media.MediaTimeline> mit einem <xref:System.Windows.Media.VideoDrawing>, Sie die folgenden Schritte ausführen:  
  
1.  Deklarieren Sie die <xref:System.Windows.Media.MediaTimeline> und legen Sie die Zeitsteuerungsverhalten.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2.  Erstellen Sie eine <xref:System.Windows.Media.MediaClock> aus der <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3.  Erstellen einer <xref:System.Windows.Media.MediaPlayer> und verwenden Sie die <xref:System.Windows.Media.MediaClock> Festlegen seiner <xref:System.Windows.Media.MediaPlayer.Clock%2A> Eigenschaft.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4.  Erstellen einer <xref:System.Windows.Media.VideoDrawing> und weisen Sie die <xref:System.Windows.Media.MediaPlayer> auf die <xref:System.Windows.Media.VideoDrawing.Player%2A> Eigenschaft der <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.MediaTimeline> mit einem <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing> , ein Video wiederholt abzuspielen.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Beachten Sie, dass bei der Verwendung einer <xref:System.Windows.Media.MediaTimeline>, verwenden Sie die interaktive <xref:System.Windows.Media.Animation.ClockController> Merry der <xref:System.Windows.Media.Animation.Clock.Controller%2A> Eigenschaft der <xref:System.Windows.Media.MediaClock> zum Steuern der Medienwiedergabe anstelle der interaktiven Methoden der <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Zeichnen von Text  
 Um Text zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.GlyphRunDrawing> und <xref:System.Windows.Media.GlyphRun>. Im folgenden Beispiel wird eine <xref:System.Windows.Media.GlyphRunDrawing> zum Zeichnen des Texts "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Ein <xref:System.Windows.Media.GlyphRun> ist ein Low-Level-Objekt für die Verwendung mit festem Format Dokumentpräsentation und Druckszenarios vorgesehen. Eine einfachere Möglichkeit zum Zeichnen von Text auf dem Bildschirm ist die Verwendung einer <xref:System.Windows.Controls.Label> oder <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zu <xref:System.Windows.Media.GlyphRun>, finden Sie unter den [Einführung in das GlyphRun-Objekt und das Glyphs-Element](../../../../docs/framework/wpf/advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) Übersicht.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Zusammengesetzte Zeichnungen  
 Ein <xref:System.Windows.Media.DrawingGroup> können Sie mehrere Zeichnungen in einer zusammengesetzten Zeichnung kombinieren. Mithilfe einer <xref:System.Windows.Media.DrawingGroup>, können Sie Formen, Bildern und Text in einem einzelnen kombinieren <xref:System.Windows.Media.Drawing> Objekt.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingGroup> kombiniert zwei <xref:System.Windows.Media.GeometryDrawing> Objekte und eine <xref:System.Windows.Media.ImageDrawing> Objekt. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "Graphicsmm_simple")  
Eine zusammengesetzte Zeichnung  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Ein <xref:System.Windows.Media.DrawingGroup> ermöglicht auch Durchlässigkeitsmasken, Transformationen, Bitmapeffekte und andere Vorgänge auf die Inhalte anwenden. <xref:System.Windows.Media.DrawingGroup> Vorgänge werden in der folgenden Reihenfolge angewendet: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, und klicken Sie dann <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Die folgende Abbildung zeigt die Reihenfolge, in dem <xref:System.Windows.Media.DrawingGroup> Vorgänge angewendet werden.  
  
 ![DrawingGroup-Reihenfolge der Vorgänge](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "Graphcismm_drawinggroup_order")  
Reihenfolge der DrawingGroup-Vorgänge  
  
 Die folgende Tabelle beschreibt die Eigenschaften Sie zum Bearbeiten können einer <xref:System.Windows.Media.DrawingGroup> Inhalt des Objekts.  
  
|Eigenschaft|Beschreibung|Darstellung|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Ändert die Durchlässigkeit von ausgewählten Teilen des der <xref:System.Windows.Media.DrawingGroup> Inhalt. Ein Beispiel finden Sie unter [Gewusst wie: Steuern der Durchlässigkeit einer Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)).|![Eine DrawingGroup mit einer Deckkraftmaske](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-opmask.png "Graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Ändert gleichmäßig die Durchlässigkeit des der <xref:System.Windows.Media.DrawingGroup> Inhalt. Verwenden Sie diese Eigenschaft zu einer <xref:System.Windows.Media.Drawing> transparent bzw. teilweise transparent. Ein Beispiel finden Sie unter [Gewusst wie: Anwenden eine Deckkraftmaske auf eine Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)).|![DrawingGroups mit unterschiedlichen Deckkrafteinstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Wendet eine <xref:System.Windows.Media.Effects.BitmapEffect> auf die <xref:System.Windows.Media.DrawingGroup> Inhalt. Ein Beispiel finden Sie unter [Gewusst wie: Anwenden von Bitmapeffekten auf eine Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)).|![DrawingGroup mit einem BlurBitmapEffect](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-bitmap.png "Graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Schneidet die <xref:System.Windows.Media.DrawingGroup> Inhalt in einer Region beschrieben werden, mithilfe einer <xref:System.Windows.Media.Geometry>. Ein Beispiel finden Sie unter [Gewusst wie: Beschneiden einer Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) .|![DrawingGroup mit einem definierten Clip-Bereich](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipgeom.png "Graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Richtet geräteunabhängige Pixel anhand der angegebenen Richtlinien an Gerätepixel aus. Diese Eigenschaft ist hilfreich, um sicherzustellen, dass datailreiche Grafiken auf Bildschirmen mit niedrigem DPI-Wert scharf gerendert werden. Ein Beispiel finden Sie unter [Anwenden eines Führungsliniensatzes auf eine Zeichnung](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-a-guidelineset-to-a-drawing.md).|![Eine DrawingGroup mit und ohne ein GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "Graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Transformiert die <xref:System.Windows.Media.DrawingGroup> Inhalt. Ein Beispiel finden Sie unter [Gewusst wie: Anwenden einer Transformation auf eine Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)).|![Eine gedrehte DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rotate.png "Graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Anzeigen einer Zeichnung als Bild  
 Zum Anzeigen einer <xref:System.Windows.Media.Drawing> mit eine <xref:System.Windows.Controls.Image> steuern, verwenden Sie eine <xref:System.Windows.Media.DrawingImage> als die <xref:System.Windows.Controls.Image> des Steuerelements <xref:System.Windows.Controls.Image.Source%2A> und legen Sie die <xref:System.Windows.Media.DrawingImage> des Objekts <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> Eigenschaft, um die Zeichnung, die Sie anzeigen möchten.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingImage> und <xref:System.Windows.Controls.Image> -Steuerelement zum Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")  
Ein DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Zeichnen eines Objekts mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> ist ein Pinsel, der einen Bereich mit einem Zeichnungsobjekt zeichnet. Sie können ihn verwenden, um ein jedes beliebige graphische Objekt mit einer Zeichnung zu zeichnen. Die <xref:System.Windows.Media.Drawing> Eigenschaft eine <xref:System.Windows.Media.DrawingBrush> beschreibt seine <xref:System.Windows.Media.DrawingBrush.Drawing%2A>. Zum Rendern einer <xref:System.Windows.Media.Drawing> mit einer <xref:System.Windows.Media.DrawingBrush>, auf den Pinsel über des Pinsels hinzufügen <xref:System.Windows.Media.Drawing> -Eigenschaft und der Pinsel zum Zeichnen von einem grafischen Objekts, z. B. ein Steuerelement oder im Bereich verwendet.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einer <xref:System.Windows.Shapes.Rectangle> mit einem Muster von erstellt eine <xref:System.Windows.Media.GeometryDrawing>. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Ein Kacheleffekt DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-geometrydrawing.png "Graphicsmm_drawingbrush_geometrydrawing")  
Eine mit einem DrawingBrush verwendete GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 Die <xref:System.Windows.Media.DrawingBrush> Klasse bietet eine Vielzahl von Optionen zum Strecken und unterteilen des Inhalts. Weitere Informationen zu <xref:System.Windows.Media.DrawingBrush>, finden Sie unter den [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md) Übersicht.  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Rendern einer Zeichnung mit einem visuellen Element  
 Ein <xref:System.Windows.Media.DrawingVisual> ist ein Typ des visuellen Objekts entwickelt, um eine Zeichnung zu rendern. Das direkte Arbeiten auf der visuellen Ebene ist eine Option für Entwickler, die eine stark benutzerdefinierte grafische Umgebung erstellen möchten; dies wird in dieser Übersicht nicht beschrieben. Weitere Informationen finden Sie unter [Verwenden von DrawingVisual-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>DrawingContext-Objekte  
 Die <xref:System.Windows.Media.DrawingContext> -Klasse können Sie zum Auffüllen einer <xref:System.Windows.Media.Visual> oder <xref:System.Windows.Media.Drawing> mit visuellem Inhalt. Viele solcher Low-Level-Graphics-Objekte verwenden eine <xref:System.Windows.Media.DrawingContext> da es sehr effizient Grafikinhalte beschreibt.  
  
 Obwohl die <xref:System.Windows.Media.DrawingContext> ähneln den Zeichenmethode des Draw-Methoden die <xref:System.Drawing.Graphics?displayProperty=nameWithType> geben, sind sie doch sehr verschieden. <xref:System.Windows.Media.DrawingContext> ist zwar mit einem System mit retained Mode-Grafiken verwendet, die <xref:System.Drawing.Graphics?displayProperty=nameWithType> Typ wird mit einem Grafiksystem unmittelbarer Modus verwendet. Bei Verwendung einer <xref:System.Windows.Media.DrawingContext> des Objekts zeichnen-Befehle, speichern Sie einen Satz von Renderinganweisungen (obwohl der tatsächliche Speichermechanismus hängt vom Typ des Objekts, das angibt der <xref:System.Windows.Media.DrawingContext>), die später von Grafiken verwendet werden System; Sie werden nicht in Echtzeit auf dem Bildschirm gezeichnet. Weitere Informationen zur Funktionsweise der Windows Presentation Foundation (WPF)-Grafiksystem finden Sie unter den [Grafiken Übersicht über das WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 Instanziieren Sie nie direkt eine <xref:System.Windows.Media.DrawingContext>; Sie können jedoch einen Zeichnungskontext mit bestimmten Methoden, abrufen, wie z. B. <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> und <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Auflisten der Inhalte eines visuellen Objekts  
 Neben ihren anderen Verwendungszwecken <xref:System.Windows.Media.Drawing> Objekte stellen auch ein Objektmodell für das Auflisten des Inhalts einer <xref:System.Windows.Media.Visual>.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> Methode zum Abrufen der <xref:System.Windows.Media.DrawingGroup> Wert eine <xref:System.Windows.Media.Visual> zählt Sie ihn.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Übersicht über das WPF-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
- [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/drawings-how-to-topics.md)
