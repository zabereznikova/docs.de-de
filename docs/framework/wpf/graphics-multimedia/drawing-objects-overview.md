---
title: "&#220;bersicht &#252;ber Zeichnungsobjekte | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zeichnungsobjekte"
  - "DrawingGroup-Objekte"
  - "Zeichnungen, Informationen über Zeichnungen"
  - "GeometryDrawing-Objekte"
  - "GlyphRunDrawing-Objekte"
  - "ImageDrawing-Objekte"
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# &#220;bersicht &#252;ber Zeichnungsobjekte
In diesem Thema werden <xref:System.Windows.Media.Drawing>\-Objekte eingeführt. Außerdem wird gezeigt, wie mit ihnen Formen, Bitmaps, Text und Medien effizient gezeichnet werden.  Verwenden Sie <xref:System.Windows.Media.Drawing>\-Objekte, wenn Sie ClipArt erstellen, mit einem <xref:System.Windows.Media.DrawingBrush> zeichnen oder <xref:System.Windows.Media.Visual>\-Objekte verwenden.  
  
   
  
<a name="whatisadrawingsection"></a>   
## Was ist ein Zeichnungsobjekt?  
 Ein <xref:System.Windows.Media.Drawing>\-Objekt beschreibt sichtbaren Inhalt, z. B. eine Form, Bitmap, ein Video oder eine Textzeile.  Die verschiedenen Zeichnungstypen beschreiben unterschiedliche Inhaltstypen.  Die folgende Liste enthält die verschiedenen Typen von Zeichnungsobjekten.  
  
-   <xref:System.Windows.Media.GeometryDrawing> – Zeichnet eine Form.  
  
-   <xref:System.Windows.Media.ImageDrawing> – Zeichnet ein Bild.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> – Zeichnet Text.  
  
-   <xref:System.Windows.Media.VideoDrawing> – Gibt eine Audio\- oder Videodatei wieder.  
  
-   <xref:System.Windows.Media.DrawingGroup> – Zeichnet andere Zeichnungen.  Verwenden Sie eine Zeichnungsgruppe, um aus anderen Zeichnungen eine einzelne zusammengesetzte Zeichnung zu bilden.  
  
 <xref:System.Windows.Media.Drawing>\-Objekte sind vielseitig. Es gibt viele Möglichkeiten, wie Sie ein <xref:System.Windows.Media.Drawing>\-Objekt verwenden können.  
  
-   Sie können es als Bild anzeigen, indem Sie ein <xref:System.Windows.Media.DrawingImage> und ein <xref:System.Windows.Controls.Image>\-Steuerelement verwenden.  
  
-   Sie können es mit einem <xref:System.Windows.Media.DrawingBrush> verwenden, um ein Objekt zu zeichnen, z. B. den <xref:System.Windows.Controls.Page.Background%2A> einer <xref:System.Windows.Controls.Page>.  
  
-   Sie können es verwenden, um die Darstellung eines <xref:System.Windows.Media.DrawingVisual>\-Objekts zu beschreiben.  
  
