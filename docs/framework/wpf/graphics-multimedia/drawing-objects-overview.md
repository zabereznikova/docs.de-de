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
ms.openlocfilehash: c896cd0c070ae30cb825cfc64dd9df9f8832e4ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558186"
---
# <a name="drawing-objects-overview"></a>Übersicht über Zeichnungsobjekte
Dieses Thema enthält <xref:System.Windows.Media.Drawing> Objekte und beschreibt deren Verwendung zum Zeichnen von Formen, Bitmaps, Text und Medien effizient. Verwenden Sie <xref:System.Windows.Media.Drawing> Zeichnen von Objekten, die bei der Erstellung von ClipArt-Objekt, mit einem <xref:System.Windows.Media.DrawingBrush>, oder verwenden Sie <xref:System.Windows.Media.Visual> Objekte.  
  
 
  
<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>Was ist ein Zeichnungsobjekt?  
 Ein <xref:System.Windows.Media.Drawing> Objekt beschreibt sichtbaren Inhalt, z. B. eine Form, Bitmap, Video oder eine Textzeile. Verschiedene Arten von Zeichnungen beschreiben verschiedene Arten von Inhalten. Im Folgenden finden Sie eine Liste der unterschiedlichen Typen von Zeichnungsobjekten.  
  
-   <xref:System.Windows.Media.GeometryDrawing> – Zeichnet eine Form.  
  
-   <xref:System.Windows.Media.ImageDrawing> – Zeichnet ein Bild.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> – Zeichnet Text.  
  
-   <xref:System.Windows.Media.VideoDrawing> – Gibt eine audio oder video.  
  
-   <xref:System.Windows.Media.DrawingGroup> – Zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 <xref:System.Windows.Media.Drawing> -Objekte sind vielseitig. Es gibt viele Möglichkeiten Sie können eine <xref:System.Windows.Media.Drawing> Objekt.  
  
-   Mithilfe von als Bild anzeigen einer <xref:System.Windows.Media.DrawingImage> und ein <xref:System.Windows.Controls.Image> Steuerelement.  
  
-   Können Sie ihn mit einer <xref:System.Windows.Media.DrawingBrush> ein Objekts, z. B. Paint-Ereignis der <xref:System.Windows.Controls.Page.Background%2A> von einer <xref:System.Windows.Controls.Page>.  
  
-   Können Sie es um die Darstellung der beschreiben eine <xref:System.Windows.Media.DrawingVisual>.  
  
