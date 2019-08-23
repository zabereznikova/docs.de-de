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
ms.openlocfilehash: d739865a692fa5ef448eba91369015580e5eda97
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916312"
---
# <a name="drawing-objects-overview"></a>Übersicht über Zeichnungsobjekte
In diesem Thema <xref:System.Windows.Media.Drawing> werden-Objekte vorgestellt und beschrieben, wie diese verwendet werden, um Formen, Bitmaps, Text und Medien effizient zu zeichnen. Verwenden <xref:System.Windows.Media.Drawing> Sie-Objekte, wenn Sie Clip Grafiken erstellen, <xref:System.Windows.Media.DrawingBrush>mit einem zeichnen <xref:System.Windows.Media.Visual> oder Objekte verwenden.  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>Was ist ein Zeichnungsobjekt?  
 Ein <xref:System.Windows.Media.Drawing> -Objekt beschreibt sichtbare Inhalte, z. b. eine Form, eine Bitmap, ein Video oder eine Textzeile. Verschiedene Arten von Zeichnungen beschreiben verschiedene Arten von Inhalten. Im Folgenden finden Sie eine Liste der unterschiedlichen Typen von Zeichnungsobjekten.  
  
- <xref:System.Windows.Media.GeometryDrawing>– Zeichnet eine Form.  
  
- <xref:System.Windows.Media.ImageDrawing>– Zeichnet ein Bild.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>– Zeichnet Text.  
  
- <xref:System.Windows.Media.VideoDrawing>– Gibt eine Audiodatei oder Videodatei wieder.  
  
- <xref:System.Windows.Media.DrawingGroup>– Zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 <xref:System.Windows.Media.Drawing>Objekte sind vielseitiger. Es gibt viele Möglichkeiten, ein <xref:System.Windows.Media.Drawing> -Objekt zu verwenden.  
  
- Sie können es als Bild anzeigen, indem Sie ein <xref:System.Windows.Media.DrawingImage> -Steuer <xref:System.Windows.Controls.Image> Element und ein-Steuerelement verwenden.  
  
- Sie können Sie mit einem <xref:System.Windows.Media.DrawingBrush> verwenden, um ein Objekt zu zeichnen, z. b. den <xref:System.Windows.Controls.Page.Background%2A> einer <xref:System.Windows.Controls.Page>.  
  
- Sie können es verwenden, um die Darstellung eines <xref:System.Windows.Media.DrawingVisual>zu beschreiben.  
  
