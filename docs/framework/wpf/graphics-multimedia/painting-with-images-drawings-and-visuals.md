---
title: "Zeichnen mit Bildern, Zeichnungen und visuellen Elementen | Microsoft Docs"
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
  - "Pinsel, Zeichnen mit Zeichnungen"
  - "Pinsel, Zeichnen mit Bildern"
  - "Pinsel, Zeichnen mit grafischen Elementen"
  - "Zeichnen mit grafischen Elementen"
  - "Zeichnen, Mit Zeichnungen"
  - "Zeichnen, Mit Bildern"
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# Zeichnen mit Bildern, Zeichnungen und visuellen Elementen
In diesem Thema wird beschrieben, wie mithilfe der Objekte <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>\-ein Bereich mit einem Bild, einer <xref:System.Windows.Media.Drawing> oder einem <xref:System.Windows.Media.Visual> gezeichnet wird.  
  
   
  
<a name="prereqs"></a>   
## Vorbereitungsmaßnahmen  
 Für dieses Thema sollten Sie mit den von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellten unterschiedlichen Pinseltypen sowie deren grundlegenden Features vertraut sein.  Eine Einführung finden Sie unter [Übersicht über WPF\-Pinsel](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  
  
<a name="image"></a>   
## Zeichnen eines Bereichs mit einem Bild  
 Ein <xref:System.Windows.Media.ImageBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.ImageSource>\-Objekt.  Der mit einem <xref:System.Windows.Media.ImageBrush> am häufigsten verwendete <xref:System.Windows.Media.ImageSource>\-Typ ist ein <xref:System.Windows.Media.Imaging.BitmapImage>, was eine Bitmapgrafik darstellt.  Sie können zum Zeichnen ein <xref:System.Windows.Media.DrawingImage> mithilfe eines <xref:System.Windows.Media.Drawing>\-Objekts verwenden, wobei ein <xref:System.Windows.Media.DrawingBrush> einfacher anzuwenden ist.  Weitere Informationen über <xref:System.Windows.Media.ImageSource>\-Objekte finden Sie unter [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
 Um mit einem <xref:System.Windows.Media.ImageBrush> zu zeichnen, erstellen Sie ein <xref:System.Windows.Media.Imaging.BitmapImage> und verwenden es zum Laden des Bitmapinhalts.  Verwenden Sie dann das <xref:System.Windows.Media.Imaging.BitmapImage>, um die <xref:System.Windows.Media.ImageBrush.ImageSource%2A>\-Eigenschaft für den <xref:System.Windows.Media.ImageBrush> festzulegen.  Zum Schluss wenden Sie den <xref:System.Windows.Media.ImageBrush> auf das zu zeichnende Objekt an.  In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie aber auch einfach die <xref:System.Windows.Media.ImageBrush.ImageSource%2A>\-Eigenschaft von <xref:System.Windows.Media.ImageBrush> auf den Pfad des zu ladenden Bilds setzen.  
  
 Wie alle <xref:System.Windows.Media.Brush>\-Objekte kann ein <xref:System.Windows.Media.ImageBrush> zum Zeichnen von Objekten, z. B. Formen, Bereichen, Steuerelementen und Text, verwendet werden.  Die folgende Abbildung zeigt einige Effekte, die mit einem <xref:System.Windows.Media.ImageBrush> erreicht werden können.  
  
 ![ImageBrush&#45;Ausgabebeispiele](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.png "wcpsdk\_mmgraphics\_imagebrushexamples")  
  
        Von einem ImageBrush gezeichnete Objekte  
  
 Standardmäßig wird ein Bild mithilfe von <xref:System.Windows.Media.ImageBrush> gestreckt, um den zu zeichnenden Bereich vollständig auszufüllen. Dabei wird das Bild möglicherweise verzerrt, wenn der gezeichnete Bereich ein anderes Seitenverhältnis als das Bild aufweist.  Sie können dieses Verhalten ändern, indem Sie die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft von ihrem Standardwert <xref:System.Windows.Media.Stretch> in <xref:System.Windows.Media.Stretch>, <xref:System.Windows.Media.Stretch> oder <xref:System.Windows.Media.Stretch> ändern.  Da <xref:System.Windows.Media.ImageBrush> ein <xref:System.Windows.Media.TileBrush>\-Typ ist, können Sie genau angeben, wie ein Bildpinsel den Ausgabebereich ausfüllt, und sogar Muster erstellen.  Weitere Informationen über die erweiterten <xref:System.Windows.Media.TileBrush>\-Features finden Sie unter [Übersicht über TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## Beispiel: Zeichnen eines Objekts mit einem Bitmapbild  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush> verwendet, um den <xref:System.Windows.Controls.Panel.Background%2A> von einem <xref:System.Windows.Controls.Canvas> zu zeichnen.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## Zeichnen eines Bereichs mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> ermöglicht es Ihnen, einen Bereich mithilfe von Formen, Text, Bildern und einem Video zu zeichnen.  Die Formen innerhalb des Zeichenpinsels können selbst mit einer Volltonfarbe, einem Farbverlauf, einem Bild oder sogar mit einem weiteren <xref:System.Windows.Media.DrawingBrush> gezeichnet sein.  In der folgenden Abbildung werden einige Verwendungen für den <xref:System.Windows.Media.DrawingBrush> veranschaulicht.  
  
 ![DrawingBrush&#45;Ausgabebeispiele](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk\_mmgraphics\_drawingbrushexamples")  
  
        Von einem DrawingBrush \(Zeichenpinsel\) gezeichnete Objekte  
  
 Ein <xref:System.Windows.Media.DrawingBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Drawing>\-Objekt.  Ein <xref:System.Windows.Media.Drawing>\-Objekt beschreibt sichtbaren Inhalt, z. B. eine Form, Bitmap, ein Video oder eine Textzeile.  Die verschiedenen Zeichnungstypen beschreiben unterschiedliche Inhaltstypen.  Die folgende Liste enthält die verschiedenen Typen von Zeichnungsobjekten.  
  
-   <xref:System.Windows.Media.GeometryDrawing> – Zeichnet eine Form.  
  
-   <xref:System.Windows.Media.ImageDrawing> – Zeichnet ein Bild.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> – Zeichnet Text.  
  
-   <xref:System.Windows.Media.VideoDrawing> – Gibt eine Audio\- oder Videodatei wieder.  
  
-   <xref:System.Windows.Media.DrawingGroup> – Zeichnet andere Zeichnungen.  Verwenden Sie eine Zeichnungsgruppe, um aus anderen Zeichnungen eine einzelne zusammengesetzte Zeichnung zu bilden.  
  
 Weitere Informationen zu <xref:System.Windows.Media.Drawing>\-Objekten finden Sie unter [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
 Wie ein <xref:System.Windows.Media.ImageBrush> streckt ein <xref:System.Windows.Media.DrawingBrush> seine <xref:System.Windows.Media.DrawingBrush.Drawing%2A>, um den Ausgabebereich auszufüllen.  Sie können dieses Verhalten überschreiben, indem Sie die Standardeinstellung <xref:System.Windows.Media.Stretch> der <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft ändern.  Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## Beispiel: Zeichnen eines Objekts mit einer Zeichnung  
 Das folgende Beispiel zeigt, wie ein Objekt mithilfe einer Zeichnung aus drei Ellipsen gezeichnet wird.  Für die Beschreibung der Ellipsen wird ein <xref:System.Windows.Media.GeometryDrawing>\-Zeichnungsobjekt verwendet.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## Zeichnen eines Bereichs mit einem visuellen Element  
 <xref:System.Windows.Media.VisualBrush> ist der vielseitigste und leistungsfähigste aller Pinsel und zeichnet einen Bereich mit einem <xref:System.Windows.Media.Visual>.  Ein <xref:System.Windows.Media.Visual> ist ein Grafiktyp auf niedriger Ebene, der für viele nützliche grafische Komponenten als Stammelement fungiert.  Die Klassen <xref:System.Windows.Window>, <xref:System.Windows.FrameworkElement> und <xref:System.Windows.Controls.Control> sind beispielsweise alle <xref:System.Windows.Media.Visual>\-Objekttypen.  Mithilfe von <xref:System.Windows.Media.VisualBrush> können Sie Bereiche mit fast jedem grafischen Objekt in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zeichnen.  
  
> [!NOTE]
>  Obwohl <xref:System.Windows.Media.VisualBrush> ein <xref:System.Windows.Freezable>\-Objekttyp ist, kann es nicht gesperrt \(als schreibgeschützt definiert\) werden, wenn die <xref:System.Windows.Media.VisualBrush.Visual%2A>\-Eigenschaft nicht auf den Wert `null` festgelegt ist.  
  
 Es gibt zwei Möglichkeiten, den <xref:System.Windows.Media.VisualBrush.Visual%2A>\-Inhalt von einem <xref:System.Windows.Media.VisualBrush> anzugeben.  
  
-   Erstellen Sie ein neues <xref:System.Windows.Media.Visual>\-Element, und verwenden Sie es, um die <xref:System.Windows.Media.VisualBrush.Visual%2A>\-Eigenschaft vom <xref:System.Windows.Media.VisualBrush> festzulegen.  Ein Beispiel finden Sie im folgenden Abschnitt unter [Beispiel: Zeichnen eines Objekts mit einem visuellen Element](#examplevisualbrush1).  
  
-   Verwenden Sie ein vorhandenes <xref:System.Windows.Media.Visual>\-Element, das vom Ziel\-<xref:System.Windows.Media.Visual> ein Bildduplikat erstellt.  Sie können dann den <xref:System.Windows.Media.VisualBrush> verwenden, um interessante Effekte zu erstellen, z. B. Reflektion und Vergrößerung.  Ein Beispiel finden Sie im Abschnitt [Beispiel: Erstellen einer Reflektion](#examplevisualbrush2).  
  
 Wenn Sie ein neues <xref:System.Windows.Media.VisualBrush.Visual%2A> für einen <xref:System.Windows.Media.VisualBrush> definieren und es sich bei dem <xref:System.Windows.Media.Visual> um ein <xref:System.Windows.UIElement> handelt \(z. B. ein Bereich oder ein Steuerelement\), wird das Layoutsystem auf dem <xref:System.Windows.UIElement> und dessen untergeordneten Elementen ausgeführt, sofern die <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A>\-Eigenschaft auf `true` festgelegt ist.  Das Stamm\-<xref:System.Windows.UIElement> ist jedoch im Grunde vom Rest des Systems isoliert: Stile und externes Layout können diese Abgrenzung nicht durchdringen.  Daher sollten Sie die Größe für das Stamm\-<xref:System.Windows.UIElement> explizit angeben, zumal <xref:System.Windows.Media.VisualBrush> sein einziges übergeordnetes Objekt ist und es sich deshalb nicht automatisch an den gezeichneten Bereich anpassen kann.  Weitere Informationen über Layouts in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Layout](../../../../docs/framework/wpf/advanced/layout.md).  
  
 Wie ein <xref:System.Windows.Media.ImageBrush> und ein <xref:System.Windows.Media.DrawingBrush> streckt ein <xref:System.Windows.Media.VisualBrush> seinen Inhalt, um den Ausgabebereich auszufüllen.  Sie können dieses Verhalten überschreiben, indem Sie die Standardeinstellung <xref:System.Windows.Media.Stretch> der <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft ändern.  Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft.  
  
<a name="examplevisualbrush1"></a>   
## Beispiel: Zeichnen eines Objekts mit einem visuellen Element  
 Im folgenden Beispiel werden mehrere Steuerelemente und ein Bereich verwendet, um ein Rechteck zu zeichnen.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## Beispiel: Erstellen einer Reflektion  
 Im vorherigen Beispiel wurde veranschaulicht, wie ein neues <xref:System.Windows.Media.Visual> zur Verwendung als Hintergrund erstellt wird.  Sie können mit einem <xref:System.Windows.Media.VisualBrush> auch vorhandene visuelle Elemente anzeigen. Durch diese Funktion lassen sich interessante visuelle Effekte wie Reflektionen und Vergrößerungen darstellen.  Im folgenden Beispiel wird mit <xref:System.Windows.Media.VisualBrush> eine Reflektion von <xref:System.Windows.Controls.Border> erstellt, die mehrere Elemente enthält.  In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Ein reflektiertes Visual&#45;Objekt](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.png "graphicsmm\_visualbrush\_reflection\_small")  
  
        Ein reflektiertes visuelles Objekt  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Weitere Beispiele zur Vergrößerung von Bildschirmbereichen und zur Erstellung von Reflektionen finden Sie unter [Beispiel zu VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## TileBrush\-Features  
 Die Elemente <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush> sind Typen von <xref:System.Windows.Media.TileBrush>\-Objekten.  <xref:System.Windows.Media.TileBrush>\-Objekte bieten Ihnen umfangreiche Steuerungsmöglichkeiten beim Zeichnen eines Bereichs mit einem Bild, einer Zeichnung oder einem visuellen Element.  Sie können beispielsweise zum Zeichnen eines Bereichs anstelle eines einzelnen gestreckten Bilds eine Reihe von Bildkacheln verwenden, die ein Muster ergeben.  
  
 Ein <xref:System.Windows.Media.TileBrush> verfügt über drei primäre Komponenten: Inhalt, Kacheln und Ausgabebereich.  
  
 ![TileBrush&#45;Komponenten](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk\_mmgraphics\_defaultcontentprojection2")  
  
        Komponenten eines TileBrush mit einer einzelnen Kachel  
  
 ![Komponenten eines gekachelten TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm\_tiledprojection")  
Komponenten eines TileBrush mit mehreren Kacheln  
  
 Weitere Informationen über das Kacheln von <xref:System.Windows.Media.TileBrush>\-Objekten finden Sie unter [Übersicht über TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.ImageBrush>   
 <xref:System.Windows.Media.DrawingBrush>   
 <xref:System.Windows.Media.VisualBrush>   
 <xref:System.Windows.Media.TileBrush>   
 [Übersicht über TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)   
 [Übersicht über WPF\-Pinsel](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)   
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Übersicht über Durchlässigkeitsmasken](../../../../docs/framework/wpf/graphics-multimedia/opacity-masks-overview.md)   
 [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Beispiel zu ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005)   
 [Beispiel zu VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049)