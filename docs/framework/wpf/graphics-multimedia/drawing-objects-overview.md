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
ms.openlocfilehash: d4527c331308ff6cd517705212e09428216d2378
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459731"
---
# <a name="drawing-objects-overview"></a>Übersicht über Zeichnungsobjekte
In diesem Thema werden <xref:System.Windows.Media.Drawing> Objekte vorgestellt und beschrieben, wie diese verwendet werden, um Formen, Bitmaps, Text und Medien effizient zu zeichnen. Verwenden Sie <xref:System.Windows.Media.Drawing> Objekte beim Erstellen von Clip Grafiken, zeichnen mit einem <xref:System.Windows.Media.DrawingBrush>oder Verwenden von <xref:System.Windows.Media.Visual> Objekten.  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>Was ist ein Zeichnungsobjekt?  
 Ein <xref:System.Windows.Media.Drawing>-Objekt beschreibt sichtbare Inhalte, z. b. eine Form, eine Bitmap, ein Video oder eine Textzeile. Verschiedene Arten von Zeichnungen beschreiben verschiedene Arten von Inhalten. Im Folgenden finden Sie eine Liste der unterschiedlichen Typen von Zeichnungsobjekten.  
  
- <xref:System.Windows.Media.GeometryDrawing> – zeichnet eine Form.  
  
- <xref:System.Windows.Media.ImageDrawing> – zeichnet ein Bild.  
  
- <xref:System.Windows.Media.GlyphRunDrawing> – zeichnet Text.  
  
- <xref:System.Windows.Media.VideoDrawing> – gibt eine Audiodatei oder Videodatei wieder.  
  
- <xref:System.Windows.Media.DrawingGroup> – zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 <xref:System.Windows.Media.Drawing> Objekte sind vielseitiger. Es gibt viele Möglichkeiten, ein <xref:System.Windows.Media.Drawing> Objekt zu verwenden.  
  
- Sie können es als Bild mithilfe eines <xref:System.Windows.Media.DrawingImage> und eines <xref:System.Windows.Controls.Image> Steuer Elements anzeigen.  
  
- Sie können Sie mit einem <xref:System.Windows.Media.DrawingBrush> verwenden, um ein Objekt zu zeichnen, z. b. die <xref:System.Windows.Controls.Page.Background%2A> eines <xref:System.Windows.Controls.Page>.  
  
- Sie können es verwenden, um die Darstellung einer <xref:System.Windows.Media.DrawingVisual>zu beschreiben.  
  