- Sie können Sie verwenden, um den Inhalt <xref:System.Windows.Media.Visual>eines aufzulisten.  
  
 WPF bietet andere Arten von Objekten, zeichnen Formen, Bitmaps, Text und Medien. Beispielsweise können Sie-Objekte auch <xref:System.Windows.Shapes.Shape> zum Zeichnen von Formen verwenden, und <xref:System.Windows.Controls.MediaElement> das-Steuerelement bietet eine weitere Möglichkeit zum Hinzufügen von Videos zu Ihrer Anwendung. Wann sollten Sie also Objekte <xref:System.Windows.Media.Drawing> verwenden? Wenn Sie Features auf Frameworkebene Opfern können, um Leistungsvorteile zu <xref:System.Windows.Freezable> erzielen oder Features zu benötigen. Da <xref:System.Windows.Media.Drawing> Objekte keine Unterstützung für [Layout](../advanced/layout.md), Eingabe und Fokus haben, bieten Sie Leistungsvorteile, die Sie ideal für das Beschreiben von Hintergründen, Clip Grafiken und für das Zeichnen auf <xref:System.Windows.Media.Visual> niedriger Ebene mit Objekten machen.  
  
 Da es sich um ein <xref:System.Windows.Freezable> Type- <xref:System.Windows.Media.Drawing> Objekt handelt, haben-Objekte mehrere besondere Features, darunter die folgenden: Sie können als [Ressourcen](../advanced/xaml-resources.md)deklariert, von mehreren Objekten gemeinsam genutzt und schreibgeschützt werden, um die Leistung zu verbessern, geklont zu werden. Thread sicher. Weitere Informationen zu den verschiedenen Funktionen, die von <xref:System.Windows.Freezable> -Objekten bereitgestellt werden, finden Sie unter [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Zeichnen einer Form  
 Um eine Form zu zeichnen, verwenden Sie <xref:System.Windows.Media.GeometryDrawing>eine. Die-Eigenschaft einer <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> Geometrie Zeichnung beschreibt die zu zeichnende <xref:System.Windows.Media.GeometryDrawing.Brush%2A> Form. die-Eigenschaft beschreibt, wie das Innere der Form gezeichnet <xref:System.Windows.Media.GeometryDrawing.Pen%2A> werden soll, und die-Eigenschaft beschreibt, wie Ihre Gliederung gezeichnet werden soll.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.GeometryDrawing> -Typ verwendet, um eine Form zu zeichnen. Die Form wird durch ein <xref:System.Windows.Media.GeometryGroup> und zwei <xref:System.Windows.Media.EllipseGeometry> -Objekte beschrieben. Das Innere der Form wird mit einem <xref:System.Windows.Media.LinearGradientBrush> gezeichnet, und der Umriss wird mit einem <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>gezeichnet.  
  
 In diesem Beispiel wird Folgendes <xref:System.Windows.Media.GeometryDrawing>erstellt:  
  
 ![Eine GeometryDrawing von zwei Ellipsen](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Eine GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Das vollständige Beispiel finden Sie unter [Erstellen einer GeometryDrawing](how-to-create-a-geometrydrawing.md).  
  
 Andere <xref:System.Windows.Media.Geometry> Klassen, <xref:System.Windows.Media.PathGeometry> wie z. b. ermöglichen es Ihnen, komplexere Formen durch das Erstellen von Kurven und Arcs zu erstellen. Weitere Informationen zu- <xref:System.Windows.Media.Geometry> Objekten finden Sie in der Übersicht über die [Geometrie](geometry-overview.md).  
  
 Weitere Informationen zu anderen Methoden zum Zeichnen von Formen, die keine <xref:System.Windows.Media.Drawing> Objekte verwenden, finden Sie unter [Übersicht über Formen und grundlegende Zeichnungen in WPF](shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Zeichnen eines Bilds  
 Zum Zeichnen eines Bilds verwenden Sie eine <xref:System.Windows.Media.ImageDrawing>. Die <xref:System.Windows.Media.ImageDrawing> -Eigenschaft <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> eines Objekts beschreibt das zu zeichnende Bild, <xref:System.Windows.Media.ImageDrawing.Rect%2A> und seine-Eigenschaft definiert den Bereich, in dem das Bild gezeichnet wird.  
  
 Im folgende Beispiel wird ein Bild in ein Rechteck bei (75,75) gezeichnet, das 100 x 100 Pixel groß ist. Die folgende Abbildung zeigt die <xref:System.Windows.Media.ImageDrawing> im Beispiel erstellte. Es wurde ein grauer Rahmen hinzugefügt, um die Begrenzungen <xref:System.Windows.Media.ImageDrawing>von anzuzeigen.  
  
 ![A 100 von 100 ImageDrawing, gezeichnet &#40;um 75,&#41; 75](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
Eine ImageDrawing mit den Maßen 100 x 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Weitere Informationen zu Bildern finden Sie unter der [Überblick über die Bildverarbeitung](imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Wiedergeben von Medien (nur Code)  
  
> [!NOTE]
> Obwohl Sie ein <xref:System.Windows.Media.VideoDrawing> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]deklarieren können, können Sie seine Medien nur mit Code laden und wiedergeben. Zum Abspielen von Videos [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]in verwenden Sie <xref:System.Windows.Controls.MediaElement> stattdessen eine.  
  
 Um eine Audiodatei oder Videodatei wiederzugeben, verwenden <xref:System.Windows.Media.VideoDrawing> Sie eine <xref:System.Windows.Media.MediaPlayer>und eine. Es gibt zwei Methoden zum Laden und Wiedergeben von Medien. Der erste besteht darin, ein <xref:System.Windows.Media.MediaPlayer> und ein <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer> eigenständig zu verwenden, und die zweite Möglichkeit besteht darin, <xref:System.Windows.Media.MediaTimeline> einen eigenen zu erstellen, <xref:System.Windows.Media.VideoDrawing>der mit und verwendet werden kann.  
  
> [!NOTE]
> Wenn Sie Medien mit Ihrer Anwendung verteilen, können Sie keine Mediendatei als Ressource verwenden, wie Sie das mit einem Bild machen würden. In der Projektdatei müssen Sie stattdessen den Medientyp auf `Content` festlegen, und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always`.  
  
 Führen Sie die folgenden Schritte aus, <xref:System.Windows.Media.MediaTimeline>um Medien wiederzugeben, ohne Sie selbst erstellen zu müssen.  
  
1. Erstellen eines <xref:System.Windows.Media.MediaPlayer>-Objekts  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Verwenden Sie <xref:System.Windows.Media.MediaPlayer.Open%2A> die-Methode, um die Mediendatei zu laden.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Erstellen Sie eine <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Geben Sie die Größe und den Speicherort zum Zeichnen des Mediums <xref:System.Windows.Media.VideoDrawing.Rect%2A> an, indem <xref:System.Windows.Media.VideoDrawing>Sie die-Eigenschaft von festlegen.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Legen Sie die- <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer> Eigenschaft des-Objekts mit dem von Ihnen erstellten fest. <xref:System.Windows.Media.VideoDrawing.Player%2A>  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Verwenden <xref:System.Windows.Media.MediaPlayer> Sie <xref:System.Windows.Media.MediaPlayer.Play%2A> die-Methode von, um die Wiedergabe der Medien zu starten.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.VideoDrawing> und ein <xref:System.Windows.Media.MediaPlayer> verwendet, um eine Videodatei einmal wiederzugeben.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Verwenden Sie ein <xref:System.Windows.Media.MediaTimeline> -Objekt mit dem-Objekt und dem <xref:System.Windows.Media.MediaPlayer> - <xref:System.Windows.Media.VideoDrawing> Objekt, um zusätzliche zeitliche Steuerung des Mediums zu erhalten. Mit <xref:System.Windows.Media.MediaTimeline> können Sie angeben, ob das Video wiederholt werden soll. Um einen <xref:System.Windows.Media.MediaTimeline> mit einem <xref:System.Windows.Media.VideoDrawing>zu verwenden, führen Sie die folgenden Schritte aus:  
  
1. Deklarieren <xref:System.Windows.Media.MediaTimeline> Sie den, und legen Sie dessen zeitliche Steuerung fest  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Erstellen Sie <xref:System.Windows.Media.MediaClock> einen aus <xref:System.Windows.Media.MediaTimeline>dem.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Erstellen Sie <xref:System.Windows.Media.MediaPlayer> einen, und <xref:System.Windows.Media.MediaClock> verwenden Sie den <xref:System.Windows.Media.MediaPlayer.Clock%2A> , um seine-Eigenschaft festzulegen  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Erstellen <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer> Sieeinen<xref:System.Windows.Media.VideoDrawing.Player%2A> , und weisen Sie der-Eigenschaft des zu. <xref:System.Windows.Media.VideoDrawing>  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.MediaTimeline> mit einem <xref:System.Windows.Media.MediaPlayer> und einem <xref:System.Windows.Media.VideoDrawing> verwendet, um ein Video wiederholt wiederzugeben.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Beachten Sie, dass Sie, wenn <xref:System.Windows.Media.MediaTimeline>Sie einen verwenden, die <xref:System.Windows.Media.Animation.ClockController> <xref:System.Windows.Media.MediaClock> von der <xref:System.Windows.Media.Animation.Clock.Controller%2A> -Eigenschaft von zurückgegebene interaktive verwenden, um die Medienwiedergabe anstelle der <xref:System.Windows.Media.MediaPlayer>interaktiven Methoden von zu steuern.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Zeichnen von Text  
 Um Text zu zeichnen, verwenden Sie <xref:System.Windows.Media.GlyphRunDrawing> eine und <xref:System.Windows.Media.GlyphRun>eine. Im folgenden Beispiel wird ein <xref:System.Windows.Media.GlyphRunDrawing> verwendet, um den Text "Hallo Welt" zu zeichnen.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Bei <xref:System.Windows.Media.GlyphRun> handelt es sich um ein Objekt auf niedriger Ebene, das für die Verwendung mit Dokument Präsentations-und Druck Szenarien mit festem Format vorgesehen ist. Eine einfachere Möglichkeit zum Zeichnen von Text auf dem Bildschirm ist die <xref:System.Windows.Controls.Label> Verwendung von <xref:System.Windows.Controls.TextBlock>oder. Weitere Informationen <xref:System.Windows.Media.GlyphRun>zu finden [Sie unter Einführung in das GlyphRun-Objekt und Glyphs-Element](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) (Übersicht).  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Zusammengesetzte Zeichnungen  
 Mit <xref:System.Windows.Media.DrawingGroup> einem können Sie mehrere Zeichnungen zu einer einzelnen zusammengesetzten Zeichnung kombinieren. Mithilfe eines <xref:System.Windows.Media.DrawingGroup>können Sie Formen, Bilder und Text in einem einzelnen <xref:System.Windows.Media.Drawing> Objekt kombinieren.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.DrawingGroup> verwendet, um <xref:System.Windows.Media.GeometryDrawing> zwei-Objekte <xref:System.Windows.Media.ImageDrawing> und ein-Objekt zu kombinieren. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Eine zusammengesetzte Zeichnung  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Mit können Sie auch Deck Kraft Masken, Transformationen, Bitmapeffekte und andere Vorgänge auf ihren Inhalt anwenden. <xref:System.Windows.Media.DrawingGroup> <xref:System.Windows.Media.DrawingGroup>Vorgänge werden in der folgenden Reihenfolge angewendet <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>: <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, und dann <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Die folgende Abbildung zeigt die Reihenfolge, <xref:System.Windows.Media.DrawingGroup> in der Vorgänge angewendet werden.  
  
 ![DrawingGroup-Reihenfolge der Vorgänge](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Reihenfolge der DrawingGroup-Vorgänge  
  
 In der folgenden Tabelle werden die Eigenschaften beschrieben, mit denen Sie <xref:System.Windows.Media.DrawingGroup> den Inhalt eines-Objekts bearbeiten können.  
  
|Eigenschaft|Beschreibung|Darstellung|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Ändert die Deckkraft der ausgewählten Teile des <xref:System.Windows.Media.DrawingGroup> Inhalts. Ein Beispiel finden Sie unter [Gewusst wie: Steuern der Deckkraft einer Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)).|![Eine DrawingGroup mit einer Deckkraftmaske](./media/graphicsmm-opmask.png "Graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Ändert die Deckkraft des <xref:System.Windows.Media.DrawingGroup> Inhalts einheitlich. Verwenden Sie diese Eigenschaft, um <xref:System.Windows.Media.Drawing> transparent oder teilweise transparent zu machen. Ein Beispiel finden Sie unter [Gewusst wie: Anwenden einer Deck Kraft Maske auf eine Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)).|![DrawingGroups mit unterschiedlichen Deckkrafteinstellungen](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Wendet einen <xref:System.Windows.Media.Effects.BitmapEffect> auf die <xref:System.Windows.Media.DrawingGroup> Inhalte an. Ein Beispiel finden Sie unter [Gewusst wie: Anwenden eines bitmapeer ffect auf eine Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)).|![DrawingGroup mit einem BlurBitmapEffect](./media/graphicsmm-bitmap.png "Graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Schneidet den <xref:System.Windows.Media.DrawingGroup> Inhalt in einen Bereich, den Sie mit <xref:System.Windows.Media.Geometry>einem beschreiben. Ein Beispiel finden Sie unter [Gewusst wie: Schneiden Sie eine](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) Zeichnung ab.|![DrawingGroup mit einem definierten Clip-Bereich](./media/graphicsmm-clipgeom.png "Graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Richtet geräteunabhängige Pixel anhand der angegebenen Richtlinien an Gerätepixel aus. Diese Eigenschaft ist hilfreich, um sicherzustellen, dass datailreiche Grafiken auf Bildschirmen mit niedrigem DPI-Wert scharf gerendert werden. Ein Beispiel finden Sie unter [Anwenden eines Führungsliniensatzes auf eine Zeichnung](how-to-apply-a-guidelineset-to-a-drawing.md).|![Eine DrawingGroup mit und ohne ein GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "Graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Transformiert den <xref:System.Windows.Media.DrawingGroup> Inhalt. Ein Beispiel finden Sie unter [Gewusst wie: Anwenden einer Transformation auf eine Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)).|![Eine gedrehte DrawingGroup](./media/graphicsmm-rotate.png "Graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Anzeigen einer Zeichnung als Bild  
 <xref:System.Windows.Media.DrawingImage> Wenn Sie ein <xref:System.Windows.Media.Drawing> mit einem <xref:System.Windows.Controls.Image> -Steuerelement anzeigen möchten, <xref:System.Windows.Controls.Image> verwenden Sie <xref:System.Windows.Controls.Image.Source%2A> als die des <xref:System.Windows.Media.DrawingImage> -Steuer <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> Elements, und legen Sie die-Eigenschaft des-Objekts auf die anzuzeigende Zeichnung fest  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Controls.Image> und ein-Steuerelement verwendet <xref:System.Windows.Media.GeometryDrawing>, um einen anzuzeigen. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Eine GeometryDrawing von zwei Ellipsen](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Ein DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Zeichnen eines Objekts mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> ist ein Typ von Pinsel, der einen Bereich mit einem Zeichnungsobjekt zeichnet. Sie können ihn verwenden, um ein jedes beliebige graphische Objekt mit einer Zeichnung zu zeichnen. Die <xref:System.Windows.Media.Drawing> -Eigenschaft <xref:System.Windows.Media.DrawingBrush> eines beschreibt seine <xref:System.Windows.Media.DrawingBrush.Drawing%2A>. Um einen <xref:System.Windows.Media.Drawing> mit einem <xref:System.Windows.Media.DrawingBrush>zu erstellen, fügen Sie ihn mithilfe der- <xref:System.Windows.Media.Drawing> Eigenschaft des Pinsels dem Pinsel hinzu, und zeichnen Sie mithilfe des Pinsels ein grafisches Objekt, z. b. ein Steuerelement oder einen Panel.  
  
 In den folgenden Beispielen wird <xref:System.Windows.Media.DrawingBrush> ein verwendet, <xref:System.Windows.Shapes.Shape.Fill%2A> um die <xref:System.Windows.Shapes.Rectangle> eines mit einem Muster zu zeichnen <xref:System.Windows.Media.GeometryDrawing>, das aus einem erstellt wurde. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Ein gekachelter DrawingBrush](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Eine mit einem DrawingBrush verwendete GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 Die <xref:System.Windows.Media.DrawingBrush> -Klasse bietet eine Vielzahl von Optionen zum Strecken und überspannen ihres Inhalts. Weitere Informationen zu <xref:System.Windows.Media.DrawingBrush>finden Sie unter Übersicht über das Zeichnen [mit Bildern, Zeichnungen und Visualisierungen](painting-with-images-drawings-and-visuals.md) .  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Rendern einer Zeichnung mit einem visuellen Element  
 Ein <xref:System.Windows.Media.DrawingVisual> ist ein visueller Objekttyp, der zum Rendering einer Zeichnung entworfen wurde. Das direkte Arbeiten auf der visuellen Ebene ist eine Option für Entwickler, die eine stark benutzerdefinierte grafische Umgebung erstellen möchten; dies wird in dieser Übersicht nicht beschrieben. Weitere Informationen finden Sie unter [Verwenden von DrawingVisual-Objekten](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>DrawingContext-Objekte  
 Mit <xref:System.Windows.Media.DrawingContext> der-Klasse können Sie ein <xref:System.Windows.Media.Visual> -Element oder <xref:System.Windows.Media.Drawing> ein-Element mit visuellen Inhalten auffüllen. Viele dieser untergeordneten Grafik Objekte verwenden eine <xref:System.Windows.Media.DrawingContext> , da Sie grafische Inhalte sehr effizient beschreibt.  
  
 Obwohl die <xref:System.Windows.Media.DrawingContext> Draw-Methoden ähnlich aussehen wie die Draw-Methoden <xref:System.Drawing.Graphics?displayProperty=nameWithType> des Typs, sind Sie tatsächlich sehr verschieden. <xref:System.Windows.Media.DrawingContext>wird mit einem Grafiksystem im beibehaltenen Modus verwendet <xref:System.Drawing.Graphics?displayProperty=nameWithType> , während der-Typ mit einem Grafiksystem im unmittelbaren Modus verwendet wird. Wenn Sie die Draw <xref:System.Windows.Media.DrawingContext> -Befehle eines-Objekts verwenden, speichern Sie tatsächlich eine Reihe von Renderinganweisungen (obwohl der genaue Speichermechanismus vom Objekttyp abhängig <xref:System.Windows.Media.DrawingContext>ist, der die bereitstellt), der später vom Grafiksystem verwendet wird. Sie werden nicht in Echtzeit auf den Bildschirm gezeichnet. Weitere Informationen zur Funktionsweise des WPF-Grafik Systems (Windows Presentation Foundation) finden Sie in der [Übersicht über das WPF-Grafik Rendering](wpf-graphics-rendering-overview.md).  
  
 Sie können niemals direkt instanziieren <xref:System.Windows.Media.DrawingContext>. Sie können jedoch einen Zeichnungs Kontext von bestimmten Methoden abrufen, <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> z. b. und <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Auflisten der Inhalte eines visuellen Objekts  
 Zusätzlich zu den anderen Verwendungsmöglichkeiten <xref:System.Windows.Media.Drawing> stellen-Objekte auch ein Objektmodell für das Auflisten des Inhalts <xref:System.Windows.Media.Visual>von bereit.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> <xref:System.Windows.Media.Visual> -Methode verwendet, <xref:System.Windows.Media.DrawingGroup> um den Wert eines abzurufen und ihn aufzulisten.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Übersicht über Geometrien](geometry-overview.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
- [Themen zu Vorgehensweisen](drawings-how-to-topics.md)