-   Sie können es verwenden, um die Inhalte eines <xref:System.Windows.Media.Visual>\-Objekts aufzulisten.  
  
 WPF stellt andere Objekttypen bereit, mit denen sich Formen, Bitmaps, Text und Medien zeichnen lassen.  Zum Beispiel können Sie auch mit <xref:System.Windows.Shapes.Shape>\-Objekten Formen zeichnen, und das <xref:System.Windows.Controls.MediaElement>\-Steuerelement bietet eine andere Möglichkeit, der Anwendung Videofunktionen hinzuzufügen.  Wann also sollten Sie <xref:System.Windows.Media.Drawing>\-Objekte verwenden?  Wenn Sie Features auf Frameworkebene zugunsten von Leistungsvorteilen opfern können oder wenn Sie <xref:System.Windows.Freezable>\-Features benötigen.  Da <xref:System.Windows.Media.Drawing>\-Objekte [Layout](../../../../docs/framework/wpf/advanced/layout.md), Eingabe und Fokus nicht unterstützen, bieten Sie Leistungsvorteile, aufgrund deren sie sich perfekt für die Beschreibung von Hintergründen und ClipArt sowie das Zeichnen auf niedriger Ebene mit <xref:System.Windows.Media.Visual>\-Objekten eignen.  
  
 Da sie den Typ <xref:System.Windows.Freezable> aufweisen, erhalten <xref:System.Windows.Media.Drawing>\-Objekte mehrere spezielle Features. Dazu zählt, dass sie als [Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) deklariert, von mehreren Objekten gleichzeitig verwendet, für eine höhere Leistung als schreibgeschützt definiert, geklont und als threadsicher festgelegt werden können.  Weitere Informationen über die verschiedenen von <xref:System.Windows.Freezable>\-Objekten bereitgestellten Features finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## Zeichnen einer Form  
 Um eine Form zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.GeometryDrawing>.  Die <xref:System.Windows.Media.GeometryDrawing.Geometry%2A>\-Eigenschaft einer Geometriezeichnung beschreibt die zu zeichnende Form, die <xref:System.Windows.Media.GeometryDrawing.Brush%2A>\-Eigenschaft beschreibt, wie das Innere der Form zu zeichnen ist, und die <xref:System.Windows.Media.GeometryDrawing.Pen%2A>\-Eigenschaft beschreibt, wie die Kontur zu zeichnen ist.  
  
 Im folgenden Beispiel wird mithilfe einer <xref:System.Windows.Media.GeometryDrawing> eine Form gezeichnet.  Die Form wird von einer <xref:System.Windows.Media.GeometryGroup> und zwei <xref:System.Windows.Media.EllipseGeometry>\-Objekten beschrieben.  Das Innere der Form wird mit einem <xref:System.Windows.Media.LinearGradientBrush>, die Kontur mit einem <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen> gezeichnet.  
  
 In diesem Beispiel wird die folgende <xref:System.Windows.Media.GeometryDrawing> erstellt.  
  
 ![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
  
        Eine GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Das vollständige Beispiel finden Sie unter [Erstellen einer GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-geometrydrawing.md).  
  
 Mit anderen <xref:System.Windows.Media.Geometry>\-Klassen, z. B. <xref:System.Windows.Media.PathGeometry>, können Sie komplexere Formen erzeugen, indem Sie Kurven und Bögen erstellen.  Weitere Informationen über <xref:System.Windows.Media.Geometry>\-Objekte finden Sie unter [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 Weitere Informationen über andere Möglichkeiten zum Zeichnen von Formen, die ohne <xref:System.Windows.Media.Drawing>\-Objekte auskommen, finden Sie unter [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## Zeichnen eines Bilds  
 Um ein Bild zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.ImageDrawing>.  Die <xref:System.Windows.Media.ImageDrawing.ImageSource%2A>\-Eigenschaft eines <xref:System.Windows.Media.ImageDrawing>\-Objekts beschreibt das zu zeichnende Bild, und die <xref:System.Windows.Media.ImageDrawing.Rect%2A>\-Eigenschaft definiert den Bereich, in dem das Bild gezeichnet wird.  
  
 Im folgenden Beispiel wird an der Position \(75,75\) ein Bild, das 100 x 100 [Pixel](GTMT) groß ist, in ein Rechteck gezeichnet.  In der folgenden Abbildung wird die durch das Beispiel erstellte <xref:System.Windows.Media.ImageDrawing> dargestellt.  Es wurde ein grauer Rahmen hinzugefügt, um die Grenzen der <xref:System.Windows.Media.ImageDrawing> anzuzeigen.  
  
 ![Eine bei &#40;75,75&#41; gezeichnete ImageDrawing mit den Maßen 100 x 100](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm\_simple\_imagedrawing\_offset")  
  
        ImageDrawing mit einer Größe von 100 x 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Weitere Informationen über Bilder finden Sie unter [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
<a name="playmedia"></a>   
## Wiedergeben von Medien \(Nur Code\)  
  
> [!NOTE]
>  Sie können zwar in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] eine <xref:System.Windows.Media.VideoDrawing> deklarieren, aber Sie können die zugehörigen Medien nur mithilfe von Code laden und wiedergeben.  Um Videos in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wiederzugeben, verwenden Sie stattdessen ein <xref:System.Windows.Controls.MediaElement>.  
  
 Um eine Audio\- oder Videodatei wiederzugeben, verwenden Sie eine <xref:System.Windows.Media.VideoDrawing> und einen <xref:System.Windows.Media.MediaPlayer>.  Es gibt zwei Möglichkeiten, Medien zu laden und wiederzugeben.  Sie können entweder einen <xref:System.Windows.Media.MediaPlayer> und eine <xref:System.Windows.Media.VideoDrawing> alleine verwenden, oder Sie erstellen eine eigene <xref:System.Windows.Media.MediaTimeline> und setzen diese zusammen mit dem <xref:System.Windows.Media.MediaPlayer> und der <xref:System.Windows.Media.VideoDrawing> ein.  
  
> [!NOTE]
>  Wenn Sie Medien mit der Anwendung verteilen, können Sie eine Mediendatei, im Gegensatz zu einem Bild, nicht als Projektressource verwenden.  Sie müssen stattdessen in der Projektdatei den Medientyp auf `Content` und `CopyToOutputDirectory` auf `PreserveNewest` oder `Always` festlegen.  
  
 Um Medien wiederzugeben, ohne eine eigene <xref:System.Windows.Media.MediaTimeline> zu erstellen, führen Sie die folgenden Schritte aus.  
  
1.  Erstellen eines <xref:System.Windows.Media.MediaPlayer>\-Objekts  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2.  Laden Sie die Mediendatei mithilfe der <xref:System.Windows.Media.MediaPlayer.Open%2A>\-Methode.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3.  Erstellen Sie eine <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4.  Geben Sie die Größe und den Speicherort zum Zeichnen der Medien an, indem Sie die <xref:System.Windows.Media.VideoDrawing.Rect%2A>\-Eigenschaft der <xref:System.Windows.Media.VideoDrawing> festlegen.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5.  Legen Sie die <xref:System.Windows.Media.VideoDrawing.Player%2A>\-Eigenschaft der <xref:System.Windows.Media.VideoDrawing> mit dem <xref:System.Windows.Media.MediaPlayer>, den Sie erstellt haben, fest.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6.  Beginnen Sie die Medienwiedergabe mithilfe der <xref:System.Windows.Media.MediaPlayer.Play%2A>\-Methode des <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 Im folgenden Beispiel wird eine Videodatei mit einer <xref:System.Windows.Media.VideoDrawing> und einem <xref:System.Windows.Media.MediaPlayer> einmal wiedergegeben.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Um eine zusätzliche Zeitsteuerungskontrolle über die Medien zu erhalten, verwenden Sie eine <xref:System.Windows.Media.MediaTimeline> mit dem <xref:System.Windows.Media.MediaPlayer>\-Objekt und dem <xref:System.Windows.Media.VideoDrawing>\-Objekt.  Mit der <xref:System.Windows.Media.MediaTimeline> können Sie angeben, ob das Video erneut wiedergegeben werden soll.  Um eine <xref:System.Windows.Media.MediaTimeline> mit einer <xref:System.Windows.Media.VideoDrawing> zu verwenden, führen Sie die folgenden Schritte aus:  
  
1.  Deklarieren Sie die <xref:System.Windows.Media.MediaTimeline>, und legen Sie das Zeitsteuerungsverhalten fest.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2.  Erstellen Sie eine <xref:System.Windows.Media.MediaClock> aus der <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3.  Erstellen Sie einen <xref:System.Windows.Media.MediaPlayer>, und legen Sie dessen <xref:System.Windows.Media.MediaPlayer.Clock%2A>\-Eigenschaft mithilfe der <xref:System.Windows.Media.MediaClock> fest.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4.  Erstellen Sie eine <xref:System.Windows.Media.VideoDrawing>, und ordnen Sie den <xref:System.Windows.Media.MediaPlayer> der <xref:System.Windows.Media.VideoDrawing.Player%2A>\-Eigenschaft der <xref:System.Windows.Media.VideoDrawing> zu.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 Im folgenden Beispiel wird mithilfe einer <xref:System.Windows.Media.MediaTimeline>, einem <xref:System.Windows.Media.MediaPlayer> und einer <xref:System.Windows.Media.VideoDrawing> ein Video wiederholt abgespielt.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Beachten Sie, dass Sie bei der Verwendung einer <xref:System.Windows.Media.MediaTimeline> statt der interaktiven Methoden von <xref:System.Windows.Media.MediaPlayer> den interaktiven <xref:System.Windows.Media.Animation.ClockController> verwenden, der von der <xref:System.Windows.Media.Animation.Clock.Controller%2A>\-Eigenschaft der <xref:System.Windows.Media.MediaClock> zurückgegeben wird, um die Medienwiedergabe zu steuern.  
  
<a name="drawtext"></a>   
## Zeichnen von Text  
 Um Text zu zeichnen, verwenden Sie <xref:System.Windows.Media.GlyphRunDrawing> und <xref:System.Windows.Media.GlyphRun>.  Im folgenden Beispiel wird mithilfe von <xref:System.Windows.Media.GlyphRunDrawing> der Text "Hello World" gezeichnet.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Ein <xref:System.Windows.Media.GlyphRun> ist ein Objekt auf niedriger Ebene für die Darstellung von Dokumenten mit festem Format und für Druckszenarios.  Eine einfachere Möglichkeit zum Zeichnen von Text auf dem Bildschirm ist die Verwendung eines <xref:System.Windows.Controls.Label>\-Elements oder eines <xref:System.Windows.Controls.TextBlock>\-Elements.  Weitere Informationen über <xref:System.Windows.Media.GlyphRun> finden Sie in der Übersicht [Einführung in das "GlyphRun"\-Objekt und das "Glyphs"\-Element](../../../../docs/framework/wpf/advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md).  
  
<a name="compositedrawingssection"></a>   
## Zusammengesetzte Zeichnungen  
 Mit einer <xref:System.Windows.Media.DrawingGroup> können Sie mehrere Zeichnungen zu einer einzigen zusammengesetzten Zeichnung zusammenfassen.  Mit einer <xref:System.Windows.Media.DrawingGroup> können Sie Formen, Bilder und Text zu einem einzigen <xref:System.Windows.Media.Drawing>\-Objekt zusammenfassen.  
  
 Im folgenden Beispiel werden mit einer <xref:System.Windows.Media.DrawingGroup> zwei <xref:System.Windows.Media.GeometryDrawing>\-Objekte und ein <xref:System.Windows.Media.ImageDrawing>\-Objekt zusammengefasst.  Folgende Ergebnisse werden zurückgegeben:  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.png "graphicsmm\_simple")  
  
        Eine zusammengesetzte Zeichnung  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Mit einer <xref:System.Windows.Media.DrawingGroup> können Sie außerdem Durchlässigkeitsmasken, Transformationen, Bitmapeffekte und andere Vorgänge auf die Inhalte anwenden.  <xref:System.Windows.Media.DrawingGroup>\-Vorgänge werden in der folgenden Reihenfolge angewendet: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> und dann <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Die folgende Abbildung zeigt die Reihenfolge, in der <xref:System.Windows.Media.DrawingGroup>\-Vorgänge angewendet werden.  
  
 ![DrawingGroup&#45;Reihenfolge der Vorgänge](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm\_drawinggroup\_order")  
  
        Reihenfolge von DrawingGroup\-Vorgängen  
  
 In der folgenden Tabelle werden die Eigenschaften beschrieben, mit denen Sie die Inhalte eines <xref:System.Windows.Media.DrawingGroup>\-Objekts bearbeiten können.  
  
|Property|Beschreibung|Darstellung|  
|--------------|------------------|-----------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Ändert die Durchlässigkeit von ausgewählten Teilen der <xref:System.Windows.Media.DrawingGroup>\-Inhalte.  Ein Beispiel finden Sie unter [How to: Control the Opacity of a Drawing](http://msdn.microsoft.com/de-de/68580652-7d32-4d27-93cc-a5148cf4d5ee).||  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Ändert die Durchlässigkeit der <xref:System.Windows.Media.DrawingGroup>\-Inhalte gleichmäßig.  Mit dieser Eigenschaft können Sie eine <xref:System.Windows.Media.Drawing> transparent oder teilweise transparent erscheinen lassen.  Ein Beispiel finden Sie unter [How to: Apply an Opacity Mask to a Drawing](http://msdn.microsoft.com/de-de/d77b420b-9be2-479c-a45e-82f4da30eb9f).||  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Wendet einen <xref:System.Windows.Media.Effects.BitmapEffect> auf die <xref:System.Windows.Media.DrawingGroup>\-Inhalte an.  Ein Beispiel finden Sie unter [How to: Apply a BitmapEffect to a Drawing](http://msdn.microsoft.com/de-de/c5b1de83-8d09-47fb-96db-5f174471f4b5).||  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Schneidet die <xref:System.Windows.Media.DrawingGroup>\-Inhalte für einen Bereich aus, den Sie mit einer <xref:System.Windows.Media.Geometry> beschreiben.  Ein Beispiel finden Sie unter [How to: Clip a Drawing](http://msdn.microsoft.com/de-de/1f7d8a2c-c3c2-42cb-a542-e6796f9fb058).||  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Richtet [geräteunabhängige Pixel](GTMT) anhand der angegebenen Richtlinien an Gerätepixeln aus.  Diese Eigenschaft ist hilfreich, um sicherzustellen, dass detailreiche Grafiken auf niedrigauflösenden Bildschirmen scharf gerendert werden.  Ein Beispiel finden Sie unter [Anwenden eines Führungsliniensatzes auf eine Zeichnung](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-a-guidelineset-to-a-drawing.md).||  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Transformiert die <xref:System.Windows.Media.DrawingGroup>\-Inhalte.  Ein Beispiel finden Sie unter [How to: Apply a Transform to a Drawing](http://msdn.microsoft.com/de-de/0d525f2b-682d-4d67-9660-cf46929fbabd).||  
  
<a name="usingimagedrawing"></a>   
## Anzeigen einer Zeichnung als Bild  
 Um eine <xref:System.Windows.Media.Drawing> mit einem <xref:System.Windows.Controls.Image>\-Steuerelement anzuzeigen, verwenden Sie ein <xref:System.Windows.Media.DrawingImage> als <xref:System.Windows.Controls.Image.Source%2A> für das <xref:System.Windows.Controls.Image>\-Steuerelement, und legen Sie die <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=fullName>\-Eigenschaft des <xref:System.Windows.Media.DrawingImage>\-Objekts auf die anzuzeigende Zeichnung fest.  
  
 Im folgenden Beispiel wird mit einem <xref:System.Windows.Media.DrawingImage> und einem <xref:System.Windows.Controls.Image>\-Steuerelement eine <xref:System.Windows.Media.GeometryDrawing> angezeigt.  Folgende Ergebnisse werden zurückgegeben:  
  
 ![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
Ein DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## Zeichnen eines Objekts mithilfe einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> ist ein Pinseltyp, der einen Bereich mithilfe eines Zeichnungsobjekts zeichnet.  Sie können ihn verwenden, um so gut wie jedes grafische Objekt mithilfe einer Zeichnung zu zeichnen.  Die <xref:System.Windows.Media.Drawing>\-Eigenschaft von einem <xref:System.Windows.Media.DrawingBrush> beschreibt dessen <xref:System.Windows.Media.DrawingBrush.Drawing%2A>.  Um eine <xref:System.Windows.Media.Drawing> mit einem <xref:System.Windows.Media.DrawingBrush> zu rendern, fügen Sie sie dem Pinsel mithilfe dessen <xref:System.Windows.Media.Drawing>\-Eigenschaft hinzu, und zeichnen Sie mit dem Pinsel ein grafisches Objekt, z. B. ein Steuerelement oder einen Bereich.  
  
 Im folgenden Beispiel wird mit einem <xref:System.Windows.Media.DrawingBrush> die <xref:System.Windows.Shapes.Shape.Fill%2A> für ein <xref:System.Windows.Shapes.Rectangle> mit einem Muster gezeichnet, das aus einer <xref:System.Windows.Media.GeometryDrawing> erstellt wurde.  Folgende Ergebnisse werden zurückgegeben:  
  
 ![Ein gekachelter DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm\_drawingbrush\_geometrydrawing")  
  
        Eine mit einem DrawingBrush verwendete GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 Die <xref:System.Windows.Media.DrawingBrush>\-Klasse stellt eine Vielzahl von Optionen zum Strecken und Unterteilen des Inhalts bereit.  Weitere Informationen über <xref:System.Windows.Media.DrawingBrush> finden Sie in der Übersicht [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="renderingwithvisualsection"></a>   
## Rendern einer Zeichnung mit einem visuellen Element  
 Ein <xref:System.Windows.Media.DrawingVisual> ist ein visueller Objekttyp, der dazu dient, eine Zeichnung zu rendern.  Das direkte Arbeiten auf der visuellen Ebene ist eine Option für Entwickler, die eine stark angepasste grafische Umgebung erstellen möchten. Diese Option wird in dieser Übersicht nicht beschrieben.  Weitere Informationen finden Sie in der Übersicht über [Verwenden von DrawingVisual\-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## DrawingContext\-Objekte  
 Mit der <xref:System.Windows.Media.DrawingContext>\-Klasse können Sie ein <xref:System.Windows.Media.Visual>\-Element oder eine <xref:System.Windows.Media.Drawing> mit visuellem Inhalt auffüllen.  Viele solcher Grafikobjekte auf niedrigerer Ebene verwenden einen <xref:System.Windows.Media.DrawingContext>, da hiermit grafische Inhalte sehr effizient beschrieben werden.  
  
 Auch wenn die <xref:System.Windows.Media.DrawingContext>\-Zeichnungsmethoden den Zeichnungsmethoden vom Typ <xref:System.Drawing.Graphics?displayProperty=fullName> zu ähneln scheinen, sind sie doch sehr verschieden.  <xref:System.Windows.Media.DrawingContext> wird in einem Grafiksystem mit Speichermodus verwendet, während der <xref:System.Drawing.Graphics?displayProperty=fullName>\-Typ in einem Grafiksystem mit unmittelbarem Modus verwendet wird.  Wenn Sie die Zeichnungsbefehle des <xref:System.Windows.Media.DrawingContext>\-Objekts verwenden, speichern Sie einen Satz von Renderinganweisungen \(wenn auch der tatsächliche Speichermechanismus vom Typ des Objekts abhängt, das den <xref:System.Windows.Media.DrawingContext> bereitstellt\), die später vom Grafiksystem verwendet werden. Sie zeichnen nicht in Echtzeit auf dem Bildschirm.  Weitere Informationen über die Funktionsweise des [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Grafiksystems finden Sie unter [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 Ein <xref:System.Windows.Media.DrawingContext> wird niemals direkt instanziiert. Sie können jedoch mit bestimmten Methoden, z. B. <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=fullName> und <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=fullName>, einen Zeichnungskontext abrufen.  
  
<a name="enumeratevisualcontents"></a>   
## Auflisten der Inhalte eines visuellen Objekts  
 Neben ihren anderen Verwendungszwecken stellen die <xref:System.Windows.Media.Drawing>\-Objekte auch ein Objektmodell für die Auflistung der Inhalte von einem <xref:System.Windows.Media.Visual> bereit.  
  
 Im folgenden Beispiel wird mit der <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>\-Methode der <xref:System.Windows.Media.DrawingGroup>\-Wert von einem <xref:System.Windows.Media.Visual> abgerufen und aufgelistet.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## Siehe auch  
 <xref:System.Windows.Media.Drawing>   
 <xref:System.Windows.Media.DrawingGroup>   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/drawings-how-to-topics.md)