- Sie können Sie verwenden, um den Inhalt einer <xref:System.Windows.Media.Visual>aufzulisten.  
  
 WPF bietet andere Arten von Objekten, zeichnen Formen, Bitmaps, Text und Medien. Beispielsweise können Sie auch <xref:System.Windows.Shapes.Shape>-Objekte verwenden, um Formen zu zeichnen, und das <xref:System.Windows.Controls.MediaElement> Steuerelement bietet eine weitere Möglichkeit zum Hinzufügen von Videos zu Ihrer Anwendung. Wann sollten Sie also <xref:System.Windows.Media.Drawing> Objekte verwenden? Wenn Sie Features auf Frameworkebene Opfern können, um Leistungsvorteile zu erzielen, oder wenn Sie <xref:System.Windows.Freezable> Features benötigen. Da <xref:System.Windows.Media.Drawing> Objekten keine Unterstützung für [Layout](../advanced/layout.md), Eingabe und Fokus bietet, bieten Sie Leistungsvorteile, die Sie ideal für das Beschreiben von Hintergründen, Clip Grafiken und für das Zeichnen auf niedriger Ebene mit <xref:System.Windows.Media.Visual> Objekten machen.  
  
 Da es sich um einen Typ <xref:System.Windows.Freezable> Objekts handelt, erhalten <xref:System.Windows.Media.Drawing> Objekte mehrere besondere Features, darunter die folgenden: Sie können als [Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)deklariert, von mehreren Objekten gemeinsam genutzt und schreibgeschützt werden, um die Leistung zu verbessern, geklont und durchgeführt zu werden. Thread sicher. Weitere Informationen zu den verschiedenen Funktionen, die von <xref:System.Windows.Freezable> Objekten bereitgestellt werden, finden Sie in der [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Zeichnen einer Form  
 Um eine Form zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.GeometryDrawing>. Die <xref:System.Windows.Media.GeometryDrawing.Geometry%2A>-Eigenschaft einer Geometrie Zeichnung beschreibt die zu zeichnende Form, die <xref:System.Windows.Media.GeometryDrawing.Brush%2A>-Eigenschaft beschreibt, wie das Innere der Form gezeichnet werden soll, und die <xref:System.Windows.Media.GeometryDrawing.Pen%2A>-Eigenschaft beschreibt, wie Ihre Gliederung gezeichnet werden soll.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.GeometryDrawing> verwendet, um eine Form zu zeichnen. Die Form wird von einem <xref:System.Windows.Media.GeometryGroup> und zwei <xref:System.Windows.Media.EllipseGeometry> Objekten beschrieben. Das Innere der Form wird mit einem <xref:System.Windows.Media.LinearGradientBrush> gezeichnet, und der Umriss wird mit einem <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>gezeichnet.  
  
 In diesem Beispiel wird die folgende <xref:System.Windows.Media.GeometryDrawing>erstellt.  
  
 ![Eine GeometryDrawing von zwei Ellipsen](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Eine GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Das vollständige Beispiel finden Sie unter [Erstellen einer GeometryDrawing](how-to-create-a-geometrydrawing.md).  
  
 Andere <xref:System.Windows.Media.Geometry> Klassen, z. b. <xref:System.Windows.Media.PathGeometry>, ermöglichen es Ihnen, komplexere Formen durch das Erstellen von Kurven und Arcs zu erstellen. Weitere Informationen zu <xref:System.Windows.Media.Geometry> Objekten finden Sie in der [Übersicht](geometry-overview.md)über die Geometrie.  
  
 Weitere Informationen zu anderen Methoden zum Zeichnen von Formen, die keine <xref:System.Windows.Media.Drawing> Objekte verwenden, finden Sie unter [Übersicht über Formen und grundlegende Zeichnungen in WPF](shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Zeichnen eines Bilds  
 Zum Zeichnen eines Bilds verwenden Sie einen <xref:System.Windows.Media.ImageDrawing>. Die <xref:System.Windows.Media.ImageDrawing.ImageSource%2A>-Eigenschaft eines <xref:System.Windows.Media.ImageDrawing> Objekts beschreibt das zu zeichnende Bild, und seine <xref:System.Windows.Media.ImageDrawing.Rect%2A>-Eigenschaft definiert den Bereich, in dem das Bild gezeichnet wird.  
  
 Im folgende Beispiel wird ein Bild in ein Rechteck bei (75,75) gezeichnet, das 100 x 100 Pixel groß ist. Die folgende Abbildung zeigt die <xref:System.Windows.Media.ImageDrawing>, die im Beispiel erstellt wurden. Es wurde ein grauer Rahmen hinzugefügt, um die Begrenzungen des <xref:System.Windows.Media.ImageDrawing>anzuzeigen.  
  
 ![Eine bei &#40;75,75&#41; gezeichnete ImageDrawing mit den Maßen 100 x 100](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
Eine ImageDrawing mit den Maßen 100 x 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Weitere Informationen zu Bildern finden Sie unter der [Überblick über die Bildverarbeitung](imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Wiedergeben von Medien (nur Code)  
  
> [!NOTE]
> Obwohl Sie eine <xref:System.Windows.Media.VideoDrawing> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]deklarieren können, können Sie Ihre Medien nur mit Code laden und wiedergeben. Verwenden Sie stattdessen eine <xref:System.Windows.Controls.MediaElement>, um Videos in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]wiederzugeben.  
  
 Um eine Audiodatei oder Videodatei wiederzugeben, verwenden Sie eine <xref:System.Windows.Media.VideoDrawing> und eine <xref:System.Windows.Media.MediaPlayer>. Es gibt zwei Methoden zum Laden und Wiedergeben von Medien. Der erste besteht darin, eine <xref:System.Windows.Media.MediaPlayer> und eine <xref:System.Windows.Media.VideoDrawing> eigenständig zu verwenden. die zweite Möglichkeit besteht darin, ihre eigenen <xref:System.Windows.Media.MediaTimeline> zu erstellen, die mit den <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing>verwendet werden.  
  
> [!NOTE]
> Wenn Sie Medien mit Ihrer Anwendung verteilen, können Sie keine Mediendatei als Ressource verwenden, wie Sie das mit einem Bild machen würden. Sie müssen stattdessen in der Projektdatei den Medientyp auf `Content` und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always` festlegen.  
  
 Führen Sie die folgenden Schritte aus, um Medien wiederzugeben, ohne eigene <xref:System.Windows.Media.MediaTimeline>zu erstellen.  
  
1. Erstellen eines <xref:System.Windows.Media.MediaPlayer>-Objekts  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Verwenden Sie die <xref:System.Windows.Media.MediaPlayer.Open%2A>-Methode, um die Mediendatei zu laden.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Erstellen Sie eine <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Geben Sie die Größe und den Speicherort zum Zeichnen des Mediums an, indem Sie die <xref:System.Windows.Media.VideoDrawing.Rect%2A>-Eigenschaft der <xref:System.Windows.Media.VideoDrawing>festlegen.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Legen Sie die <xref:System.Windows.Media.VideoDrawing.Player%2A>-Eigenschaft des <xref:System.Windows.Media.VideoDrawing> mit dem <xref:System.Windows.Media.MediaPlayer> fest, den Sie erstellt haben.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Verwenden Sie die <xref:System.Windows.Media.MediaPlayer.Play%2A>-Methode des <xref:System.Windows.Media.MediaPlayer>, um die Wiedergabe der Medien zu starten.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.VideoDrawing> und ein <xref:System.Windows.Media.MediaPlayer> verwendet, um eine Videodatei einmal wiederzugeben.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Verwenden Sie eine <xref:System.Windows.Media.MediaTimeline> mit den Objekten <xref:System.Windows.Media.MediaPlayer> und <xref:System.Windows.Media.VideoDrawing>, um zusätzliche zeitliche Steuerung des Mediums zu erhalten. Mit der <xref:System.Windows.Media.MediaTimeline> können Sie angeben, ob das Video wiederholt werden soll. Führen Sie die folgenden Schritte aus, um eine <xref:System.Windows.Media.MediaTimeline> mit einem <xref:System.Windows.Media.VideoDrawing>zu verwenden:  
  
1. Deklarieren Sie die <xref:System.Windows.Media.MediaTimeline>, und legen Sie deren zeitliche Steuerung fest.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Erstellen Sie eine <xref:System.Windows.Media.MediaClock> aus der <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Erstellen Sie eine <xref:System.Windows.Media.MediaPlayer>, und verwenden Sie die <xref:System.Windows.Media.MediaClock>, um die <xref:System.Windows.Media.MediaPlayer.Clock%2A>-Eigenschaft festzulegen.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Erstellen Sie eine <xref:System.Windows.Media.VideoDrawing>, und weisen Sie die <xref:System.Windows.Media.MediaPlayer> der Eigenschaft <xref:System.Windows.Media.VideoDrawing.Player%2A> der <xref:System.Windows.Media.VideoDrawing>zu.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.MediaTimeline> mit einem <xref:System.Windows.Media.MediaPlayer> und einem <xref:System.Windows.Media.VideoDrawing> verwendet, um ein Video wiederholt wiederzugeben.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Beachten Sie, dass Sie bei Verwendung einer <xref:System.Windows.Media.MediaTimeline>die interaktive <xref:System.Windows.Media.Animation.ClockController> verwenden, die von der Eigenschaft <xref:System.Windows.Media.Animation.Clock.Controller%2A> der <xref:System.Windows.Media.MediaClock> zurückgegeben wurde, um die Medienwiedergabe anstelle der interaktiven Methoden <xref:System.Windows.Media.MediaPlayer>zu steuern.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Zeichnen von Text  
 Um Text zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.GlyphRunDrawing> und eine <xref:System.Windows.Media.GlyphRun>. Im folgenden Beispiel wird ein <xref:System.Windows.Media.GlyphRunDrawing> verwendet, um den Text "Hallo Welt" zu zeichnen.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Bei einem <xref:System.Windows.Media.GlyphRun> handelt es sich um ein Objekt auf niedriger Ebene, das für die Verwendung mit Dokument Präsentations-und Druck Szenarien mit festem Format vorgesehen ist Eine einfachere Möglichkeit zum Zeichnen von Text auf dem Bildschirm ist die Verwendung eines <xref:System.Windows.Controls.Label> oder eines <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zu <xref:System.Windows.Media.GlyphRun>finden [Sie in der Einführung in das GlyphRun-Objekt und in der Übersicht über das Glyphs-Element](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) .  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Zusammengesetzte Zeichnungen  
 Mit einem <xref:System.Windows.Media.DrawingGroup> können Sie mehrere Zeichnungen zu einer einzelnen zusammengesetzten Zeichnung kombinieren. Mithilfe eines <xref:System.Windows.Media.DrawingGroup>können Sie Formen, Bilder und Text in einem einzelnen <xref:System.Windows.Media.Drawing> Objekt kombinieren.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.DrawingGroup> verwendet, um zwei <xref:System.Windows.Media.GeometryDrawing>-Objekte und ein <xref:System.Windows.Media.ImageDrawing>-Objekt zu kombinieren. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Eine zusammengesetzte Zeichnung  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Mit einem <xref:System.Windows.Media.DrawingGroup> können Sie auch Deck Kraft Masken, Transformationen, Bitmapeffekte und andere Vorgänge auf ihren Inhalt anwenden. <xref:System.Windows.Media.DrawingGroup> Vorgänge werden in der folgenden Reihenfolge angewendet: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>und dann <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Die folgende Abbildung zeigt die Reihenfolge, in der <xref:System.Windows.Media.DrawingGroup> Vorgänge angewendet werden.  
  
 ![DrawingGroup-Reihenfolge der Vorgänge](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Reihenfolge der DrawingGroup-Vorgänge  
  
 In der folgenden Tabelle werden die Eigenschaften beschrieben, die Sie zum Bearbeiten der Inhalte eines <xref:System.Windows.Media.DrawingGroup> Objekts verwenden können.  
  
|property|Beschreibung|Darstellung|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Ändert die Deckkraft der ausgewählten Teile des <xref:System.Windows.Media.DrawingGroup> Inhalts. Ein Beispiel finden Sie unter [Vorgehensweise: Steuern der Durchlässigkeit einer Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)).|![Eine DrawingGroup mit einer Deck Kraft Maske](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Ändert die Deckkraft des <xref:System.Windows.Media.DrawingGroup> Inhalts einheitlich. Verwenden Sie diese Eigenschaft, um einen <xref:System.Windows.Media.Drawing> transparent oder teilweise transparent zu machen. Ein Beispiel finden Sie unter [Vorgehensweise: Anwenden einer Deckkraftmaske auf eine Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)).|![Drawinggroups mit unterschiedlichen Deckkraft Einstellungen](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Wendet eine <xref:System.Windows.Media.Effects.BitmapEffect> auf den <xref:System.Windows.Media.DrawingGroup>-Inhalt an. Ein Beispiel finden Sie unter [Vorgehensweise: Anwenden von Bitmapeffekten auf eine Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)).|![DrawingGroup mit einem blurbitmapffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Schneidet den <xref:System.Windows.Media.DrawingGroup> Inhalt mithilfe eines <xref:System.Windows.Media.Geometry>in einen Bereich ab, den Sie beschreiben. Ein Beispiel finden Sie unter [Verfahrensweise: Beschneiden einer Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) .|![DrawingGroup mit einem definierten Clip-Bereich](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Richtet geräteunabhängige Pixel anhand der angegebenen Richtlinien an Gerätepixel aus. Diese Eigenschaft ist hilfreich, um sicherzustellen, dass datailreiche Grafiken auf Bildschirmen mit niedrigem DPI-Wert scharf gerendert werden. Ein Beispiel finden Sie unter [Anwenden eines Führungsliniensatzes auf eine Zeichnung](how-to-apply-a-guidelineset-to-a-drawing.md).|![Eine DrawingGroup mit und ohne ein GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Transformiert den <xref:System.Windows.Media.DrawingGroup> Inhalt. Ein Beispiel finden Sie unter [Vorgehensweise: Anwenden einer Transformation auf eine Zeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)).|![Eine gedrehte DrawingGroup](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Anzeigen einer Zeichnung als Bild  
 Verwenden Sie zum Anzeigen einer <xref:System.Windows.Media.Drawing> mit einem <xref:System.Windows.Controls.Image> Steuerelement eine <xref:System.Windows.Media.DrawingImage> als <xref:System.Windows.Controls.Image.Source%2A> des <xref:System.Windows.Controls.Image> Steuer Elements, und legen Sie die <xref:System.Windows.Media.DrawingImage>-Eigenschaft des <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> Objekts auf die anzuzeigende Zeichnung fest.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.DrawingImage> und ein <xref:System.Windows.Controls.Image>-Steuerelement verwendet, um eine <xref:System.Windows.Media.GeometryDrawing>anzuzeigen. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Eine GeometryDrawing von zwei Ellipsen](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Ein DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Zeichnen eines Objekts mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> ist ein Typ von Pinsel, der einen Bereich mit einem Zeichnungsobjekt zeichnet. Sie können ihn verwenden, um ein jedes beliebige graphische Objekt mit einer Zeichnung zu zeichnen. Die <xref:System.Windows.Media.Drawing>-Eigenschaft einer <xref:System.Windows.Media.DrawingBrush> die die <xref:System.Windows.Media.DrawingBrush.Drawing%2A>beschreibt. Um eine <xref:System.Windows.Media.Drawing> mit einem <xref:System.Windows.Media.DrawingBrush>zu erstellen, fügen Sie Sie mithilfe der <xref:System.Windows.Media.Drawing>-Eigenschaft des Pinsels dem Pinsel hinzu, und zeichnen Sie mithilfe des Pinsels ein grafisches Objekt, z. b. ein Steuerelement oder einen Panel.  
  
 In den folgenden Beispielen wird eine <xref:System.Windows.Media.DrawingBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> eines <xref:System.Windows.Shapes.Rectangle> mit einem Muster zu zeichnen, das aus einer <xref:System.Windows.Media.GeometryDrawing>erstellt wurde. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Ein gekachelter DrawingBrush](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Eine mit einem DrawingBrush verwendete GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 Die <xref:System.Windows.Media.DrawingBrush>-Klasse bietet eine Vielzahl von Optionen zum Strecken und überspannen ihres Inhalts. Weitere Informationen zu <xref:System.Windows.Media.DrawingBrush>finden Sie unter Übersicht über das Zeichnen [mit Bildern, Zeichnungen und Visualisierungen](painting-with-images-drawings-and-visuals.md) .  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Rendern einer Zeichnung mit einem visuellen Element  
 Ein <xref:System.Windows.Media.DrawingVisual> ist ein visueller Objekttyp, der zum Rendering einer Zeichnung entworfen wurde. Das direkte Arbeiten auf der visuellen Ebene ist eine Option für Entwickler, die eine stark benutzerdefinierte grafische Umgebung erstellen möchten; dies wird in dieser Übersicht nicht beschrieben. Weitere Informationen finden Sie unter [Verwenden von DrawingVisual-Objekten](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>DrawingContext-Objekte  
 Die <xref:System.Windows.Media.DrawingContext>-Klasse ermöglicht es Ihnen, eine <xref:System.Windows.Media.Visual> oder eine <xref:System.Windows.Media.Drawing> mit visuellen Inhalten aufzufüllen. Viele dieser untergeordneten Grafik Objekte verwenden eine <xref:System.Windows.Media.DrawingContext>, da Sie grafische Inhalte sehr effizient beschreibt.  
  
 Obwohl die <xref:System.Windows.Media.DrawingContext> Draw-Methoden ähnlich aussehen wie die Draw-Methoden des <xref:System.Drawing.Graphics?displayProperty=nameWithType> Typs, sind Sie tatsächlich sehr verschieden. <xref:System.Windows.Media.DrawingContext> wird mit einem Grafiksystem im beibehaltenen Modus verwendet, während der <xref:System.Drawing.Graphics?displayProperty=nameWithType> Typ mit einem Grafiksystem im unmittelbaren Modus verwendet wird. Wenn Sie die draw-Befehle eines <xref:System.Windows.Media.DrawingContext> Objekts verwenden, speichern Sie tatsächlich eine Reihe von Renderinganweisungen (obwohl der genaue Speichermechanismus vom Objekttyp abhängig ist, der die <xref:System.Windows.Media.DrawingContext>bereitstellt), der später vom Grafiksystem verwendet wird. Sie werden nicht in Echtzeit auf den Bildschirm gezeichnet. Weitere Informationen zur Funktionsweise des WPF-Grafik Systems (Windows Presentation Foundation) finden Sie in der [Übersicht über das WPF-Grafik Rendering](wpf-graphics-rendering-overview.md).  
  
 Eine <xref:System.Windows.Media.DrawingContext>wird nicht direkt instanziiert. Sie können jedoch einen Zeichnungs Kontext von bestimmten Methoden abrufen, z. b. <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> und <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Auflisten der Inhalte eines visuellen Objekts  
 Zusätzlich zu den anderen Verwendungsmöglichkeiten stellen <xref:System.Windows.Media.Drawing>-Objekte auch ein Objektmodell für das Auflisten des Inhalts einer <xref:System.Windows.Media.Visual>bereit.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>-Methode verwendet, um den <xref:System.Windows.Media.DrawingGroup> Wert eines <xref:System.Windows.Media.Visual> abzurufen und aufzuzählen.  
  
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
