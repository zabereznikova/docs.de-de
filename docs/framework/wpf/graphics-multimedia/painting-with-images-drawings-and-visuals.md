---
title: Zeichnen mit Bildern, Zeichnungen und visuellen Elementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- painting [WPF], with images
- painting with visuals [WPF]
- brushes [WPF], painting with images
- brushes [WPF], painting with visuals
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
ms.openlocfilehash: e80132a5467f932e5569787f43427044ba2be256
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929607"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Zeichnen mit Bildern, Zeichnungen und visuellen Elementen
In <xref:System.Windows.Media.ImageBrush>diesem Thema <xref:System.Windows.Media.Visual>wird <xref:System.Windows.Media.DrawingBrush>beschrieben, wie Sie mithilfe <xref:System.Windows.Media.VisualBrush> von-,-und-Objekten einen Bereich mit <xref:System.Windows.Media.Drawing>einem Bild, einem oder einem zeichnen.  

<a name="prereqs"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Als Voraussetzung für dieses Thema sollten Sie mit den von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellten unterschiedlichen Pinseltypen und ihren grundlegenden Funktionen vertraut sein. Eine Einführung finden Sie unter [Übersicht über WPF-Pinsel](wpf-brushes-overview.md).  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>Zeichnen eines Bereichs mit einem Bild  
 Ein <xref:System.Windows.Media.ImageBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.ImageSource>. Der häufigste Typ von <xref:System.Windows.Media.ImageSource> , der mit einem <xref:System.Windows.Media.ImageBrush> verwendet wird, <xref:System.Windows.Media.Imaging.BitmapImage>ist eine, die eine Bitmap-Grafik beschreibt. Sie können einen <xref:System.Windows.Media.DrawingImage> zum Zeichnen mithilfe eines <xref:System.Windows.Media.Drawing> -Objekts verwenden, aber es ist einfacher, stattdessen <xref:System.Windows.Media.DrawingBrush> eine zu verwenden. Weitere Informationen zu <xref:System.Windows.Media.ImageSource> Objekten finden Sie in der [Übersicht über die Bildverarbeitung](imaging-overview.md).  
  
 Um mit einem <xref:System.Windows.Media.ImageBrush>zu zeichnen, erstellen <xref:System.Windows.Media.Imaging.BitmapImage> Sie eine und verwenden Sie, um den Bitmapinhalt zu laden. Verwenden Sie dann den <xref:System.Windows.Media.Imaging.BitmapImage> , um die <xref:System.Windows.Media.ImageBrush.ImageSource%2A> -Eigenschaft von <xref:System.Windows.Media.ImageBrush>festzulegen. Wenden Sie schließlich auf <xref:System.Windows.Media.ImageBrush> das Objekt an, das Sie zeichnen möchten.  In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]können Sie auch einfach die <xref:System.Windows.Media.ImageBrush.ImageSource%2A> -Eigenschaft des <xref:System.Windows.Media.ImageBrush> -Objekts mit dem Pfad des zu ladenden Bilds festlegen.  
  
 Wie bei <xref:System.Windows.Media.Brush> allen-Objekten <xref:System.Windows.Media.ImageBrush> kann auch verwendet werden, um Objekte zu zeichnen, z. b. Formen, Bereiche, Steuerelemente und Text. Die folgende Abbildung zeigt einige Effekte, die mit einem <xref:System.Windows.Media.ImageBrush>erreicht werden können.  
  
 ![ImageBrush-Ausgabe Beispiele](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Von einem ImageBrush gezeichnete Objekte  
  
 Standardmäßig wird das <xref:System.Windows.Media.ImageBrush> Bild von einem gestreckt, um den Bereich, der gezeichnet wird, vollständig auszufüllen. möglicherweise wird das Bild verzerrt, wenn der gezeichnete Bereich ein anderes Seitenverhältnis als das Bild hat. Sie können dieses Verhalten ändern, indem Sie <xref:System.Windows.Media.TileBrush.Stretch%2A> die-Eigenschaft vom Standardwert <xref:System.Windows.Media.Stretch.Fill> von <xref:System.Windows.Media.Stretch.None>in <xref:System.Windows.Media.Stretch.Uniform>, oder <xref:System.Windows.Media.Stretch.UniformToFill>ändern. Da <xref:System.Windows.Media.ImageBrush> ein Typ von <xref:System.Windows.Media.TileBrush>ist, können Sie genau angeben, wie ein Bild Pinsel den Ausgabebereich füllt und sogar Muster erstellen. Weitere Informationen zu erweiterten <xref:System.Windows.Media.TileBrush> Funktionen finden Sie in der [Übersicht über TileBrush](tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Beispiel: Zeichnen eines Objekts mit einem Bitmap-Bild  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush> verwendet, um <xref:System.Windows.Controls.Panel.Background%2A> die eines <xref:System.Windows.Controls.Canvas>zu zeichnen.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>Zeichnen eines Bereichs mit einer Zeichnung  
 Mit <xref:System.Windows.Media.DrawingBrush> einem können Sie einen Bereich mit Formen, Text, Bildern und Videos zeichnen. Formen innerhalb eines Zeichnungs Pinsels können selbst mit einer voll Tonfarbe, einem Farbverlauf, einem Bild oder <xref:System.Windows.Media.DrawingBrush>einem anderen gezeichnet werden. In der folgenden Abbildung werden einige Verwendungen <xref:System.Windows.Media.DrawingBrush>von veranschaulicht.  
  
 ![DrawingBrush-Ausgabe Beispiele](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Von einem DrawingBrush gezeichnete Objekte  
  
 Ein <xref:System.Windows.Media.DrawingBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Drawing> -Objekt. Ein <xref:System.Windows.Media.Drawing> -Objekt beschreibt sichtbare Inhalte, z. b. eine Form, eine Bitmap, ein Video oder eine Textzeile. Verschiedene Arten von Zeichnungen beschreiben verschiedene Arten von Inhalten. Im Folgenden finden Sie eine Liste der unterschiedlichen Typen von Zeichnungsobjekten.  
  
- <xref:System.Windows.Media.GeometryDrawing>– Zeichnet eine Form.  
  
- <xref:System.Windows.Media.ImageDrawing>– Zeichnet ein Bild.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>– Zeichnet Text.  
  
- <xref:System.Windows.Media.VideoDrawing>– Gibt eine Audiodatei oder Videodatei wieder.  
  
- <xref:System.Windows.Media.DrawingGroup>– Zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 Weitere Informationen zu Objekten <xref:System.Windows.Media.Drawing> finden Sie unter [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).  
  
 Wie eine <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush> erstreckt<xref:System.Windows.Media.DrawingBrush.Drawing%2A> sich ein, um seinen Ausgabebereich auszufüllen. Sie können dieses Verhalten überschreiben, indem <xref:System.Windows.Media.TileBrush.Stretch%2A> Sie die-Eigenschaft von der <xref:System.Windows.Media.Stretch.Fill>Standardeinstellung von ändern. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.TileBrush.Stretch%2A>-Eigenschaft.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>Beispiel: Zeichnen eines Objekts mit einer Zeichnung  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt mit einer Zeichnung aus drei Ellipsen gezeichnet wird. Eine <xref:System.Windows.Media.GeometryDrawing> wird verwendet, um die Ellipsen zu beschreiben.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>Zeichnen eines Bereichs mit einem visuellen Element  
 Der vielseitigste und leistungsfähigste von allen Pinseln, <xref:System.Windows.Media.VisualBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Visual>. Ein <xref:System.Windows.Media.Visual> ist ein grafischer Typ auf niedriger Ebene, der als Vorgänger zahlreicher nützlicher grafischer Komponenten fungiert. Die <xref:System.Windows.Window>Klassen, <xref:System.Windows.FrameworkElement>und <xref:System.Windows.Controls.Control> sind z. b. alle Typen von <xref:System.Windows.Media.Visual> -Objekten. Mit einem <xref:System.Windows.Media.VisualBrush>können Sie Bereiche mit fast allen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] grafischen Objekten zeichnen.  
  
> [!NOTE]
> Obwohl <xref:System.Windows.Media.VisualBrush> <xref:System.Windows.Media.VisualBrush.Visual%2A> `null`ein <xref:System.Windows.Freezable> Objekttyp ist, kann er nicht eingefroren (schreibgeschützt) werden, wenn seine-Eigenschaft auf einen anderen Wert als festgelegt ist.  
  
 Es gibt zwei Möglichkeiten, den <xref:System.Windows.Media.VisualBrush.Visual%2A> Inhalt einer <xref:System.Windows.Media.VisualBrush>anzugeben.  
  
- Erstellen Sie einen <xref:System.Windows.Media.Visual> neuen, und verwenden Sie ihn <xref:System.Windows.Media.VisualBrush.Visual%2A> zum Festlegen der <xref:System.Windows.Media.VisualBrush>-Eigenschaft von. Ein Beispiel finden Sie im [Beispiel: Zeichnen Sie ein-Objekt mit](#examplevisualbrush1) einem visuellen Abschnitt, der folgt.  
  
- Verwenden Sie ein <xref:System.Windows.Media.Visual>vorhandenes, das ein doppeltes Bild des Ziels <xref:System.Windows.Media.Visual>erstellt. Anschließend können Sie mit dem <xref:System.Windows.Media.VisualBrush> interessante Effekte erstellen, z. b. Reflektion und Vergrößerung. Ein Beispiel finden Sie im [Beispiel: Erstellen Sie einen](#examplevisualbrush2) Reflektionstyp.  
  
 Wenn Sie einen neuen <xref:System.Windows.Media.VisualBrush.Visual%2A> für einen <xref:System.Windows.Media.VisualBrush> <xref:System.Windows.Media.Visual> definieren, der ein <xref:System.Windows.UIElement> ist (z. b. ein Panel oder Steuerelement), wird das Layoutsystem auf dem <xref:System.Windows.UIElement> und seinen <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> untergeordneten Elementen ausgeführt `true`, wenn die-Eigenschaft auf festgelegt ist. Der <xref:System.Windows.UIElement> Stamm ist jedoch im Wesentlichen vom Rest des Systems isoliert: Stile, und das externe Layout kann diese Grenze nicht durchdringen. Daher sollten Sie die Größe des <xref:System.Windows.UIElement>Stamms explizit angeben, da das einzige übergeordnete Element das <xref:System.Windows.Media.VisualBrush> -Element ist und sich daher nicht automatisch für den Bereich eignet, der gezeichnet wird. Weitere Informationen zum Layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Layout](../advanced/layout.md).  
  
 Wie <xref:System.Windows.Media.ImageBrush> und <xref:System.Windows.Media.DrawingBrush>, wird<xref:System.Windows.Media.VisualBrush> der Inhalt von so gestreckt, dass er seinen Ausgabebereich ausgleicht. Sie können dieses Verhalten überschreiben, indem <xref:System.Windows.Media.TileBrush.Stretch%2A> Sie die-Eigenschaft von der <xref:System.Windows.Media.Stretch.Fill>Standardeinstellung von ändern. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.TileBrush.Stretch%2A>-Eigenschaft.  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>Beispiel: Zeichnen eines Objekts mit einem visuellen Element  
 Im folgenden Beispiel werden mehrere Steuerelemente und ein Bereich verwendet, um ein Rechteck zu zeichnen.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>Beispiel: Erstellen einer Reflektion  
 Im vorherigen Beispiel wurde gezeigt, wie ein neues <xref:System.Windows.Media.Visual> für die Verwendung als Hintergrund erstellt wird. Sie können auch einen <xref:System.Windows.Media.VisualBrush> verwenden, um ein vorhandenes Visual anzuzeigen. diese Funktion ermöglicht es Ihnen, interessante visuelle Effekte zu erzeugen, wie z. b. Spiegelungen und Vergrößerung. Im folgenden Beispiel wird ein <xref:System.Windows.Media.VisualBrush> verwendet, um eine Reflektion <xref:System.Windows.Controls.Border> von einem zu erstellen, das mehrere-Elemente enthält. In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Ein reflektiertes visuelles Objekt](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Ein reflektiertes Visual-Objekt  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Weitere Beispiele, die zeigen, wie Bildschirmbereiche vergrößert und Reflektionen erstellt werden, finden Sie unter [Beispiel zu VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>TileBrush-Funktionen  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>und sind <xref:System.Windows.Media.VisualBrush> Typen von <xref:System.Windows.Media.TileBrush> -Objekten. <xref:System.Windows.Media.TileBrush>-Objekte bieten Ihnen sehr viel Kontrolle über die Art und Weise, wie ein Bereich mit einem Bild, einer Zeichnung oder einem visuellen Element gezeichnet wird. Sie können beispielsweise zum Zeichnen eines Bereichs anstelle eines einzelnen gestreckten Bilds eine Reihe von Bildkacheln verwenden, die ein Muster ergeben.  
  
 Eine <xref:System.Windows.Media.TileBrush> weist drei Hauptkomponenten auf: Inhalt, Kacheln und den Ausgabebereich.  
  
 ![TileBrush-Komponenten](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Komponenten eines TileBrush mit einer einzelnen Kachel  
  
 ![Komponenten eines gekachelten TileBrush](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Komponente eines TileBrush mit mehreren Kacheln  
  
 Weitere Informationen zu den Funktionen von Objekten finden Sie <xref:System.Windows.Media.TileBrush> in der Übersicht über [TileBrush](tilebrush-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Übersicht über TileBrush](tilebrush-overview.md)
- [Übersicht über WPF-Pinsel](wpf-brushes-overview.md)
- [Übersicht über die Bildverarbeitung](imaging-overview.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Übersicht über Durchlässigkeitsmasken](opacity-masks-overview.md)
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
- [ImageBrush-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160005)
- [VisualBrush-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160049)