-   Können sie den Inhalt auflisten einer <xref:System.Windows.Media.Visual>.  
  
 WPF bietet andere Arten von Objekten, zeichnen Formen, Bitmaps, Text und Medien. Angenommen, Sie können auch <xref:System.Windows.Shapes.Shape> Objekte zum Zeichnen von Formen, und die <xref:System.Windows.Controls.MediaElement> Steuerelement stellt eine weitere Möglichkeit zum Hinzufügen von Videos zu Ihrer Anwendung. Daher sollten Verwendung <xref:System.Windows.Media.Drawing> Objekte? Wenn Features auf Leistungsvorteilen Frameworkebene geopfert werden können oder wenn Sie <xref:System.Windows.Freezable> Funktionen. Da <xref:System.Windows.Media.Drawing> Objekte verfügen nicht über Unterstützung für [Layout](../../../../docs/framework/wpf/advanced/layout.md), Eingabe und zu konzentrieren, bieten sie Leistungsvorteile, die sie sich ideal zum Beschreiben von Hintergründen, ClipArt sowie zum Zeichnen auf niedriger Ebene mit machen <xref:System.Windows.Media.Visual> Objekte.  
  
 Da es sich um einen Typ sind <xref:System.Windows.Freezable> -Objekt, <xref:System.Windows.Media.Drawing> Objekte zu erhalten, mehrere besondere Features zählen folgende: sie können deklariert werden, als [Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)gemeinsam von mehreren Objekten, die zur Verbesserung der Schreibschutz versehen wurden Leistung, geklont und als threadsicher. Weitere Informationen zu den verschiedenen Features von <xref:System.Windows.Freezable> anzuzeigen, die [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Zeichnen einer Form  
 Verwenden Sie zum Zeichnen einer Form eine <xref:System.Windows.Media.GeometryDrawing>. Einer Geometry-Zeichnung <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> Eigenschaft beschreibt die Form zu zeichnen, dessen <xref:System.Windows.Media.GeometryDrawing.Brush%2A> Eigenschaft beschreibt, wie das Innere der Form gezeichnet werden soll, und die zugehörige <xref:System.Windows.Media.GeometryDrawing.Pen%2A> Eigenschaft beschreibt, wie seine Kontur gezeichnet werden soll.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.GeometryDrawing> zeichnen eine Form. Die Form wird beschrieben, indem eine <xref:System.Windows.Media.GeometryGroup> und zwei <xref:System.Windows.Media.EllipseGeometry> Objekte. Das Innere der Form gezeichnet wird, mit einem <xref:System.Windows.Media.LinearGradientBrush> und seine Kontur gezeichnet wird, mit einer <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.  
  
 Dieses Beispiel erstellt die folgenden <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")  
Eine GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Das vollständige Beispiel finden Sie unter [Erstellen einer GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-geometrydrawing.md).  
  
 Andere <xref:System.Windows.Media.Geometry> Klassen, z. B. <xref:System.Windows.Media.PathGeometry> ermöglichen es Ihnen, Kurven und Bögen erstellen komplexere Formen erstellen. Weitere Informationen zu <xref:System.Windows.Media.Geometry> anzuzeigen, die [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 Weitere Informationen zu anderen Methoden zum Zeichnen von Formen, die nicht verwenden <xref:System.Windows.Media.Drawing> anzuzeigen, [Formen und die grundlegenden Funktionen zum Zeichnen in WPF Übersicht](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Zeichnen eines Bilds  
 Um ein Bild zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.ImageDrawing>. Ein <xref:System.Windows.Media.ImageDrawing> des Objekts <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> Eigenschaft beschreibt das Bild gezeichnet werden soll, und die zugehörige <xref:System.Windows.Media.ImageDrawing.Rect%2A> -Eigenschaft definiert den Bereich, in dem das Bild gezeichnet wird.  
  
 Im folgende Beispiel wird ein Bild in ein Rechteck bei (75,75) gezeichnet, das 100 x 100 Pixel groß ist. Die folgende Abbildung zeigt die <xref:System.Windows.Media.ImageDrawing> durch das Beispiel erstellt. Ein grauer Rahmen wurde hinzugefügt, um die Grenzen des Anzeigen der <xref:System.Windows.Media.ImageDrawing>.  
  
 ![Eine Maßen 100 x 100 ImageDrawing gezeichnet &#40;75,75&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-imagedrawing-offset.png "Graphicsmm_simple_imagedrawing_offset")  
Eine ImageDrawing mit den Maßen 100 x 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Weitere Informationen zu Bildern finden Sie unter der [Überblick über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Wiedergeben von Medien (nur Code)  
  
> [!NOTE]
>  Sie können Deklarieren einer <xref:System.Windows.Media.VideoDrawing> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], können Sie nur geladen und Wiedergeben von Medien mithilfe von Code. Zum Wiedergeben von Videos in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], verwenden Sie eine <xref:System.Windows.Controls.MediaElement> stattdessen.  
  
 Um eine Audio- oder eine Datei wiederzugeben, verwenden Sie eine <xref:System.Windows.Media.VideoDrawing> und ein <xref:System.Windows.Media.MediaPlayer>. Es gibt zwei Methoden zum Laden und Wiedergeben von Medien. Der erste Schritt besteht im Verwenden einer <xref:System.Windows.Media.MediaPlayer> und ein <xref:System.Windows.Media.VideoDrawing> von selbst, während die zweite besteht darin, Ihre eigenen erstellen <xref:System.Windows.Media.MediaTimeline> für die Verwendung mit der <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Wenn Sie Medien mit Ihrer Anwendung verteilen, können Sie keine Mediendatei als Ressource verwenden, wie Sie das mit einem Bild machen würden. In der Projektdatei müssen Sie stattdessen den Medientyp auf `Content` festlegen, und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always`.  
  
 Um Medium wiederzugeben, ohne die Erstellung Ihres eigenen <xref:System.Windows.Media.MediaTimeline>, Sie die folgenden Schritte ausführen.  
  
1.  Erstellen eines <xref:System.Windows.Media.MediaPlayer>-Objekts  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2.  Verwenden der <xref:System.Windows.Media.MediaPlayer.Open%2A> Methode, um die Media-Datei zu laden.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3.  Erstellen Sie eine <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4.  Geben Sie die Größe und Position zum Zeichnen der Medien durch Festlegen der <xref:System.Windows.Media.VideoDrawing.Rect%2A> Eigenschaft von der <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5.  Festlegen der <xref:System.Windows.Media.VideoDrawing.Player%2A> Eigenschaft von der <xref:System.Windows.Media.VideoDrawing> mit der <xref:System.Windows.Media.MediaPlayer> Sie erstellt haben.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6.  Verwenden der <xref:System.Windows.Media.MediaPlayer.Play%2A> Methode der <xref:System.Windows.Media.MediaPlayer> Wiedergabe von Medien.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.VideoDrawing> und ein <xref:System.Windows.Media.MediaPlayer> einmal eine Videodatei wiederzugeben.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Um zusätzliche Timing Kontrolle über die Medien zu erhalten, verwenden Sie eine <xref:System.Windows.Media.MediaTimeline> mit der <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing> Objekte. Die <xref:System.Windows.Media.MediaTimeline> können Sie angeben, ob das Video wiederholt werden soll. Verwenden einer <xref:System.Windows.Media.MediaTimeline> mit einem <xref:System.Windows.Media.VideoDrawing>, Sie die folgenden Schritte ausführen:  
  
1.  Deklarieren Sie die <xref:System.Windows.Media.MediaTimeline> und die Zeitsteuerungsverhalten festgelegt.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2.  Erstellen einer <xref:System.Windows.Media.MediaClock> aus der <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3.  Erstellen einer <xref:System.Windows.Media.MediaPlayer> und Verwenden der <xref:System.Windows.Media.MediaClock> Festlegen seiner <xref:System.Windows.Media.MediaPlayer.Clock%2A> Eigenschaft.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4.  Erstellen einer <xref:System.Windows.Media.VideoDrawing> , und weisen Sie die <xref:System.Windows.Media.MediaPlayer> auf die <xref:System.Windows.Media.VideoDrawing.Player%2A> Eigenschaft der <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.MediaTimeline> mit einem <xref:System.Windows.Media.MediaPlayer> und ein <xref:System.Windows.Media.VideoDrawing> ein Video wiederholt abgespielt.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Beachten Sie, dass bei der Verwendung ein <xref:System.Windows.Media.MediaTimeline>, verwenden Sie die interaktive <xref:System.Windows.Media.Animation.ClockController> Merry der <xref:System.Windows.Media.Animation.Clock.Controller%2A> Eigenschaft der <xref:System.Windows.Media.MediaClock> Medien Wiedergabe anstelle der interaktiven Methoden der <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Zeichnen von Text  
 Um Text zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.GlyphRunDrawing> und ein <xref:System.Windows.Media.GlyphRun>. Im folgenden Beispiel wird eine <xref:System.Windows.Media.GlyphRunDrawing> zum Zeichnen des Texts "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Ein <xref:System.Windows.Media.GlyphRun> ist ein Low-Level-Objekt für die Verwendung mit festem Format Dokumentpräsentation und Drucken Szenarien vorgesehen. Eine einfachere Möglichkeit zum Zeichnen von Text auf dem Bildschirm ist die Verwendung einer <xref:System.Windows.Controls.Label> oder ein <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zu <xref:System.Windows.Media.GlyphRun>, finden Sie unter der [Einführung in die GlyphRun-Objekt und die Symbolelement](../../../../docs/framework/wpf/advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) (Übersicht).  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Zusammengesetzte Zeichnungen  
 Ein <xref:System.Windows.Media.DrawingGroup> ermöglicht es Ihnen, mehrere Zeichnungen in einem einzelnen zusammengesetzten Zeichnung kombinieren. Mithilfe einer <xref:System.Windows.Media.DrawingGroup>, Kombinieren von Formen, Bilder und Text in einem einzelnen <xref:System.Windows.Media.Drawing> Objekt.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingGroup> kombiniert zwei <xref:System.Windows.Media.GeometryDrawing> Objekte und eine <xref:System.Windows.Media.ImageDrawing> Objekt. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "Graphicsmm_simple")  
Eine zusammengesetzte Zeichnung  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Ein <xref:System.Windows.Media.DrawingGroup> auch ermöglicht es Ihnen, die Deckkraftmasken, Transformationen, Bitmapeffekte und andere Vorgänge auf seinen Inhalt angewendet. <xref:System.Windows.Media.DrawingGroup> Vorgänge werden in der folgenden Reihenfolge angewendet: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, und klicken Sie dann <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Die folgende Abbildung zeigt die Reihenfolge, in dem <xref:System.Windows.Media.DrawingGroup> Vorgänge angewendet werden.  
  
 ![DrawingGroup-Reihenfolge der Vorgänge](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "Graphcismm_drawinggroup_order")  
Reihenfolge der DrawingGroup-Vorgänge  
  
 Die folgende Tabelle beschreibt die Eigenschaften Sie zum Bearbeiten können einer <xref:System.Windows.Media.DrawingGroup> Inhalt des Objekts.  
  
|Eigenschaft|Beschreibung|Darstellung|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Ändert die Durchlässigkeit des ausgewählten Teile der <xref:System.Windows.Media.DrawingGroup> Inhalt. Ein Beispiel finden Sie unter [Vorgehensweise: Steuern der Durchlässigkeit einer Zeichnung](http://msdn.microsoft.com/library/68580652-7d32-4d27-93cc-a5148cf4d5ee).|![Eine DrawingGroup mit einer Deckkraftmaske](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-opmask.png "Graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Die Deckkraft einheitlich ändert die <xref:System.Windows.Media.DrawingGroup> Inhalt. Verwenden Sie diese Eigenschaft zu einer <xref:System.Windows.Media.Drawing> transparent oder teilweise transparent. Ein Beispiel finden Sie unter [Vorgehensweise: Anwenden einer Deckkraftmaske auf eine Zeichnung](http://msdn.microsoft.com/library/d77b420b-9be2-479c-a45e-82f4da30eb9f).|![DrawingGroups mit unterschiedlichen Deckkrafteinstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Wendet eine <xref:System.Windows.Media.Effects.BitmapEffect> auf die <xref:System.Windows.Media.DrawingGroup> Inhalt. Ein Beispiel finden Sie unter [Vorgehensweise: Anwenden von Bitmapeffekten auf eine Zeichnung](http://msdn.microsoft.com/library/c5b1de83-8d09-47fb-96db-5f174471f4b5).|![DrawingGroup mit einem BlurBitmapEffect](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-bitmap.png "Graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Schneidet die <xref:System.Windows.Media.DrawingGroup> Inhalt in einer Region beschreiben Sie mithilfe einer <xref:System.Windows.Media.Geometry>. Ein Beispiel finden Sie unter [Verfahrensweise: Beschneiden einer Zeichnung](http://msdn.microsoft.com/library/1f7d8a2c-c3c2-42cb-a542-e6796f9fb058) .|![DrawingGroup mit einem definierten Clip-Bereich](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipgeom.png "Graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Richtet geräteunabhängige Pixel anhand der angegebenen Richtlinien an Gerätepixel aus. Diese Eigenschaft ist hilfreich, um sicherzustellen, dass datailreiche Grafiken auf Bildschirmen mit niedrigem DPI-Wert scharf gerendert werden. Ein Beispiel finden Sie unter [Anwenden eines Führungsliniensatzes auf eine Zeichnung](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-a-guidelineset-to-a-drawing.md).|![Eine DrawingGroup mit und ohne ein GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "Graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Transformiert die <xref:System.Windows.Media.DrawingGroup> Inhalt. Ein Beispiel finden Sie unter [Vorgehensweise: Anwenden einer Transformation auf eine Zeichnung](http://msdn.microsoft.com/library/0d525f2b-682d-4d67-9660-cf46929fbabd).|![Eine gedrehte DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rotate.png "Graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Anzeigen einer Zeichnung als Bild  
 Anzuzeigende eine <xref:System.Windows.Media.Drawing> mit eine <xref:System.Windows.Controls.Image> steuern, verwenden Sie eine <xref:System.Windows.Media.DrawingImage> als die <xref:System.Windows.Controls.Image> des Steuerelements <xref:System.Windows.Controls.Image.Source%2A> und legen Sie die <xref:System.Windows.Media.DrawingImage> des Objekts <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> Eigenschaft, um die Zeichnung angezeigt werden soll.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingImage> und ein <xref:System.Windows.Controls.Image> -Steuerelement zum Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")  
Ein DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Zeichnen eines Objekts mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> ist ein Pinsel, einen Bereich mit einem zeichnen-Objekt zeichnet. Sie können ihn verwenden, um ein jedes beliebige graphische Objekt mit einer Zeichnung zu zeichnen. Die <xref:System.Windows.Media.Drawing> Eigenschaft eine <xref:System.Windows.Media.DrawingBrush> beschreibt die <xref:System.Windows.Media.DrawingBrush.Drawing%2A>. Zum Rendern einer <xref:System.Windows.Media.Drawing> mit einem <xref:System.Windows.Media.DrawingBrush>, fügen Sie es auf den Pinsel über des Pinsels <xref:System.Windows.Media.Drawing> Eigenschaft und die Verwendung der Pinsel (grafische(r) Paint-Ereignis, z. B. ein Steuerelement oder Bereich.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingBrush> Paint-Ereignis der <xref:System.Windows.Shapes.Shape.Fill%2A> des eine <xref:System.Windows.Shapes.Rectangle> mit einem Muster aus erstellt eine <xref:System.Windows.Media.GeometryDrawing>. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Ein nebeneinander DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-geometrydrawing.png "Graphicsmm_drawingbrush_geometrydrawing")  
Eine mit einem DrawingBrush verwendete GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 Die <xref:System.Windows.Media.DrawingBrush> Klasse bietet eine Vielzahl von Optionen zum Strecken und seinen Inhalt zu unterteilen. Weitere Informationen zu <xref:System.Windows.Media.DrawingBrush>, finden Sie unter der [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md) (Übersicht).  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Rendern einer Zeichnung mit einem visuellen Element  
 Ein <xref:System.Windows.Media.DrawingVisual> ist ein visuelles Objekt entwickelt, um eine Zeichnung zu rendern. Das direkte Arbeiten auf der visuellen Ebene ist eine Option für Entwickler, die eine stark benutzerdefinierte grafische Umgebung erstellen möchten; dies wird in dieser Übersicht nicht beschrieben. Weitere Informationen finden Sie unter [Verwenden von DrawingVisual-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>DrawingContext-Objekte  
 Die <xref:System.Windows.Media.DrawingContext> Klasse können Sie zum Auffüllen einer <xref:System.Windows.Media.Visual> oder ein <xref:System.Windows.Media.Drawing> mit visuellen Inhalt. Viele solcher auf niedrigerer Ebene Grafikobjekten verwenden eine <xref:System.Windows.Media.DrawingContext> da grafische Inhalt sehr effizient beschrieben.  
  
 Obwohl der <xref:System.Windows.Media.DrawingContext> Draw-Methoden vergleichbar mit den Draw-Methoden von stehen die <xref:System.Drawing.Graphics?displayProperty=nameWithType> Typ, sind sie tatsächlich sehr unterschiedlich. <xref:System.Windows.Media.DrawingContext> wird dagegen mit einem Grafiksystem Speichermodus verwendet wird, die <xref:System.Drawing.Graphics?displayProperty=nameWithType> mit einem Grafiksystem unmittelbarer Modus verwendet wird. Bei Verwendung von ein <xref:System.Windows.Media.DrawingContext> objektspezifischen draw-Befehle, speichern Sie einen Satz von Renderinganweisungen (obwohl die genaue Speichermechanismus hängt vom Typ des Objekts, das angibt der <xref:System.Windows.Media.DrawingContext>), die später von Grafiken verwendet System; Sie nicht werden in Echtzeit auf dem Bildschirm gezeichnet. Weitere Informationen zur Funktionsweise von Windows Presentation Foundation (WPF)-Grafiksystem finden Sie unter der [WPF-Grafiken Rendering Overview](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 Nie direkt instanziieren einer <xref:System.Windows.Media.DrawingContext>; Sie können jedoch einen Zeichnung Kontext vom bestimmte Methoden, wie z. B. abrufen <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> und <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Auflisten der Inhalte eines visuellen Objekts  
 Zusätzlich zu anderen ihres Verwendungszwecks <xref:System.Windows.Media.Drawing> Objekte enthalten auch ein Objektmodell für das Auflisten des Inhalts eines eine <xref:System.Windows.Media.Visual>.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> Methode zum Abrufen der <xref:System.Windows.Media.DrawingGroup> Wert, der eine <xref:System.Windows.Media.Visual> und aufgelistet.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Übersicht über das WPF-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/drawings-how-to-topics.md)
